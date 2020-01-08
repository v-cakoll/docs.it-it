---
title: Esercitazione sull'elaborazione batch con .NET per Apache Spark
description: Informazioni su come eseguire l'elaborazione batch con .NET per Apache Spark.
author: mamccrea
ms.author: mamccrea
ms.date: 12/13/2019
ms.topic: tutorial
ms.openlocfilehash: bd91fb401b9beb6ae74c4599b25e43284473f8b0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75466413"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a>Esercitazione: elaborazione batch con .NET per Apache Spark

In questa esercitazione si apprenderà come eseguire l'elaborazione batch con .NET per Apache Spark. L'elaborazione batch è la trasformazione dei dati inattivi, vale a dire che i dati di origine sono già stati caricati nell'archivio dati. 

L'elaborazione batch viene in genere eseguita su set di impostazioni di grandi dimensioni e flat che devono essere preparati per un'ulteriore analisi. L'elaborazione dei log e il data warehousing sono scenari comuni di elaborazione batch. In questo scenario si analizzano le informazioni sui progetti GitHub, ad esempio il numero di volte in cui è stato eseguito il fork di progetti diversi o la modalità di aggiornamento dei progetti di recente. 

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> * Creare ed eseguire un'applicazione .NET per Apache Spark
> * Leggere i dati in un frame di dati e prepararli per l'analisi
> * Elaborare i dati con Spark SQL

## <a name="prerequisites"></a>Prerequisiti 

Se è la prima volta che si usa .NET per Apache Spark, vedere l'esercitazione [Introduzione a .NET per Apache Spark](../tutorials/get-started.md) per informazioni su come preparare l'ambiente ed eseguire la prima applicazione .net per Apache Spark.

## <a name="download-the-sample-data"></a>Scaricare i dati di esempio

[GHTorrent](http://ghtorrent.org/) monitora tutti gli eventi GitHub pubblici, ad esempio informazioni su progetti, commit e Watcher, e archivia gli eventi e la relativa struttura nei database. I dati raccolti in periodi di tempo diversi sono disponibili come archivi scaricabili. Poiché i file dump sono molto grandi, questa guida usa una [versione troncata del file dump](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) che può essere scaricata da GitHub.

> [!NOTE]
> Il set di dati GHTorrent viene distribuito in base a uno schema Dual Licensing ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)). Per gli usi non commerciali (inclusi, a titolo esemplificativo, didattico, ricerca o uso personale), il set di dati viene distribuito con la [licenza CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   Il comando `dotnet` crea un'applicazione `new` di tipo `console` automaticamente. Il parametro `-o` crea una directory denominata *mySparkBatchApp* in cui l'app viene archiviata e la popola con i file necessari. Il comando `cd mySparkBatchApp` imposta la directory sulla directory dell'app appena creata.

1. Per usare .NET per Apache Spark in un'app, installare il pacchetto Microsoft. Spark. Nella console eseguire il comando seguente:

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a>Creare un SparkSession

1. Aggiungere le seguenti istruzioni `using` aggiuntive all'inizio del file *Program.cs* in *mySparkBatchApp*.

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Aggiungere il codice seguente allo spazio dei nomi del progetto. *s_referenceData* viene usato in un secondo momento nel programma per filtrare in base alla data.

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. Aggiungere il codice seguente all'interno del metodo Main per stabilire un nuovo SparkSession. SparkSession è il punto di ingresso per la programmazione di Spark con il set di dati e l'API dataframe. Chiamando l'oggetto `spark`, è possibile accedere alla funzionalità Spark e dataframe nell'intero programma.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a>Preparare i dati

1. Leggere il file di input in un `DataFrame`, ovvero una raccolta distribuita di dati organizzati in colonne denominate. È possibile impostare le colonne per i dati tramite <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>. Usare il metodo <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> per visualizzare i dati nel frame di dati. Assicurarsi di aggiornare il percorso del file CSV al percorso dei dati di GitHub scaricati.

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

1. Usare il metodo <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> per eliminare righe con valori NA (null) e il metodo <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> per rimuovere determinate colonne dai dati. Ciò consente di evitare errori se si tenta di analizzare i dati o le colonne null che non sono rilevanti per l'analisi finale.

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a>Analizzare i dati

Spark SQL consente di eseguire chiamate SQL sui dati. È comune combinare le funzioni definite dall'utente e Spark SQL per applicare una funzione definita dall'utente a tutte le righe del dataframe.

È possibile chiamare in modo specifico `spark.Sql` per simulare le chiamate SQL standard visualizzate in altri tipi di app. È anche possibile chiamare metodi come <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> e <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> per combinare, filtrare ed eseguire calcoli sui dati in modo specifico.

L'obiettivo di questa app è ottenere informazioni approfondite sui dati dei progetti GitHub. Aggiungere i frammenti di codice seguenti al programma per analizzare i dati.

1. Aggiungere il blocco di codice seguente per trovare il numero di volte in cui ogni lingua è stata diramata. Per prima cosa, i dati vengono raggruppati in base alla lingua. Viene quindi assunto il numero medio di fork da ogni lingua.

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. Aggiungere il blocco di codice seguente per ordinare il numero medio di fork in ordine decrescente per vedere quali lingue sono più fork. Ovvero il numero maggiore di fork verrà visualizzato per primo.

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show(); 
   ```

1. Il blocco di codice successivo Mostra il modo in cui i progetti sono stati aggiornati di recente. Si registra una nuova funzione definita dall'utente denominata *MyUDF* e la si confronta con una data, *s_referenceDate*, che è stata dichiarata all'inizio dell'esercitazione. La data per ogni progetto viene confrontata con la data di riferimento. Viene quindi usato Spark SQL per chiamare la funzione definita dall'utente in ogni riga dei dati per analizzare ogni progetto nel set di dati.

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

1. Chiamare `spark.Stop()` per terminare il SparkSession.

## <a name="use-spark-submit-to-run-your-app"></a>Usare Spark-Submit per eseguire l'app

1. Usare il comando seguente per compilare l'app .NET:

   ```dotnetcli
   dotnet build
   ```

1. Eseguire l'app con `spark-submit`. Assicurarsi di aggiornare il comando seguente con i percorsi effettivi del file jar di Microsoft Spark.

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a>Ottenere il codice

È possibile visualizzare la [soluzione completa](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) su GitHub.

## <a name="next-steps"></a>Passaggi successivi

Passare all'articolo successivo per informazioni su come elaborare i dati di streaming con .NET per Apache Spark.
> [!div class="nextstepaction"]
> [Esercitazione: flusso strutturato con .NET per Apache Spark](streaming.md)
