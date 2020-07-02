---
title: Esercitazione sull'analisi dei sentimenti con .NET per Apache Spark e ML.NET
description: In questa esercitazione si apprenderà come usare ML.NET con .NET per Apache Spark per l'analisi dei sentimenti.
author: mamccrea
ms.author: mamccrea
ms.date: 06/25/2020
ms.topic: tutorial
ms.openlocfilehash: 69deb30419b98536fa309547d94f59bb266e413c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617580"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a><span data-ttu-id="a6233-103">Esercitazione: analisi dei sentimenti con .NET per Apache Spark e ML.NET</span><span class="sxs-lookup"><span data-stu-id="a6233-103">Tutorial: Sentiment analysis with .NET for Apache Spark and ML.NET</span></span>

<span data-ttu-id="a6233-104">Questa esercitazione illustra come eseguire l'analisi dei sentimenti delle revisioni online usando ML.NET e .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a6233-104">This tutorial teaches you how to do sentiment analysis of online reviews using ML.NET and .NET for Apache Spark.</span></span> <span data-ttu-id="a6233-105">[Ml.NET](http://dot.net/ml) è un framework gratuito, multipiattaforma open source di machine learning.</span><span class="sxs-lookup"><span data-stu-id="a6233-105">[ML.NET](http://dot.net/ml) is a free, cross-platform, open-source machine learning framework.</span></span> <span data-ttu-id="a6233-106">È possibile usare ML.NET con .NET per Apache Spark per ridimensionare il training e la stima degli algoritmi di machine learning.</span><span class="sxs-lookup"><span data-stu-id="a6233-106">You can use ML.NET with .NET for Apache Spark to scale the training and prediction of machine learning algorithms.</span></span>

<span data-ttu-id="a6233-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="a6233-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="a6233-108">Creare un modello di analisi dei sentimenti usando il generatore di modelli ML.NET in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a6233-108">Create a sentiment analysis model using ML.NET Model Builder in Visual Studio.</span></span>
> * <span data-ttu-id="a6233-109">Creare un'applicazione .NET per Apache Spark console.</span><span class="sxs-lookup"><span data-stu-id="a6233-109">Create a .NET for Apache Spark console app.</span></span>
> * <span data-ttu-id="a6233-110">Scrivere e implementare una funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a6233-110">Write and implement a user-defined function.</span></span>
> * <span data-ttu-id="a6233-111">Eseguire un'applicazione .NET per Apache Spark console.</span><span class="sxs-lookup"><span data-stu-id="a6233-111">Run a .NET for Apache Spark console app.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="a6233-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a6233-112">Prerequisites</span></span>

* <span data-ttu-id="a6233-113">Se in precedenza non è stata sviluppata un'applicazione .NET per Apache Spark, iniziare con l' [esercitazione Introduzione](get-started.md) per acquisire familiarità con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="a6233-113">If you haven't developed a .NET for Apache Spark application before, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span> <span data-ttu-id="a6233-114">Completare tutti i prerequisiti per l'esercitazione Introduzione prima di continuare con questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="a6233-114">Complete all of the prerequisites for the Getting Started tutorial before you continue with this tutorial.</span></span>

* <span data-ttu-id="a6233-115">Questa esercitazione usa il generatore di modelli ML.NET (anteprima), un'interfaccia visiva disponibile in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a6233-115">This tutorial uses the ML.NET Model Builder (preview), a visual interface available in Visual Studio.</span></span> <span data-ttu-id="a6233-116">Se non si dispone già di Visual Studio, è possibile [scaricare gratuitamente la versione community di Visual Studio](https://visualstudio.microsoft.com/downloads/) .</span><span class="sxs-lookup"><span data-stu-id="a6233-116">If you don't already have Visual Studio, you can [download the Community version of Visual Studio](https://visualstudio.microsoft.com/downloads/) for free.</span></span>

* <span data-ttu-id="a6233-117">[Scaricare e installare](https://marketplace.visualstudio.com/items?itemName=MLNET.07) Generatore di modelli ML.NET (anteprima).</span><span class="sxs-lookup"><span data-stu-id="a6233-117">[Download and install](https://marketplace.visualstudio.com/items?itemName=MLNET.07) ML.NET Model Builder (preview).</span></span>

* <span data-ttu-id="a6233-118">Scaricare i set di impostazioni di [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) e [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp Review.</span><span class="sxs-lookup"><span data-stu-id="a6233-118">Download the [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) and [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp review datasets.</span></span>

## <a name="review-the-data"></a><span data-ttu-id="a6233-119">Esaminare i dati</span><span class="sxs-lookup"><span data-stu-id="a6233-119">Review the data</span></span>

<span data-ttu-id="a6233-120">Il set di dati delle revisioni di Yelp contiene recensioni di Yelp online sui vari servizi.</span><span class="sxs-lookup"><span data-stu-id="a6233-120">The Yelp reviews dataset contains online Yelp reviews about various services.</span></span> <span data-ttu-id="a6233-121">Aprire [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) e osservare la struttura dei dati.</span><span class="sxs-lookup"><span data-stu-id="a6233-121">Open [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) and notice the structure of the data.</span></span> <span data-ttu-id="a6233-122">La prima colonna contiene il testo della revisione e la seconda colonna contiene i punteggi dei sentimenti.</span><span class="sxs-lookup"><span data-stu-id="a6233-122">The first column contains review text, and the second column contains sentiment scores.</span></span> <span data-ttu-id="a6233-123">Se il Punteggio di valutazione è 1, la revisione è positiva e se il punteggio del sentimento è 0, la verifica è negativa.</span><span class="sxs-lookup"><span data-stu-id="a6233-123">If the sentiment score is 1, the review is positive, and if the sentiment score is 0, the review is negative.</span></span>

<span data-ttu-id="a6233-124">La tabella seguente contiene dati di esempio:</span><span class="sxs-lookup"><span data-stu-id="a6233-124">The following table contains sample data:</span></span>

|<span data-ttu-id="a6233-125">ReviewText</span><span class="sxs-lookup"><span data-stu-id="a6233-125">ReviewText</span></span>|<span data-ttu-id="a6233-126">Valutazione</span><span class="sxs-lookup"><span data-stu-id="a6233-126">Sentiment</span></span>|
|-|-|
|<span data-ttu-id="a6233-127">Wow... Questo posto è stato apprezzato.</span><span class="sxs-lookup"><span data-stu-id="a6233-127">Wow... Loved this place.</span></span>|    <span data-ttu-id="a6233-128">1</span><span class="sxs-lookup"><span data-stu-id="a6233-128">1</span></span>|
|<span data-ttu-id="a6233-129">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="a6233-129">Crust is not good.</span></span>|    <span data-ttu-id="a6233-130">0</span><span class="sxs-lookup"><span data-stu-id="a6233-130">0</span></span>|

## <a name="build-your-machine-learning-model"></a><span data-ttu-id="a6233-131">Compilare il modello di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="a6233-131">Build your machine learning model</span></span>

1. <span data-ttu-id="a6233-132">Aprire Visual Studio e creare una nuova app console C# (.NET Core).</span><span class="sxs-lookup"><span data-stu-id="a6233-132">Open Visual Studio and create a new C# Console App (.NET Core).</span></span> <span data-ttu-id="a6233-133">Denominare il progetto *MLSparkModel*.</span><span class="sxs-lookup"><span data-stu-id="a6233-133">Name the project *MLSparkModel*.</span></span>

1. <span data-ttu-id="a6233-134">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *MLSparkModel* .</span><span class="sxs-lookup"><span data-stu-id="a6233-134">In **Solution Explorer**, right-click the *MLSparkModel* project.</span></span> <span data-ttu-id="a6233-135">Quindi selezionare **aggiungi > Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="a6233-135">Then select **Add > Machine Learning**.</span></span>

1. <span data-ttu-id="a6233-136">Dal generatore di modelli ML.NET selezionare il riquadro scenario **analisi del sentiment** .</span><span class="sxs-lookup"><span data-stu-id="a6233-136">From the ML.NET Model Builder, select the **Sentiment Analysis** scenario tile.</span></span>

1. <span data-ttu-id="a6233-137">Nella pagina **Aggiungi dati** caricare il set di dati *yelptrain.csv* .</span><span class="sxs-lookup"><span data-stu-id="a6233-137">On the **Add data** page, upload the *yelptrain.csv* data set.</span></span>

1. <span data-ttu-id="a6233-138">Scegliere *sentimento* dall'elenco **a discesa colonne da stimare** .</span><span class="sxs-lookup"><span data-stu-id="a6233-138">Choose *Sentiment* from the **Columns to Predict** dropdown.</span></span>

1. <span data-ttu-id="a6233-139">Nella pagina **Train** impostare il tempo di training su *60 secondi* e selezionare **Avvia Training**.</span><span class="sxs-lookup"><span data-stu-id="a6233-139">On the **Train** page, set the time to train to *60 seconds* and select **Start training**.</span></span> <span data-ttu-id="a6233-140">Si noti lo stato della formazione in **corso**.</span><span class="sxs-lookup"><span data-stu-id="a6233-140">Notice the status of your training under **Progress**.</span></span>

1. <span data-ttu-id="a6233-141">Una volta completato il training del generatore di modelli, **valutare** i risultati della formazione.</span><span class="sxs-lookup"><span data-stu-id="a6233-141">Once Model Builder is finished training, **Evaluate** the training results.</span></span> <span data-ttu-id="a6233-142">È possibile digitare frasi nella casella di testo seguente **provare a usare il modello** e selezionare **stima** per visualizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="a6233-142">You can type phrases into the text box below **Try your model** and select **Predict** to see the output.</span></span>

1. <span data-ttu-id="a6233-143">Selezionare il **codice** e quindi selezionare **Aggiungi progetti** per aggiungere il modello ml alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="a6233-143">Select **Code** and then select **Add Projects** to add the ML model to the solution.</span></span>

1. <span data-ttu-id="a6233-144">Si noti che per le soluzioni vengono aggiunti due progetti: **MLSparkModelML. ConsoleApp** e **MLSparkModelML. Model**.</span><span class="sxs-lookup"><span data-stu-id="a6233-144">Notice that two projects are added to your solutions: **MLSparkModelML.ConsoleApp** and **MLSparkModelML.Model**.</span></span>

1. <span data-ttu-id="a6233-145">Fare doppio clic sul progetto *MLSpark* C# e notare che è stato aggiunto il seguente riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="a6233-145">Double-click on your *MLSpark* C# project and notice that the following project reference has been added.</span></span>

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a><span data-ttu-id="a6233-146">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="a6233-146">Create a console app</span></span>

<span data-ttu-id="a6233-147">Generatore di modelli crea automaticamente un'app console.</span><span class="sxs-lookup"><span data-stu-id="a6233-147">Model Builder creates a console app for you.</span></span>

1. <span data-ttu-id="a6233-148">Fare clic con il pulsante destro del mouse su **MLSparkModelML. console** in Esplora soluzioni e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a6233-148">Right-click on **MLSparkModelML.Console** in Solution Explorer, and select **Manage NuGet Packages**.</span></span>

1. <span data-ttu-id="a6233-149">Cercare **Microsoft. Spark** e installare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a6233-149">Search for **Microsoft.Spark** and install the package.</span></span> <span data-ttu-id="a6233-150">**Microsoft.ml** viene automaticamente installato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="a6233-150">**Microsoft.ML** is automatically installed for you by Model Builder.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="a6233-151">Creare un SparkSession</span><span class="sxs-lookup"><span data-stu-id="a6233-151">Create a SparkSession</span></span>

1. <span data-ttu-id="a6233-152">Aprire il file *Program.cs* per **MLSparkModelML. ConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="a6233-152">Open the *Program.cs* file for **MLSparkModelML.ConsoleApp**.</span></span> <span data-ttu-id="a6233-153">Questo file è stato generato automaticamente dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="a6233-153">This file was autogenerated by Model Builder.</span></span> <span data-ttu-id="a6233-154">Eliminare le `using` istruzioni, il contenuto del metodo Main () e l' `CreateSingleDataSample` area.</span><span class="sxs-lookup"><span data-stu-id="a6233-154">Delete the `using` statements, the contents of the Main() method, and the `CreateSingleDataSample` region.</span></span>

1. <span data-ttu-id="a6233-155">Aggiungere le istruzioni aggiuntive seguenti `using` all'inizio di *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="a6233-155">Add the following additional `using` statements to the top of the *Program.cs*:</span></span>

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. <span data-ttu-id="a6233-156">Modificare il `DATA_FILEPATH` percorso del *yelptest.csv*.</span><span class="sxs-lookup"><span data-stu-id="a6233-156">Change the `DATA_FILEPATH` to the path of your *yelptest.csv*.</span></span>

1. <span data-ttu-id="a6233-157">Aggiungere il codice seguente al `Main` metodo per creare un nuovo oggetto `SparkSession` .</span><span class="sxs-lookup"><span data-stu-id="a6233-157">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="a6233-158">La sessione Spark è il punto di ingresso per la programmazione di Spark con il set di dati e l'API dataframe.</span><span class="sxs-lookup"><span data-stu-id="a6233-158">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   <span data-ttu-id="a6233-159">La chiamata all'oggetto *Spark* creato in precedenza consente di accedere alle funzionalità di Spark e dataframe in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="a6233-159">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="create-a-dataframe-and-print-to-console"></a><span data-ttu-id="a6233-160">Creare un dataframe e stamparlo nella console</span><span class="sxs-lookup"><span data-stu-id="a6233-160">Create a DataFrame and print to console</span></span>

<span data-ttu-id="a6233-161">Leggere i dati della verifica di Yelp dal file di *yelptest.csv* come `DataFrame` .</span><span class="sxs-lookup"><span data-stu-id="a6233-161">Read in the Yelp review data from the *yelptest.csv* file as a `DataFrame`.</span></span> <span data-ttu-id="a6233-162">Includere `header` le `inferSchema` Opzioni e.</span><span class="sxs-lookup"><span data-stu-id="a6233-162">Include `header` and `inferSchema` options.</span></span> <span data-ttu-id="a6233-163">L' `header` opzione legge la prima riga di *yelptest.csv* come nomi di colonna anziché come dati.</span><span class="sxs-lookup"><span data-stu-id="a6233-163">The `header` option reads the first line of *yelptest.csv* as column names instead of data.</span></span> <span data-ttu-id="a6233-164">L' `inferSchema` opzione deduce i tipi di colonna in base ai dati.</span><span class="sxs-lookup"><span data-stu-id="a6233-164">The `inferSchema` option infers column types based on the data.</span></span>

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a><span data-ttu-id="a6233-165">Registrare una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="a6233-165">Register a user-defined function</span></span>

<span data-ttu-id="a6233-166">È possibile usare UDF, *funzioni definite dall'utente*nelle applicazioni Spark per eseguire calcoli e analisi sui dati.</span><span class="sxs-lookup"><span data-stu-id="a6233-166">You can use UDFs, *user-defined functions*, in Spark applications to do calculations and analysis on your data.</span></span> <span data-ttu-id="a6233-167">In questa esercitazione si userà ML.NET con una funzione definita dall'utente per valutare ogni revisione di Yelp.</span><span class="sxs-lookup"><span data-stu-id="a6233-167">In this tutorial, you use ML.NET with a UDF to evaluate each Yelp review.</span></span>

<span data-ttu-id="a6233-168">Aggiungere il codice seguente al `Main` metodo per registrare una funzione definita dall'utente denominata `MLudf` .</span><span class="sxs-lookup"><span data-stu-id="a6233-168">Add the following code to your `Main` method to register a UDF called `MLudf`.</span></span>

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

<span data-ttu-id="a6233-169">Questa funzione definita dall'utente accetta una stringa di verifica Yelp come input e restituisce true o false rispettivamente per i sentimenti positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="a6233-169">This UDF takes a Yelp review string as input, and outputs true or false for positive or negative sentiments, respectively.</span></span> <span data-ttu-id="a6233-170">Usa il metodo *Predict ()* definito in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a6233-170">It uses the *predict()* method that you define in a later step.</span></span>

### <a name="use-spark-sql-to-call-the-udf"></a><span data-ttu-id="a6233-171">Usare Spark SQL per chiamare la funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="a6233-171">Use Spark SQL to call the UDF</span></span>

<span data-ttu-id="a6233-172">Ora che sono stati letti i dati e sono stati incorporati ML, usare Spark SQL per chiamare la funzione definita dall'utente che eseguirà l'analisi dei sentimenti in ogni riga del dataframe.</span><span class="sxs-lookup"><span data-stu-id="a6233-172">Now that you've read in your data and incorporated ML, use Spark SQL to call the UDF that will run sentiment analysis on each row of your DataFrame.</span></span> <span data-ttu-id="a6233-173">Aggiungere il codice seguente al metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="a6233-173">Add the following code to your `Main` method:</span></span>

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

### <a name="create-predict-method"></a><span data-ttu-id="a6233-174">Crea metodo Predict ()</span><span class="sxs-lookup"><span data-stu-id="a6233-174">Create predict() method</span></span>

<span data-ttu-id="a6233-175">Aggiungere il codice seguente prima del `Main()` metodo.</span><span class="sxs-lookup"><span data-stu-id="a6233-175">Add the following code before your `Main()` method.</span></span> <span data-ttu-id="a6233-176">Questo codice è simile a quello prodotto dal generatore di modelli in *ConsumeModel.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6233-176">This code is similar to what is produced by Model Builder in *ConsumeModel.cs*.</span></span> <span data-ttu-id="a6233-177">Se si trasferisce questo metodo nella console, il caricamento del modello viene caricato ogni volta che si esegue l'app.</span><span class="sxs-lookup"><span data-stu-id="a6233-177">Moving this method to your console loads the model loading each time you run your app.</span></span>

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

## <a name="add-the-model-to-your-console-app"></a><span data-ttu-id="a6233-178">Aggiungere il modello all'app console</span><span class="sxs-lookup"><span data-stu-id="a6233-178">Add the model to your console app</span></span>

<span data-ttu-id="a6233-179">In Esplora soluzioni copiare il file di *MLModel.zip* dal progetto **MLSparkModelML. Model** e incollarlo nel progetto **MLSparkModelML. ConsoleApp** .</span><span class="sxs-lookup"><span data-stu-id="a6233-179">In Solution Explorer, copy the *MLModel.zip* file from the **MLSparkModelML.Model** project and paste it in the **MLSparkModelML.ConsoleApp** project.</span></span> <span data-ttu-id="a6233-180">Un riferimento viene aggiunto automaticamente in *MLSparkModelML. ConsoleApp. csproj*.</span><span class="sxs-lookup"><span data-stu-id="a6233-180">A reference is automatically added in *MLSparkModelML.ConsoleApp.csproj*.</span></span>

## <a name="run-your-code"></a><span data-ttu-id="a6233-181">Eseguire il codice</span><span class="sxs-lookup"><span data-stu-id="a6233-181">Run your code</span></span>

<span data-ttu-id="a6233-182">Usare `spark-submit` per eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="a6233-182">Use `spark-submit` to run your code.</span></span> <span data-ttu-id="a6233-183">Passare alla cartella radice dell'app console usando il prompt dei comandi ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="a6233-183">Navigate to your console app's root folder using the command prompt and run the following commands.</span></span>

<span data-ttu-id="a6233-184">Per prima cosa, pulire e pubblicare l'app.</span><span class="sxs-lookup"><span data-stu-id="a6233-184">First, clean and publish your app.</span></span>

```dotnetcli
dotnet clean
dotnet publish
```

<span data-ttu-id="a6233-185">Passare quindi alla cartella di pubblicazione dell'app console ed eseguire il `spark-submit` comando seguente.</span><span class="sxs-lookup"><span data-stu-id="a6233-185">Then navigate to the console app's publish folder and run the following `spark-submit` command.</span></span> <span data-ttu-id="a6233-186">Ricordarsi di aggiornare il comando con il percorso effettivo del file jar di Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="a6233-186">Remember to update the command with the actual path of your Microsoft Spark jar file.</span></span>

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2.4.x-0.10.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a><span data-ttu-id="a6233-187">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="a6233-187">Get the code</span></span>

<span data-ttu-id="a6233-188">Questa esercitazione è simile al codice dell'esempio [analisi del sentiment con Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) .</span><span class="sxs-lookup"><span data-stu-id="a6233-188">This tutorial is similar to the code from the [Sentiment Analysis with Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6233-189">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a6233-189">Next steps</span></span>

<span data-ttu-id="a6233-190">Passare all'articolo successivo per informazioni su come eseguire lo streaming strutturato con .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a6233-190">Advance to the next article to learn how to do Structured Streaming with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a6233-191">Esercitazione: flusso strutturato con .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a6233-191">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
