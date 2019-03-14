---
title: Calcolare la metrica per valutare la qualità del modello di Machine Learning - ML.NET
description: Informazioni su come calcolare la metrica per valutare e verificare la qualità del modello di Machine Learning con ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: ad71f7da6981ac370e60725f88d3c70b1d5c5237
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679216"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a><span data-ttu-id="2cb69-103">Calcolare la metrica per valutare la qualità del modello di Machine Learning - ML.NET</span><span class="sxs-lookup"><span data-stu-id="2cb69-103">Calculate metrics to evaluate machine learning model quality - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="2cb69-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="2cb69-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="2cb69-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2cb69-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="2cb69-106">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="2cb69-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="2cb69-107">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="2cb69-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="2cb69-108">Come si valuta la qualità dopo avere eseguito il training del modello?</span><span class="sxs-lookup"><span data-stu-id="2cb69-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="2cb69-109">Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.</span><span class="sxs-lookup"><span data-stu-id="2cb69-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="2cb69-110">È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2cb69-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```