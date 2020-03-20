---
title: Esercitazione sull'elaborazione batch con .NET per Apache Spark
description: Informazioni su come eseguire l'elaborazione batch usando .NET per Apache Spark.Learn how to do batch processing using .NET for Apache Spark.
author: mamccrea
ms.author: mamccrea
ms.date: 12/13/2019
ms.topic: tutorial
ms.openlocfilehash: 460c37e66c2c0a8a9b197a9abaff9eead842bdeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187559"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a>Esercitazione: Eseguire l'elaborazione batch con .NET per Apache SparkTutorial: Do batch processing with .NET for Apache Spark

In this tutorial, you learn how to do batch processing using .NET for Apache Spark. L'elaborazione batch è la trasformazione dei dati inattivi, il che significa che i dati di origine sono già stati caricati nell'archiviazione dei dati.

L'elaborazione batch viene in genere eseguita su set di dati flat di grandi dimensioni che devono essere preparati per un'ulteriore analisi. L'elaborazione dei log e il data warehousing sono scenari di elaborazione batch comuni. In questo scenario, si analizzano le informazioni sui progetti GitHub, ad esempio il numero di progetti diversi sono stati sottoposti a perforato o la quantità di recente l'aggiornamento dei progetti.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> * Creare ed eseguire un'applicazione .NET per Apache SparkCreate and run a .NET for Apache Spark application
> * Leggere i dati in un dataframe e prepararlo per l'analisiRead data into a DataFrame and prepare it for analysis
> * Elaborare i dati utilizzando Spark SQLProcess the data using Spark SQL

## <a name="prerequisites"></a>Prerequisites

Se è la prima volta che si usa .NET per Apache Spark, vedere l'esercitazione [Introduzione a .NET per Apache Spark](../tutorials/get-started.md) per informazioni su come preparare l'ambiente ed eseguire la prima applicazione .NET per Apache Spark.

## <a name="download-the-sample-data"></a>Scaricare i dati di esempio

[GHTorrent](http://ghtorrent.org/) monitora tutti gli eventi GitHub pubblici, ad esempio informazioni su progetti, commit e osservatori, e archivia gli eventi e la relativa struttura nei database. I dati raccolti in diversi periodi di tempo sono disponibili come archivi scaricabili. Poiché i file di dump sono molto grandi, questa guida utilizza una [versione troncata del file dump](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) che può essere scaricato da GitHub.

> [!NOTE]
> Il set di dati GHTorrent è distribuito nell'ambito di uno schema di doppia licenza ([Creative Commons )](https://wiki.creativecommons.org/wiki/CCPlus). Per usi non commerciali (compresi, ma non limitati a, scopi educativi, di ricerca o personali), il set di dati è distribuito con la [licenza CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   Il `dotnet` comando `new` crea automaticamente `console` un'applicazione di tipo. Il `-o` parametro crea una directory denominata *mySparkBatchApp* in cui l'app è archiviata e la popola con i file necessari. Il `cd mySparkBatchApp` comando modifica la directory in base alla directory dell'app appena creata.

1. Per usare .NET per Apache Spark in un'app, installa il pacchetto Microsoft.Spark. Nella console, eseguire il comando seguente:

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a>Creare una SparkSessionCreate a SparkSession

1. Aggiungere le `using` seguenti istruzioni aggiuntive all'inizio del file *Program.cs* in *mySparkBatchApp*.

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Aggiungere il codice seguente allo spazio dei nomi del progetto. *s_referenceData* viene utilizzata in un secondo momento nel programma per filtrare in base alla data.

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. Aggiungere il codice seguente all'interno del metodo Main per stabilire una nuova SparkSession.Add the following code inside your Main method to establish a new SparkSession. SparkSession è il punto di ingresso alla programmazione di Spark con l'API Dataset e DataFrame. Chiamando l'oggetto, `spark` è possibile accedere alle funzionalità Spark e DataFrame in tutto il programma.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a>Preparare i dati

1. Leggere il file `DataFrame`di input in un oggetto , ovvero una raccolta distribuita di dati organizzati in colonne denominate. È possibile impostare le <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>colonne per i dati tramite . Utilizzare <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> il metodo per visualizzare i dati nel frame di dati. Assicurarsi di aggiornare il percorso del file CSV al percorso dei dati GitHub scaricati.

   ```csharp
   DataFrame projectsDf = spark
       .Read()
       .Schema("id INT, url STRING, owner_id INT, " +
       "name STRING, descriptor STRING, language STRING, " +
       "created_at STRING, forked_from INT, deleted STRING" +
       "updated_at STRING")
       .Csv("filepath");

   projectsDf.Show();
   ```

1. Utilizzare <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> il metodo per eliminare le righe con <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> NA (null) valori e il metodo per rimuovere determinate colonne dai dati. In questo modo si evitano errori se si tenta di analizzare dati null o colonne non rilevanti per l'analisi finale.

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a>Analizzare i dati

Spark SQL consente di effettuare chiamate SQL sui dati. È comune combinare le funzioni definite dall'utente e Spark SQL per applicare una funzione definita dall'utente a tutte le righe del frame di dati.

È possibile `spark.Sql` chiamare in modo specifico per simulare le chiamate SQL standard visualizzate in altri tipi di app. È inoltre possibile <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> chiamare <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> metodi come e per combinare, filtrare ed eseguire calcoli sui dati in modo specifico.

L'obiettivo di questa applicazione è quello di ottenere alcune informazioni sui dati di progetti GitHub. Aggiungere i frammenti di codice seguenti al programma per analizzare i dati.

1. Aggiungi il seguente blocco di codice trova il numero di volte in cui ogni lingua è stata sottoposta a un isk. In primo luogo, i dati sono raggruppati per lingua. Quindi, viene preso il numero medio di forcelle da ogni lingua.

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. Aggiungere il seguente blocco di codice per ordinare il numero medio di forcelle in ordine decrescente per vedere quali lingue sono le più forate. Cioè, il maggior numero di forcelle apparirà per primo.

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. Il blocco di codice successivo mostra quanto recentemente sono stati aggiornati i progetti. Si registra una nuova funzione definita dall'utente denominata *MyUDF* e confrontarla con una data, *s_referenceDate*, dichiarata all'inizio dell'esercitazione. La data per ogni progetto viene confrontata con la data di riferimento. Quindi, Spark SQL viene utilizzato per chiamare la funzione definita dall'utente su ogni riga dei dati per analizzare ogni progetto nel set di dati.

   ```csharp
   spark.Udf().Register<string, bool>(
       "MyUDF",
       (date) => DateTime.TryParse(date, out DateTime convertedDate) &&
           (convertedDate > s_referenceDate);
   cleanedProjects.CreateOrReplaceTempView("dateView");

   DataFrame dateDf = spark.Sql(
       "SELECT *, MyUDF(dateView.updated_at) AS datebefore FROM dateView");
   dateDf.Show();
   ```

1. Chiamata `spark.Stop()` per terminare SparkSession.

## <a name="use-spark-submit-to-run-your-app"></a>Usare l'invio di spark per eseguire l'appUse spark-submit to run your app

1. Usare il comando seguente per compilare l'app .NET:

   ```dotnetcli
   dotnet build
   ```

1. Esegui l'app con `spark-submit`. Assicurarsi di aggiornare il comando seguente con i percorsi effettivi del file jar di Microsoft Spark.

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a>Ottenere il codice

È possibile visualizzare la soluzione completa su GitHub.You can see the [full solution](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) on GitHub.

## <a name="next-steps"></a>Passaggi successivi

Passare all'articolo successivo per informazioni su come elaborare i dati di streaming con .NET per Apache Spark.
> [!div class="nextstepaction"]
> [Esercitazione: Streaming strutturato con .NET per Apache SparkTutorial: Structured Streaming with .NET for Apache Spark](streaming.md)
