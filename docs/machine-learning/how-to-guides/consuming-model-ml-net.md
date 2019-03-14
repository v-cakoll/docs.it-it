---
title: Rendere operativo un modello di Machine Learning sottoposto a training nelle app - ML.NET
description: Informazioni su come usare ML.NET per utilizzare un modello di Machine Learning sottoposto a training e valutato nelle applicazioni
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: be6906c939b82d00067babaeebe809dae3de413a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675134"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="6b904-103">Rendere operativo un modello di Machine Learning sottoposto a training nelle app - ML.NET</span><span class="sxs-lookup"><span data-stu-id="6b904-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="6b904-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="6b904-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="6b904-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="6b904-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="6b904-106">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="6b904-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="6b904-107">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="6b904-107">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="6b904-108">Quando le metriche del modello risultano corrette, è il momento di rendere operativo il modello.</span><span class="sxs-lookup"><span data-stu-id="6b904-108">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="6b904-109">L'oggetto `model` creato può essere utilizzato, reso persistente e riutilizzato in diversi ambienti, applicando gli stessi passaggi che ha appreso durante il training.</span><span class="sxs-lookup"><span data-stu-id="6b904-109">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="6b904-110">Per salvare il modello in un file e ricaricarlo, eventualmente in un contesto diverso, usare l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6b904-110">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

```csharp
using (var stream = File.Create(modelPath))
{
    // Saving and loading happens to 'dynamic' models.
    mlContext.Model.Save(model, stream);
}

// Potentially, the lines below can be in a different process altogether.

// When you load the model, it's a transformer.
ITransformer loadedModel;
using (var stream = File.OpenRead(modelPath))
    loadedModel = mlContext.Model.Load(stream);
```
