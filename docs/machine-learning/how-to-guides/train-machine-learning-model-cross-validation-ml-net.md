---
title: Eseguire il training di un modello di Machine Learning tramite convalida incrociata
description: Di seguito viene descritto come usare la convalida incrociata per creare modelli di Machine Learning più affidabili in ML.NET. La convalida incrociata è una tecnica di training e valutazione del modello che suddivide i dati in più partizioni ed esegue il training di più algoritmi nelle partizioni.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 87eae789478752423f3e682d4db6cead0391aa6e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976920"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a>Eseguire il training di un modello di Machine Learning tramite convalida incrociata

Di seguito viene descritto come usare la convalida incrociata per eseguire il training di modelli di Machine Learning più affidabili in ML.NET.

La convalida incrociata è una tecnica di training e valutazione del modello che suddivide i dati in più partizioni ed esegue il training di più algoritmi nelle partizioni. Questa tecnica consente di migliorare l'affidabilità del modello offrendo dati provenienti dal processo di training. Oltre a migliorare le prestazioni sulle osservazioni non visibili, in ambienti con limiti di dati può rappresentare uno strumento efficace per il training di modelli con set di dati di dimensioni minori.

## <a name="the-data-and-data-model"></a>Dati e modello di dati

Si considerino i dati di un file con il formato seguente:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

I dati possono essere modellati da una classe come `HousingData` e caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

## <a name="prepare-the-data"></a>Preparare i dati

Pre-elaborare i dati prima di usarli per creare il modello di Machine Learning. In questo esempio, le colonne `Size` e `HistoricalPrices` vengono unite in un unico vettore di funzionalità che viene restituito in una nuova colonna denominata `Features` usando il metodo [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*). Oltre a ottenere i dati nel formato previsto dagli algoritmi di ML.NET, il concatenamento delle colonne consente di ottimizzare le operazioni successive nella pipeline applicando l'operazione una sola volta per la colonna concatenata anziché per ogni colonna separata.

Dopo aver unito le colonne in un unico vettore, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) viene applicato alla colonna `Features` per ottenere `Size` e `HistoricalPrices` nello stesso intervallo compreso tra 0 e 1.

```csharp
// Define data prep estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Transform data
IDataView transformedData = dataPrepTransformer.Transform(data);
```

## <a name="train-model-with-cross-validation"></a>Eseguire il training del modello con la convalida incrociata

Dopo aver pre-elaborato i dati, è possibile procedere al training del modello. Selezionare innanzitutto l'algoritmo più allineato all'attività di Machine Learning da eseguire. Poiché il valore previsto è un valore numerico continuo, l'attività è una regressione. Uno degli algoritmi di regressione implementati da ML.NET è l'algoritmo [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer). Per eseguire il training del modello con la convalida incrociata usare il metodo [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*).

> [!NOTE]
> Anche se questo esempio usa un modello di regressione lineare, CrossValidate è applicabile a tutte le altre attività di Machine Learning in ML.NET, ad eccezione del rilevamento delle anomalie.

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) esegue le operazioni seguenti:

1. Partiziona i dati in un numero di partizioni corrispondente al valore specificato nel parametro `numberOfFolds`. Il risultato di ogni partizione è un oggetto [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData).
1. Viene eseguito il training di un modello in ogni partizione usando lo strumento di previsione dell'algoritmo di Machine Learning specificato nel training set.
1. Le prestazioni di ogni modello vengono valutate usando il metodo [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) nel set di dati di test.
1. Ogni modello viene restituito con le relative metriche.

Il risultato archiviato in `cvResults` è una raccolta di oggetti [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601). Questo oggetto include il modello con training e le metriche, entrambi accessibili rispettivamente dalle proprietà [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) e [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics). In questo esempio la proprietà `Model` è di tipo [`ITransformer`](xref:Microsoft.ML.ITransformer) e la proprietà `Metrics` è di tipo [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).

## <a name="evaluate-the-model"></a>Valutare il modello

Le metriche per i diversi modelli con training sono accessibili tramite la proprietà `Metrics` del singolo oggetto [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601). In questo caso la [metrica R quadrato](https://en.wikipedia.org/wiki/Coefficient_of_determination) è accessibile e archiviata nella variabile `rSquared`.

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

Se si esamina il contenuto della variabile `rSquared`, l'output dovrebbe essere di cinque valori compresi tra 0 e 1, dove il valore più prossimo a 1 rappresenta l'elemento migliore. Usando le metriche come R quadrato, selezionare i modelli dal modello con le prestazioni migliori al modello con le prestazioni peggiori. Quindi, selezionare il modello migliore con cui eseguire le previsioni o altre operazioni.

```csharp
// Select all models
ITransformer[] models =
    cvResults
        .OrderByDescending(fold => fold.Metrics.RSquared)
        .Select(fold => fold.Model)
        .ToArray();

// Get Top Model
ITransformer topModel = models[0];
```
