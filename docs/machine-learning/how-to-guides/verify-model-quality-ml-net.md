---
title: Calcolare la metrica per valutare la qualità del modello di Machine Learning - ML.NET
description: Informazioni su come calcolare la metrica per valutare e verificare la qualità del modello di Machine Learning con ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 6fd4dfab6104b4398918e42ed70584b04169a8c1
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149523"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a>Calcolare la metrica per valutare la qualità del modello di Machine Learning - ML.NET

Come si valuta la qualità dopo avere eseguito il training del modello? Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.

È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```