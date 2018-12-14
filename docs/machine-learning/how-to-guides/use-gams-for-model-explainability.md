---
title: Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET
description: Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET
ms.date: 12/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 489aee34d0404293bc080b934636c01bdab92fe9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156629"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a><span data-ttu-id="6c2d6-103">Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET</span><span class="sxs-lookup"><span data-stu-id="6c2d6-103">Use Generalized Additive Models and shape functions for model explainability in ML.NET</span></span>

<span data-ttu-id="6c2d6-104">Quando si creano modelli di Machine Learning, spesso non è sufficiente eseguire semplicemente stime.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-104">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="6c2d6-105">Spesso gli sviluppatori, i responsabili delle decisioni e gli utenti interessati ai modelli devono comprendere quali criteri vengono adottati dai modelli di Machine Learning per prendere decisioni e quali caratteristiche contribuiscono alle relative prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-105">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="6c2d6-106">I **modelli additivi personalizzati** (GAM, Generalized Additive Model) vengono usati internamente presso Microsoft per la comprensibilità dei modelli in modo da aiutare gli sviluppatori di Machine Learning a creare modelli con capacità elevata facilmente interpretabili da altri.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-106">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model explainability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="6c2d6-107">I modelli GAM sono una classe di **modelli interpretabili**, ovvero modelli lineari in cui i termini sono funzioni non lineari, denominate "funzioni di forma" di una singola variabile.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-107">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="6c2d6-108">In quanto lineari, questi modelli vengono interpretati facilmente, ma poiché apprendono funzioni relative a caratteristiche anziché a una singola ponderazione, possono modellare relazioni più complesse rispetto a un modello lineare semplice.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-108">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="6c2d6-109">Il modello predittivo GAM risultante ha un termine di intercetta che rappresenta la stima media relativa al set di training e funzioni di forma che rappresentano la deviazione dalla stima media.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-109">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="6c2d6-110">Le funzioni di forma possono essere esaminate visivamente per verificare la risposta del modello ai diversi valori di una caratteristica e possono essere rappresentate con il grafico seguente, riportato dopo l'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-110">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="6c2d6-111">L'algoritmo di apprendimento GAM in ML.NET viene implementato usando alberi con gradient boosting, ad esempio ceppi di albero, per apprendere le funzioni di forma non parametriche ed è basato sul metodo descritto nell'articolo [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Modelli intelligibili per la classificazione e la regressione) di Lou, Caruana e Gehrke.</span><span class="sxs-lookup"><span data-stu-id="6c2d6-111">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

```csharp
// Train the Generalized Additive Model
var gamTrainer = mlContext.Regression.Trainers.GeneralizedAdditiveModels()
var gamModel = gamTrainer.Fit(data);
 
// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
 
// Get the feature names from the training set
var featureNames = data.Schema.GetColumns()
                .Select(tuple => tuple.column.Name) // Get the column names
                .Where(name => name != labelName) // Drop the Label
                .ToArray();
 
// Get the index of a variable from the training data
var myFeatureIndex = featureNames.ToList().FindIndex(str => str.Equals("MyFeature"));
 
// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetFeatureBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetFeatureWeights(myFeatureIndex);
 
// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
  Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
```

![Grafico delle funzioni di forma dei modelli additivi generalizzati](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

<span data-ttu-id="6c2d6-113">Per un esempio di come eseguire il training di un modello GAM e analizzare e interpretare i risultati, vedere il [repository dotnet/machinelearning in GitHub](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span><span class="sxs-lookup"><span data-stu-id="6c2d6-113">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>