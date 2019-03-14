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
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a>Calcolare la metrica per valutare la qualità del modello di Machine Learning - ML.NET

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Come si valuta la qualità dopo avere eseguito il training del modello? Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.

È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```