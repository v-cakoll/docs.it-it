---
title: Analisi del sentiment con .NET per Apache Spark e ML.NET tutorial
description: In questa esercitazione si apprenderà come usare ML.NET con .NET per Apache Spark per l'analisi del sentiment.
author: mamccrea
ms.author: mamccrea
ms.date: 03/25/2019
ms.topic: tutorial
ms.openlocfilehash: cdd1214c26a5d5a4b159df3a396ec6f36b9fc0dd
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391258"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a><span data-ttu-id="0bd4c-103">Esercitazione: Analisi del sentiment con .NET per Apache Spark e ML.NET</span><span class="sxs-lookup"><span data-stu-id="0bd4c-103">Tutorial: Sentiment analysis with .NET for Apache Spark and ML.NET</span></span>

<span data-ttu-id="0bd4c-104">Questo tutorial ti insegna come eseguire l'analisi del sentiment delle recensioni online usando ML.NET e .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-104">This tutorial teaches you how to do sentiment analysis of online reviews using ML.NET and .NET for Apache Spark.</span></span> <span data-ttu-id="0bd4c-105">[ML.NET](http://dot.net/ml) è un framework di apprendimento automatico gratuito, multipiattaforma e open source.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-105">[ML.NET](http://dot.net/ml) is a free, cross-platform, open-source machine learning framework.</span></span> <span data-ttu-id="0bd4c-106">È possibile usare ML.NET con .NET per Apache Spark per ridimensionare il training e la stima degli algoritmi di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-106">You can use ML.NET with .NET for Apache Spark to scale the training and prediction of machine learning algorithms.</span></span>

<span data-ttu-id="0bd4c-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="0bd4c-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="0bd4c-108">Creare un modello di analisi del sentiment usando ML.NET Model Builder in Visual Studio.Create a sentiment analysis model using ML.NET Model Builder in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-108">Create a sentiment analysis model using ML.NET Model Builder in Visual Studio.</span></span>
> * <span data-ttu-id="0bd4c-109">Creare un'app console .NET per Apache Spark.Create a .NET for Apache Spark console app.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-109">Create a .NET for Apache Spark console app.</span></span>
> * <span data-ttu-id="0bd4c-110">Scrivere e implementare una funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-110">Write and implement a user-defined function.</span></span>
> * <span data-ttu-id="0bd4c-111">Eseguire un'app console .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-111">Run a .NET for Apache Spark console app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0bd4c-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0bd4c-112">Prerequisites</span></span>

* <span data-ttu-id="0bd4c-113">Se non è stata sviluppata un'applicazione .NET per Apache Spark in precedenza, iniziare con [l'esercitazione introduttiva](get-started.md) per acquisire familiarità con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-113">If you haven't developed a .NET for Apache Spark application before, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span> <span data-ttu-id="0bd4c-114">Completare tutti i prerequisiti per l'esercitazione introduttiva prima di continuare con questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-114">Complete all of the prerequisites for the Getting Started tutorial before you continue with this tutorial.</span></span>

* <span data-ttu-id="0bd4c-115">Questa esercitazione usa il ML.NET Model Builder (anteprima), un'interfaccia visiva disponibile in Visual Studio.This tutorial uses the ML.NET Model Builder (preview), a visual interface available in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-115">This tutorial uses the ML.NET Model Builder (preview), a visual interface available in Visual Studio.</span></span> <span data-ttu-id="0bd4c-116">Se non si dispone già di Visual Studio, è possibile [scaricare gratuitamente la versione Community di Visual Studio.](https://visualstudio.microsoft.com/downloads/)</span><span class="sxs-lookup"><span data-stu-id="0bd4c-116">If you don't already have Visual Studio, you can [download the Community version of Visual Studio](https://visualstudio.microsoft.com/downloads/) for free.</span></span>

* <span data-ttu-id="0bd4c-117">[Scarica e installa](https://marketplace.visualstudio.com/items?itemName=MLNET.07) ML.NET Model Builder (anteprima).</span><span class="sxs-lookup"><span data-stu-id="0bd4c-117">[Download and install](https://marketplace.visualstudio.com/items?itemName=MLNET.07) ML.NET Model Builder (preview).</span></span>

* <span data-ttu-id="0bd4c-118">Scaricare i set di dati [Yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) e [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-118">Download the [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) and [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp review datasets.</span></span>

## <a name="review-the-data"></a><span data-ttu-id="0bd4c-119">Esaminare i dati</span><span class="sxs-lookup"><span data-stu-id="0bd4c-119">Review the data</span></span>

<span data-ttu-id="0bd4c-120">Il set di dati Yelp reviews contiene recensioni Yelp online su vari servizi.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-120">The Yelp reviews dataset contains online Yelp reviews about various services.</span></span> <span data-ttu-id="0bd4c-121">Aprire [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) e notare la struttura dei dati.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-121">Open [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) and notice the structure of the data.</span></span> <span data-ttu-id="0bd4c-122">La prima colonna contiene il testo della recensione e la seconda colonna contiene i punteggi di valutazione.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-122">The first column contains review text, and the second column contains sentiment scores.</span></span> <span data-ttu-id="0bd4c-123">Se il punteggio del sentiment è 1, la recensione è positiva e se il punteggio del sentiment è 0, la recensione è negativa.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-123">If the sentiment score is 1, the review is positive, and if the sentiment score is 0, the review is negative.</span></span>

<span data-ttu-id="0bd4c-124">La tabella seguente contiene dati di esempio:The following table contains sample data:</span><span class="sxs-lookup"><span data-stu-id="0bd4c-124">The following table contains sample data:</span></span>

|<span data-ttu-id="0bd4c-125">Testorevisione</span><span class="sxs-lookup"><span data-stu-id="0bd4c-125">ReviewText</span></span>|<span data-ttu-id="0bd4c-126">Valutazione</span><span class="sxs-lookup"><span data-stu-id="0bd4c-126">Sentiment</span></span>|
|-|-|
|<span data-ttu-id="0bd4c-127">Wow... Mi è piaciuto molto questo posto.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-127">Wow... Loved this place.</span></span>|    <span data-ttu-id="0bd4c-128">1</span><span class="sxs-lookup"><span data-stu-id="0bd4c-128">1</span></span>|
|<span data-ttu-id="0bd4c-129">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-129">Crust is not good.</span></span>|    <span data-ttu-id="0bd4c-130">0</span><span class="sxs-lookup"><span data-stu-id="0bd4c-130">0</span></span>|

## <a name="build-your-machine-learning-model"></a><span data-ttu-id="0bd4c-131">Crea il tuo modello di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="0bd4c-131">Build your machine learning model</span></span>

1. <span data-ttu-id="0bd4c-132">Aprire Visual Studio e creare una nuova applicazione console di C .</span><span class="sxs-lookup"><span data-stu-id="0bd4c-132">Open Visual Studio and create a new C# Console App (.NET Core).</span></span> <span data-ttu-id="0bd4c-133">Denominare il progetto *MLSparkModel*.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-133">Name the project *MLSparkModel*.</span></span>

1. <span data-ttu-id="0bd4c-134">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *MLSparkModel.*</span><span class="sxs-lookup"><span data-stu-id="0bd4c-134">In **Solution Explorer**, right-click the *MLSparkModel* project.</span></span> <span data-ttu-id="0bd4c-135">Selezionare quindi **Aggiungi > Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-135">Then select **Add > Machine Learning**.</span></span>

1. <span data-ttu-id="0bd4c-136">Nella ML.NET Model Builder selezionare il riquadro scenario **Analisi valutazione.**</span><span class="sxs-lookup"><span data-stu-id="0bd4c-136">From the ML.NET Model Builder, select the **Sentiment Analysis** scenario tile.</span></span>

1. <span data-ttu-id="0bd4c-137">Nella pagina **Aggiungi dati** caricare il set di dati *yelptrain.csv.*</span><span class="sxs-lookup"><span data-stu-id="0bd4c-137">On the **Add data** page, upload the *yelptrain.csv* data set.</span></span>

1. <span data-ttu-id="0bd4c-138">Scegli *Valutazione* dall'elenco a discesa **Colonne da pronostilare.**</span><span class="sxs-lookup"><span data-stu-id="0bd4c-138">Choose *Sentiment* from the **Columns to Predict** dropdown.</span></span>

1. <span data-ttu-id="0bd4c-139">Nella pagina **Treno** impostare l'ora di training su *60 secondi* e selezionare **Avvia formazione**.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-139">On the **Train** page, set the time to train to *60 seconds* and select **Start training**.</span></span> <span data-ttu-id="0bd4c-140">Si noti lo stato della formazione in **Progress**.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-140">Notice the status of your training under **Progress**.</span></span>

1. <span data-ttu-id="0bd4c-141">Al termine del training di Model Builder, **valutare** i risultati del training.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-141">Once Model Builder is finished training, **Evaluate** the training results.</span></span> <span data-ttu-id="0bd4c-142">È possibile digitare frasi nella casella di testo sotto **Provare il modello** e selezionare **Previsione** per visualizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-142">You can type phrases into the text box below **Try your model** and select **Predict** to see the output.</span></span>

1. <span data-ttu-id="0bd4c-143">Selezionare **Codice** e quindi **Aggiungi progetti** per aggiungere il modello di Configurazione istantanea alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-143">Select **Code** and then select **Add Projects** to add the ML model to the solution.</span></span>

1. <span data-ttu-id="0bd4c-144">Si noti che vengono aggiunti due progetti alle soluzioni: **MLSparkModelML.ConsoleApp** e **MLSparkModelML.Model**.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-144">Notice that two projects are added to your solutions: **MLSparkModelML.ConsoleApp** and **MLSparkModelML.Model**.</span></span>

1. <span data-ttu-id="0bd4c-145">Fare doppio clic sul progetto *MLSpark* in C, quindi notare che è stato aggiunto il riferimento al progetto seguente.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-145">Double-click on your *MLSpark* C# project and notice that the following project reference has been added.</span></span>

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a><span data-ttu-id="0bd4c-146">Creare un'app console</span><span class="sxs-lookup"><span data-stu-id="0bd4c-146">Create a console app</span></span>

<span data-ttu-id="0bd4c-147">Model Builder crea automaticamente un'app console.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-147">Model Builder creates a console app for you.</span></span>

1. <span data-ttu-id="0bd4c-148">Fare clic con il pulsante destro del mouse su **MLSparkModelML.Console** in Esplora soluzioni e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-148">Right-click on **MLSparkModelML.Console** in Solution Explorer, and select **Manage NuGet Packages**.</span></span>

1. <span data-ttu-id="0bd4c-149">Cercare **Microsoft.Spark** e installare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-149">Search for **Microsoft.Spark** and install the package.</span></span> <span data-ttu-id="0bd4c-150">**Microsoft.ML** viene installato automaticamente da Model Builder.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-150">**Microsoft.ML** is automatically installed for you by Model Builder.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="0bd4c-151">Creare una SparkSessionCreate a SparkSession</span><span class="sxs-lookup"><span data-stu-id="0bd4c-151">Create a SparkSession</span></span>

1. <span data-ttu-id="0bd4c-152">Aprire il file *di Program.cs* per **MLSparkModelML.ConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-152">Open the *Program.cs* file for **MLSparkModelML.ConsoleApp**.</span></span> <span data-ttu-id="0bd4c-153">Questo file è stato generato automaticamente da Model Builder.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-153">This file was autogenerated by Model Builder.</span></span> <span data-ttu-id="0bd4c-154">Eliminare `using` le istruzioni, il contenuto del metodo `CreateSingleDataSample` Main() e l'area.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-154">Delete the `using` statements, the contents of the Main() method, and the `CreateSingleDataSample` region.</span></span>

1. <span data-ttu-id="0bd4c-155">Aggiungere le `using` seguenti istruzioni aggiuntive all'inizio del *Program.cs:*</span><span class="sxs-lookup"><span data-stu-id="0bd4c-155">Add the following additional `using` statements to the top of the *Program.cs*:</span></span>

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. <span data-ttu-id="0bd4c-156">Modificare `DATA_FILEPATH` il percorso del *file yelptest.csv*.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-156">Change the `DATA_FILEPATH` to the path of your *yelptest.csv*.</span></span>

1. <span data-ttu-id="0bd4c-157">Aggiungere il codice `Main` seguente al metodo `SparkSession`per creare un nuovo oggetto .</span><span class="sxs-lookup"><span data-stu-id="0bd4c-157">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="0bd4c-158">La sessione Spark è il punto di ingresso alla programmazione Spark con il Dataset e l'API DataFrame.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-158">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   <span data-ttu-id="0bd4c-159">La chiamata all'oggetto *spark* creato in precedenza consente di accedere alle funzionalità Spark e DataFrame in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-159">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="create-a-dataframe-and-print-to-console"></a><span data-ttu-id="0bd4c-160">Creare un frame di dati e stamparlo su consoleCreate a DataFrame and print to console</span><span class="sxs-lookup"><span data-stu-id="0bd4c-160">Create a DataFrame and print to console</span></span>

<span data-ttu-id="0bd4c-161">Leggere i dati di revisione di Yelp dal file `DataFrame` *yelptest.csv* come file .</span><span class="sxs-lookup"><span data-stu-id="0bd4c-161">Read in the Yelp review data from the *yelptest.csv* file as a `DataFrame`.</span></span> <span data-ttu-id="0bd4c-162">Includi `header` `inferSchema` e opzioni.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-162">Include `header` and `inferSchema` options.</span></span> <span data-ttu-id="0bd4c-163">L'opzione `header` legge la prima riga di *yelptest.csv* come nomi di colonna anziché come dati.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-163">The `header` option reads the first line of *yelptest.csv* as column names instead of data.</span></span> <span data-ttu-id="0bd4c-164">L'opzione `inferSchema` deduce i tipi di colonna in base ai dati.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-164">The `inferSchema` option infers column types based on the data.</span></span>

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a><span data-ttu-id="0bd4c-165">Registrare una funzione definita dall'utenteRegister a user-defined function</span><span class="sxs-lookup"><span data-stu-id="0bd4c-165">Register a user-defined function</span></span>

<span data-ttu-id="0bd4c-166">È possibile utilizzare funzioni definite dall'utente, *funzioni definite dall'utente,* nelle applicazioni Spark per eseguire calcoli e analisi sui dati.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-166">You can use UDFs, *user-defined functions*, in Spark applications to do calculations and analysis on your data.</span></span> <span data-ttu-id="0bd4c-167">In questa esercitazione si userà ML.NET con una funzione definita dall'utente per valutare ogni revisione Yelp.In this tutorial, you use a share with a UDF to evaluate each Yelp review.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-167">In this tutorial, you use ML.NET with a UDF to evaluate each Yelp review.</span></span>

<span data-ttu-id="0bd4c-168">Aggiungere il codice `Main` seguente al metodo per `MLudf`registrare una funzione definita dall'utente denominata .</span><span class="sxs-lookup"><span data-stu-id="0bd4c-168">Add the following code to your `Main` method to register a UDF called `MLudf`.</span></span>

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

<span data-ttu-id="0bd4c-169">Questa funzione definita dall'utente accetta una stringa di revisione Yelp come input e restituisce true o false rispettivamente per i sentimenti positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-169">This UDF takes a Yelp review string as input, and outputs true or false for positive or negative sentiments, respectively.</span></span> <span data-ttu-id="0bd4c-170">Utilizza il metodo *predict()* definito in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-170">It uses the *predict()* method that you define in a later step.</span></span>

### <a name="use-spark-sql-to-call-the-udf"></a><span data-ttu-id="0bd4c-171">Usare Spark SQL per chiamare la funzione definita dall'utenteUse Spark SQL to call the UDF</span><span class="sxs-lookup"><span data-stu-id="0bd4c-171">Use Spark SQL to call the UDF</span></span>

<span data-ttu-id="0bd4c-172">Ora che hai letto i dati e incorporato ML, utilizzare Spark SQL per chiamare la funzione definita dall'utente che eseguirà l'analisi del sentiment su ogni riga del frame di dati.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-172">Now that you've read in your data and incorporated ML, use Spark SQL to call the UDF that will run sentiment analysis on each row of your DataFrame.</span></span> <span data-ttu-id="0bd4c-173">Aggiungere il codice seguente al metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="0bd4c-173">Add the following code to your `Main` method:</span></span>

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a><span data-ttu-id="0bd4c-174">Crea metodo predict()</span><span class="sxs-lookup"><span data-stu-id="0bd4c-174">Create predict() method</span></span>

<span data-ttu-id="0bd4c-175">Aggiungere il codice `Main()` seguente prima del metodo.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-175">Add the following code before your `Main()` method.</span></span> <span data-ttu-id="0bd4c-176">Questo codice è simile a quello prodotto da Model Builder in *ConsumeModel.cs*.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-176">This code is similar to what is produced by Model Builder in *ConsumeModel.cs*.</span></span> <span data-ttu-id="0bd4c-177">Lo spostamento di questo metodo nella console carica il caricamento del modello ogni volta che si esegue l'app.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-177">Moving this method to your console loads the model loading each time you run your app.</span></span>

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a><span data-ttu-id="0bd4c-178">Aggiungere il modello all'app console</span><span class="sxs-lookup"><span data-stu-id="0bd4c-178">Add the model to your console app</span></span>

<span data-ttu-id="0bd4c-179">In Esplora soluzioni copiare il file *MLModel.zip* dal progetto **MLSparkModelML.Model** e incollarlo nel progetto **MLSparkModelML.ConsoleApp.**</span><span class="sxs-lookup"><span data-stu-id="0bd4c-179">In Solution Explorer, copy the *MLModel.zip* file from the **MLSparkModelML.Model** project and paste it in the **MLSparkModelML.ConsoleApp** project.</span></span> <span data-ttu-id="0bd4c-180">Un riferimento viene aggiunto automaticamente in *MLSparkModelML.ConsoleApp.csproj*.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-180">A reference is automatically added in *MLSparkModelML.ConsoleApp.csproj*.</span></span>

## <a name="run-your-code"></a><span data-ttu-id="0bd4c-181">Eseguire il codiceRun your code</span><span class="sxs-lookup"><span data-stu-id="0bd4c-181">Run your code</span></span>

<span data-ttu-id="0bd4c-182">Utilizzare `spark-submit` per eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-182">Use `spark-submit` to run your code.</span></span> <span data-ttu-id="0bd4c-183">Passare alla cartella radice dell'app console usando il prompt dei comandi ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-183">Navigate to your console app's root folder using the command prompt and run the following commands.</span></span>

<span data-ttu-id="0bd4c-184">Innanzitutto, pulisci e pubblica la tua app.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-184">First, clean and publish your app.</span></span>

```dotnetcli
dotnet clean
dotnet publish
```

<span data-ttu-id="0bd4c-185">Passare quindi alla cartella di pubblicazione dell'app console ed eseguire il comando seguente. `spark-submit`</span><span class="sxs-lookup"><span data-stu-id="0bd4c-185">Then navigate to the console app's publish folder and run the following `spark-submit` command.</span></span> <span data-ttu-id="0bd4c-186">Ricordarsi di aggiornare il comando con il percorso effettivo del file jar di Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-186">Remember to update the command with the actual path of your Microsoft Spark jar file.</span></span>

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2.4.x-0.10.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a><span data-ttu-id="0bd4c-187">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="0bd4c-187">Get the code</span></span>

<span data-ttu-id="0bd4c-188">Questa esercitazione è simile al codice dell'esempio [di analisi del sentiment con Big Data.This](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) tutorial is similar to the code from the Sentiment Analysis with Big Data example.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-188">This tutorial is similar to the code from the [Sentiment Analysis with Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0bd4c-189">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0bd4c-189">Next steps</span></span>

<span data-ttu-id="0bd4c-190">Passare all'articolo successivo per informazioni su come eseguire lo streaming strutturato con .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-190">Advance to the next article to learn how to do Structured Streaming with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0bd4c-191">Esercitazione: Streaming strutturato con .NET per Apache SparkTutorial: Structured Streaming with .NET for Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bd4c-191">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
