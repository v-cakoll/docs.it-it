---
title: Interpretare modelli ML.NET con modelli additivi generalizzati
description: Utilizzare modelli additivi generalizzati e funzioni di forma per l'interpretazione del modello in ML.NET
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 6df19eff4fec98c5815a9f8f4d8e4e9a80cba6ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77092473"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-interpretability-in-mlnet"></a>Utilizzare modelli additivi generalizzati e funzioni di forma per l'interpretazione del modello in ML.NET

Quando si creano modelli di Machine Learning, spesso non è sufficiente eseguire semplicemente stime. Spesso gli sviluppatori, i responsabili delle decisioni e gli utenti interessati ai modelli devono comprendere quali criteri vengono adottati dai modelli di Machine Learning per prendere decisioni e quali caratteristiche contribuiscono alle relative prestazioni. **I modelli additivi generalizzati (GAM, Generalized Additive Models)** vengono usati internamente a Microsoft per l'interpretazione dei modelli per consentire agli sviluppatori di apprendimento automatico di creare modelli ad alta capacità che possono essere facilmente interpretati da altri.

I modelli GAM sono una classe di **modelli interpretabili**, ovvero modelli lineari in cui i termini sono funzioni non lineari, denominate "funzioni di forma" di una singola variabile. In quanto lineari, questi modelli vengono interpretati facilmente, ma poiché apprendono funzioni relative a caratteristiche anziché a una singola ponderazione, possono modellare relazioni più complesse rispetto a un modello lineare semplice. Il modello predittivo GAM risultante ha un termine di intercetta che rappresenta la stima media relativa al set di training e funzioni di forma che rappresentano la deviazione dalla stima media. Le funzioni di forma possono essere esaminate visivamente per verificare la risposta del modello ai diversi valori di una caratteristica e possono essere rappresentate con il grafico seguente, riportato dopo l'esempio di codice. L'algoritmo di apprendimento GAM in ML.NET viene implementato usando alberi con gradient boosting, ad esempio ceppi di albero, per apprendere le funzioni di forma non parametriche ed è basato sul metodo descritto nell'articolo [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Modelli intelligibili per la classificazione e la regressione) di Lou, Caruana e Gehrke.

```csharp
// Train the Generalized Additive Model
var fitPipeline = pipeline.Fit(data);
var gamModel = fitPipeline.LastTransformer.Model;

// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
Console.WriteLine($"Average predicted cost: {intercept:0.00}");

// Get the column names from the training set
var columnNames = data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Get the index of a variable from the training data
var myFeatureIndex = columnNames.ToList().FindIndex(str => str.Equals("MyFeature"));

// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetBinEffects(myFeatureIndex);

// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
{
    Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
}
```

![Grafico delle funzioni di forma dei modelli additivi generalizzati](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

Per un esempio di come eseguire il training di un modello GAM e analizzare e interpretare i risultati, vedere il [repository dotnet/machinelearning in GitHub](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).
