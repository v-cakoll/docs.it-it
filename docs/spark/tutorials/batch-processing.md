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
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a><span data-ttu-id="9f7dd-103">Esercitazione: Eseguire l'elaborazione batch con .NET per Apache SparkTutorial: Do batch processing with .NET for Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9f7dd-103">Tutorial: Do batch processing with .NET for Apache Spark</span></span>

<span data-ttu-id="9f7dd-104">In this tutorial, you learn how to do batch processing using .NET for Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-104">In this tutorial, you learn how to do batch processing using .NET for Apache Spark.</span></span> <span data-ttu-id="9f7dd-105">L'elaborazione batch è la trasformazione dei dati inattivi, il che significa che i dati di origine sono già stati caricati nell'archiviazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-105">Batch processing is the transformation of data at rest, meaning that the source data has already been loaded into data storage.</span></span>

<span data-ttu-id="9f7dd-106">L'elaborazione batch viene in genere eseguita su set di dati flat di grandi dimensioni che devono essere preparati per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-106">Batch processing is generally performed over large, flat datasets that need to be prepared for further analysis.</span></span> <span data-ttu-id="9f7dd-107">L'elaborazione dei log e il data warehousing sono scenari di elaborazione batch comuni.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-107">Log processing and data warehousing are common batch processing scenarios.</span></span> <span data-ttu-id="9f7dd-108">In questo scenario, si analizzano le informazioni sui progetti GitHub, ad esempio il numero di progetti diversi sono stati sottoposti a perforato o la quantità di recente l'aggiornamento dei progetti.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-108">In this scenario, you analyze information about GitHub projects, such as the number of time different projects have been forked or how recently projects have been updated.</span></span>

<span data-ttu-id="9f7dd-109">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="9f7dd-109">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="9f7dd-110">Creare ed eseguire un'applicazione .NET per Apache SparkCreate and run a .NET for Apache Spark application</span><span class="sxs-lookup"><span data-stu-id="9f7dd-110">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="9f7dd-111">Leggere i dati in un dataframe e prepararlo per l'analisiRead data into a DataFrame and prepare it for analysis</span><span class="sxs-lookup"><span data-stu-id="9f7dd-111">Read data into a DataFrame and prepare it for analysis</span></span>
> * <span data-ttu-id="9f7dd-112">Elaborare i dati utilizzando Spark SQLProcess the data using Spark SQL</span><span class="sxs-lookup"><span data-stu-id="9f7dd-112">Process the data using Spark SQL</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9f7dd-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="9f7dd-113">Prerequisites</span></span>

<span data-ttu-id="9f7dd-114">Se è la prima volta che si usa .NET per Apache Spark, vedere l'esercitazione [Introduzione a .NET per Apache Spark](../tutorials/get-started.md) per informazioni su come preparare l'ambiente ed eseguire la prima applicazione .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-114">If this is your first time using .NET for Apache Spark, check out the [Get started with .NET for Apache Spark](../tutorials/get-started.md) tutorial to learn how to prepare your environment and run your first .NET for Apache Spark application.</span></span>

## <a name="download-the-sample-data"></a><span data-ttu-id="9f7dd-115">Scaricare i dati di esempio</span><span class="sxs-lookup"><span data-stu-id="9f7dd-115">Download the sample data</span></span>

<span data-ttu-id="9f7dd-116">[GHTorrent](http://ghtorrent.org/) monitora tutti gli eventi GitHub pubblici, ad esempio informazioni su progetti, commit e osservatori, e archivia gli eventi e la relativa struttura nei database.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-116">[GHTorrent](http://ghtorrent.org/) monitors all public GitHub events, such as info about projects, commits, and watchers, and stores the events and their structure in databases.</span></span> <span data-ttu-id="9f7dd-117">I dati raccolti in diversi periodi di tempo sono disponibili come archivi scaricabili.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-117">Data collected over different time periods is available as downloadable archives.</span></span> <span data-ttu-id="9f7dd-118">Poiché i file di dump sono molto grandi, questa guida utilizza una [versione troncata del file dump](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) che può essere scaricato da GitHub.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-118">Because the dump files are very large, this guide uses a [truncated version of the dump file](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) that can be downloaded from GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="9f7dd-119">Il set di dati GHTorrent è distribuito nell'ambito di uno schema di doppia licenza ([Creative Commons )](https://wiki.creativecommons.org/wiki/CCPlus).</span><span class="sxs-lookup"><span data-stu-id="9f7dd-119">The GHTorrent dataset is distributed under a dual licensing scheme ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)).</span></span> <span data-ttu-id="9f7dd-120">Per usi non commerciali (compresi, ma non limitati a, scopi educativi, di ricerca o personali), il set di dati è distribuito con la [licenza CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).</span><span class="sxs-lookup"><span data-stu-id="9f7dd-120">For non-commercial uses (including, but not limited to, educational, research or personal uses), the dataset is distributed under the [CC-BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="9f7dd-121">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="9f7dd-121">Create a console application</span></span>

1. <span data-ttu-id="9f7dd-122">Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="9f7dd-122">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   <span data-ttu-id="9f7dd-123">Il `dotnet` comando `new` crea automaticamente `console` un'applicazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-123">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="9f7dd-124">Il `-o` parametro crea una directory denominata *mySparkBatchApp* in cui l'app è archiviata e la popola con i file necessari.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-124">The `-o` parameter creates a directory named *mySparkBatchApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="9f7dd-125">Il `cd mySparkBatchApp` comando modifica la directory in base alla directory dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-125">The `cd mySparkBatchApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="9f7dd-126">Per usare .NET per Apache Spark in un'app, installa il pacchetto Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-126">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="9f7dd-127">Nella console, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="9f7dd-127">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a><span data-ttu-id="9f7dd-128">Creare una SparkSessionCreate a SparkSession</span><span class="sxs-lookup"><span data-stu-id="9f7dd-128">Create a SparkSession</span></span>

1. <span data-ttu-id="9f7dd-129">Aggiungere le `using` seguenti istruzioni aggiuntive all'inizio del file *Program.cs* in *mySparkBatchApp*.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-129">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkBatchApp*.</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="9f7dd-130">Aggiungere il codice seguente allo spazio dei nomi del progetto.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-130">Add the following code to your project namespace.</span></span> <span data-ttu-id="9f7dd-131">*s_referenceData* viene utilizzata in un secondo momento nel programma per filtrare in base alla data.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-131">*s_referenceData* is used later in the program to filter based on date.</span></span>

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. <span data-ttu-id="9f7dd-132">Aggiungere il codice seguente all'interno del metodo Main per stabilire una nuova SparkSession.Add the following code inside your Main method to establish a new SparkSession.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-132">Add the following code inside your Main method to establish a new SparkSession.</span></span> <span data-ttu-id="9f7dd-133">SparkSession è il punto di ingresso alla programmazione di Spark con l'API Dataset e DataFrame.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-133">The SparkSession is the entry point to programming Spark with the Dataset and DataFrame API.</span></span> <span data-ttu-id="9f7dd-134">Chiamando l'oggetto, `spark` è possibile accedere alle funzionalità Spark e DataFrame in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-134">By calling the `spark` object, you can access Spark and DataFrame functionality throughout your program.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a><span data-ttu-id="9f7dd-135">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="9f7dd-135">Prepare the data</span></span>

1. <span data-ttu-id="9f7dd-136">Leggere il file `DataFrame`di input in un oggetto , ovvero una raccolta distribuita di dati organizzati in colonne denominate.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-136">Read the input file into a `DataFrame`, which is a distributed collection of data organized into named columns.</span></span> <span data-ttu-id="9f7dd-137">È possibile impostare le <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>colonne per i dati tramite .</span><span class="sxs-lookup"><span data-stu-id="9f7dd-137">You can set the columns for your data through <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>.</span></span> <span data-ttu-id="9f7dd-138">Utilizzare <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> il metodo per visualizzare i dati nel frame di dati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-138">Use the <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> method to display the data in your DataFrame.</span></span> <span data-ttu-id="9f7dd-139">Assicurarsi di aggiornare il percorso del file CSV al percorso dei dati GitHub scaricati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-139">Be sure to update the CSV file path to the location of the GitHub data you downloaded.</span></span>

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

1. <span data-ttu-id="9f7dd-140">Utilizzare <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> il metodo per eliminare le righe con <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> NA (null) valori e il metodo per rimuovere determinate colonne dai dati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-140">Use the <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> method to drop rows with NA (null) values, and the <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> method to remove certain columns from your data.</span></span> <span data-ttu-id="9f7dd-141">In questo modo si evitano errori se si tenta di analizzare dati null o colonne non rilevanti per l'analisi finale.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-141">This helps prevent errors if you try to analyze null data or columns that are not relevant to your final analysis.</span></span>

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a><span data-ttu-id="9f7dd-142">Analizzare i dati</span><span class="sxs-lookup"><span data-stu-id="9f7dd-142">Analyze the data</span></span>

<span data-ttu-id="9f7dd-143">Spark SQL consente di effettuare chiamate SQL sui dati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-143">Spark SQL allows you to make SQL calls on your data.</span></span> <span data-ttu-id="9f7dd-144">È comune combinare le funzioni definite dall'utente e Spark SQL per applicare una funzione definita dall'utente a tutte le righe del frame di dati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-144">It's common to combine user-defined functions and Spark SQL to apply a user-defined function to all rows of your DataFrame.</span></span>

<span data-ttu-id="9f7dd-145">È possibile `spark.Sql` chiamare in modo specifico per simulare le chiamate SQL standard visualizzate in altri tipi di app.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-145">You can specifically call `spark.Sql` to mimic standard SQL calls seen in other types of apps.</span></span> <span data-ttu-id="9f7dd-146">È inoltre possibile <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> chiamare <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> metodi come e per combinare, filtrare ed eseguire calcoli sui dati in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-146">You can also call methods like <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> and <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> to specifically combine, filter, and perform calculations on your data.</span></span>

<span data-ttu-id="9f7dd-147">L'obiettivo di questa applicazione è quello di ottenere alcune informazioni sui dati di progetti GitHub.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-147">The goal of this app is to gain some insights about the GitHub projects data.</span></span> <span data-ttu-id="9f7dd-148">Aggiungere i frammenti di codice seguenti al programma per analizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-148">Add the following code snippets to your program to analyze the data.</span></span>

1. <span data-ttu-id="9f7dd-149">Aggiungi il seguente blocco di codice trova il numero di volte in cui ogni lingua è stata sottoposta a un isk.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-149">Add the following block of code finds the number of times each language has been forked.</span></span> <span data-ttu-id="9f7dd-150">In primo luogo, i dati sono raggruppati per lingua.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-150">First, the data is grouped by language.</span></span> <span data-ttu-id="9f7dd-151">Quindi, viene preso il numero medio di forcelle da ogni lingua.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-151">Then, the average number of forks from each language is taken.</span></span>

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. <span data-ttu-id="9f7dd-152">Aggiungere il seguente blocco di codice per ordinare il numero medio di forcelle in ordine decrescente per vedere quali lingue sono le più forate.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-152">Add the following block of code to order the average number of forks in descending order to see which languages are the most forked.</span></span> <span data-ttu-id="9f7dd-153">Cioè, il maggior numero di forcelle apparirà per primo.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-153">That is, the largest number of forks will appear first.</span></span>

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. <span data-ttu-id="9f7dd-154">Il blocco di codice successivo mostra quanto recentemente sono stati aggiornati i progetti.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-154">The next block of code shows you how recently projects have been updated.</span></span> <span data-ttu-id="9f7dd-155">Si registra una nuova funzione definita dall'utente denominata *MyUDF* e confrontarla con una data, *s_referenceDate*, dichiarata all'inizio dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-155">You register a new user-defined function called *MyUDF* and compare it with a date, *s_referenceDate*, which was declared at the beginning of the tutorial.</span></span> <span data-ttu-id="9f7dd-156">La data per ogni progetto viene confrontata con la data di riferimento.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-156">The date for each project is compared against the reference date.</span></span> <span data-ttu-id="9f7dd-157">Quindi, Spark SQL viene utilizzato per chiamare la funzione definita dall'utente su ogni riga dei dati per analizzare ogni progetto nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-157">Then, Spark SQL is used to call the UDF on each row of the data to analyze each project in the data set.</span></span>

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

1. <span data-ttu-id="9f7dd-158">Chiamata `spark.Stop()` per terminare SparkSession.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-158">Call `spark.Stop()` to end the SparkSession.</span></span>

## <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="9f7dd-159">Usare l'invio di spark per eseguire l'appUse spark-submit to run your app</span><span class="sxs-lookup"><span data-stu-id="9f7dd-159">Use spark-submit to run your app</span></span>

1. <span data-ttu-id="9f7dd-160">Usare il comando seguente per compilare l'app .NET:</span><span class="sxs-lookup"><span data-stu-id="9f7dd-160">Use the following command to build your .NET app:</span></span>

   ```dotnetcli
   dotnet build
   ```

1. <span data-ttu-id="9f7dd-161">Esegui l'app con `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-161">Run your app with `spark-submit`.</span></span> <span data-ttu-id="9f7dd-162">Assicurarsi di aggiornare il comando seguente con i percorsi effettivi del file jar di Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-162">Be sure to update the following command with the actual paths to your Microsoft Spark jar file.</span></span>

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a><span data-ttu-id="9f7dd-163">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="9f7dd-163">Get the code</span></span>

<span data-ttu-id="9f7dd-164">È possibile visualizzare la soluzione completa su GitHub.You can see the [full solution](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) on GitHub.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-164">You can see the [full solution](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) on GitHub.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f7dd-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9f7dd-165">Next steps</span></span>

<span data-ttu-id="9f7dd-166">Passare all'articolo successivo per informazioni su come elaborare i dati di streaming con .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-166">Advance to the next article to learn how to process streaming data with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="9f7dd-167">Esercitazione: Streaming strutturato con .NET per Apache SparkTutorial: Structured Streaming with .NET for Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9f7dd-167">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
