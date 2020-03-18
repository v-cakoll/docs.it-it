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
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a>Calcolare la metrica per valutare la qualità del modello di Machine Learning

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per ulteriori informazioni, visita la [pagina ML.NET.](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet)

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Come si valuta la qualità dopo avere eseguito il training del modello? Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.

È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
