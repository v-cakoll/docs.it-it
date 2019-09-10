---
title: Calcolare la metrica per valutare la qualità del modello di Machine Learning
description: Informazioni su come calcolare la metrica per valutare e verificare la qualità del modello di Machine Learning con ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 529003913b166c966e131b006800f944096605b7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855570"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a>Calcolare la metrica per valutare la qualità del modello di Machine Learning 

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per ulteriori informazioni, visitare la pagina [ml.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) .

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Come si valuta la qualità dopo avere eseguito il training del modello? Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.

È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
