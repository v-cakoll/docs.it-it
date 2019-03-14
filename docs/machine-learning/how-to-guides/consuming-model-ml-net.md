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
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Rendere operativo un modello di Machine Learning sottoposto a training nelle app - ML.NET

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

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
