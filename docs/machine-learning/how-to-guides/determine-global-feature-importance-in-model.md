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
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a><span data-ttu-id="0e7f5-103">Determinare l'importanza delle caratteristiche dei modelli con Permutation Feature Importance in ML.NET</span><span class="sxs-lookup"><span data-stu-id="0e7f5-103">Determine the feature importance of models with Permutation Feature Importance in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="0e7f5-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="0e7f5-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="0e7f5-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="0e7f5-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="0e7f5-106">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="0e7f5-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="0e7f5-107">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="0e7f5-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="0e7f5-108">Quando si creano modelli di Machine Learning, spesso non è sufficiente eseguire semplicemente stime.</span><span class="sxs-lookup"><span data-stu-id="0e7f5-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="0e7f5-109">Spesso gli sviluppatori, i responsabili delle decisioni e gli utenti interessati ai modelli devono comprendere quali criteri vengono adottati dai modelli di Machine Learning per prendere decisioni e quali caratteristiche contribuiscono alle relative prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0e7f5-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="0e7f5-110">`Permutation Feature Importance` (PFI) è uno strumento per la comprensibilità dei modelli che viene usato internamente presso Microsoft per aiutare gli sviluppatori di Machine Learning a comprendere meglio l'importanza delle caratteristiche dei modelli.</span><span class="sxs-lookup"><span data-stu-id="0e7f5-110">`Permutation Feature Importance` (PFI) is a model explainability tool that is used internally at Microsoft to help machine learning developers better understand the feature importance of models.</span></span>

<span data-ttu-id="0e7f5-111">PFI è una tecnica per determinare l'**importanza delle caratteristiche globali** in un modello di Machine Learning sottoposto a training, come spiegato da Breiman nella [sezione 10 del documento "Random Forests"](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (Foreste casuali).</span><span class="sxs-lookup"><span data-stu-id="0e7f5-111">PFI is a technique to determine **global feature importance** in a trained machine learning model, motivated by Breiman in the ["Random Forests" paper, section 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span></span> <span data-ttu-id="0e7f5-112">PFI misura l'importanza delle caratteristiche ponendo la domanda seguente: "Che effetto avrebbe sul modello l'impostazione di un valore casuale\* per una caratteristica?".</span><span class="sxs-lookup"><span data-stu-id="0e7f5-112">PFI measures feature importance by asking the question, "What would the effect on the model be if the values for a feature were set to a random\* value?".</span></span> <span data-ttu-id="0e7f5-113">Il vantaggio del metodo PFI è dato dal fatto che è indipendente dal modello, ovvero funziona con qualsiasi modello che può essere valutato, e può usare qualsiasi set di dati, non solo il set di training, per calcolare l'importanza delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="0e7f5-113">The advantage of the PFI method is that it is model agnostic — it works with any model that can be evaluated — and it can use any dataset, not just the training set, to compute feature importance.</span></span> <span data-ttu-id="0e7f5-114">È possibile usare PFI per generare i vari gradi di importanza delle caratteristiche, come in questo grafico:</span><span class="sxs-lookup"><span data-stu-id="0e7f5-114">You can use PFI like so to produce feature importances like this graph:</span></span>

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

<span data-ttu-id="0e7f5-116">Per un esempio d'uso di PFI per analizzare l'importanza delle caratteristiche di un modello, vedere il [repository dotnet/machinelearning in GitHub](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span><span class="sxs-lookup"><span data-stu-id="0e7f5-116">For a sample using PFI to analyze the feature importance of a model, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span></span>

<span data-ttu-id="0e7f5-117">/\* Non esattamente casuale, ma permutato attraverso il set di esempi.</span><span class="sxs-lookup"><span data-stu-id="0e7f5-117">/\* Well, not random exactly, but permuted across the set of examples.</span></span>
