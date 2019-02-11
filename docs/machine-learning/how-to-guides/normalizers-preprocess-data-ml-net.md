---
title: Pre-elaborare i dati di training con normalizzatori da usare nell'elaborazione dei dati - ML.NET
description: Informazioni su come usare i normalizzatori per pre-elaborare i dati di training da usare per la creazione del modello di Machine Learning, il training e l'assegnazione dei punteggi con ML.NET
ms.date: 02/01/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4311307f5410a96bb4a30fcedd88bc43afd25c12
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738578"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="a8be0-103">Pre-elaborare i dati di training con normalizzatori da usare nell'elaborazione dei dati - ML.NET</span><span class="sxs-lookup"><span data-stu-id="a8be0-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

<span data-ttu-id="a8be0-104">ML.NET espone alcuni [algoritmi parametrici e non parametrici](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span><span class="sxs-lookup"><span data-stu-id="a8be0-104">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="a8be0-105">La scelta del normalizzatore **non** è importante quanto l'**uso** di un normalizzatore per il training di modelli parametrici lineari o di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="a8be0-105">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="a8be0-106">Includere sempre il normalizzatore direttamente nella pipeline di apprendimento di ML.NET in modo che:</span><span class="sxs-lookup"><span data-stu-id="a8be0-106">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="a8be0-107">il training venga eseguito solo sui dati di training e non sui dati di test,</span><span class="sxs-lookup"><span data-stu-id="a8be0-107">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="a8be0-108">venga correttamente applicato a tutti i nuovi dati in ingresso, senza che siano necessarie altre operazioni di pre-elaborazione in fase di stima.</span><span class="sxs-lookup"><span data-stu-id="a8be0-108">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="a8be0-109">Di seguito è riportato un frammento di codice che illustra la normalizzazione nelle pipeline di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="a8be0-109">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="a8be0-110">Presuppone che venga usato il set di dati Iris:</span><span class="sxs-lookup"><span data-stu-id="a8be0-110">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
