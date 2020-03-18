---
title: Calcolare la metrica per valutare la qualità del modello di Machine Learning
description: Informazioni su come calcolare la metrica per valutare e verificare la qualità del modello di Machine Learning con ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: d6409307cd283ae67d7546c4dc6e19e6089a0766
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73975833"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="0d52f-103">Calcolare la metrica per valutare la qualità del modello di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="0d52f-103">Calculate metrics to evaluate machine learning model quality</span></span>

> [!NOTE]
> <span data-ttu-id="0d52f-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="0d52f-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="0d52f-105">Per ulteriori informazioni, visita la [pagina ML.NET.](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet)</span><span class="sxs-lookup"><span data-stu-id="0d52f-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="0d52f-106">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="0d52f-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="0d52f-107">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="0d52f-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="0d52f-108">Come si valuta la qualità dopo avere eseguito il training del modello?</span><span class="sxs-lookup"><span data-stu-id="0d52f-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="0d52f-109">Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.</span><span class="sxs-lookup"><span data-stu-id="0d52f-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="0d52f-110">È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0d52f-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
