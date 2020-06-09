---
title: Esercitazione sull'elaborazione batch con .NET per Apache Spark
description: Informazioni su come eseguire l'elaborazione batch con .NET per Apache Spark.
author: mamccrea
ms.author: mamccrea
ms.date: 12/13/2019
ms.topic: tutorial
ms.openlocfilehash: b00f560317c085058d791e17954603670fccf60f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594517"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a><span data-ttu-id="f1d17-103">Esercitazione: elaborazione batch con .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="f1d17-103">Tutorial: Do batch processing with .NET for Apache Spark</span></span>

<span data-ttu-id="f1d17-104">In questa esercitazione si apprenderà come eseguire l'elaborazione batch con .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="f1d17-104">In this tutorial, you learn how to do batch processing using .NET for Apache Spark.</span></span> <span data-ttu-id="f1d17-105">L'elaborazione batch è la trasformazione dei dati inattivi, vale a dire che i dati di origine sono già stati caricati nell'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="f1d17-105">Batch processing is the transformation of data at rest, meaning that the source data has already been loaded into data storage.</span></span>

<span data-ttu-id="f1d17-106">L'elaborazione batch viene in genere eseguita su set di impostazioni di grandi dimensioni e flat che devono essere preparati per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="f1d17-106">Batch processing is generally performed over large, flat datasets that need to be prepared for further analysis.</span></span> <span data-ttu-id="f1d17-107">L'elaborazione dei log e il data warehousing sono scenari comuni di elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="f1d17-107">Log processing and data warehousing are common batch processing scenarios.</span></span> <span data-ttu-id="f1d17-108">In questo scenario si analizzano le informazioni sui progetti GitHub, ad esempio il numero di volte in cui è stato eseguito il fork di progetti diversi o la modalità di aggiornamento dei progetti di recente.</span><span class="sxs-lookup"><span data-stu-id="f1d17-108">In this scenario, you analyze information about GitHub projects, such as the number of time different projects have been forked or how recently projects have been updated.</span></span>

<span data-ttu-id="f1d17-109">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="f1d17-109">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="f1d17-110">Creare ed eseguire un'applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="f1d17-110">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="f1d17-111">Leggere i dati in un frame di dati e prepararli per l'analisi</span><span class="sxs-lookup"><span data-stu-id="f1d17-111">Read data into a DataFrame and prepare it for analysis</span></span>
> * <span data-ttu-id="f1d17-112">Elaborare i dati con Spark SQL</span><span class="sxs-lookup"><span data-stu-id="f1d17-112">Process the data using Spark SQL</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1d17-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f1d17-113">Prerequisites</span></span>

<span data-ttu-id="f1d17-114">Se è la prima volta che si usa .NET per Apache Spark, vedere l'esercitazione [Introduzione a .NET per Apache Spark](get-started.md) per informazioni su come preparare l'ambiente ed eseguire la prima applicazione .net per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="f1d17-114">If this is your first time using .NET for Apache Spark, check out the [Get started with .NET for Apache Spark](get-started.md) tutorial to learn how to prepare your environment and run your first .NET for Apache Spark application.</span></span>

## <a name="download-the-sample-data"></a><span data-ttu-id="f1d17-115">Scaricare i dati di esempio</span><span class="sxs-lookup"><span data-stu-id="f1d17-115">Download the sample data</span></span>

<span data-ttu-id="f1d17-116">[GHTorrent](http://ghtorrent.org/) monitora tutti gli eventi GitHub pubblici, ad esempio informazioni su progetti, commit e Watcher, e archivia gli eventi e la relativa struttura nei database.</span><span class="sxs-lookup"><span data-stu-id="f1d17-116">[GHTorrent](http://ghtorrent.org/) monitors all public GitHub events, such as info about projects, commits, and watchers, and stores the events and their structure in databases.</span></span> <span data-ttu-id="f1d17-117">I dati raccolti in periodi di tempo diversi sono disponibili come archivi scaricabili.</span><span class="sxs-lookup"><span data-stu-id="f1d17-117">Data collected over different time periods is available as downloadable archives.</span></span> <span data-ttu-id="f1d17-118">Poiché i file dump sono molto grandi, questa guida usa una [versione troncata del file dump](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) che può essere scaricata da GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1d17-118">Because the dump files are very large, this guide uses a [truncated version of the dump file](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) that can be downloaded from GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="f1d17-119">Il set di dati GHTorrent viene distribuito in base a uno schema Dual Licensing ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)).</span><span class="sxs-lookup"><span data-stu-id="f1d17-119">The GHTorrent dataset is distributed under a dual licensing scheme ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)).</span></span> <span data-ttu-id="f1d17-120">Per gli usi non commerciali (inclusi, a titolo esemplificativo, didattico, ricerca o uso personale), il set di dati viene distribuito con la [licenza CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).</span><span class="sxs-lookup"><span data-stu-id="f1d17-120">For non-commercial uses (including, but not limited to, educational, research or personal uses), the dataset is distributed under the [CC-BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f1d17-121">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="f1d17-121">Create a console application</span></span>

1. <span data-ttu-id="f1d17-122">Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="f1d17-122">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   <span data-ttu-id="f1d17-123">Il `dotnet` comando crea automaticamente un' `new` applicazione di tipo `console` .</span><span class="sxs-lookup"><span data-stu-id="f1d17-123">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="f1d17-124">Il `-o` parametro crea una directory denominata *mySparkBatchApp* in cui l'app viene archiviata e la popola con i file necessari.</span><span class="sxs-lookup"><span data-stu-id="f1d17-124">The `-o` parameter creates a directory named *mySparkBatchApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="f1d17-125">Il `cd mySparkBatchApp` comando imposta la directory sulla directory dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="f1d17-125">The `cd mySparkBatchApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="f1d17-126">Per usare .NET per Apache Spark in un'app, installare il pacchetto Microsoft. Spark.</span><span class="sxs-lookup"><span data-stu-id="f1d17-126">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="f1d17-127">Nella console eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1d17-127">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a><span data-ttu-id="f1d17-128">Creare un SparkSession</span><span class="sxs-lookup"><span data-stu-id="f1d17-128">Create a SparkSession</span></span>

1. <span data-ttu-id="f1d17-129">Aggiungere le istruzioni aggiuntive seguenti `using` all'inizio del file *Program.cs* in *mySparkBatchApp*.</span><span class="sxs-lookup"><span data-stu-id="f1d17-129">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkBatchApp*.</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="f1d17-130">Aggiungere il codice seguente allo spazio dei nomi del progetto.</span><span class="sxs-lookup"><span data-stu-id="f1d17-130">Add the following code to your project namespace.</span></span> <span data-ttu-id="f1d17-131">*s_referenceData* viene usato in un secondo momento nel programma per filtrare in base alla data.</span><span class="sxs-lookup"><span data-stu-id="f1d17-131">*s_referenceData* is used later in the program to filter based on date.</span></span>

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. <span data-ttu-id="f1d17-132">Aggiungere il codice seguente all'interno del metodo Main per stabilire un nuovo SparkSession.</span><span class="sxs-lookup"><span data-stu-id="f1d17-132">Add the following code inside your Main method to establish a new SparkSession.</span></span> <span data-ttu-id="f1d17-133">SparkSession è il punto di ingresso per la programmazione di Spark con il set di dati e l'API dataframe.</span><span class="sxs-lookup"><span data-stu-id="f1d17-133">The SparkSession is the entry point to programming Spark with the Dataset and DataFrame API.</span></span> <span data-ttu-id="f1d17-134">Chiamando l' `spark` oggetto, è possibile accedere alla funzionalità Spark e dataframe nell'intero programma.</span><span class="sxs-lookup"><span data-stu-id="f1d17-134">By calling the `spark` object, you can access Spark and DataFrame functionality throughout your program.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a><span data-ttu-id="f1d17-135">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="f1d17-135">Prepare the data</span></span>

1. <span data-ttu-id="f1d17-136">Leggere il file di input in un oggetto `DataFrame` , ovvero una raccolta distribuita di dati organizzati in colonne denominate.</span><span class="sxs-lookup"><span data-stu-id="f1d17-136">Read the input file into a `DataFrame`, which is a distributed collection of data organized into named columns.</span></span> <span data-ttu-id="f1d17-137">È possibile impostare le colonne per i dati tramite <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A> .</span><span class="sxs-lookup"><span data-stu-id="f1d17-137">You can set the columns for your data through <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>.</span></span> <span data-ttu-id="f1d17-138">Usare il <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> metodo per visualizzare i dati nel frame di dati.</span><span class="sxs-lookup"><span data-stu-id="f1d17-138">Use the <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> method to display the data in your DataFrame.</span></span> <span data-ttu-id="f1d17-139">Assicurarsi di aggiornare il percorso del file CSV al percorso dei dati di GitHub scaricati.</span><span class="sxs-lookup"><span data-stu-id="f1d17-139">Be sure to update the CSV file path to the location of the GitHub data you downloaded.</span></span>

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

1. <span data-ttu-id="f1d17-140">Usare il <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> metodo per eliminare righe con valori na (null) e il <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> metodo per rimuovere determinate colonne dai dati.</span><span class="sxs-lookup"><span data-stu-id="f1d17-140">Use the <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> method to drop rows with NA (null) values, and the <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> method to remove certain columns from your data.</span></span> <span data-ttu-id="f1d17-141">Ciò consente di evitare errori se si tenta di analizzare i dati o le colonne null che non sono rilevanti per l'analisi finale.</span><span class="sxs-lookup"><span data-stu-id="f1d17-141">This helps prevent errors if you try to analyze null data or columns that are not relevant to your final analysis.</span></span>

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a><span data-ttu-id="f1d17-142">Analizzare i dati</span><span class="sxs-lookup"><span data-stu-id="f1d17-142">Analyze the data</span></span>

<span data-ttu-id="f1d17-143">Spark SQL consente di eseguire chiamate SQL sui dati.</span><span class="sxs-lookup"><span data-stu-id="f1d17-143">Spark SQL allows you to make SQL calls on your data.</span></span> <span data-ttu-id="f1d17-144">È comune combinare le funzioni definite dall'utente e Spark SQL per applicare una funzione definita dall'utente a tutte le righe del dataframe.</span><span class="sxs-lookup"><span data-stu-id="f1d17-144">It's common to combine user-defined functions and Spark SQL to apply a user-defined function to all rows of your DataFrame.</span></span>

<span data-ttu-id="f1d17-145">È possibile chiamare in modo specifico `spark.Sql` per simulare chiamate SQL standard visualizzate in altri tipi di app.</span><span class="sxs-lookup"><span data-stu-id="f1d17-145">You can specifically call `spark.Sql` to mimic standard SQL calls seen in other types of apps.</span></span> <span data-ttu-id="f1d17-146">È anche possibile chiamare metodi come <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> e <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> per combinare, filtrare ed eseguire calcoli sui dati in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="f1d17-146">You can also call methods like <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> and <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> to specifically combine, filter, and perform calculations on your data.</span></span>

<span data-ttu-id="f1d17-147">L'obiettivo di questa app è ottenere informazioni approfondite sui dati dei progetti GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1d17-147">The goal of this app is to gain some insights about the GitHub projects data.</span></span> <span data-ttu-id="f1d17-148">Aggiungere i frammenti di codice seguenti al programma per analizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="f1d17-148">Add the following code snippets to your program to analyze the data.</span></span>

1. <span data-ttu-id="f1d17-149">Aggiungere il blocco di codice seguente per trovare il numero di volte in cui ogni lingua è stata diramata.</span><span class="sxs-lookup"><span data-stu-id="f1d17-149">Add the following block of code finds the number of times each language has been forked.</span></span> <span data-ttu-id="f1d17-150">Per prima cosa, i dati vengono raggruppati in base alla lingua.</span><span class="sxs-lookup"><span data-stu-id="f1d17-150">First, the data is grouped by language.</span></span> <span data-ttu-id="f1d17-151">Viene quindi assunto il numero medio di fork da ogni lingua.</span><span class="sxs-lookup"><span data-stu-id="f1d17-151">Then, the average number of forks from each language is taken.</span></span>

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. <span data-ttu-id="f1d17-152">Aggiungere il blocco di codice seguente per ordinare il numero medio di fork in ordine decrescente per vedere quali lingue sono più fork.</span><span class="sxs-lookup"><span data-stu-id="f1d17-152">Add the following block of code to order the average number of forks in descending order to see which languages are the most forked.</span></span> <span data-ttu-id="f1d17-153">Ovvero il numero maggiore di fork verrà visualizzato per primo.</span><span class="sxs-lookup"><span data-stu-id="f1d17-153">That is, the largest number of forks will appear first.</span></span>

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. <span data-ttu-id="f1d17-154">Il blocco di codice successivo Mostra il modo in cui i progetti sono stati aggiornati di recente.</span><span class="sxs-lookup"><span data-stu-id="f1d17-154">The next block of code shows you how recently projects have been updated.</span></span> <span data-ttu-id="f1d17-155">Si registra una nuova funzione definita dall'utente denominata *MyUDF* e la si confronta con una data, *s_referenceDate*, che è stata dichiarata all'inizio dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="f1d17-155">You register a new user-defined function called *MyUDF* and compare it with a date, *s_referenceDate*, which was declared at the beginning of the tutorial.</span></span> <span data-ttu-id="f1d17-156">La data per ogni progetto viene confrontata con la data di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f1d17-156">The date for each project is compared against the reference date.</span></span> <span data-ttu-id="f1d17-157">Viene quindi usato Spark SQL per chiamare la funzione definita dall'utente in ogni riga dei dati per analizzare ogni progetto nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="f1d17-157">Then, Spark SQL is used to call the UDF on each row of the data to analyze each project in the data set.</span></span>

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

1. <span data-ttu-id="f1d17-158">Chiamare `spark.Stop()` per terminare l'SparkSession.</span><span class="sxs-lookup"><span data-stu-id="f1d17-158">Call `spark.Stop()` to end the SparkSession.</span></span>

## <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="f1d17-159">Usare Spark-Submit per eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="f1d17-159">Use spark-submit to run your app</span></span>

1. <span data-ttu-id="f1d17-160">Usare il comando seguente per compilare l'app .NET:</span><span class="sxs-lookup"><span data-stu-id="f1d17-160">Use the following command to build your .NET app:</span></span>

   ```dotnetcli
   dotnet build
   ```

1. <span data-ttu-id="f1d17-161">Eseguire l'app con `spark-submit` .</span><span class="sxs-lookup"><span data-stu-id="f1d17-161">Run your app with `spark-submit`.</span></span> <span data-ttu-id="f1d17-162">Assicurarsi di aggiornare il comando seguente con i percorsi effettivi del file jar di Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="f1d17-162">Be sure to update the following command with the actual paths to your Microsoft Spark jar file.</span></span>

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a><span data-ttu-id="f1d17-163">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="f1d17-163">Get the code</span></span>

<span data-ttu-id="f1d17-164">È possibile visualizzare la [soluzione completa](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1d17-164">You can see the [full solution](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) on GitHub.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1d17-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f1d17-165">Next steps</span></span>

<span data-ttu-id="f1d17-166">Passare all'articolo successivo per informazioni su come elaborare i dati di streaming con .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="f1d17-166">Advance to the next article to learn how to process streaming data with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f1d17-167">Esercitazione: flusso strutturato con .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="f1d17-167">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
