---
title: Esaminare i valori dei dati intermedi durante l'elaborazione della pipeline di ML.NET
description: Informazioni su come esaminare i valori effettivi dei dati intermedi durante l'elaborazione della pipeline di apprendimento automatico di ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 362cb9351c3cb77b6aa67d59154854e882869ad9
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2019
ms.locfileid: "57843416"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a>Esaminare i valori dei dati intermedi durante l'elaborazione della pipeline di ML.NET

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Durante l'esperimento è possibile osservare e convalidare i risultati dell'elaborazione dei dati in un determinato momento. Non è facile poiché le operazioni di ML.NET sono differite e costruiscono oggetti che sono "promesse" di dati.

Il metodo di estensione `GetColumn<T>` consente di esaminare i dati intermedi. Restituisce il contenuto di una colonna di dati come oggetto `IEnumerable`.

L'esempio seguente illustra l'uso del metodo di estensione `GetColumn<T>`:

[File di esempio](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):

<!-- markdownlint-disable MD010 -->
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```
<!-- markdownlint-enable MD010 -->

La classe viene definita come segue:

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
