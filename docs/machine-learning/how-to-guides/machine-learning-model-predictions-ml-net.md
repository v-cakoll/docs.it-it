---
title: Effettuare previsioni con un modello con training
description: Informazioni su come effettuare previsioni con un modello con training
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: dac3b3bfa68776975a2e5e762f46db16e39d61fb
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065604"
---
# <a name="make-predictions-with-a-trained-model"></a>Effettuare previsioni con un modello con training

Informazioni su come usare un modello con training per effettuare previsioni

## <a name="create-data-models"></a>Creare modelli di dati

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

Poiché l'algoritmo usato in questo esempio è un algoritmo di regressione lineare, il nome predefinito della colonna di output è `Score` definito dall'attributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) nella proprietà `PredictedPrice`.

```csharp
class HousingPrediction : HousingData
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

Il modello di dati `HousingPrediction` eredita da `HousingData` per rendere più semplice la visualizzazione dei dati di input originali con l'output generato dal modello.  

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

Per effettuare una previsione singola, creare una classe [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) usando la pipeline di previsione caricata.

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

Quindi usare il metodo [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) e passare i dati di input come parametro. Si noti che per usare il metodo [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) non è necessario che l'input sia [`IDataView`](xref:Microsoft.ML.IDataView). Poiché il metodo acquisisce la modifica del tipo di dati dell'input, è possibile passare un oggetto del tipo di dati dell'input. Inoltre, poiché `CurrentPrice` è la destinazione o etichetta per cui si tenta di effettuare la previsione usando i nuovi dati, si presuppone che non includa ancora alcun valore.

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

## <a name="batch-prediction"></a>Previsione in batch

Caricare i dati seguenti in [`IDataView`](xref:Microsoft.ML.IDataView). Poiché `CurrentPrice` è la destinazione o etichetta per cui si tenta di effettuare la previsione usando i nuovi dati, si presuppone che non includa ancora alcun valore.

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f }
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

Quindi usare il metodo [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) per applicare le trasformazioni di dati e generare le previsioni.

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

Esaminare i valori previsti usando il metodo [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).

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
