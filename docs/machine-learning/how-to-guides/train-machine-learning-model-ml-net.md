---
title: Eseguire il training di un modello e valutarlo
description: Informazioni su come creare modelli di Machine Learning, raccogliere metriche e misurare le prestazioni con ML.NET. Un modello di Machine Learning identifica i modelli nei dati di training per eseguire stime usando nuovi dati.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 0e0f43225b9bf243c31b3095817bdcbdb3123012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976764"
---
# <a name="train-and-evaluate-a-model"></a>Eseguire il training di un modello e valutarlo

Informazioni su come creare modelli di Machine Learning, raccogliere metriche e misurare le prestazioni con ML.NET. Questo campione esegue il training di un modello di regressione. I concetti, tuttavia, sono applicabili alla maggior parte degli altri algoritmi.

## <a name="split-data-for-training-and-testing"></a>Divisione dei dati per training e test

L'obiettivo di un modello di Machine Learning è di identificare motivi all'interno dei dati di training. Questi motivi vengono usati per eseguire stime con nuovi dati.

I dati possono essere modellati in base a una classe come `HousingData`.

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

Dati i seguenti dati caricati in un [`IDataView`](xref:Microsoft.ML.IDataView)file .

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

Utilizzare [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) il metodo per suddividere i dati in set di training e test. Il risultato [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) sarà un [`IDataView`](xref:Microsoft.ML.IDataView) oggetto che contiene due membri, uno per il set di treni e l'altro per il set di test. La percentuale di suddivisione dei dati è determinata dal parametro `testFraction`. Il frammento di codice seguente contiene il 20% dei dati originali per il set di test.

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a>Preparare i dati

I dati devono essere pre-elaborati prima del training di un modello di Machine Learning. Altre informazioni sulla preparazione dei dati sono reperibili nell'[articolo sulla procedura di preparazione dei dati](prepare-data-ml-net.md), nonché in [`transforms page`](../resources/transforms.md).

Gli algoritmi ML.NET presentano vincoli per i tipi di colonna di input. Quando non viene specificato alcun valore, poi, vengono usati valori predefiniti per i nomi delle colonne di input e di output.

### <a name="working-with-expected-column-types"></a>Uso di tipi di colonna previsti

Gli algoritmi di Machine Learning in ML.NET prevedono come input un vettore float di dimensione nota. Applicare [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) l'attributo al modello di dati quando tutti i dati sono già in formato numerico ed è destinato a essere elaborato insieme (ad esempio pixel dell'immagine).

Se i dati non sono tutti numerici e si desidera applicare trasformazioni [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) di dati diverse singolarmente in ognuna delle colonne, utilizzare il metodo dopo che tutte le colonne sono state elaborate per combinare tutte le singole colonne in un singolo vettore di funzionalità che viene restituito in una nuova colonna.

Il frammento di codice seguente combina le colonne `Size` e `HistoricalPrices` in un unico vettore di funzionalità che viene restituito come output in una nuova colonna denominata `Features`. Poiché esiste una differenza [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) nelle scale, `Features` viene applicato alla colonna per normalizzare i dati.

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply transforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a>Uso di nomi di colonna predefiniti

Quando non vengono specificati nomi di colonna, gli algoritmi ML.NET usano nomi di colonna predefiniti. Tutti gli strumenti di training hanno un parametro denominato `featureColumnName` per gli input dell'algoritmo e, quando applicabile, hanno anche un parametro per il valore previsto, denominato `labelColumnName`. Per impostazione predefinita, tali valori sono rispettivamente `Features` e `Label`.

Utilizzando il [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) metodo durante la pre-elaborazione `Features`per creare una nuova colonna denominata , non è necessario specificare il `IDataView`nome della colonna della funzionalità nei parametri dell'algoritmo poiché esiste già nella pre-elaborata. La colonna `CurrentPrice`label è [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) , ma poiché l'attributo `CurrentPrice` viene `Label` utilizzato nel modello di `labelColumnName` dati, ML.NET rinomina la colonna in cui rimuove la necessità di fornire il parametro allo stimatore dell'algoritmo di apprendimento automatico.

Se non si vogliono usare i nomi di colonna predefiniti, passare i nomi delle colonne Features e Label come parametri quando si definisce la stima dell'algoritmo di Machine Learning, come illustrato dal frammento di codice seguente:

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="train-the-machine-learning-model"></a>Eseguire il training del modello di Machine Learning

Dopo aver pre-elaborato i [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) dati, usare il metodo [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) per eseguire il training del modello di apprendimento automatico con l'algoritmo di regressione.

```csharp
// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a>Estrarre i parametri del modello

Dopo aver eseguito il training [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) del modello, estrarre l'oggetto appreso per l'ispezione o la riqualificazione. I [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) coefficienti o i pesi appresi e di bias e learned del modello sottoposto a training.

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> Altri modelli hanno parametri specifici per le proprie attività. L'[algoritmo K-Means](xref:Microsoft.ML.Trainers.KMeansTrainer), ad esempio, inserisce dati in un cluster in base al baricentro e [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) contiene una proprietà che archivia i baricentri appresi. Per altre informazioni, visitare la [ `Microsoft.ML.Trainers` documentazione dell'API](xref:Microsoft.ML.Trainers) e cercare le classi che contengono `ModelParameters` nel nome.

## <a name="evaluate-model-quality"></a>Valutare la qualità del modello

Per facilitare la scelta del modello dalle prestazioni migliori, è essenziale valutarne le prestazioni su dati di test. Usare [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) il metodo per misurare varie metriche per il modello sottoposto a training.

> [!NOTE]
> Il metodo `Evaluate` genera metriche diverse a seconda dell'attività di Machine Learning eseguita. Per ulteriori dettagli, visitare la [ `Microsoft.ML.Data` documentazione dell'API](xref:Microsoft.ML.Data) e cercare le classi che contengono `Metrics` nel nome.

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

Nel codice di esempio precedente:

1. Il set di dati di test viene pre-elaborato tramite le trasformazioni di preparazione dei dati definite in precedenza.
2. Il modello di Machine Learning con training viene usato per eseguire stime sui dati di test.
3. Nel metodo `Evaluate` i valori nella colonna `CurrentPrice` del set di dati di test vengono confrontati con la colonna `Score` delle stime appena generate come output per calcolare le metriche per il modello di regressione, una delle quali, R quadrato, viene memorizzata nella variabile `rSquared`.

> [!NOTE]
> In questo breve esempio, R quadrato è un numero non compreso nell'intervallo 0-1 a causa della dimensione limitata dei dati. In uno scenario reale, si deve prevedere un valore compreso tra 0 e 1.
