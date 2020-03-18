---
title: Effettuare previsioni con un modello con training
description: Informazioni su come effettuare previsioni con un modello con training
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 182350cc5143155133385c6fd77986b271f6db91
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977037"
---
# <a name="make-predictions-with-a-trained-model"></a>Effettuare previsioni con un modello con training

Informazioni su come usare un modello con training per effettuare previsioni

## <a name="create-data-models"></a>Creare i modelli di dati

### <a name="input-data"></a>Dati di input

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

### <a name="output-data"></a>Dati di output

Analogamente ai nomi delle colonne di input `Features` e `Label`, ML.NET include nomi predefiniti per le colonne di valori previsti prodotte da un modello. I nomi possono variare a seconda dell'attività.

Poiché l'algoritmo utilizzato in questo esempio è un algoritmo di regressione lineare, il nome predefinito della colonna di output è `Score` definito dall'attributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) nella `PredictedPrice` proprietà .

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a>Configurare una pipeline di previsione

Per effettuare previsioni in batch o singole, è necessario caricare la pipeline di previsione nell'applicazione. La pipeline contiene le trasformazioni di pre-elaborazione dei dati e il modello con training. Il frammento di codice seguente carica la pipeline di previsione da un file denominato `model.zip`.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a>Previsione singola

Per eseguire una singola [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) stima, creare un usando la pipeline di stima caricata.

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

Quindi, utilizzare [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) il metodo e passare i dati di input come parametro. Si noti [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) che l'utilizzo del [`IDataView`](xref:Microsoft.ML.IDataView)metodo non richiede che l'input sia un oggetto ). Poiché il metodo acquisisce la modifica del tipo di dati dell'input, è possibile passare un oggetto del tipo di dati dell'input. Inoltre, poiché `CurrentPrice` è la destinazione o etichetta per cui si tenta di effettuare la previsione usando i nuovi dati, si presuppone che non includa ancora alcun valore.

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

Se si accede alla proprietà `Score` dell'oggetto `prediction`, si otterrà un valore simile a `150079`.

## <a name="multiple-predictions"></a>Più stime

Dati i dati seguenti, [`IDataView`](xref:Microsoft.ML.IDataView)caricarli in un file . In questo caso, il [`IDataView`](xref:Microsoft.ML.IDataView) `inputData`nome del è . Poiché `CurrentPrice` è la destinazione o etichetta per cui si tenta di effettuare la previsione usando i nuovi dati, si presuppone che non includa ancora alcun valore.

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f, 175000f, 210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

Quindi, utilizzare [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) il metodo per applicare le trasformazioni dei dati e generare stime.

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

Esaminare i valori [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) previsti utilizzando il metodo .

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

I valori previsti nella colonna di punteggio dovrebbero essere simili ai seguenti:

| Osservazione | Previsione |
|---|---|
| 1 | 144638.2 |
| 2 | 150079.4 |
| 3 | 107789.8 |
