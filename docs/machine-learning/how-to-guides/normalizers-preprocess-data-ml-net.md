---
title: Pre-elaborare i dati di training con normalizzatori da usare nell'elaborazione dei dati - ML.NET
description: Informazioni su come usare i normalizzatori per pre-elaborare i dati di training da usare per la creazione del modello di Machine Learning, il training e l'assegnazione dei punteggi con ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2d18f7c19a51fd929ac6efb7f600cb1ac2733de8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676603"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>Pre-elaborare i dati di training con normalizzatori da usare nell'elaborazione dei dati - ML.NET

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

ML.NET espone alcuni [algoritmi parametrici e non parametrici](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).

La scelta del normalizzatore **non** è importante quanto l'**uso** di un normalizzatore per il training di modelli parametrici lineari o di altro tipo.

Includere sempre il normalizzatore direttamente nella pipeline di apprendimento di ML.NET in modo che:

- il training venga eseguito solo sui dati di training e non sui dati di test,
- venga correttamente applicato a tutti i nuovi dati in ingresso, senza che siano necessarie altre operazioni di pre-elaborazione in fase di stima.

Di seguito è riportato un frammento di codice che illustra la normalizzazione nelle pipeline di apprendimento. Presuppone che venga usato il set di dati Iris:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
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
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
