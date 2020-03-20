---
title: Esercitazione sul flusso di streaming strutturato con .NET per Apache Spark
description: In this tutorial, you learn how to use .NET for Apache Spark for Spark Structured Streaming.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: 125ef834da8e42c99c8080a3d5414a7927ce7636
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79186505"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a>Esercitazione: Streaming strutturato con .NET per Apache SparkTutorial: Structured Streaming with .NET for Apache Spark

In questa esercitazione viene illustrato come richiamare Spark Structured Streaming usando .NET per Apache Spark.This tutorial teaches you how to invoke Spark Structured Streaming using .NET for Apache Spark. Spark Structured Streaming è il supporto di Apache Spark per l'elaborazione di flussi di dati in tempo reale. L'elaborazione del flusso significa analizzare i dati in tempo reale durante la produzione.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> * Creare ed eseguire un'applicazione .NET per Apache SparkCreate and run a .NET for Apache Spark application
> * Usare netcat per creare un flusso di datiUse netcat to create a data stream
> * Usare le funzioni definite dall'utente e SparkSQL per analizzare i dati di streamingUse user-defined functions and SparkSQL to analyze streaming data

## <a name="prerequisites"></a>Prerequisites

Se si tratta della prima applicazione .NET per Apache Spark, iniziare con [l'esercitazione introduttiva](get-started.md) per acquisire familiarità con le nozioni di base.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:

   ```dotnetcli
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   Il `dotnet` comando `new` crea automaticamente `console` un'applicazione di tipo. Il `-o` parametro crea una directory denominata *mySparkStreamingApp* in cui l'app è archiviata e la popola con i file necessari. Il `cd mySparkStreamingApp` comando modifica la directory in base alla directory dell'app appena creata.

1. Per usare .NET per Apache Spark in un'app, installa il pacchetto Microsoft.Spark. Nella console, eseguire il comando seguente:

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a>Stabilire e connettersi a un flusso di dati

Un modo popolare per testare l'elaborazione del flusso è tramite **netcat**. netcat (noto anche come *nc*) consente di leggere e scrivere su connessioni di rete. Stabilire una connessione di rete con netcat attraverso una finestra del terminale.

### <a name="create-a-data-stream-with-netcat"></a>Creare un flusso di dati con netcatCreate a data stream with netcat

1. [Scarica netcat](https://sourceforge.net/projects/nc110/files/). Quindi, estrarre il file dal download zip e aggiungere la directory estratta alla variabile di ambiente "PATH".

2. Per avviare una nuova connessione, aprire una nuova console ed eseguire il comando seguente che si connette a localhost sulla porta 9999.

   In Windows:

   ```console
   nc -vvv -l -p 9999
   ```

   In Linux:

   ```console
   nc -lk 9999
   ```

   Il programma Spark è in ascolto dell'input digitato in questo prompt dei comandi.

### <a name="create-a-sparksession"></a>Creare una SparkSessionCreate a SparkSession

1. Aggiungere le `using` seguenti istruzioni aggiuntive all'inizio del file *Program.cs* in *mySparkStreamingApp*:

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Aggiungere il codice `Main` seguente al metodo `SparkSession`per creare un nuovo oggetto . La sessione Spark è il punto di ingresso alla programmazione Spark con il Dataset e l'API DataFrame.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   La chiamata all'oggetto *spark* creato in precedenza consente di accedere alle funzionalità Spark e DataFrame in tutto il programma.

### <a name="connect-to-a-stream-with-readstream"></a>Connettersi a un flusso con ReadStream()

Il `ReadStream()` metodo `DataStreamReader` restituisce un oggetto che può `DataFrame`essere utilizzato per leggere i dati di streaming come oggetto . Includi le informazioni sull'host e sulla porta per indicare all'app Spark dove aspettarsi i dati di streaming.

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a>Registrare una funzione definita dall'utenteRegister a user-defined function

È possibile utilizzare funzioni definite dall'utente, *funzioni definite dall'utente,* nelle applicazioni Spark per eseguire calcoli e analisi sui dati.

Aggiungere il codice `Main` seguente al metodo per `udfArray`registrare una funzione definita dall'utente denominata .

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

Questa funzione definita dall'utente elabora ogni stringa ricevuta dal terminale netcat per produrre una matrice che include la stringa originale (contenuta in *str*), seguita dalla stringa originale concatenata alla lunghezza della stringa originale.

Ad esempio, l'immissione di *Hello world* nel terminale netcat produce una matrice in cui:

* matrice\[0] - Ciao mondo
* matrice\[1] - Ciao mondo 11

## <a name="use-sparksql"></a>Usare SparkSQLUse SparkSQL

Usare SparkSQL per eseguire varie funzioni sui dati archiviati nel frame di dati. È comune combinare UDF e SparkSQL per applicare una funzione definita dall'utente a ogni riga di un frame di dati.

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

Questo frammento di codice applica *udfArray* a ogni valore nel DataFrame, che rappresenta ogni stringa letta dal terminale netcat. Applicare il SparkSQL metodo <xref:Microsoft.Spark.Sql.Functions.Explode%2A> per inserire ogni voce della matrice nella propria riga. Infine, <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> utilizzare per inserire le colonne prodotte nel nuovo ArrayDF di Frame di *dati.*

## <a name="display-your-stream"></a>Visualizzare lo stream

Consente <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> di stabilire le caratteristiche dell'output, ad esempio la stampa dei risultati nella console e la visualizzazione solo dell'output più recente.

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a>Eseguire il codiceRun your code

Lo streaming strutturato in Spark elabora i dati attraverso una serie di piccoli **batch.**  Quando si esegue il programma, il prompt dei comandi in cui si stabilisce la connessione netcat consente di iniziare a digitare. Ogni volta che si preme il tasto INVIO dopo aver digitato i dati nel prompt dei comandi, Spark considera l'immissione di un batch ed esegue la funzione definita dall'utente.

### <a name="use-spark-submit-to-run-your-app"></a>Usare l'invio di spark per eseguire l'appUse spark-submit to run your app

Dopo aver avviato una nuova sessione netcat, aprire un nuovo terminale ed eseguire il `spark-submit` comando, simile al seguente comando:

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> Assicurarsi di aggiornare il comando precedente con il percorso effettivo del file jar di Microsoft Spark. Il comando precedente presuppone inoltre che il server netcat sia in esecuzione sulla porta localhost 9999.

## <a name="get-the-code"></a>Ottenere il codice

Questa esercitazione usa [l'esempio di StructuredNetworkCharacterCount.cs,](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) ma ci sono altri tre esempi di elaborazione di flusso completo su GitHub:This tutorial uses the example example, but there are three other full stream processing examples on GitHub:

* [StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): conteggio parole sui dati trasmessi da qualsiasi origine
* [StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): conteggio parole su dati con logica di windowing
* [StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): conteggio parole sui dati trasmessi in streaming da Kafka

## <a name="next-steps"></a>Passaggi successivi

Passare all'articolo successivo per informazioni su come distribuire l'applicazione .NET per Apache Spark a Databricks.
> [!div class="nextstepaction"]
> [Esercitazione: Distribuire un'applicazione .NET per Apache Spark in DatabricksTutorial: Deploy a .NET for Apache Spark application to Databricks](databricks-deployment.md)
