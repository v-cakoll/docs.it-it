---
title: Determinare l'importanza delle caratteristiche dei modelli con Permutation Feature Importance in ML.NET
description: Comprendere l'importanza delle caratteristiche dei modelli con Permutation Feature Importance in ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b0457bc07168579403e5a00383864c5612e1d17f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675550"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>Determinare l'importanza delle caratteristiche dei modelli con Permutation Feature Importance in ML.NET

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Quando si creano modelli di Machine Learning, spesso non è sufficiente eseguire semplicemente stime. Spesso gli sviluppatori, i responsabili delle decisioni e gli utenti interessati ai modelli devono comprendere quali criteri vengono adottati dai modelli di Machine Learning per prendere decisioni e quali caratteristiche contribuiscono alle relative prestazioni. `Permutation Feature Importance` (PFI) è uno strumento per la comprensibilità dei modelli che viene usato internamente presso Microsoft per aiutare gli sviluppatori di Machine Learning a comprendere meglio l'importanza delle caratteristiche dei modelli.

PFI è una tecnica per determinare l'**importanza delle caratteristiche globali** in un modello di Machine Learning sottoposto a training, come spiegato da Breiman nella [sezione 10 del documento "Random Forests"](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (Foreste casuali). PFI misura l'importanza delle caratteristiche ponendo la domanda seguente: "Che effetto avrebbe sul modello l'impostazione di un valore casuale* per una caratteristica?". Il vantaggio del metodo PFI è dato dal fatto che è indipendente dal modello, ovvero funziona con qualsiasi modello che può essere valutato, e può usare qualsiasi set di dati, non solo il set di training, per calcolare l'importanza delle caratteristiche. È possibile usare PFI per generare i vari gradi di importanza delle caratteristiche, come in questo grafico:

![Grafico di Permutation Feature Importance](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

Per un esempio d'uso di PFI per analizzare l'importanza delle caratteristiche di un modello, vedere il [repository dotnet/machinelearning in GitHub](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).

/* Non esattamente casuale, ma permutato attraverso il set di esempi.
