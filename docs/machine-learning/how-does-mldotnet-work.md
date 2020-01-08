---
title: Che cos'è ML.NET e come funziona?
description: ML.NET offre la possibilità di aggiungere funzionalità di Machine Learning alle applicazioni .NET, in scenari online o offline. Con questa funzionalità è possibile eseguire stime automatiche usando i dati disponibili per l'applicazione senza che sia necessario connettersi a una rete per usare ML.NET. Questo articolo illustra le nozioni fondamentali dell'apprendimento automatico in ML.NET.
ms.date: 11/5/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 7d15c49ade4cd32389f7c86440b3a66aec8e4ea8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345192"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="38eea-105">Che cos'è ML.NET e come funziona?</span><span class="sxs-lookup"><span data-stu-id="38eea-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="38eea-106">ML.NET offre la possibilità di aggiungere funzionalità di Machine Learning alle applicazioni .NET, in scenari online o offline.</span><span class="sxs-lookup"><span data-stu-id="38eea-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="38eea-107">Con questa funzionalità è possibile eseguire stime automatiche usando i dati disponibili per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38eea-107">With this capability, you can make automatic predictions using the data available to your application.</span></span>

<span data-ttu-id="38eea-108">Central per ML.NET è un **modello**di machine learning.</span><span class="sxs-lookup"><span data-stu-id="38eea-108">Central to ML.NET is a machine learning **model**.</span></span> <span data-ttu-id="38eea-109">Il modello specifica i passaggi necessari per trasformare i dati di input in una stima.</span><span class="sxs-lookup"><span data-stu-id="38eea-109">The model specifies the steps needed to transform your input data into a prediction.</span></span> <span data-ttu-id="38eea-110">Con ML.NET è possibile eseguire il training di un modello personalizzato specificando un algoritmo oppure è possibile importare modelli TensorFlow e ONNX con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="38eea-110">With ML.NET, you can train a custom model by specifying an algorithm, or you can import pre-trained TensorFlow and ONNX models.</span></span>

<span data-ttu-id="38eea-111">Quando si dispone di un modello, è possibile aggiungerlo all'applicazione per eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="38eea-111">Once you have a model, you can add it to your application to make the predictions.</span></span>

<span data-ttu-id="38eea-112">ML.NET viene eseguito in Windows, Linux e macOS con .NET Core o Windows con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38eea-112">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="38eea-113">64 bit è supportato in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="38eea-113">64 bit is supported on all platforms.</span></span> <span data-ttu-id="38eea-114">32 bit è supportato in Windows, ad eccezione delle funzionalità correlate a TensorFlow, LightGBM e ONNX.</span><span class="sxs-lookup"><span data-stu-id="38eea-114">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX-related functionality.</span></span>

<span data-ttu-id="38eea-115">Esempi del tipo di stime che è possibile apportare con ML.NET:</span><span class="sxs-lookup"><span data-stu-id="38eea-115">Examples of the type of predictions that you can make with ML.NET:</span></span>

|||
|-|-|
|<span data-ttu-id="38eea-116">Classificazione/categorizzazione</span><span class="sxs-lookup"><span data-stu-id="38eea-116">Classification/Categorization</span></span>|<span data-ttu-id="38eea-117">Suddivisione automatica del feedback dei clienti in categorie positive e negative</span><span class="sxs-lookup"><span data-stu-id="38eea-117">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="38eea-118">Regressione/stima di valori continui</span><span class="sxs-lookup"><span data-stu-id="38eea-118">Regression/Predict continuous values</span></span>|<span data-ttu-id="38eea-119">Stimare il prezzo di unità immobiliari sulla base di dimensioni e posizione</span><span class="sxs-lookup"><span data-stu-id="38eea-119">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="38eea-120">Rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="38eea-120">Anomaly Detection</span></span>|<span data-ttu-id="38eea-121">Rilevare le transazioni bancarie illecite</span><span class="sxs-lookup"><span data-stu-id="38eea-121">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="38eea-122">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="38eea-122">Recommendations</span></span>|<span data-ttu-id="38eea-123">Suggerire prodotti che possono risultare interessanti agli acquirenti online sulla base dei loro acquisti precedenti</span><span class="sxs-lookup"><span data-stu-id="38eea-123">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|
|<span data-ttu-id="38eea-124">Serie temporali/dati sequenziali</span><span class="sxs-lookup"><span data-stu-id="38eea-124">Time series/sequential data</span></span>|<span data-ttu-id="38eea-125">Prevedere le vendite Meteo/prodotto</span><span class="sxs-lookup"><span data-stu-id="38eea-125">Forecast the weather/product sales</span></span>|
|<span data-ttu-id="38eea-126">Classificazione immagini</span><span class="sxs-lookup"><span data-stu-id="38eea-126">Image classification</span></span>|<span data-ttu-id="38eea-127">Categorizzare le patologie nelle immagini medicali</span><span class="sxs-lookup"><span data-stu-id="38eea-127">Categorize pathologies in medical images</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="38eea-128">Hello ML.NET World</span><span class="sxs-lookup"><span data-stu-id="38eea-128">Hello ML.NET World</span></span>

<span data-ttu-id="38eea-129">Il codice del frammento seguente illustra l'applicazione più semplice di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="38eea-129">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="38eea-130">Questo esempio crea un modello di regressione lineare per stimare i prezzi di unità immobiliari usando i dati delle dimensioni e del prezzo dell'unità immobiliare.</span><span class="sxs-lookup"><span data-stu-id="38eea-130">This example constructs a linear regression model to predict house prices using house size and price data.</span></span> 

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;

    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }

        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }

        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();

            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));

            // 3. Train model
            var model = pipeline.Fit(trainingData);

            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    }
```

## <a name="code-workflow"></a><span data-ttu-id="38eea-131">Flusso di lavoro del codice</span><span class="sxs-lookup"><span data-stu-id="38eea-131">Code workflow</span></span>

<span data-ttu-id="38eea-132">Il diagramma seguente rappresenta la struttura del codice dell'applicazione e il processo iterativo di sviluppo del modello:</span><span class="sxs-lookup"><span data-stu-id="38eea-132">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="38eea-133">Raccogliere e caricare i dati di training in un oggetto **IDataView**</span><span class="sxs-lookup"><span data-stu-id="38eea-133">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="38eea-134">Specificare una pipeline di operazioni per estrarre caratteristiche e applicare un algoritmo di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="38eea-134">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="38eea-135">Eseguire il training di un modello chiamando **Fit()** sulla pipeline</span><span class="sxs-lookup"><span data-stu-id="38eea-135">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="38eea-136">Valutare il modello ed eseguire l'iterazione per migliorare</span><span class="sxs-lookup"><span data-stu-id="38eea-136">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="38eea-137">Salvare il modello in formato binario, per l'uso in un'applicazione</span><span class="sxs-lookup"><span data-stu-id="38eea-137">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="38eea-138">Caricare il modello in un oggetto **ITransformer**</span><span class="sxs-lookup"><span data-stu-id="38eea-138">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="38eea-139">Eseguire stime chiamando **CreatePredictionEngine.Predict()**</span><span class="sxs-lookup"><span data-stu-id="38eea-139">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![Flusso di sviluppo dell'applicazione ML.NET che include componenti per la generazione dei dati, sviluppo di pipeline, training del modello, valutazione del modello e uso del modello](./media/mldotnet-annotated-workflow.png)

<span data-ttu-id="38eea-141">Ora si approfondiranno questi concetti.</span><span class="sxs-lookup"><span data-stu-id="38eea-141">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="38eea-142">Modello di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="38eea-142">Machine learning model</span></span>

<span data-ttu-id="38eea-143">Un modello ML.NET è un oggetto che contiene le trasformazioni da eseguire sui dati di input per ottenere l'output previsto.</span><span class="sxs-lookup"><span data-stu-id="38eea-143">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="38eea-144">Basic</span><span class="sxs-lookup"><span data-stu-id="38eea-144">Basic</span></span>

<span data-ttu-id="38eea-145">Il modello più semplice è la regressione lineare bidimensionale, in cui una quantità continua è proporzionale a un'altra, come illustrato nell'esempio di prezzi di unità immobiliari precedente.</span><span class="sxs-lookup"><span data-stu-id="38eea-145">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span>

![Modello di regressione lineare con parametri di distorsione e peso](./media/linear-regression-model.svg)

<span data-ttu-id="38eea-147">Il modello è semplicemente: $Price = b + Size \* w$.</span><span class="sxs-lookup"><span data-stu-id="38eea-147">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="38eea-148">I parametri $b$ e $w$ vengono stimati adattando una riga a un set di coppie (size, price).</span><span class="sxs-lookup"><span data-stu-id="38eea-148">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="38eea-149">I dati usati per trovare i parametri del modello sono detti **dati di training**.</span><span class="sxs-lookup"><span data-stu-id="38eea-149">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="38eea-150">Gli input di un modello di Machine Learning vengono chiamati **caratteristiche**.</span><span class="sxs-lookup"><span data-stu-id="38eea-150">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="38eea-151">In questo esempio $Size$ è l'unica caratteristica.</span><span class="sxs-lookup"><span data-stu-id="38eea-151">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="38eea-152">I valori di base usati per il training di un modello di Machine Learning sono detti **etichette**.</span><span class="sxs-lookup"><span data-stu-id="38eea-152">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="38eea-153">In questo caso le etichette sono i valori di $Price$ nel training set.</span><span class="sxs-lookup"><span data-stu-id="38eea-153">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="38eea-154">Più complesso</span><span class="sxs-lookup"><span data-stu-id="38eea-154">More complex</span></span>

<span data-ttu-id="38eea-155">Un modello più complesso classifica le transazioni finanziarie in categorie usando la descrizione di testo della transazione.</span><span class="sxs-lookup"><span data-stu-id="38eea-155">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="38eea-156">Ogni descrizione di transazione è suddivisa in un set di caratteristiche, tramite la rimozione delle parole e dei caratteri ridondanti e il conteggio delle combinazioni di parole e caratteri.</span><span class="sxs-lookup"><span data-stu-id="38eea-156">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="38eea-157">Il set di caratteristiche è usato per il training di un modello lineare sulla base del set di categorie nei dati di training.</span><span class="sxs-lookup"><span data-stu-id="38eea-157">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="38eea-158">Più una nuova descrizione è simile a quelle del training set, maggiore è la probabilità che sia assegnata alla stessa categoria.</span><span class="sxs-lookup"><span data-stu-id="38eea-158">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span>

![Modello di classificazione del testo](./media/text-classification-model.svg)

<span data-ttu-id="38eea-160">Sia il modello di tariffazione delle unità immobiliari sia il modello di classificazione del testo sono modelli **lineari**.</span><span class="sxs-lookup"><span data-stu-id="38eea-160">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="38eea-161">A seconda della natura dei dati e del problema da risolvere, è anche possibile usare modelli **albero delle decisioni**, modelli **additivi generalizzati (GAM)** e altri ancora.</span><span class="sxs-lookup"><span data-stu-id="38eea-161">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="38eea-162">Per altre informazioni sui modelli, vedere [Attività](./resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="38eea-162">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="38eea-163">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="38eea-163">Data preparation</span></span>

<span data-ttu-id="38eea-164">Nella maggior parte dei casi i dati disponibili non sono pronti per l'uso nel training di un modello di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="38eea-164">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="38eea-165">I dati non elaborati devono essere preparati o pre-elaborati prima di poter essere utilizzati per trovare i parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="38eea-165">The raw data needs to be prepared, or pre-processed, before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="38eea-166">Può essere necessaria la conversione dei dati da valori stringa a una rappresentazione numerica.</span><span class="sxs-lookup"><span data-stu-id="38eea-166">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="38eea-167">I dati di input potrebbero contenere informazioni ridondanti.</span><span class="sxs-lookup"><span data-stu-id="38eea-167">You might have redundant information in your input data.</span></span> <span data-ttu-id="38eea-168">Potrebbe essere necessario ridurre o espandere le dimensioni dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="38eea-168">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="38eea-169">I dati potrebbero richiedere la normalizzazione o la scalatura.</span><span class="sxs-lookup"><span data-stu-id="38eea-169">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="38eea-170">Le [esercitazioni di ML.NET](./tutorials/index.md) illustrano diverse pipeline di elaborazione per dati di testo, immagini, serie temporali e dati numerici usati per attività di apprendimento automatico specifiche.</span><span class="sxs-lookup"><span data-stu-id="38eea-170">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="38eea-171">La [procedura per preparare i dati](./how-to-guides/prepare-data-ml-net.md) Mostra come applicare la preparazione dei dati più in generale.</span><span class="sxs-lookup"><span data-stu-id="38eea-171">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to apply data preparation more generally.</span></span>

<span data-ttu-id="38eea-172">Un'appendice con tutte le [trasformazioni](./resources/transforms.md) è disponibile nella sezione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="38eea-172">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="38eea-173">Valutazione del modello</span><span class="sxs-lookup"><span data-stu-id="38eea-173">Model evaluation</span></span>

<span data-ttu-id="38eea-174">Dopo aver eseguito il training del modello, come si sa se le stime future verranno eseguite correttamente?</span><span class="sxs-lookup"><span data-stu-id="38eea-174">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="38eea-175">Con ML.NET è possibile valutare il modello rispetto a nuovi dati di test.</span><span class="sxs-lookup"><span data-stu-id="38eea-175">With ML.NET, you can evaluate your model against some new test data.</span></span>

<span data-ttu-id="38eea-176">Ogni tipo di attività di apprendimento automatico dispone di metriche che vengono usate per valutare l'accuratezza e la precisione del modello rispetto al set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="38eea-176">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="38eea-177">Per l'esempio di definizione dei prezzi di unità immobiliari è stata usata l'attività **Regressione**.</span><span class="sxs-lookup"><span data-stu-id="38eea-177">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="38eea-178">Per valutare il modello, aggiungere il codice seguente all'esempio originale.</span><span class="sxs-lookup"><span data-stu-id="38eea-178">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);

        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="38eea-179">Le metriche di valutazione indicano che la quantità di errori è ridotta e che la correlazione tra l'output previsto e l'output del test è elevata.</span><span class="sxs-lookup"><span data-stu-id="38eea-179">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="38eea-180">Questa elaborazione non ha presentato problemi.</span><span class="sxs-lookup"><span data-stu-id="38eea-180">That was easy!</span></span> <span data-ttu-id="38eea-181">Negli esempi reali, per ottenere metriche del modello valide sono necessarie più operazioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="38eea-181">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="38eea-182">Architettura ML.NET</span><span class="sxs-lookup"><span data-stu-id="38eea-182">ML.NET architecture</span></span>

<span data-ttu-id="38eea-183">In questa sezione si prendono in considerazione i modelli architettonici di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="38eea-183">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="38eea-184">Per gli sviluppatori .NET esperti alcuni di questi modelli risulteranno familiari e altri meno familiari.</span><span class="sxs-lookup"><span data-stu-id="38eea-184">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="38eea-185">Si procede per gradi.</span><span class="sxs-lookup"><span data-stu-id="38eea-185">Hold tight, while we dive in!</span></span>

<span data-ttu-id="38eea-186">Un'applicazione ML.NET inizia con un oggetto <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="38eea-186">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="38eea-187">Questo oggetto singleton contiene **cataloghi**.</span><span class="sxs-lookup"><span data-stu-id="38eea-187">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="38eea-188">Un catalogo è una factory per il caricamento e salvataggio di dati, le trasformazioni, i formatori e i componenti di gestione del modello.</span><span class="sxs-lookup"><span data-stu-id="38eea-188">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="38eea-189">Ogni oggetto catalogo dispone di metodi per creare diversi tipi di componenti:</span><span class="sxs-lookup"><span data-stu-id="38eea-189">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="38eea-190">Caricamento e salvataggio dei dati</span><span class="sxs-lookup"><span data-stu-id="38eea-190">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="38eea-191">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="38eea-191">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="38eea-192">Algoritmi di training</span><span class="sxs-lookup"><span data-stu-id="38eea-192">Training algorithms</span></span>|<span data-ttu-id="38eea-193">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="38eea-193">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="38eea-194">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="38eea-194">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="38eea-195">Rilevamento di anomalie</span><span class="sxs-lookup"><span data-stu-id="38eea-195">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="38eea-196">Clustering</span><span class="sxs-lookup"><span data-stu-id="38eea-196">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="38eea-197">Previsione</span><span class="sxs-lookup"><span data-stu-id="38eea-197">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="38eea-198">Ranking</span><span class="sxs-lookup"><span data-stu-id="38eea-198">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="38eea-199">Regressione</span><span class="sxs-lookup"><span data-stu-id="38eea-199">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="38eea-200">Indicazione</span><span class="sxs-lookup"><span data-stu-id="38eea-200">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="38eea-201">Aggiungere il pacchetto NuGet `Microsoft.ML.Recommender`</span><span class="sxs-lookup"><span data-stu-id="38eea-201">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="38eea-202">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="38eea-202">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="38eea-203">Aggiungere il pacchetto NuGet `Microsoft.ML.TimeSeries`</span><span class="sxs-lookup"><span data-stu-id="38eea-203">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="38eea-204">Uso dei modelli</span><span class="sxs-lookup"><span data-stu-id="38eea-204">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="38eea-205">È possibile passare ai metodi di creazione in ognuna delle categorie precedenti.</span><span class="sxs-lookup"><span data-stu-id="38eea-205">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="38eea-206">Se si usa Visual Studio i cataloghi sono visualizzabili tramite IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="38eea-206">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![IntelliSense per gli algoritmi di training di regressione](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="38eea-208">Creare la pipeline</span><span class="sxs-lookup"><span data-stu-id="38eea-208">Build the pipeline</span></span>

<span data-ttu-id="38eea-209">Ogni catalogo include un set di metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="38eea-209">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="38eea-210">Ora si esaminerà come i metodi di estensione consentono di creare una pipeline di training.</span><span class="sxs-lookup"><span data-stu-id="38eea-210">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="38eea-211">Nel frammento, sia `Concatenate` che `Sdca` sono metodi nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="38eea-211">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="38eea-212">Ognuno di essi crea un oggetto [IEstimator](xref:Microsoft.ML.IEstimator%601) che viene accodato alla pipeline.</span><span class="sxs-lookup"><span data-stu-id="38eea-212">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="38eea-213">In questa fase viene eseguita solo la creazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="38eea-213">At this point, the objects are created only.</span></span> <span data-ttu-id="38eea-214">Non si verifica ancora nessuna esecuzione.</span><span class="sxs-lookup"><span data-stu-id="38eea-214">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="38eea-215">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="38eea-215">Train the model</span></span>

<span data-ttu-id="38eea-216">Dopo che sono stati creati gli oggetti nella pipeline, è possibile usare i dati per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="38eea-216">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="38eea-217">La chiamata di `Fit()` usa i dati di training di input per stimare i parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="38eea-217">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="38eea-218">Tale processo è noto come training del modello.</span><span class="sxs-lookup"><span data-stu-id="38eea-218">This is known as training the model.</span></span> <span data-ttu-id="38eea-219">Ricordare che il modello di regressione lineare precedente aveva due parametri di modello: **bias** e **weight**.</span><span class="sxs-lookup"><span data-stu-id="38eea-219">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="38eea-220">Dopo la chiamata `Fit()` i valori dei parametri sono noti.</span><span class="sxs-lookup"><span data-stu-id="38eea-220">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="38eea-221">La maggior parte dei modelli ha un numero di parametri di molto superiore a questo.</span><span class="sxs-lookup"><span data-stu-id="38eea-221">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="38eea-222">Per altre informazioni sul training del modello, vedere [Come eseguire il training del modello](./how-to-guides/train-machine-learning-model-ml-net.md)</span><span class="sxs-lookup"><span data-stu-id="38eea-222">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md)</span></span>

<span data-ttu-id="38eea-223">L'oggetto modello risultante implementa l'interfaccia <xref:Microsoft.ML.ITransformer>.</span><span class="sxs-lookup"><span data-stu-id="38eea-223">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="38eea-224">In altre parole il modello trasforma i dati di input in stime.</span><span class="sxs-lookup"><span data-stu-id="38eea-224">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="38eea-225">Usare il modello</span><span class="sxs-lookup"><span data-stu-id="38eea-225">Use the model</span></span>

<span data-ttu-id="38eea-226">È possibile trasformare in stime i dati di input in blocco o un input alla volta.</span><span class="sxs-lookup"><span data-stu-id="38eea-226">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="38eea-227">Nell'esempio dei prezzi di unità immobiliari sono state eseguite entrambe le trasformazioni: in blocco per valutare il modello e un input alla volta per eseguire una nuova stima.</span><span class="sxs-lookup"><span data-stu-id="38eea-227">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="38eea-228">Ora si analizzano le singole stime.</span><span class="sxs-lookup"><span data-stu-id="38eea-228">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```

<span data-ttu-id="38eea-229">Il metodo `CreatePredictionEngine()` accetta una classe di input e una classe di output.</span><span class="sxs-lookup"><span data-stu-id="38eea-229">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="38eea-230">I nomi di campo e/o gli attributi di codice determinano i nomi delle colonne di dati usate durante il training del modello e la stima.</span><span class="sxs-lookup"><span data-stu-id="38eea-230">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="38eea-231">Per altre informazioni vedere [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) (Come eseguire una stima singola) nella sezione Procedure.</span><span class="sxs-lookup"><span data-stu-id="38eea-231">You can read about  [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) in the How-to section.</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="38eea-232">Modelli di dati e schema</span><span class="sxs-lookup"><span data-stu-id="38eea-232">Data models and schema</span></span>

<span data-ttu-id="38eea-233">Alla base di una pipeline di apprendimento automatico ML.NET si trovano gli oggetti [DataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="38eea-233">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="38eea-234">Ogni trasformazione nella pipeline presenta uno schema di input (nomi, tipi e dimensioni dei dati che la trasformazione prevede come input) e uno schema di output (nomi, tipi e dimensioni dei dati che vengono prodotti dopo la trasformazione).</span><span class="sxs-lookup"><span data-stu-id="38eea-234">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> <span data-ttu-id="38eea-235">Il documento seguente offre una spiegazione approfondita dell'[interfaccia IDataView e del relativo sistema di tipi](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span><span class="sxs-lookup"><span data-stu-id="38eea-235">The following document provides an in-depth explanation of the [IDataView interface and its type system](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span></span>

<span data-ttu-id="38eea-236">Se lo schema di output di una trasformazione della pipeline non corrisponde allo schema di input della trasformazione successiva, ML.NET genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="38eea-236">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="38eea-237">Un oggetto visualizzazione include colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="38eea-237">A data view object has columns and rows.</span></span> <span data-ttu-id="38eea-238">Ogni colonna ha un nome, un tipo e una lunghezza.</span><span class="sxs-lookup"><span data-stu-id="38eea-238">Each column has a name and a type and a length.</span></span> <span data-ttu-id="38eea-239">Ad esempio, le colonne di input nell'esempio del prezzo della casa sono **size** e **Price**.</span><span class="sxs-lookup"><span data-stu-id="38eea-239">For example, the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="38eea-240">Sono entrambi di tipo e sono quantità scalari piuttosto che vettoriali.</span><span class="sxs-lookup"><span data-stu-id="38eea-240">They are both type and they are scalar quantities rather than vector ones.</span></span>

   ![Esempio di visualizzazione dati ML.NET con dati di stima dei prezzi di unità immobiliari](./media/ml-net-dataview.png)

<span data-ttu-id="38eea-242">Tutti gli algoritmi ML.NET cercano una colonna di input che è un vettore.</span><span class="sxs-lookup"><span data-stu-id="38eea-242">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="38eea-243">Per impostazione predefinita questa colonna vettore è denominata **Features** (Caratteristiche).</span><span class="sxs-lookup"><span data-stu-id="38eea-243">By default this vector column is called **Features**.</span></span> <span data-ttu-id="38eea-244">Per questo motivo la colonna **Size** è stata concatenata in una nuova colonna denominata **Features** nell'esempio per i prezzi di unità immobiliari.</span><span class="sxs-lookup"><span data-stu-id="38eea-244">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="38eea-245">Tutti gli algoritmi creano a loro volta nuove colonne dopo che hanno eseguito una stima.</span><span class="sxs-lookup"><span data-stu-id="38eea-245">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="38eea-246">I nomi fissi di queste nuove colonne dipendono dal tipo di algoritmo di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="38eea-246">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="38eea-247">Per l'attività di regressione una delle nuove colonne è chiamata **Score** (Punteggio).</span><span class="sxs-lookup"><span data-stu-id="38eea-247">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="38eea-248">Ecco perché ai dati dei prezzi è stato assegnato un attributo con questo nome.</span><span class="sxs-lookup"><span data-stu-id="38eea-248">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```

<span data-ttu-id="38eea-249">Per altre informazioni sulle colonne di output delle diverse attività di apprendimento automatico, vedere [Attività di apprendimento automatico](resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="38eea-249">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="38eea-250">Una proprietà importante degli oggetti DataView è che vengono valutati **in modo differito**.</span><span class="sxs-lookup"><span data-stu-id="38eea-250">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="38eea-251">Le visualizzazioni dei dati vengono caricate ed elaborate solo durante il training e la valutazione del modello e la stima dei dati.</span><span class="sxs-lookup"><span data-stu-id="38eea-251">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="38eea-252">Durante la creazione e il testing dell'applicazione ML.NET è possibile usare il debugger di Visual Studio per visualizzare gli oggetti visualizzazione dati tramite la chiamata del metodo [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*).</span><span class="sxs-lookup"><span data-stu-id="38eea-252">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="38eea-253">È possibile visualizzare la variabile `debug` nel debugger ed esaminarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="38eea-253">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="38eea-254">Non usare il metodo Preview nel codice di produzione, perché riduce notevolmente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="38eea-254">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="38eea-255">Distribuzione del modello</span><span class="sxs-lookup"><span data-stu-id="38eea-255">Model Deployment</span></span>

<span data-ttu-id="38eea-256">Nelle applicazioni reali il codice di training e valutazione del modello è separato dalla stima.</span><span class="sxs-lookup"><span data-stu-id="38eea-256">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="38eea-257">Di fatto, queste due attività vengono spesso eseguite da team separati.</span><span class="sxs-lookup"><span data-stu-id="38eea-257">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="38eea-258">Il team di sviluppo del modello può salvare il modello per l'uso nell'applicazione di stima.</span><span class="sxs-lookup"><span data-stu-id="38eea-258">Your model development team can save the model for use in the prediction application.</span></span>

```csharp
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="next-steps"></a><span data-ttu-id="38eea-259">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="38eea-259">Next steps</span></span>

* <span data-ttu-id="38eea-260">Informazioni su come creare applicazioni usando diverse attività di Machine Learning con set di dati più realistici nelle [esercitazioni](./tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="38eea-260">Learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

* <span data-ttu-id="38eea-261">Per informazioni dettagliate sugli argomenti specifici, vedere la [Guida alle procedure](./how-to-guides/index.md).</span><span class="sxs-lookup"><span data-stu-id="38eea-261">Learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

* <span data-ttu-id="38eea-262">Se si è molto appassionati, è possibile passare direttamente alla [documentazione di riferimento delle API](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="38eea-262">If you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet).</span></span>
