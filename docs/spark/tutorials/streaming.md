---
title: Esercitazione su Structured streaming con .NET per Apache Spark
description: Questa esercitazione illustra come usare .NET per Apache Spark per Spark Structured streaming.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: d0fe79ef79125c06be9acd8ba80001a33e150adb
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802847"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a><span data-ttu-id="ac01e-103">Esercitazione: flusso strutturato con .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="ac01e-103">Tutorial: Structured Streaming with .NET for Apache Spark</span></span> 

<span data-ttu-id="ac01e-104">Questa esercitazione illustra come richiamare Spark Structured streaming con .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="ac01e-104">This tutorial teaches you how to invoke Spark Structured Streaming using .NET for Apache Spark.</span></span> <span data-ttu-id="ac01e-105">Spark Structured streaming è il supporto di Apache Spark per l'elaborazione di flussi di dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ac01e-105">Spark Structured Streaming is Apache Spark's support for processing real-time data streams.</span></span> <span data-ttu-id="ac01e-106">L'elaborazione del flusso significa analizzare i dati in tempo reale durante la produzione.</span><span class="sxs-lookup"><span data-stu-id="ac01e-106">Stream processing means analyzing live data as it's being produced.</span></span>

<span data-ttu-id="ac01e-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="ac01e-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="ac01e-108">Creare ed eseguire un'applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="ac01e-108">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="ac01e-109">Usare netcat per creare un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ac01e-109">Use netcat to create a data stream</span></span>
> * <span data-ttu-id="ac01e-110">Usare funzioni definite dall'utente e SparkSQL per analizzare i dati di streaming</span><span class="sxs-lookup"><span data-stu-id="ac01e-110">Use user-defined functions and SparkSQL to analyze streaming data</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac01e-111">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ac01e-111">Prerequisites</span></span>

<span data-ttu-id="ac01e-112">Se si tratta della prima applicazione .NET per Apache Spark, iniziare con l' [esercitazione Introduzione](get-started.md) per acquisire familiarità con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="ac01e-112">If this is your first .NET for Apache Spark application, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="ac01e-113">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="ac01e-113">Create a console application</span></span>

1. <span data-ttu-id="ac01e-114">Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="ac01e-114">In your command prompt, run the following commands to create a new console application:</span></span>

   ```console
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   <span data-ttu-id="ac01e-115">Il comando `dotnet` crea un'applicazione `new` di tipo `console` automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac01e-115">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="ac01e-116">Il parametro `-o` crea una directory denominata *mySparkStreamingApp* in cui l'app viene archiviata e la popola con i file necessari.</span><span class="sxs-lookup"><span data-stu-id="ac01e-116">The `-o` parameter creates a directory named *mySparkStreamingApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="ac01e-117">Il comando `cd mySparkStreamingApp` imposta la directory sulla directory dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="ac01e-117">The `cd mySparkStreamingApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="ac01e-118">Per usare .NET per Apache Spark in un'app, installare il pacchetto Microsoft. Spark.</span><span class="sxs-lookup"><span data-stu-id="ac01e-118">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="ac01e-119">Nella console eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ac01e-119">In your console, run the following command:</span></span>

   ```console
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a><span data-ttu-id="ac01e-120">Stabilire e connettersi a un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ac01e-120">Establish and connect to a data stream</span></span>

<span data-ttu-id="ac01e-121">Un modo comune per testare l'elaborazione dei flussi consiste nell'usare **netcat**.</span><span class="sxs-lookup"><span data-stu-id="ac01e-121">One popular way to test stream processing is through **netcat**.</span></span> <span data-ttu-id="ac01e-122">Netcat (noto anche come *NC*) consente di leggere e scrivere in connessioni di rete.</span><span class="sxs-lookup"><span data-stu-id="ac01e-122">netcat (also known as *nc*) allows you to read from and write to network connections.</span></span> <span data-ttu-id="ac01e-123">Viene stabilita una connessione di rete con netcat tramite una finestra del terminale.</span><span class="sxs-lookup"><span data-stu-id="ac01e-123">You establish a network connection with netcat through a terminal window.</span></span> 

### <a name="create-a-data-stream-with-netcat"></a><span data-ttu-id="ac01e-124">Creare un flusso di dati con netcat</span><span class="sxs-lookup"><span data-stu-id="ac01e-124">Create a data stream with netcat</span></span>

1. <span data-ttu-id="ac01e-125">[Scaricare netcat](https://sourceforge.net/projects/nc110/files/).</span><span class="sxs-lookup"><span data-stu-id="ac01e-125">[Download netcat](https://sourceforge.net/projects/nc110/files/).</span></span> <span data-ttu-id="ac01e-126">Estrarre quindi il file dal Download di zip e aggiungere la directory estratta nella variabile di ambiente "PATH".</span><span class="sxs-lookup"><span data-stu-id="ac01e-126">Then, extract the file from the zip download and append the directory you extracted to your "PATH" environment variable.</span></span>

2. <span data-ttu-id="ac01e-127">Per avviare una nuova connessione, aprire una nuova console ed eseguire il comando seguente che si connette a localhost sulla porta 9999.</span><span class="sxs-lookup"><span data-stu-id="ac01e-127">To start a new connection, open a new console and run the following command which connects to localhost on port 9999.</span></span>

   <span data-ttu-id="ac01e-128">In Windows:</span><span class="sxs-lookup"><span data-stu-id="ac01e-128">On Windows:</span></span>

   ```console
   nc -vvv -l -p 9999
   ```

   <span data-ttu-id="ac01e-129">In Linux:</span><span class="sxs-lookup"><span data-stu-id="ac01e-129">On Linux:</span></span>

   ```console
   nc -lk 9999
   ```

   <span data-ttu-id="ac01e-130">Il programma Spark è in ascolto dell'input digitato in questo prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ac01e-130">Your Spark program listens for the input you type into this command prompt.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="ac01e-131">Creare un SparkSession</span><span class="sxs-lookup"><span data-stu-id="ac01e-131">Create a SparkSession</span></span>

1. <span data-ttu-id="ac01e-132">Aggiungere le seguenti istruzioni `using` aggiuntive all'inizio del file *Program.cs* in *mySparkStreamingApp*:</span><span class="sxs-lookup"><span data-stu-id="ac01e-132">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkStreamingApp*:</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="ac01e-133">Aggiungere il codice seguente al metodo `Main` per creare una nuova `SparkSession`.</span><span class="sxs-lookup"><span data-stu-id="ac01e-133">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="ac01e-134">La sessione Spark è il punto di ingresso per la programmazione di Spark con il set di dati e l'API dataframe.</span><span class="sxs-lookup"><span data-stu-id="ac01e-134">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   <span data-ttu-id="ac01e-135">La chiamata all'oggetto *Spark* creato in precedenza consente di accedere alle funzionalità di Spark e dataframe in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="ac01e-135">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="connect-to-a-stream-with-readstream"></a><span data-ttu-id="ac01e-136">Connettersi a un flusso con ReadStream ()</span><span class="sxs-lookup"><span data-stu-id="ac01e-136">Connect to a stream with ReadStream()</span></span>

<span data-ttu-id="ac01e-137">Il metodo `ReadStream()` restituisce un `DataStreamReader` che può essere usato per leggere i dati in streaming in come `DataFrame`.</span><span class="sxs-lookup"><span data-stu-id="ac01e-137">The `ReadStream()` method returns a `DataStreamReader` that can be used to read streaming data in as a `DataFrame`.</span></span> <span data-ttu-id="ac01e-138">Includere le informazioni sull'host e sulla porta per indicare all'app Spark dove si aspettano i dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="ac01e-138">Include the host and port information to tell your Spark app where to expect its streaming data.</span></span>

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a><span data-ttu-id="ac01e-139">Registrare una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="ac01e-139">Register a user-defined function</span></span>

<span data-ttu-id="ac01e-140">È possibile usare *funzioni definite dall'utente e funzioni definite dall'utente*nelle applicazioni Spark per eseguire calcoli e analisi sui dati.</span><span class="sxs-lookup"><span data-stu-id="ac01e-140">You can use UDFs, *user-defined functions*, in Spark applications to perform calculations and analysis on your data.</span></span>

<span data-ttu-id="ac01e-141">Aggiungere il codice seguente al metodo `Main` per registrare una funzione definita dall'utente denominata `udfArray`.</span><span class="sxs-lookup"><span data-stu-id="ac01e-141">Add the following code to your `Main` method to register a UDF called `udfArray`.</span></span> 

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

<span data-ttu-id="ac01e-142">Questa funzione definita dall'utente elabora ogni stringa ricevuta dal terminale netcat per produrre una matrice che include la stringa originale (contenuta in *Str*), seguita dalla stringa originale concatenata alla lunghezza della stringa originale.</span><span class="sxs-lookup"><span data-stu-id="ac01e-142">This UDF processes each string it receives from the netcat terminal to produce an array that includes the original string (contained in *str*), followed by the original string concatenated with the length of the original string.</span></span> 

<span data-ttu-id="ac01e-143">Ad esempio, l'immissione di *Hello World* nel terminale netcat produce una matrice in cui:</span><span class="sxs-lookup"><span data-stu-id="ac01e-143">For example, entering *Hello world* in the netcat terminal produces an array where:</span></span>

* <span data-ttu-id="ac01e-144">Array\[0] = Hello World</span><span class="sxs-lookup"><span data-stu-id="ac01e-144">array\[0] = Hello world</span></span>
* <span data-ttu-id="ac01e-145">Array\[1] = Hello World 11</span><span class="sxs-lookup"><span data-stu-id="ac01e-145">array\[1] = Hello world 11</span></span>

## <a name="use-sparksql"></a><span data-ttu-id="ac01e-146">Usare SparkSQL</span><span class="sxs-lookup"><span data-stu-id="ac01e-146">Use SparkSQL</span></span>

<span data-ttu-id="ac01e-147">Usare SparkSQL per eseguire varie funzioni sui dati archiviati nel dataframe.</span><span class="sxs-lookup"><span data-stu-id="ac01e-147">Use SparkSQL to perform various functions on the data stored in your DataFrame.</span></span> <span data-ttu-id="ac01e-148">È comune combinare UDF e SparkSQL per applicare una funzione definita dall'utente a ogni riga di un dataframe.</span><span class="sxs-lookup"><span data-stu-id="ac01e-148">It's common to combine UDFs and SparkSQL to apply a UDF to each row of a DataFrame.</span></span>

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

<span data-ttu-id="ac01e-149">Questo frammento di codice applica *udfArray* a ogni valore nel dataframe, che rappresenta ogni stringa letta dal terminale netcat.</span><span class="sxs-lookup"><span data-stu-id="ac01e-149">This code snippet applies *udfArray* to each value in your DataFrame, which represents each string read from your netcat terminal.</span></span> <span data-ttu-id="ac01e-150">Applicare il metodo SparkSQL <xref:Microsoft.Spark.Sql.Functions.Explode%2A> per inserire ogni voce della matrice nella propria riga.</span><span class="sxs-lookup"><span data-stu-id="ac01e-150">Apply the SparkSQL method <xref:Microsoft.Spark.Sql.Functions.Explode%2A> to put each entry of your array in its own row.</span></span> <span data-ttu-id="ac01e-151">Usare infine <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> per inserire le colonne generate nel nuovo dataframe *arrayDF.*</span><span class="sxs-lookup"><span data-stu-id="ac01e-151">Finally, use <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> to place the columns you've produced in the new DataFrame *arrayDF.*</span></span>

## <a name="display-your-stream"></a><span data-ttu-id="ac01e-152">Visualizzare il flusso</span><span class="sxs-lookup"><span data-stu-id="ac01e-152">Display your stream</span></span>

<span data-ttu-id="ac01e-153">Usare <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> per stabilire le caratteristiche dell'output, ad esempio la stampa dei risultati nella console e la visualizzazione solo dell'output più recente.</span><span class="sxs-lookup"><span data-stu-id="ac01e-153">Use <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> to establish characteristics of your output, such as printing results to the console and displaying only the most recent output.</span></span>

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a><span data-ttu-id="ac01e-154">Eseguire il codice</span><span class="sxs-lookup"><span data-stu-id="ac01e-154">Run your code</span></span>

<span data-ttu-id="ac01e-155">Il flusso strutturato in Spark elabora i dati attraverso una serie di piccoli **batch**.</span><span class="sxs-lookup"><span data-stu-id="ac01e-155">Structured streaming in Spark processes data through a series of small **batches**.</span></span>  <span data-ttu-id="ac01e-156">Quando si esegue il programma, il prompt dei comandi in cui viene stabilita la connessione netcat consente di iniziare a digitare.</span><span class="sxs-lookup"><span data-stu-id="ac01e-156">When you run your program, the command prompt where you establish the netcat connection allows you to start typing.</span></span> <span data-ttu-id="ac01e-157">Ogni volta che si preme il tasto INVIO dopo aver digitato i dati nel prompt dei comandi, Spark considera la voce un batch ed esegue la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ac01e-157">Each time you press the Enter key after typing data in that command prompt, Spark considers your entry a batch and runs the UDF.</span></span>

### <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="ac01e-158">Usare Spark-Submit per eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="ac01e-158">Use spark-submit to run your app</span></span>

<span data-ttu-id="ac01e-159">Dopo l'avvio di una nuova sessione di netcat, aprire un nuovo terminale ed eseguire il comando di `spark-submit`, in modo analogo al seguente comando:</span><span class="sxs-lookup"><span data-stu-id="ac01e-159">After starting a new netcat session, open a new terminal and run your `spark-submit` command, similar to the following command:</span></span>

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> <span data-ttu-id="ac01e-160">Assicurarsi di aggiornare il comando precedente con il percorso effettivo del file jar di Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="ac01e-160">Be sure to update the above command with the actual path to your Microsoft Spark jar file.</span></span> <span data-ttu-id="ac01e-161">Il comando precedente presuppone anche che il server netcat sia in esecuzione sulla porta localhost 9999.</span><span class="sxs-lookup"><span data-stu-id="ac01e-161">The above command also assumes your netcat server is running on localhost port 9999.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="ac01e-162">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="ac01e-162">Get the code</span></span>

<span data-ttu-id="ac01e-163">Questa esercitazione usa l'esempio [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) , ma sono disponibili altri tre esempi di elaborazione di flussi completi in GitHub:</span><span class="sxs-lookup"><span data-stu-id="ac01e-163">This tutorial uses the [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) example, but there are three other full stream processing examples on GitHub:</span></span>

* <span data-ttu-id="ac01e-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): conteggio delle parole sui dati trasmessi da qualsiasi origine</span><span class="sxs-lookup"><span data-stu-id="ac01e-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): word count on data streamed from any source</span></span>
* <span data-ttu-id="ac01e-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): conteggio delle parole sui dati con la logica della finestra</span><span class="sxs-lookup"><span data-stu-id="ac01e-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): word count on data with windowing logic</span></span>
* <span data-ttu-id="ac01e-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): conteggio delle parole sui dati trasmessi da Kafka</span><span class="sxs-lookup"><span data-stu-id="ac01e-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): word count on data streamed from Kafka</span></span>

## <a name="next-steps"></a><span data-ttu-id="ac01e-167">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ac01e-167">Next steps</span></span>

<span data-ttu-id="ac01e-168">Passare all'articolo successivo per informazioni su come distribuire .NET per Apache Spark applicazione in databricks.</span><span class="sxs-lookup"><span data-stu-id="ac01e-168">Advance to the next article to learn how to deploy your .NET for Apache Spark application to Databricks.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ac01e-169">Esercitazione: distribuire un'applicazione .NET per Apache Spark a databricks</span><span class="sxs-lookup"><span data-stu-id="ac01e-169">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>](databricks-deployment.md)
