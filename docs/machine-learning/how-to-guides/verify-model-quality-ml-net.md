---
title: Calcolare la metrica per valutare la qualità del modello di Machine Learning
description: Informazioni su come calcolare la metrica per valutare e verificare la qualità del modello di Machine Learning con ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2c7749205b862a42f42b857972057c441ab84364
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641102"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="e4044-103">Calcolare la metrica per valutare la qualità del modello di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="e4044-103">Calculate metrics to evaluate machine learning model quality</span></span> 

> [!NOTE]
> <span data-ttu-id="e4044-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="e4044-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="e4044-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e4044-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="e4044-106">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="e4044-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="e4044-107">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="e4044-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="e4044-108">Come si valuta la qualità dopo avere eseguito il training del modello?</span><span class="sxs-lookup"><span data-stu-id="e4044-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="e4044-109">Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.</span><span class="sxs-lookup"><span data-stu-id="e4044-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="e4044-110">È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e4044-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
