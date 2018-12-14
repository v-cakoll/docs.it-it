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
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Rendere operativo un modello di Machine Learning sottoposto a training nelle app - ML.NET

Quando le metriche del modello risultano corrette, è il momento di rendere operativo il modello. L'oggetto `model` creato può essere utilizzato, reso persistente e riutilizzato in diversi ambienti, applicando gli stessi passaggi che ha appreso durante il training.

Per salvare il modello in un file e ricaricarlo, eventualmente in un contesto diverso, usare l'esempio seguente:

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
