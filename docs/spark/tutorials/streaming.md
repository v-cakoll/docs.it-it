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
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a><span data-ttu-id="83d08-103">Esercitazione: Streaming strutturato con .NET per Apache SparkTutorial: Structured Streaming with .NET for Apache Spark</span><span class="sxs-lookup"><span data-stu-id="83d08-103">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>

<span data-ttu-id="83d08-104">In questa esercitazione viene illustrato come richiamare Spark Structured Streaming usando .NET per Apache Spark.This tutorial teaches you how to invoke Spark Structured Streaming using .NET for Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="83d08-104">This tutorial teaches you how to invoke Spark Structured Streaming using .NET for Apache Spark.</span></span> <span data-ttu-id="83d08-105">Spark Structured Streaming è il supporto di Apache Spark per l'elaborazione di flussi di dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="83d08-105">Spark Structured Streaming is Apache Spark's support for processing real-time data streams.</span></span> <span data-ttu-id="83d08-106">L'elaborazione del flusso significa analizzare i dati in tempo reale durante la produzione.</span><span class="sxs-lookup"><span data-stu-id="83d08-106">Stream processing means analyzing live data as it's being produced.</span></span>

<span data-ttu-id="83d08-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="83d08-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="83d08-108">Creare ed eseguire un'applicazione .NET per Apache SparkCreate and run a .NET for Apache Spark application</span><span class="sxs-lookup"><span data-stu-id="83d08-108">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="83d08-109">Usare netcat per creare un flusso di datiUse netcat to create a data stream</span><span class="sxs-lookup"><span data-stu-id="83d08-109">Use netcat to create a data stream</span></span>
> * <span data-ttu-id="83d08-110">Usare le funzioni definite dall'utente e SparkSQL per analizzare i dati di streamingUse user-defined functions and SparkSQL to analyze streaming data</span><span class="sxs-lookup"><span data-stu-id="83d08-110">Use user-defined functions and SparkSQL to analyze streaming data</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83d08-111">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="83d08-111">Prerequisites</span></span>

<span data-ttu-id="83d08-112">Se si tratta della prima applicazione .NET per Apache Spark, iniziare con [l'esercitazione introduttiva](get-started.md) per acquisire familiarità con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="83d08-112">If this is your first .NET for Apache Spark application, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="83d08-113">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="83d08-113">Create a console application</span></span>

1. <span data-ttu-id="83d08-114">Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="83d08-114">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   <span data-ttu-id="83d08-115">Il `dotnet` comando `new` crea automaticamente `console` un'applicazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="83d08-115">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="83d08-116">Il `-o` parametro crea una directory denominata *mySparkStreamingApp* in cui l'app è archiviata e la popola con i file necessari.</span><span class="sxs-lookup"><span data-stu-id="83d08-116">The `-o` parameter creates a directory named *mySparkStreamingApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="83d08-117">Il `cd mySparkStreamingApp` comando modifica la directory in base alla directory dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="83d08-117">The `cd mySparkStreamingApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="83d08-118">Per usare .NET per Apache Spark in un'app, installa il pacchetto Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="83d08-118">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="83d08-119">Nella console, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="83d08-119">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a><span data-ttu-id="83d08-120">Stabilire e connettersi a un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="83d08-120">Establish and connect to a data stream</span></span>

<span data-ttu-id="83d08-121">Un modo popolare per testare l'elaborazione del flusso è tramite **netcat**.</span><span class="sxs-lookup"><span data-stu-id="83d08-121">One popular way to test stream processing is through **netcat**.</span></span> <span data-ttu-id="83d08-122">netcat (noto anche come *nc*) consente di leggere e scrivere su connessioni di rete.</span><span class="sxs-lookup"><span data-stu-id="83d08-122">netcat (also known as *nc*) allows you to read from and write to network connections.</span></span> <span data-ttu-id="83d08-123">Stabilire una connessione di rete con netcat attraverso una finestra del terminale.</span><span class="sxs-lookup"><span data-stu-id="83d08-123">You establish a network connection with netcat through a terminal window.</span></span>

### <a name="create-a-data-stream-with-netcat"></a><span data-ttu-id="83d08-124">Creare un flusso di dati con netcatCreate a data stream with netcat</span><span class="sxs-lookup"><span data-stu-id="83d08-124">Create a data stream with netcat</span></span>

1. <span data-ttu-id="83d08-125">[Scarica netcat](https://sourceforge.net/projects/nc110/files/).</span><span class="sxs-lookup"><span data-stu-id="83d08-125">[Download netcat](https://sourceforge.net/projects/nc110/files/).</span></span> <span data-ttu-id="83d08-126">Quindi, estrarre il file dal download zip e aggiungere la directory estratta alla variabile di ambiente "PATH".</span><span class="sxs-lookup"><span data-stu-id="83d08-126">Then, extract the file from the zip download and append the directory you extracted to your "PATH" environment variable.</span></span>

2. <span data-ttu-id="83d08-127">Per avviare una nuova connessione, aprire una nuova console ed eseguire il comando seguente che si connette a localhost sulla porta 9999.</span><span class="sxs-lookup"><span data-stu-id="83d08-127">To start a new connection, open a new console and run the following command which connects to localhost on port 9999.</span></span>

   <span data-ttu-id="83d08-128">In Windows:</span><span class="sxs-lookup"><span data-stu-id="83d08-128">On Windows:</span></span>

   ```console
   nc -vvv -l -p 9999
   ```

   <span data-ttu-id="83d08-129">In Linux:</span><span class="sxs-lookup"><span data-stu-id="83d08-129">On Linux:</span></span>

   ```console
   nc -lk 9999
   ```

   <span data-ttu-id="83d08-130">Il programma Spark è in ascolto dell'input digitato in questo prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="83d08-130">Your Spark program listens for the input you type into this command prompt.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="83d08-131">Creare una SparkSessionCreate a SparkSession</span><span class="sxs-lookup"><span data-stu-id="83d08-131">Create a SparkSession</span></span>

1. <span data-ttu-id="83d08-132">Aggiungere le `using` seguenti istruzioni aggiuntive all'inizio del file *Program.cs* in *mySparkStreamingApp*:</span><span class="sxs-lookup"><span data-stu-id="83d08-132">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkStreamingApp*:</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="83d08-133">Aggiungere il codice `Main` seguente al metodo `SparkSession`per creare un nuovo oggetto .</span><span class="sxs-lookup"><span data-stu-id="83d08-133">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="83d08-134">La sessione Spark è il punto di ingresso alla programmazione Spark con il Dataset e l'API DataFrame.</span><span class="sxs-lookup"><span data-stu-id="83d08-134">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   <span data-ttu-id="83d08-135">La chiamata all'oggetto *spark* creato in precedenza consente di accedere alle funzionalità Spark e DataFrame in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="83d08-135">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="connect-to-a-stream-with-readstream"></a><span data-ttu-id="83d08-136">Connettersi a un flusso con ReadStream()</span><span class="sxs-lookup"><span data-stu-id="83d08-136">Connect to a stream with ReadStream()</span></span>

<span data-ttu-id="83d08-137">Il `ReadStream()` metodo `DataStreamReader` restituisce un oggetto che può `DataFrame`essere utilizzato per leggere i dati di streaming come oggetto .</span><span class="sxs-lookup"><span data-stu-id="83d08-137">The `ReadStream()` method returns a `DataStreamReader` that can be used to read streaming data in as a `DataFrame`.</span></span> <span data-ttu-id="83d08-138">Includi le informazioni sull'host e sulla porta per indicare all'app Spark dove aspettarsi i dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="83d08-138">Include the host and port information to tell your Spark app where to expect its streaming data.</span></span>

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a><span data-ttu-id="83d08-139">Registrare una funzione definita dall'utenteRegister a user-defined function</span><span class="sxs-lookup"><span data-stu-id="83d08-139">Register a user-defined function</span></span>

<span data-ttu-id="83d08-140">È possibile utilizzare funzioni definite dall'utente, *funzioni definite dall'utente,* nelle applicazioni Spark per eseguire calcoli e analisi sui dati.</span><span class="sxs-lookup"><span data-stu-id="83d08-140">You can use UDFs, *user-defined functions*, in Spark applications to perform calculations and analysis on your data.</span></span>

<span data-ttu-id="83d08-141">Aggiungere il codice `Main` seguente al metodo per `udfArray`registrare una funzione definita dall'utente denominata .</span><span class="sxs-lookup"><span data-stu-id="83d08-141">Add the following code to your `Main` method to register a UDF called `udfArray`.</span></span>

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

<span data-ttu-id="83d08-142">Questa funzione definita dall'utente elabora ogni stringa ricevuta dal terminale netcat per produrre una matrice che include la stringa originale (contenuta in *str*), seguita dalla stringa originale concatenata alla lunghezza della stringa originale.</span><span class="sxs-lookup"><span data-stu-id="83d08-142">This UDF processes each string it receives from the netcat terminal to produce an array that includes the original string (contained in *str*), followed by the original string concatenated with the length of the original string.</span></span>

<span data-ttu-id="83d08-143">Ad esempio, l'immissione di *Hello world* nel terminale netcat produce una matrice in cui:</span><span class="sxs-lookup"><span data-stu-id="83d08-143">For example, entering *Hello world* in the netcat terminal produces an array where:</span></span>

* <span data-ttu-id="83d08-144">matrice\[0] - Ciao mondo</span><span class="sxs-lookup"><span data-stu-id="83d08-144">array\[0] = Hello world</span></span>
* <span data-ttu-id="83d08-145">matrice\[1] - Ciao mondo 11</span><span class="sxs-lookup"><span data-stu-id="83d08-145">array\[1] = Hello world 11</span></span>

## <a name="use-sparksql"></a><span data-ttu-id="83d08-146">Usare SparkSQLUse SparkSQL</span><span class="sxs-lookup"><span data-stu-id="83d08-146">Use SparkSQL</span></span>

<span data-ttu-id="83d08-147">Usare SparkSQL per eseguire varie funzioni sui dati archiviati nel frame di dati.</span><span class="sxs-lookup"><span data-stu-id="83d08-147">Use SparkSQL to perform various functions on the data stored in your DataFrame.</span></span> <span data-ttu-id="83d08-148">È comune combinare UDF e SparkSQL per applicare una funzione definita dall'utente a ogni riga di un frame di dati.</span><span class="sxs-lookup"><span data-stu-id="83d08-148">It's common to combine UDFs and SparkSQL to apply a UDF to each row of a DataFrame.</span></span>

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

<span data-ttu-id="83d08-149">Questo frammento di codice applica *udfArray* a ogni valore nel DataFrame, che rappresenta ogni stringa letta dal terminale netcat.</span><span class="sxs-lookup"><span data-stu-id="83d08-149">This code snippet applies *udfArray* to each value in your DataFrame, which represents each string read from your netcat terminal.</span></span> <span data-ttu-id="83d08-150">Applicare il SparkSQL metodo <xref:Microsoft.Spark.Sql.Functions.Explode%2A> per inserire ogni voce della matrice nella propria riga.</span><span class="sxs-lookup"><span data-stu-id="83d08-150">Apply the SparkSQL method <xref:Microsoft.Spark.Sql.Functions.Explode%2A> to put each entry of your array in its own row.</span></span> <span data-ttu-id="83d08-151">Infine, <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> utilizzare per inserire le colonne prodotte nel nuovo ArrayDF di Frame di *dati.*</span><span class="sxs-lookup"><span data-stu-id="83d08-151">Finally, use <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> to place the columns you've produced in the new DataFrame *arrayDF.*</span></span>

## <a name="display-your-stream"></a><span data-ttu-id="83d08-152">Visualizzare lo stream</span><span class="sxs-lookup"><span data-stu-id="83d08-152">Display your stream</span></span>

<span data-ttu-id="83d08-153">Consente <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> di stabilire le caratteristiche dell'output, ad esempio la stampa dei risultati nella console e la visualizzazione solo dell'output più recente.</span><span class="sxs-lookup"><span data-stu-id="83d08-153">Use <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> to establish characteristics of your output, such as printing results to the console and displaying only the most recent output.</span></span>

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a><span data-ttu-id="83d08-154">Eseguire il codiceRun your code</span><span class="sxs-lookup"><span data-stu-id="83d08-154">Run your code</span></span>

<span data-ttu-id="83d08-155">Lo streaming strutturato in Spark elabora i dati attraverso una serie di piccoli **batch.**</span><span class="sxs-lookup"><span data-stu-id="83d08-155">Structured streaming in Spark processes data through a series of small **batches**.</span></span>  <span data-ttu-id="83d08-156">Quando si esegue il programma, il prompt dei comandi in cui si stabilisce la connessione netcat consente di iniziare a digitare.</span><span class="sxs-lookup"><span data-stu-id="83d08-156">When you run your program, the command prompt where you establish the netcat connection allows you to start typing.</span></span> <span data-ttu-id="83d08-157">Ogni volta che si preme il tasto INVIO dopo aver digitato i dati nel prompt dei comandi, Spark considera l'immissione di un batch ed esegue la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="83d08-157">Each time you press the Enter key after typing data in that command prompt, Spark considers your entry a batch and runs the UDF.</span></span>

### <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="83d08-158">Usare l'invio di spark per eseguire l'appUse spark-submit to run your app</span><span class="sxs-lookup"><span data-stu-id="83d08-158">Use spark-submit to run your app</span></span>

<span data-ttu-id="83d08-159">Dopo aver avviato una nuova sessione netcat, aprire un nuovo terminale ed eseguire il `spark-submit` comando, simile al seguente comando:</span><span class="sxs-lookup"><span data-stu-id="83d08-159">After starting a new netcat session, open a new terminal and run your `spark-submit` command, similar to the following command:</span></span>

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> <span data-ttu-id="83d08-160">Assicurarsi di aggiornare il comando precedente con il percorso effettivo del file jar di Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="83d08-160">Be sure to update the above command with the actual path to your Microsoft Spark jar file.</span></span> <span data-ttu-id="83d08-161">Il comando precedente presuppone inoltre che il server netcat sia in esecuzione sulla porta localhost 9999.</span><span class="sxs-lookup"><span data-stu-id="83d08-161">The above command also assumes your netcat server is running on localhost port 9999.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="83d08-162">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="83d08-162">Get the code</span></span>

<span data-ttu-id="83d08-163">Questa esercitazione usa [l'esempio di StructuredNetworkCharacterCount.cs,](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) ma ci sono altri tre esempi di elaborazione di flusso completo su GitHub:This tutorial uses the example example, but there are three other full stream processing examples on GitHub:</span><span class="sxs-lookup"><span data-stu-id="83d08-163">This tutorial uses the [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) example, but there are three other full stream processing examples on GitHub:</span></span>

* <span data-ttu-id="83d08-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): conteggio parole sui dati trasmessi da qualsiasi origine</span><span class="sxs-lookup"><span data-stu-id="83d08-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): word count on data streamed from any source</span></span>
* <span data-ttu-id="83d08-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): conteggio parole su dati con logica di windowing</span><span class="sxs-lookup"><span data-stu-id="83d08-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): word count on data with windowing logic</span></span>
* <span data-ttu-id="83d08-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): conteggio parole sui dati trasmessi in streaming da Kafka</span><span class="sxs-lookup"><span data-stu-id="83d08-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): word count on data streamed from Kafka</span></span>

## <a name="next-steps"></a><span data-ttu-id="83d08-167">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="83d08-167">Next steps</span></span>

<span data-ttu-id="83d08-168">Passare all'articolo successivo per informazioni su come distribuire l'applicazione .NET per Apache Spark a Databricks.</span><span class="sxs-lookup"><span data-stu-id="83d08-168">Advance to the next article to learn how to deploy your .NET for Apache Spark application to Databricks.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="83d08-169">Esercitazione: Distribuire un'applicazione .NET per Apache Spark in DatabricksTutorial: Deploy a .NET for Apache Spark application to Databricks</span><span class="sxs-lookup"><span data-stu-id="83d08-169">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>](databricks-deployment.md)
