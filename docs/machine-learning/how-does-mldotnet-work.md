---
title: Che cos'è ML.NET e come funziona?
description: ML.NET offre la possibilità di aggiungere funzionalità di Machine Learning alle applicazioni .NET, in scenari online o offline. Con questa funzionalità è possibile eseguire stime automatiche usando i dati disponibili per l'applicazione senza che sia necessario connettersi a una rete per usare ML.NET. Questo articolo illustra le nozioni fondamentali dell'apprendimento automatico in ML.NET.
ms.date: 11/5/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 0929005e02ad9b43636213735f8c7232aa6d4f42
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607771"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="af6e3-105">Che cos'è ML.NET e come funziona?</span><span class="sxs-lookup"><span data-stu-id="af6e3-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="af6e3-106">ML.NET offre la possibilità di aggiungere funzionalità di Machine Learning alle applicazioni .NET, in scenari online o offline.</span><span class="sxs-lookup"><span data-stu-id="af6e3-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="af6e3-107">Con questa funzionalità è possibile eseguire stime automatiche usando i dati disponibili per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="af6e3-107">With this capability, you can make automatic predictions using the data available to your application.</span></span> <span data-ttu-id="af6e3-108">Le applicazioni di apprendimento automatico usano modelli nei dati per fare previsioni piuttosto che dover essere programmate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="af6e3-108">Machine learning applications make use of patterns in the data to make predictions rather than needing to be explicitly programmed.</span></span>

<span data-ttu-id="af6e3-109">Centrale per ML.NET è un **modello**di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="af6e3-109">Central to ML.NET is a machine learning **model**.</span></span> <span data-ttu-id="af6e3-110">Il modello specifica i passaggi necessari per trasformare i dati di input in una stima.</span><span class="sxs-lookup"><span data-stu-id="af6e3-110">The model specifies the steps needed to transform your input data into a prediction.</span></span> <span data-ttu-id="af6e3-111">Con ML.NET, è possibile eseguire il training di un modello personalizzato specificando un algoritmo oppure importare modelli TensorFlow e ONNX con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="af6e3-111">With ML.NET, you can train a custom model by specifying an algorithm, or you can import pre-trained TensorFlow and ONNX models.</span></span>

<span data-ttu-id="af6e3-112">Dopo aver a disposizione un modello, è possibile aggiungerlo all'applicazione per eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="af6e3-112">Once you have a model, you can add it to your application to make the predictions.</span></span>

<span data-ttu-id="af6e3-113">ML.NET vengono eseguiti in Windows, Linux e macOS usando .NET Core o Windows con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af6e3-113">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="af6e3-114">64 bit è supportato su tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="af6e3-114">64 bit is supported on all platforms.</span></span> <span data-ttu-id="af6e3-115">La funzionalità relativa a 32 bit è supportata in Windows, ad eccezione di TensorFlow, LightGBM e ONNX.</span><span class="sxs-lookup"><span data-stu-id="af6e3-115">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX-related functionality.</span></span>

<span data-ttu-id="af6e3-116">Esempi del tipo di stime che è possibile eseguire con ML.NET:</span><span class="sxs-lookup"><span data-stu-id="af6e3-116">Examples of the type of predictions that you can make with ML.NET:</span></span>

|||
|-|-|
|<span data-ttu-id="af6e3-117">Classificazione/categorizzazione</span><span class="sxs-lookup"><span data-stu-id="af6e3-117">Classification/Categorization</span></span>|<span data-ttu-id="af6e3-118">Suddivisione automatica dei commenti e dei suggerimenti degli utenti in categorie positive e negative</span><span class="sxs-lookup"><span data-stu-id="af6e3-118">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="af6e3-119">Regressione/stima di valori continui</span><span class="sxs-lookup"><span data-stu-id="af6e3-119">Regression/Predict continuous values</span></span>|<span data-ttu-id="af6e3-120">Previsione del prezzo delle case in base alle dimensioni e alla posizione</span><span class="sxs-lookup"><span data-stu-id="af6e3-120">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="af6e3-121">Anomaly Detection</span><span class="sxs-lookup"><span data-stu-id="af6e3-121">Anomaly Detection</span></span>|<span data-ttu-id="af6e3-122">Rilevamento di transazioni bancarie fraudolente</span><span class="sxs-lookup"><span data-stu-id="af6e3-122">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="af6e3-123">Consigli</span><span class="sxs-lookup"><span data-stu-id="af6e3-123">Recommendations</span></span>|<span data-ttu-id="af6e3-124">Suggerimento di prodotti che gli acquirenti online potrebbero voler acquistare, in base agli acquisti precedenti</span><span class="sxs-lookup"><span data-stu-id="af6e3-124">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|
|<span data-ttu-id="af6e3-125">Serie temporali/dati sequenziali</span><span class="sxs-lookup"><span data-stu-id="af6e3-125">Time series/sequential data</span></span>|<span data-ttu-id="af6e3-126">Prevedere le vendite meteo/prodotto</span><span class="sxs-lookup"><span data-stu-id="af6e3-126">Forecast the weather/product sales</span></span>|
|<span data-ttu-id="af6e3-127">Classificazione di immagini</span><span class="sxs-lookup"><span data-stu-id="af6e3-127">Image classification</span></span>|<span data-ttu-id="af6e3-128">Categorizzare le patologie nelle immagini mediche</span><span class="sxs-lookup"><span data-stu-id="af6e3-128">Categorize pathologies in medical images</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="af6e3-129">Hello ML.NET World</span><span class="sxs-lookup"><span data-stu-id="af6e3-129">Hello ML.NET World</span></span>

<span data-ttu-id="af6e3-130">Il codice del frammento seguente illustra l'applicazione più semplice di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="af6e3-130">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="af6e3-131">Questo esempio crea un modello di regressione lineare per stimare i prezzi di unità immobiliari usando i dati delle dimensioni e del prezzo dell'unità immobiliare.</span><span class="sxs-lookup"><span data-stu-id="af6e3-131">This example constructs a linear regression model to predict house prices using house size and price data.</span></span>

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

## <a name="code-workflow"></a><span data-ttu-id="af6e3-132">Flusso di lavoro del codice</span><span class="sxs-lookup"><span data-stu-id="af6e3-132">Code workflow</span></span>

<span data-ttu-id="af6e3-133">Il diagramma seguente rappresenta la struttura del codice dell'applicazione e il processo iterativo di sviluppo del modello:</span><span class="sxs-lookup"><span data-stu-id="af6e3-133">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="af6e3-134">Raccogliere e caricare i dati di training in un oggetto **IDataView**</span><span class="sxs-lookup"><span data-stu-id="af6e3-134">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="af6e3-135">Specificare una pipeline di operazioni per estrarre caratteristiche e applicare un algoritmo di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="af6e3-135">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="af6e3-136">Eseguire il training di un modello chiamando **Fit()** sulla pipeline</span><span class="sxs-lookup"><span data-stu-id="af6e3-136">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="af6e3-137">Valutare il modello ed eseguire l'iterazione per migliorare</span><span class="sxs-lookup"><span data-stu-id="af6e3-137">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="af6e3-138">Salvare il modello in formato binario, per l'uso in un'applicazione</span><span class="sxs-lookup"><span data-stu-id="af6e3-138">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="af6e3-139">Caricare il modello in un oggetto **ITransformer**</span><span class="sxs-lookup"><span data-stu-id="af6e3-139">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="af6e3-140">Eseguire stime chiamando **CreatePredictionEngine.Predict()**</span><span class="sxs-lookup"><span data-stu-id="af6e3-140">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![Flusso di sviluppo dell'applicazione ML.NET che include componenti per la generazione dei dati, sviluppo di pipeline, training del modello, valutazione del modello e uso del modello](./media/mldotnet-annotated-workflow.png)

<span data-ttu-id="af6e3-142">Ora si approfondiranno questi concetti.</span><span class="sxs-lookup"><span data-stu-id="af6e3-142">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="af6e3-143">Modello di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="af6e3-143">Machine learning model</span></span>

<span data-ttu-id="af6e3-144">Un modello ML.NET è un oggetto che contiene le trasformazioni da eseguire sui dati di input per ottenere l'output previsto.</span><span class="sxs-lookup"><span data-stu-id="af6e3-144">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="af6e3-145">Basic</span><span class="sxs-lookup"><span data-stu-id="af6e3-145">Basic</span></span>

<span data-ttu-id="af6e3-146">Il modello più semplice è la regressione lineare bidimensionale, in cui una quantità continua è proporzionale a un'altra, come illustrato nell'esempio di prezzi di unità immobiliari precedente.</span><span class="sxs-lookup"><span data-stu-id="af6e3-146">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span>

![Modello di regressione lineare con parametri di distorsione e peso](./media/linear-regression-model.svg)

<span data-ttu-id="af6e3-148">Il modello è semplicemente: $Price = b + Size \* w$.</span><span class="sxs-lookup"><span data-stu-id="af6e3-148">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="af6e3-149">I parametri $b$ e $w$ vengono stimati adattando una riga a un set di coppie (size, price).</span><span class="sxs-lookup"><span data-stu-id="af6e3-149">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="af6e3-150">I dati usati per trovare i parametri del modello sono detti **dati di training**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-150">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="af6e3-151">Gli input di un modello di Machine Learning vengono chiamati **caratteristiche**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-151">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="af6e3-152">In questo esempio $Size$ è l'unica caratteristica.</span><span class="sxs-lookup"><span data-stu-id="af6e3-152">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="af6e3-153">I valori di base usati per il training di un modello di Machine Learning sono detti **etichette**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-153">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="af6e3-154">In questo caso le etichette sono i valori di $Price$ nel training set.</span><span class="sxs-lookup"><span data-stu-id="af6e3-154">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="af6e3-155">Più complesso</span><span class="sxs-lookup"><span data-stu-id="af6e3-155">More complex</span></span>

<span data-ttu-id="af6e3-156">Un modello più complesso classifica le transazioni finanziarie in categorie usando la descrizione di testo della transazione.</span><span class="sxs-lookup"><span data-stu-id="af6e3-156">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="af6e3-157">Ogni descrizione di transazione è suddivisa in un set di caratteristiche, tramite la rimozione delle parole e dei caratteri ridondanti e il conteggio delle combinazioni di parole e caratteri.</span><span class="sxs-lookup"><span data-stu-id="af6e3-157">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="af6e3-158">Il set di caratteristiche è usato per il training di un modello lineare sulla base del set di categorie nei dati di training.</span><span class="sxs-lookup"><span data-stu-id="af6e3-158">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="af6e3-159">Più una nuova descrizione è simile a quelle del training set, maggiore è la probabilità che sia assegnata alla stessa categoria.</span><span class="sxs-lookup"><span data-stu-id="af6e3-159">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span>

![Modello di classificazione del testo](./media/text-classification-model.svg)

<span data-ttu-id="af6e3-161">Sia il modello di tariffazione delle unità immobiliari sia il modello di classificazione del testo sono modelli **lineari**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-161">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="af6e3-162">A seconda della natura dei dati e del problema da risolvere, è anche possibile usare modelli **albero delle decisioni**, modelli **additivi generalizzati (GAM)** e altri ancora.</span><span class="sxs-lookup"><span data-stu-id="af6e3-162">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="af6e3-163">Per altre informazioni sui modelli, vedere [Attività](./resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="af6e3-163">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="af6e3-164">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="af6e3-164">Data preparation</span></span>

<span data-ttu-id="af6e3-165">Nella maggior parte dei casi i dati disponibili non sono pronti per l'uso nel training di un modello di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="af6e3-165">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="af6e3-166">I dati non elaborati devono essere preparati, o pre-elaborati, prima di poter essere utilizzati per trovare i parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="af6e3-166">The raw data needs to be prepared, or pre-processed, before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="af6e3-167">Può essere necessaria la conversione dei dati da valori stringa a una rappresentazione numerica.</span><span class="sxs-lookup"><span data-stu-id="af6e3-167">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="af6e3-168">I dati di input potrebbero contenere informazioni ridondanti.</span><span class="sxs-lookup"><span data-stu-id="af6e3-168">You might have redundant information in your input data.</span></span> <span data-ttu-id="af6e3-169">Potrebbe essere necessario ridurre o espandere le dimensioni dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="af6e3-169">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="af6e3-170">I dati potrebbero richiedere la normalizzazione o la scalatura.</span><span class="sxs-lookup"><span data-stu-id="af6e3-170">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="af6e3-171">Le [esercitazioni di ML.NET](./tutorials/index.md) illustrano diverse pipeline di elaborazione per dati di testo, immagini, serie temporali e dati numerici usati per attività di apprendimento automatico specifiche.</span><span class="sxs-lookup"><span data-stu-id="af6e3-171">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="af6e3-172">[Come preparare i dati](./how-to-guides/prepare-data-ml-net.md) mostra come applicare la preparazione dei dati in modo più generale.</span><span class="sxs-lookup"><span data-stu-id="af6e3-172">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to apply data preparation more generally.</span></span>

<span data-ttu-id="af6e3-173">Un'appendice con tutte le [trasformazioni](./resources/transforms.md) è disponibile nella sezione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="af6e3-173">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="af6e3-174">Valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="af6e3-174">Model evaluation</span></span>

<span data-ttu-id="af6e3-175">Dopo aver eseguito il training del modello, come si sa se le stime future verranno eseguite correttamente?</span><span class="sxs-lookup"><span data-stu-id="af6e3-175">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="af6e3-176">Con ML.NET è possibile valutare il modello rispetto a nuovi dati di test.</span><span class="sxs-lookup"><span data-stu-id="af6e3-176">With ML.NET, you can evaluate your model against some new test data.</span></span>

<span data-ttu-id="af6e3-177">Ogni tipo di attività di apprendimento automatico dispone di metriche che vengono usate per valutare l'accuratezza e la precisione del modello rispetto al set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="af6e3-177">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="af6e3-178">Per l'esempio di definizione dei prezzi di unità immobiliari è stata usata l'attività **Regressione**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-178">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="af6e3-179">Per valutare il modello, aggiungere il codice seguente all'esempio originale.</span><span class="sxs-lookup"><span data-stu-id="af6e3-179">To evaluate the model, add the following code to the original sample.</span></span>

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

<span data-ttu-id="af6e3-180">Le metriche di valutazione indicano che la quantità di errori è ridotta e che la correlazione tra l'output previsto e l'output del test è elevata.</span><span class="sxs-lookup"><span data-stu-id="af6e3-180">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="af6e3-181">Questa elaborazione non ha presentato problemi.</span><span class="sxs-lookup"><span data-stu-id="af6e3-181">That was easy!</span></span> <span data-ttu-id="af6e3-182">Negli esempi reali, per ottenere metriche del modello valide sono necessarie più operazioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="af6e3-182">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="af6e3-183">Architettura ML.NET</span><span class="sxs-lookup"><span data-stu-id="af6e3-183">ML.NET architecture</span></span>

<span data-ttu-id="af6e3-184">In questa sezione si prendono in considerazione i modelli architettonici di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="af6e3-184">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="af6e3-185">Per gli sviluppatori .NET esperti alcuni di questi modelli risulteranno familiari e altri meno familiari.</span><span class="sxs-lookup"><span data-stu-id="af6e3-185">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="af6e3-186">Si procede per gradi.</span><span class="sxs-lookup"><span data-stu-id="af6e3-186">Hold tight, while we dive in!</span></span>

<span data-ttu-id="af6e3-187">Un'applicazione ML.NET inizia con un oggetto <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="af6e3-187">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="af6e3-188">Questo oggetto singleton contiene **cataloghi**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-188">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="af6e3-189">Un catalogo è una factory per il caricamento e salvataggio di dati, le trasformazioni, i formatori e i componenti di gestione del modello.</span><span class="sxs-lookup"><span data-stu-id="af6e3-189">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="af6e3-190">Ogni oggetto catalogo dispone di metodi per creare diversi tipi di componenti:</span><span class="sxs-lookup"><span data-stu-id="af6e3-190">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="af6e3-191">Caricamento e salvataggio dei dati</span><span class="sxs-lookup"><span data-stu-id="af6e3-191">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="af6e3-192">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="af6e3-192">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="af6e3-193">Algoritmi di training</span><span class="sxs-lookup"><span data-stu-id="af6e3-193">Training algorithms</span></span>|<span data-ttu-id="af6e3-194">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="af6e3-194">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="af6e3-195">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="af6e3-195">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="af6e3-196">Rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="af6e3-196">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="af6e3-197">Clustering</span><span class="sxs-lookup"><span data-stu-id="af6e3-197">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="af6e3-198">Previsione</span><span class="sxs-lookup"><span data-stu-id="af6e3-198">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="af6e3-199">Rango</span><span class="sxs-lookup"><span data-stu-id="af6e3-199">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="af6e3-200">Regressione</span><span class="sxs-lookup"><span data-stu-id="af6e3-200">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="af6e3-201">Recommendation</span><span class="sxs-lookup"><span data-stu-id="af6e3-201">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="af6e3-202">Aggiungere il pacchetto NuGet `Microsoft.ML.Recommender`</span><span class="sxs-lookup"><span data-stu-id="af6e3-202">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="af6e3-203">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="af6e3-203">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="af6e3-204">Aggiungere il pacchetto NuGet `Microsoft.ML.TimeSeries`</span><span class="sxs-lookup"><span data-stu-id="af6e3-204">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="af6e3-205">Uso dei modelli</span><span class="sxs-lookup"><span data-stu-id="af6e3-205">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="af6e3-206">È possibile passare ai metodi di creazione in ognuna delle categorie precedenti.</span><span class="sxs-lookup"><span data-stu-id="af6e3-206">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="af6e3-207">Se si usa Visual Studio i cataloghi sono visualizzabili tramite IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="af6e3-207">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![IntelliSense per gli algoritmi di training di regressione](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="af6e3-209">Creare la pipeline</span><span class="sxs-lookup"><span data-stu-id="af6e3-209">Build the pipeline</span></span>

<span data-ttu-id="af6e3-210">Ogni catalogo include un set di metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="af6e3-210">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="af6e3-211">Ora si esaminerà come i metodi di estensione consentono di creare una pipeline di training.</span><span class="sxs-lookup"><span data-stu-id="af6e3-211">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="af6e3-212">Nel frammento, sia `Concatenate` che `Sdca` sono metodi nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="af6e3-212">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="af6e3-213">Ognuno di essi crea un oggetto [IEstimator](xref:Microsoft.ML.IEstimator%601) che viene accodato alla pipeline.</span><span class="sxs-lookup"><span data-stu-id="af6e3-213">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="af6e3-214">In questa fase viene eseguita solo la creazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="af6e3-214">At this point, the objects are created only.</span></span> <span data-ttu-id="af6e3-215">Non si verifica ancora nessuna esecuzione.</span><span class="sxs-lookup"><span data-stu-id="af6e3-215">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="af6e3-216">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="af6e3-216">Train the model</span></span>

<span data-ttu-id="af6e3-217">Dopo che sono stati creati gli oggetti nella pipeline, è possibile usare i dati per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="af6e3-217">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="af6e3-218">La chiamata di `Fit()` usa i dati di training di input per stimare i parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="af6e3-218">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="af6e3-219">Questo processo è noto come training del modello.</span><span class="sxs-lookup"><span data-stu-id="af6e3-219">This is known as training the model.</span></span> <span data-ttu-id="af6e3-220">Ricordare che il modello di regressione lineare precedente aveva due parametri di modello: **bias** e **weight**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-220">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="af6e3-221">Dopo la chiamata `Fit()` i valori dei parametri sono noti.</span><span class="sxs-lookup"><span data-stu-id="af6e3-221">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="af6e3-222">La maggior parte dei modelli ha un numero di parametri di molto superiore a questo.</span><span class="sxs-lookup"><span data-stu-id="af6e3-222">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="af6e3-223">Per ulteriori informazioni sul training dei modelli, vedere [Come eseguire il training del modello.](./how-to-guides/train-machine-learning-model-ml-net.md)</span><span class="sxs-lookup"><span data-stu-id="af6e3-223">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md).</span></span>

<span data-ttu-id="af6e3-224">L'oggetto modello risultante implementa l'interfaccia <xref:Microsoft.ML.ITransformer>.</span><span class="sxs-lookup"><span data-stu-id="af6e3-224">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="af6e3-225">In altre parole il modello trasforma i dati di input in stime.</span><span class="sxs-lookup"><span data-stu-id="af6e3-225">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="af6e3-226">Usare il modello</span><span class="sxs-lookup"><span data-stu-id="af6e3-226">Use the model</span></span>

<span data-ttu-id="af6e3-227">È possibile trasformare in stime i dati di input in blocco o un input alla volta.</span><span class="sxs-lookup"><span data-stu-id="af6e3-227">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="af6e3-228">Nell'esempio dei prezzi di unità immobiliari sono state eseguite entrambe le trasformazioni: in blocco per valutare il modello e un input alla volta per eseguire una nuova stima.</span><span class="sxs-lookup"><span data-stu-id="af6e3-228">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="af6e3-229">Ora si analizzano le singole stime.</span><span class="sxs-lookup"><span data-stu-id="af6e3-229">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```

<span data-ttu-id="af6e3-230">Il metodo `CreatePredictionEngine()` accetta una classe di input e una classe di output.</span><span class="sxs-lookup"><span data-stu-id="af6e3-230">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="af6e3-231">I nomi di campo e/o gli attributi di codice determinano i nomi delle colonne di dati usate durante il training del modello e la stima.</span><span class="sxs-lookup"><span data-stu-id="af6e3-231">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="af6e3-232">Per ulteriori informazioni, consultate [Creare stime con un modello sottoposto a training.](how-to-guides/machine-learning-model-predictions-ml-net.md)</span><span class="sxs-lookup"><span data-stu-id="af6e3-232">For more information, see [Make predictions with a trained model](how-to-guides/machine-learning-model-predictions-ml-net.md).</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="af6e3-233">Modelli di dati e schema</span><span class="sxs-lookup"><span data-stu-id="af6e3-233">Data models and schema</span></span>

<span data-ttu-id="af6e3-234">Alla base di una pipeline di apprendimento automatico ML.NET si trovano gli oggetti [DataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="af6e3-234">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="af6e3-235">Ogni trasformazione nella pipeline presenta uno schema di input (nomi, tipi e dimensioni dei dati che la trasformazione prevede come input) e uno schema di output (nomi, tipi e dimensioni dei dati che vengono prodotti dopo la trasformazione).</span><span class="sxs-lookup"><span data-stu-id="af6e3-235">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> <span data-ttu-id="af6e3-236">Il documento seguente offre una spiegazione approfondita dell'[interfaccia IDataView e del relativo sistema di tipi](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span><span class="sxs-lookup"><span data-stu-id="af6e3-236">The following document provides an in-depth explanation of the [IDataView interface and its type system](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span></span>

<span data-ttu-id="af6e3-237">Se lo schema di output di una trasformazione della pipeline non corrisponde allo schema di input della trasformazione successiva, ML.NET genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="af6e3-237">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="af6e3-238">Un oggetto visualizzazione include colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="af6e3-238">A data view object has columns and rows.</span></span> <span data-ttu-id="af6e3-239">Ogni colonna ha un nome, un tipo e una lunghezza.</span><span class="sxs-lookup"><span data-stu-id="af6e3-239">Each column has a name and a type and a length.</span></span> <span data-ttu-id="af6e3-240">Ad esempio, le colonne di input nell'esempio di prezzo della casa sono **Dimensione** e **Prezzo**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-240">For example, the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="af6e3-241">Sono entrambi di tipo e sono quantità scalari piuttosto che vettoriali.</span><span class="sxs-lookup"><span data-stu-id="af6e3-241">They are both type and they are scalar quantities rather than vector ones.</span></span>

   ![Esempio di visualizzazione dati ML.NET con dati di stima dei prezzi di unità immobiliari](./media/ml-net-dataview.png)

<span data-ttu-id="af6e3-243">Tutti gli algoritmi ML.NET cercano una colonna di input che è un vettore.</span><span class="sxs-lookup"><span data-stu-id="af6e3-243">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="af6e3-244">Per impostazione predefinita questa colonna vettore è denominata **Features** (Caratteristiche).</span><span class="sxs-lookup"><span data-stu-id="af6e3-244">By default this vector column is called **Features**.</span></span> <span data-ttu-id="af6e3-245">Per questo motivo la colonna **Size** è stata concatenata in una nuova colonna denominata **Features** nell'esempio per i prezzi di unità immobiliari.</span><span class="sxs-lookup"><span data-stu-id="af6e3-245">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="af6e3-246">Tutti gli algoritmi creano a loro volta nuove colonne dopo che hanno eseguito una stima.</span><span class="sxs-lookup"><span data-stu-id="af6e3-246">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="af6e3-247">I nomi fissi di queste nuove colonne dipendono dal tipo di algoritmo di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="af6e3-247">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="af6e3-248">Per l'attività di regressione una delle nuove colonne è chiamata **Score** (Punteggio).</span><span class="sxs-lookup"><span data-stu-id="af6e3-248">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="af6e3-249">Ecco perché ai dati dei prezzi è stato assegnato un attributo con questo nome.</span><span class="sxs-lookup"><span data-stu-id="af6e3-249">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```

<span data-ttu-id="af6e3-250">Per altre informazioni sulle colonne di output delle diverse attività di apprendimento automatico, vedere [Attività di apprendimento automatico](resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="af6e3-250">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="af6e3-251">Una proprietà importante degli oggetti DataView è che vengono valutati **in modo differito**.</span><span class="sxs-lookup"><span data-stu-id="af6e3-251">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="af6e3-252">Le visualizzazioni dei dati vengono caricate ed elaborate solo durante il training e la valutazione del modello e la stima dei dati.</span><span class="sxs-lookup"><span data-stu-id="af6e3-252">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="af6e3-253">Durante la creazione e il testing dell'applicazione ML.NET è possibile usare il debugger di Visual Studio per visualizzare gli oggetti visualizzazione dati tramite la chiamata del metodo [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*).</span><span class="sxs-lookup"><span data-stu-id="af6e3-253">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="af6e3-254">È possibile visualizzare la variabile `debug` nel debugger ed esaminarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="af6e3-254">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="af6e3-255">Non usare il metodo Preview nel codice di produzione, perché riduce notevolmente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="af6e3-255">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="af6e3-256">Distribuzione del modello</span><span class="sxs-lookup"><span data-stu-id="af6e3-256">Model Deployment</span></span>

<span data-ttu-id="af6e3-257">Nelle applicazioni reali il codice di training e valutazione del modello è separato dalla stima.</span><span class="sxs-lookup"><span data-stu-id="af6e3-257">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="af6e3-258">Di fatto, queste due attività vengono spesso eseguite da team separati.</span><span class="sxs-lookup"><span data-stu-id="af6e3-258">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="af6e3-259">Il team di sviluppo del modello può salvare il modello per l'uso nell'applicazione di stima.</span><span class="sxs-lookup"><span data-stu-id="af6e3-259">Your model development team can save the model for use in the prediction application.</span></span>

```csharp
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="next-steps"></a><span data-ttu-id="af6e3-260">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="af6e3-260">Next steps</span></span>

* <span data-ttu-id="af6e3-261">Informazioni su come creare applicazioni usando diverse attività di apprendimento automatico con set di dati più realistici nelle [esercitazioni.](./tutorials/index.md)</span><span class="sxs-lookup"><span data-stu-id="af6e3-261">Learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

* <span data-ttu-id="af6e3-262">Per ulteriori informazioni, vedere Come eseguire le [guide.](./how-to-guides/index.md)</span><span class="sxs-lookup"><span data-stu-id="af6e3-262">Learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

* <span data-ttu-id="af6e3-263">Se sei super appassionato, puoi immergerti direttamente nella documentazione di [riferimento dell'API.](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)</span><span class="sxs-lookup"><span data-stu-id="af6e3-263">If you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet).</span></span>
