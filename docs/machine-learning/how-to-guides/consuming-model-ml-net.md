---
title: Rendere operativo un modello di Machine Learning sottoposto a training nelle app - ML.NET
description: Informazioni su come usare ML.NET per utilizzare un modello di Machine Learning sottoposto a training e valutato nelle applicazioni
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ff3f0a8856382d020129693bcf722f572fd87606
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131645"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="d1dfb-103">Rendere operativo un modello di Machine Learning sottoposto a training nelle app - ML.NET</span><span class="sxs-lookup"><span data-stu-id="d1dfb-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

<span data-ttu-id="d1dfb-104">Quando le metriche del modello risultano corrette, è il momento di rendere operativo il modello.</span><span class="sxs-lookup"><span data-stu-id="d1dfb-104">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="d1dfb-105">L'oggetto `model` creato può essere utilizzato, reso persistente e riutilizzato in diversi ambienti, applicando gli stessi passaggi che ha appreso durante il training.</span><span class="sxs-lookup"><span data-stu-id="d1dfb-105">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="d1dfb-106">Per salvare il modello in un file e ricaricarlo, eventualmente in un contesto diverso, usare l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1dfb-106">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

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
