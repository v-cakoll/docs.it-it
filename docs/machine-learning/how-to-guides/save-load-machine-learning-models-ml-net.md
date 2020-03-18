---
title: Salvare e caricare i modelli con training
description: Informazioni su come salvare e caricare i modelli con training
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: e3cebe979b5c279ce8cb90db5510f8758c24c2b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977001"
---
# <a name="save-and-load-trained-models"></a>Salvare e caricare i modelli con training

Di seguito viene descritto come salvare e caricare i modelli con training nell'applicazione.

Durante il processo di creazione del modello, un modello si trova in memoria ed è accessibile per l'intero ciclo di vita dell'applicazione. Tuttavia, quando l'esecuzione dell'applicazione viene arrestata, se il modello non viene salvato in una posizione locale o remota, il modello non sarà più accessibile. I modelli vengono in genere usati dopo il training in altre applicazioni per inferenza o per ripetere il training. Per questa ragione, è importante archiviare il modello. Salvare e caricare i modelli usando le procedure descritte nelle sezioni successive di questo documento quando si usano pipeline di preparazione dei dati e training dei modelli simili a quella illustrata di seguito. Anche se in questo esempio viene usato un modello di regressione lineare, lo stesso processo è valido per altri algoritmi di ML.NET.

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f, 125000f, 122000f },
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
    }
};

// Create MLContext
MLContext mlContext = new MLContext();

// Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Define data preparation estimator
EstimatorChain<RegressionPredictionTransformer<LinearRegressionModelParameters>> pipelineEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"))
        .Append(mlContext.Regression.Trainers.Sdca());

// Train model
ITransformer trainedModel = pipelineEstimator.Fit(data);

// Save model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

Poiché la maggior parte dei modelli e delle pipeline di preparazione dei dati ereditano dallo stesso set di classi, le firme del metodo di salvataggio e caricamento per questi componenti sono le stesse. A seconda del caso d'uso, è possibile combinare [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) la pipeline di [`ITransformer`](xref:Microsoft.ML.ITransformer) preparazione dei dati [`ITransformer`](xref:Microsoft.ML.ITransformer) e il modello in un unico che genererebbe un'output singola o separarli creando in modo separato per ognuno di essi.

## <a name="save-a-model-locally"></a>Salvare un modello in locale

Quando si salva un modello sono necessari due elementi:

1. Il [`ITransformer`](xref:Microsoft.ML.ITransformer) del modello.
2. L'dell'input [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) [`ITransformer`](xref:Microsoft.ML.ITransformer)previsto.

Dopo il training del [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) modello, usare il metodo `model.zip` per `DataViewSchema` salvare il modello sottoposto a training in un file chiamato usando il dati di input.

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a>Caricare un modello archiviato in locale

I modelli archiviati in locale possono essere usati in altri processi o applicazioni come `ASP.NET Core` e `Serverless Web Applications`. Per altre informazioni, vedere gli articoli su come [usare ML.NET nell'API Web](./serve-model-web-api-ml-net.md) e [distribuire l'app Web serverless ML.NET](./serve-model-serverless-azure-functions-ml-net.md).

In un'applicazione o un [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) processo separato, utilizzare il metodo insieme al percorso del file per ottenere il modello sottoposto a training nell'applicazione.

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a>Caricare un modello archiviato in remoto

Per caricare pipeline di preparazione dei dati e modelli archiviati in una posizione remota nell'applicazione, utilizzare un [`Stream`](xref:System.IO.Stream) percorso di file anziché un percorso di [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) file nel metodo.

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema and ITransformers
DataViewSchema modelSchema;
ITransformer trainedModel;

// Load data prep pipeline and trained model
using (HttpClient client = new HttpClient())
{
    Stream modelFile = await client.GetStreamAsync("<YOUR-REMOTE-FILE-LOCATION>");

    trainedModel = mlContext.Model.Load(modelFile, out modelSchema);
}
```

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a>Usare pipeline di preparazione dei dati e di modello separate

> [!NOTE]
> L'uso di pipeline di preparazione dei dati e di training del modello separate è facoltativo. La separazione delle pipeline rende più semplice esaminare i parametri di modello appresi. Per le previsioni, risulta più semplice salvare e caricare una singola pipeline che include le operazioni di preparazione dei dati e di training del modello.

Quando si usano pipeline di preparazione dei dati e modelli separati, viene applicato lo stesso processo delle pipeline singole, a meno che entrambe le pipeline non debbano essere salvate e caricate contemporaneamente.

Dopo aver specificato pipeline di preparazione dei dati e di training del modello separate:

```csharp
// Define data preparation estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data preparation transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Pre-process data using data prep operations
IDataView transformedData = dataPrepTransformer.Transform(data);

// Train regression model
RegressionPredictionTransformer<LinearRegressionModelParameters> trainedModel = sdcaEstimator.Fit(transformedData);
```

### <a name="save-data-preparation-pipeline-and-trained-model"></a>Salvare la pipeline di preparazione dei dati e il modello con training

Per salvare la pipeline di preparazione dei dati e il modello con training, usare i comandi seguenti:

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a>Caricare la pipeline di preparazione dei dati e il modello con training

In un processo o un'applicazione separata, caricare la pipeline di preparazione dei dati e il modello con training contemporaneamente come illustrato di seguito:

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
