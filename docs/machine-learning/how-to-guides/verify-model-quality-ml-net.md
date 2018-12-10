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
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a><span data-ttu-id="dccc7-103">Calcolare la metrica per valutare la qualità del modello di Machine Learning - ML.NET</span><span class="sxs-lookup"><span data-stu-id="dccc7-103">Calculate metrics to evaluate machine learning model quality - ML.NET</span></span>

<span data-ttu-id="dccc7-104">Come si valuta la qualità dopo avere eseguito il training del modello?</span><span class="sxs-lookup"><span data-stu-id="dccc7-104">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="dccc7-105">Ogni attività di Machine Learning espone la metrica per la valutazione della qualità.</span><span class="sxs-lookup"><span data-stu-id="dccc7-105">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="dccc7-106">È possibile usare il "contesto" corrispondente dell'attività per valutare il modello, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dccc7-106">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```