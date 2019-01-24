---
title: Usare PredictionEngine per eseguire una stima alla volta - ML.NET
description: Informazioni su come usare PredictionEngine in ML.NET per eseguire una stima alla volta
ms.date: 01/15/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 0b3f60038fe7f49ffbff3c63fd2862ba67adb506
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333642"
---
# <a name="use-the-predictionengine-to-make-one-prediction-at-a-time---mlnet"></a><span data-ttu-id="1958e-103">Usare PredictionEngine per eseguire una stima alla volta - ML.NET</span><span class="sxs-lookup"><span data-stu-id="1958e-103">Use the PredictionEngine to make one prediction at a time - ML.NET</span></span> 

<span data-ttu-id="1958e-104">Poiché qualsiasi modello ML.NET è un oggetto Transformer, si usa `model.Transform` per applicare il modello alla `DataView` al fine di eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="1958e-104">Since any ML.NET model is a transformer, you use `model.Transform` to apply the model to the `DataView` to make predictions.</span></span> 

<span data-ttu-id="1958e-105">Un caso più tipico, tuttavia, si verifica quando non è presente alcun set di dati su cui eseguire stime, ma al contrario si riceve un esempio alla volta.</span><span class="sxs-lookup"><span data-stu-id="1958e-105">A more typical case, though, is when there is no 'dataset' that you want to predict on, but instead you receive one example at a time.</span></span> <span data-ttu-id="1958e-106">Ad esempio, quando si esegue il modello come parte del sito Web ASP.NET ed è necessario eseguire una stima relativa a una richiesta HTTP in ingresso.</span><span class="sxs-lookup"><span data-stu-id="1958e-106">For instance, you run the model as part of your ASP.NET website, and need to make a prediction for an incoming HTTP request.</span></span>

<span data-ttu-id="1958e-107">`PredictionEngine` esegue un esempio alla volta tramite la pipeline di stima.</span><span class="sxs-lookup"><span data-stu-id="1958e-107">The `PredictionEngine` runs one example at a time through the prediction pipeline.</span></span>

<span data-ttu-id="1958e-108">Ecco un esempio completo in cui viene usato un modello di set di dati predefinito per la stima di iris:</span><span class="sxs-lookup"><span data-stu-id="1958e-108">Here is the full example using a prebuilt Iris prediction dataset model:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(new TextLoader.Arguments
{
    Column = new[] {
        new TextLoader.Column("SepalLength", DataKind.R4, 0),
        new TextLoader.Column("SepalWidth", DataKind.R4, 1),
        new TextLoader.Column("PetalLength", DataKind.R4, 2),
        new TextLoader.Column("PetalWidth", DataKind.R4, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    // Default separator is tab, but the dataset has comma.
    Separator = ","
});

// Retrieve the training data.
var trainData = reader.Read(irisDataPath);

// Build the training pipeline.
var pipeline =
    // Concatenate all the features together into one column 'Features'.
    mlContext.Transforms.Concatenate("Features", "SepalLength", "SepalWidth", "PetalLength", "PetalWidth")
    // Note that the label is text, so it needs to be converted to key.
    .Append(mlContext.Transforms.Categorical.MapValueToKey("Label"), TransformerScope.TrainTest)
    // Use the multi-class SDCA model to predict the label using features.
    .Append(mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent())
    // Apply the inverse conversion from 'PredictedLabel' column back to string value.
    .Append(mlContext.Transforms.Conversion.MapKeyToValue(("PredictedLabel", "Data")));

// Train the model.
var model = pipeline.Fit(trainData);
```

<span data-ttu-id="1958e-109">Per usare il meccanismo di [comprensione dello schema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) per la stima, definire una coppia di classi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1958e-109">To use [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) for prediction, define a pair of classes like the following:</span></span>

```csharp
private class IrisInput
{
    // Unfortunately, we still need the dummy 'Label' column to be present.
    [ColumnName("Label")]
    public string IgnoredLabel { get; set; }
    public float SepalLength { get; set; }
    public float SepalWidth { get; set; }
    public float PetalLength { get; set; }
    public float PetalWidth { get; set; }
}

private class IrisPrediction
{
    [ColumnName("Data")]
    public string PredictedClass { get; set; }
}
```

<span data-ttu-id="1958e-110">Il codice relativo alla stima ha ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1958e-110">The prediction code now looks as follows:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Use the model for one-time prediction.
// Make the prediction function object. Note that, on average, this call takes around 200x longer
// than one prediction, so you might want to cache and reuse the prediction engine, instead of
// creating one per prediction.
var predictionEngine = model.CreatePredictionEngine<IrisInput, IrisPrediction>(mlContext);

// Obtain the prediction. Remember that 'Predict' is not reentrant. If you want to use multiple threads
// for simultaneous prediction, make sure each thread is using its own PredictionEngine.
var prediction = predictionEngine.Predict(new IrisInput
{
    SepalLength = 4.1f,
    SepalWidth = 0.1f,
    PetalLength = 3.2f,
    PetalWidth = 1.4f
});
```
