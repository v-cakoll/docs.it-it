---
title: Esercitazione su Structured streaming con .NET per Apache Spark
description: Questa esercitazione illustra come usare .NET per Apache Spark per Spark Structured streaming.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: 83d44af080d95ab6f9311ddd3ca4860806757436
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504035"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a>Esercitazione: flusso strutturato con .NET per Apache Spark 

Questa esercitazione illustra come richiamare Spark Structured streaming con .NET per Apache Spark. Spark Structured streaming è il supporto di Apache Spark per l'elaborazione di flussi di dati in tempo reale. L'elaborazione del flusso significa analizzare i dati in tempo reale durante la produzione.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> * Creare ed eseguire un'applicazione .NET per Apache Spark
> * Usare netcat per creare un flusso di dati
> * Usare funzioni definite dall'utente e SparkSQL per analizzare i dati di streaming

## <a name="prerequisites"></a>Prerequisiti

Se si tratta della prima applicazione .NET per Apache Spark, iniziare con l' [esercitazione Introduzione](get-started.md) per acquisire familiarità con le nozioni di base.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:

   ```dotnetcli
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   Il comando `dotnet` crea un'applicazione `new` di tipo `console` automaticamente. Il parametro `-o` crea una directory denominata *mySparkStreamingApp* in cui l'app viene archiviata e la popola con i file necessari. Il comando `cd mySparkStreamingApp` imposta la directory sulla directory dell'app appena creata.

1. Per usare .NET per Apache Spark in un'app, installare il pacchetto Microsoft. Spark. Nella console eseguire il comando seguente:

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a>Stabilire e connettersi a un flusso di dati

Un modo comune per testare l'elaborazione dei flussi consiste nell'usare **netcat**. Netcat (noto anche come *NC*) consente di leggere e scrivere in connessioni di rete. Viene stabilita una connessione di rete con netcat tramite una finestra del terminale. 

### <a name="create-a-data-stream-with-netcat"></a>Creare un flusso di dati con netcat

1. [Scaricare netcat](https://sourceforge.net/projects/nc110/files/). Estrarre quindi il file dal Download di zip e aggiungere la directory estratta nella variabile di ambiente "PATH".

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

### <a name="create-a-sparksession"></a>Creare un SparkSession

1. Aggiungere le seguenti istruzioni `using` aggiuntive all'inizio del file *Program.cs* in *mySparkStreamingApp*:

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Aggiungere il codice seguente al metodo `Main` per creare una nuova `SparkSession`. La sessione Spark è il punto di ingresso per la programmazione di Spark con il set di dati e l'API dataframe.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   La chiamata all'oggetto *Spark* creato in precedenza consente di accedere alle funzionalità di Spark e dataframe in tutto il programma.

### <a name="connect-to-a-stream-with-readstream"></a>Connettersi a un flusso con ReadStream ()

Il metodo `ReadStream()` restituisce un `DataStreamReader` che può essere usato per leggere i dati in streaming in come `DataFrame`. Includere le informazioni sull'host e sulla porta per indicare all'app Spark dove si aspettano i dati di streaming.

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a>Registrare una funzione definita dall'utente

È possibile usare *funzioni definite dall'utente e funzioni definite dall'utente*nelle applicazioni Spark per eseguire calcoli e analisi sui dati.

Aggiungere il codice seguente al metodo `Main` per registrare una funzione definita dall'utente denominata `udfArray`. 

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

Questa funzione definita dall'utente elabora ogni stringa ricevuta dal terminale netcat per produrre una matrice che include la stringa originale (contenuta in *Str*), seguita dalla stringa originale concatenata alla lunghezza della stringa originale. 

Ad esempio, l'immissione di *Hello World* nel terminale netcat produce una matrice in cui:

* Array\[0] = Hello World
* Array\[1] = Hello World 11

## <a name="use-sparksql"></a>Usare SparkSQL

Usare SparkSQL per eseguire varie funzioni sui dati archiviati nel dataframe. È comune combinare UDF e SparkSQL per applicare una funzione definita dall'utente a ogni riga di un dataframe.

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

Questo frammento di codice applica *udfArray* a ogni valore nel dataframe, che rappresenta ogni stringa letta dal terminale netcat. Applicare il metodo SparkSQL <xref:Microsoft.Spark.Sql.Functions.Explode%2A> per inserire ogni voce della matrice nella propria riga. Usare infine <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> per inserire le colonne generate nel nuovo dataframe *arrayDF.*

## <a name="display-your-stream"></a>Visualizzare il flusso

Usare <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> per stabilire le caratteristiche dell'output, ad esempio la stampa dei risultati nella console e la visualizzazione solo dell'output più recente.

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a>Eseguire il codice

Il flusso strutturato in Spark elabora i dati attraverso una serie di piccoli **batch**.  Quando si esegue il programma, il prompt dei comandi in cui viene stabilita la connessione netcat consente di iniziare a digitare. Ogni volta che si preme il tasto INVIO dopo aver digitato i dati nel prompt dei comandi, Spark considera la voce un batch ed esegue la funzione definita dall'utente.

### <a name="use-spark-submit-to-run-your-app"></a>Usare Spark-Submit per eseguire l'app

Dopo l'avvio di una nuova sessione di netcat, aprire un nuovo terminale ed eseguire il comando di `spark-submit`, in modo analogo al seguente comando:

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> Assicurarsi di aggiornare il comando precedente con il percorso effettivo del file jar di Microsoft Spark. Il comando precedente presuppone anche che il server netcat sia in esecuzione sulla porta localhost 9999.

## <a name="get-the-code"></a>Ottenere il codice

Questa esercitazione usa l'esempio [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) , ma sono disponibili altri tre esempi di elaborazione di flussi completi in GitHub:

* [StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): conteggio delle parole sui dati trasmessi da qualsiasi origine
* [StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): conteggio delle parole sui dati con la logica della finestra
* [StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): conteggio delle parole sui dati trasmessi da Kafka

## <a name="next-steps"></a>Passaggi successivi

Passare all'articolo successivo per informazioni su come distribuire .NET per Apache Spark applicazione in databricks.
> [!div class="nextstepaction"]
> [Esercitazione: distribuire un'applicazione .NET per Apache Spark a databricks](databricks-deployment.md)
