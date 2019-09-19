---
title: Effettuare previsioni con un modello con training
description: Informazioni su come effettuare previsioni con un modello con training
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 33e0cb74342ca3e82ff5f108453d63e022d63d20
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71118014"
---
# <a name="make-predictions-with-a-trained-model"></a><span data-ttu-id="079df-103">Effettuare previsioni con un modello con training</span><span class="sxs-lookup"><span data-stu-id="079df-103">Make predictions with a trained model</span></span>

<span data-ttu-id="079df-104">Informazioni su come usare un modello con training per effettuare previsioni</span><span class="sxs-lookup"><span data-stu-id="079df-104">Learn how to use a trained model to make predictions</span></span>

## <a name="create-data-models"></a><span data-ttu-id="079df-105">Creare modelli di dati</span><span class="sxs-lookup"><span data-stu-id="079df-105">Create data models</span></span>

### <a name="input-data"></a><span data-ttu-id="079df-106">Dati di input</span><span class="sxs-lookup"><span data-stu-id="079df-106">Input data</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="output-data"></a><span data-ttu-id="079df-107">Dati di output</span><span class="sxs-lookup"><span data-stu-id="079df-107">Output data</span></span>

<span data-ttu-id="079df-108">Analogamente ai nomi delle colonne di input `Features` e `Label`, ML.NET include nomi predefiniti per le colonne di valori previsti prodotte da un modello.</span><span class="sxs-lookup"><span data-stu-id="079df-108">Like the `Features` and `Label` input column names, ML.NET has default names for the predicted value columns produced by a model.</span></span> <span data-ttu-id="079df-109">I nomi possono variare a seconda dell'attività.</span><span class="sxs-lookup"><span data-stu-id="079df-109">Depending on the task the name may differ.</span></span>

<span data-ttu-id="079df-110">Poiché l'algoritmo usato in questo esempio è un algoritmo di regressione lineare, il nome predefinito della colonna di output è `Score` definito dall'attributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) nella proprietà `PredictedPrice`.</span><span class="sxs-lookup"><span data-stu-id="079df-110">Because the algorithm used in this sample is a linear regression algorithm, the default name of the output column is `Score` which is defined by the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute on the `PredictedPrice` property.</span></span>

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a><span data-ttu-id="079df-111">Configurare una pipeline di previsione</span><span class="sxs-lookup"><span data-stu-id="079df-111">Set up a prediction pipeline</span></span>

<span data-ttu-id="079df-112">Per effettuare previsioni in batch o singole, è necessario caricare la pipeline di previsione nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="079df-112">Whether making a single or batch prediction, the prediction pipeline needs to be loaded into the application.</span></span> <span data-ttu-id="079df-113">La pipeline contiene le trasformazioni di pre-elaborazione dei dati e il modello con training.</span><span class="sxs-lookup"><span data-stu-id="079df-113">This pipeline contains both the data pre-processing transformations as well as the trained model.</span></span> <span data-ttu-id="079df-114">Il frammento di codice seguente carica la pipeline di previsione da un file denominato `model.zip`.</span><span class="sxs-lookup"><span data-stu-id="079df-114">The code snippet below loads the prediction pipeline from a file named `model.zip`.</span></span>

```csharp
//Create MLContext 
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a><span data-ttu-id="079df-115">Previsione singola</span><span class="sxs-lookup"><span data-stu-id="079df-115">Single prediction</span></span>

<span data-ttu-id="079df-116">Per effettuare una previsione singola, creare una classe [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) usando la pipeline di previsione caricata.</span><span class="sxs-lookup"><span data-stu-id="079df-116">To make a single prediction, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) using the loaded prediction pipeline.</span></span>

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

<span data-ttu-id="079df-117">Quindi usare il metodo [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) e passare i dati di input come parametro.</span><span class="sxs-lookup"><span data-stu-id="079df-117">Then, use the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method and pass in your input data as a parameter.</span></span> <span data-ttu-id="079df-118">Si noti che per usare il metodo [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) non è necessario che l'input sia [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="079df-118">Notice that using the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method does not require the input to be an [`IDataView`](xref:Microsoft.ML.IDataView)).</span></span> <span data-ttu-id="079df-119">Poiché il metodo acquisisce la modifica del tipo di dati dell'input, è possibile passare un oggetto del tipo di dati dell'input.</span><span class="sxs-lookup"><span data-stu-id="079df-119">This is because it conveniently internalizes the input data type manipulation so you can pass in an object of the input data type.</span></span> <span data-ttu-id="079df-120">Inoltre, poiché `CurrentPrice` è la destinazione o etichetta per cui si tenta di effettuare la previsione usando i nuovi dati, si presuppone che non includa ancora alcun valore.</span><span class="sxs-lookup"><span data-stu-id="079df-120">Additionally, since `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

<span data-ttu-id="079df-121">Se si accede alla proprietà `Score` dell'oggetto `prediction`, si otterrà un valore simile a `150079`.</span><span class="sxs-lookup"><span data-stu-id="079df-121">If you access the `Score` property of the `prediction` object, you should get a value similar to `150079`.</span></span>

## <a name="multiple-predictions"></a><span data-ttu-id="079df-122">Più stime</span><span class="sxs-lookup"><span data-stu-id="079df-122">Multiple predictions</span></span>

<span data-ttu-id="079df-123">Caricare i dati seguenti in [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="079df-123">Given the following data, load it into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="079df-124">In questo caso, il nome di [`IDataView`](xref:Microsoft.ML.IDataView) è `inputData`.</span><span class="sxs-lookup"><span data-stu-id="079df-124">In this case, the name of the [`IDataView`](xref:Microsoft.ML.IDataView) is `inputData`.</span></span> <span data-ttu-id="079df-125">Poiché `CurrentPrice` è la destinazione o etichetta per cui si tenta di effettuare la previsione usando i nuovi dati, si presuppone che non includa ancora alcun valore.</span><span class="sxs-lookup"><span data-stu-id="079df-125">Because `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

<span data-ttu-id="079df-126">Quindi usare il metodo [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) per applicare le trasformazioni di dati e generare le previsioni.</span><span class="sxs-lookup"><span data-stu-id="079df-126">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to apply the data transformations and generate predictions.</span></span>

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

<span data-ttu-id="079df-127">Esaminare i valori previsti usando il metodo [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).</span><span class="sxs-lookup"><span data-stu-id="079df-127">Inspect the predicted values by using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span>

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

<span data-ttu-id="079df-128">I valori previsti nella colonna di punteggio dovrebbero essere simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="079df-128">The predicted values in the score column should look like the following:</span></span>

| <span data-ttu-id="079df-129">Osservazione</span><span class="sxs-lookup"><span data-stu-id="079df-129">Observation</span></span> | <span data-ttu-id="079df-130">Previsione</span><span class="sxs-lookup"><span data-stu-id="079df-130">Prediction</span></span> |
|---|---|
| <span data-ttu-id="079df-131">1</span><span class="sxs-lookup"><span data-stu-id="079df-131">1</span></span> | <span data-ttu-id="079df-132">144638.2</span><span class="sxs-lookup"><span data-stu-id="079df-132">144638.2</span></span> |
| <span data-ttu-id="079df-133">2</span><span class="sxs-lookup"><span data-stu-id="079df-133">2</span></span> | <span data-ttu-id="079df-134">150079.4</span><span class="sxs-lookup"><span data-stu-id="079df-134">150079.4</span></span> |
| <span data-ttu-id="079df-135">3</span><span class="sxs-lookup"><span data-stu-id="079df-135">3</span></span> | <span data-ttu-id="079df-136">107789.8</span><span class="sxs-lookup"><span data-stu-id="079df-136">107789.8</span></span> |
