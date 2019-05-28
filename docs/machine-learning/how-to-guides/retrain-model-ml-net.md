---
title: Ripetere il training di un modello
description: Informazioni su come ripetere il training di un modello in ML.NET
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2f8f8c035166612aabede8a512485bdf296c5655
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557913"
---
# <a name="re-train-a-model"></a><span data-ttu-id="2634d-103">Ripetere il training di un modello</span><span class="sxs-lookup"><span data-stu-id="2634d-103">Re-train a model</span></span>

<span data-ttu-id="2634d-104">Informazioni su come ripetere il training di un modello di Machine Learning in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2634d-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="2634d-105">Il mondo e i dati presenti in ogni sua parte cambiano a un ritmo costante.</span><span class="sxs-lookup"><span data-stu-id="2634d-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="2634d-106">Di conseguenza, è necessario modificare e aggiornare anche i modelli.</span><span class="sxs-lookup"><span data-stu-id="2634d-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="2634d-107">ML.NET offre funzionalità per ripetere il training dei modelli usando i parametri del modello appreso come punto di partenza per continuare a sfruttare le esperienze precedenti anziché iniziare ogni volta da zero.</span><span class="sxs-lookup"><span data-stu-id="2634d-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>  

<span data-ttu-id="2634d-108">In ML.NET è possibile ripetere il training degli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2634d-108">The following algorithms are re-trainable in ML.NET:</span></span>

- [<span data-ttu-id="2634d-109">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-109">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [<span data-ttu-id="2634d-110">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-110">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [<span data-ttu-id="2634d-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="2634d-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="2634d-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="2634d-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [<span data-ttu-id="2634d-115">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-115">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [<span data-ttu-id="2634d-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="2634d-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="2634d-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="2634d-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="2634d-119">Caricare il modello con training preliminare</span><span class="sxs-lookup"><span data-stu-id="2634d-119">Load pre-trained model</span></span>

<span data-ttu-id="2634d-120">Caricare prima il modello con training preliminare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2634d-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="2634d-121">Per altre informazioni su come caricare pipeline e modelli di training, vedere il relativo [articolo sulla procedura](./consuming-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="2634d-121">To learn more about loading training pipelines and models, see the related [how-to article](./consuming-model-ml-net.md).</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data prepration pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="2634d-122">Estrarre i parametri del modello con training preliminare</span><span class="sxs-lookup"><span data-stu-id="2634d-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="2634d-123">Dopo aver caricato il modello, estrarre i parametri del modello appreso accedendo alla proprietà [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) del modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="2634d-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) property of the pre-trained model.</span></span> <span data-ttu-id="2634d-124">Il modello con training preliminare era stato sottoposto a training usando il modello di regressione lineare [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) che crea una classe [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) che restituisce [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span><span class="sxs-lookup"><span data-stu-id="2634d-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a[`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="2634d-125">Questi parametri del modello di regressione lineare contengono la distorsione e i pesi o i coefficienti appresi del modello.</span><span class="sxs-lookup"><span data-stu-id="2634d-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="2634d-126">Questi valori verranno usati come punto di partenza per il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="2634d-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters = 
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="2634d-127">Ripetere il training del modello</span><span class="sxs-lookup"><span data-stu-id="2634d-127">Re-train model</span></span>

<span data-ttu-id="2634d-128">Il processo di ripetizione del training di un modello non è diverso da quello di training di un modello.</span><span class="sxs-lookup"><span data-stu-id="2634d-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="2634d-129">L'unica differenza sta nel fatto che oltre ai dati, il metodo [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) acquisisce come input anche i parametri del modello appreso originale e li usa come punto di partenza nel processo di ripetizione del training.</span><span class="sxs-lookup"><span data-stu-id="2634d-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>  

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel = 
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a><span data-ttu-id="2634d-130">Confrontare i parametri del modello</span><span class="sxs-lookup"><span data-stu-id="2634d-130">Compare model parameters</span></span>

<span data-ttu-id="2634d-131">Come si può verificare che il training sia stato effettivamente ripetuto?</span><span class="sxs-lookup"><span data-stu-id="2634d-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="2634d-132">Un modo per verificarlo è confrontare i parametri del modello di cui si è ripetuto il training con quelli del modello originale e vedere se sono diversi.</span><span class="sxs-lookup"><span data-stu-id="2634d-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="2634d-133">Il codice di esempio riportato di seguito confronta i pesi del modello originale con quelli del modello di nuovo sottoposto a training e li visualizza nella console.</span><span class="sxs-lookup"><span data-stu-id="2634d-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs = 
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

<span data-ttu-id="2634d-134">La tabella seguente illustra il possibile output.</span><span class="sxs-lookup"><span data-stu-id="2634d-134">The table below shows what the output might look like.</span></span> 

|<span data-ttu-id="2634d-135">Originale</span><span class="sxs-lookup"><span data-stu-id="2634d-135">Original</span></span> | <span data-ttu-id="2634d-136">Training ripetuto</span><span class="sxs-lookup"><span data-stu-id="2634d-136">Retrained</span></span> | <span data-ttu-id="2634d-137">Differenza</span><span class="sxs-lookup"><span data-stu-id="2634d-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="2634d-138">33039.86</span><span class="sxs-lookup"><span data-stu-id="2634d-138">33039.86</span></span> | <span data-ttu-id="2634d-139">56293.76</span><span class="sxs-lookup"><span data-stu-id="2634d-139">56293.76</span></span> | <span data-ttu-id="2634d-140">-23253.9</span><span class="sxs-lookup"><span data-stu-id="2634d-140">-23253.9</span></span> |
| <span data-ttu-id="2634d-141">29099.14</span><span class="sxs-lookup"><span data-stu-id="2634d-141">29099.14</span></span> | <span data-ttu-id="2634d-142">49586.03</span><span class="sxs-lookup"><span data-stu-id="2634d-142">49586.03</span></span> | <span data-ttu-id="2634d-143">-20486.89</span><span class="sxs-lookup"><span data-stu-id="2634d-143">-20486.89</span></span> |
| <span data-ttu-id="2634d-144">28938.38</span><span class="sxs-lookup"><span data-stu-id="2634d-144">28938.38</span></span> | <span data-ttu-id="2634d-145">48609.23</span><span class="sxs-lookup"><span data-stu-id="2634d-145">48609.23</span></span> | <span data-ttu-id="2634d-146">-19670.85</span><span class="sxs-lookup"><span data-stu-id="2634d-146">-19670.85</span></span> |
| <span data-ttu-id="2634d-147">30484.02</span><span class="sxs-lookup"><span data-stu-id="2634d-147">30484.02</span></span> | <span data-ttu-id="2634d-148">53745.43</span><span class="sxs-lookup"><span data-stu-id="2634d-148">53745.43</span></span> | <span data-ttu-id="2634d-149">-23261.41</span><span class="sxs-lookup"><span data-stu-id="2634d-149">-23261.41</span></span> |