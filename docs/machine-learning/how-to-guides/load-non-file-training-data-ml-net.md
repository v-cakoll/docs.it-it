---
title: Eseguire il training di un modello di Machine Learning con dati non contenuti in un file di testo - ML.NET
description: Informazioni sull'uso di ML.NET per caricare dati di training non basati su file per il training di un modello di Machine Learning nell'ambito della pipeline di stima.
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4ffbc69629aa9dc6cea5d33c704bc9c57a4a612c
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092020"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a>Eseguire il training di un modello di Machine Learning con dati non contenuti in un file di testo - ML.NET

Nel caso d'uso solitamente illustrato per ML.NET viene usato `TextLoader` per la lettura dei dati di training da un file.
In scenari di training in tempo reale, tuttavia, i dati possono trovarsi altrove. Ad esempio:

* in tabelle SQL
* estratti dai file di log
* generati al momento

Usare la [comprensione dello schema](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) per portare un elemento `IEnumerable` C# esistente in ML.NET come elemento `DataView`.

Per questo esempio verrà creato il modello di stima della varianza del cliente e verranno estratte dal sistema di produzione le funzionalità seguenti:

* L'ID cliente (ignorato dal modello)
* L'eventuale varianza del cliente ("etichetta" di destinazione)
* La "categoria demografica" (una stringa, ad esempio "giovane adulto" o altro)
* Il numero di visite degli ultimi 5 giorni.

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

Caricare questi dati in `DataView` ed eseguire il training del modello usando il codice seguente:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.Data.ReadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
