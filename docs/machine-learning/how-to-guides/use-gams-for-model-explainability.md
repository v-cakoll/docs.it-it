---
title: Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli
description: Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: c58cf823007196c35da093fab7423c1e40ba1158
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855611"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a><span data-ttu-id="edd61-103">Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET</span><span class="sxs-lookup"><span data-stu-id="edd61-103">Use Generalized Additive Models and shape functions for model explainability in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="edd61-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="edd61-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="edd61-105">Per ulteriori informazioni, visitare la pagina [ml.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) .</span><span class="sxs-lookup"><span data-stu-id="edd61-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="edd61-106">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="edd61-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="edd61-107">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="edd61-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="edd61-108">Quando si creano modelli di Machine Learning, spesso non è sufficiente eseguire semplicemente stime.</span><span class="sxs-lookup"><span data-stu-id="edd61-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="edd61-109">Spesso gli sviluppatori, i responsabili delle decisioni e gli utenti interessati ai modelli devono comprendere quali criteri vengono adottati dai modelli di Machine Learning per prendere decisioni e quali caratteristiche contribuiscono alle relative prestazioni.</span><span class="sxs-lookup"><span data-stu-id="edd61-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="edd61-110">I **modelli additivi personalizzati** (GAM, Generalized Additive Model) vengono usati internamente presso Microsoft per la comprensibilità dei modelli in modo da aiutare gli sviluppatori di Machine Learning a creare modelli con capacità elevata facilmente interpretabili da altri.</span><span class="sxs-lookup"><span data-stu-id="edd61-110">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model explainability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="edd61-111">I modelli GAM sono una classe di **modelli interpretabili**, ovvero modelli lineari in cui i termini sono funzioni non lineari, denominate "funzioni di forma" di una singola variabile.</span><span class="sxs-lookup"><span data-stu-id="edd61-111">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="edd61-112">In quanto lineari, questi modelli vengono interpretati facilmente, ma poiché apprendono funzioni relative a caratteristiche anziché a una singola ponderazione, possono modellare relazioni più complesse rispetto a un modello lineare semplice.</span><span class="sxs-lookup"><span data-stu-id="edd61-112">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="edd61-113">Il modello predittivo GAM risultante ha un termine di intercetta che rappresenta la stima media relativa al set di training e funzioni di forma che rappresentano la deviazione dalla stima media.</span><span class="sxs-lookup"><span data-stu-id="edd61-113">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="edd61-114">Le funzioni di forma possono essere esaminate visivamente per verificare la risposta del modello ai diversi valori di una caratteristica e possono essere rappresentate con il grafico seguente, riportato dopo l'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="edd61-114">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="edd61-115">L'algoritmo di apprendimento GAM in ML.NET viene implementato usando alberi con gradient boosting, ad esempio ceppi di albero, per apprendere le funzioni di forma non parametriche ed è basato sul metodo descritto nell'articolo [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Modelli intelligibili per la classificazione e la regressione) di Lou, Caruana e Gehrke.</span><span class="sxs-lookup"><span data-stu-id="edd61-115">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

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

<span data-ttu-id="edd61-117">Per un esempio di come eseguire il training di un modello GAM e analizzare e interpretare i risultati, vedere il [repository dotnet/machinelearning in GitHub](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span><span class="sxs-lookup"><span data-stu-id="edd61-117">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>
