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
# <a name="save-and-load-trained-models"></a><span data-ttu-id="c5b5b-103">Salvare e caricare i modelli con training</span><span class="sxs-lookup"><span data-stu-id="c5b5b-103">Save and load trained models</span></span>

<span data-ttu-id="c5b5b-104">Di seguito viene descritto come salvare e caricare i modelli con training nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-104">Learn how to save and load trained models in your application.</span></span>

<span data-ttu-id="c5b5b-105">Durante il processo di creazione del modello, un modello si trova in memoria ed è accessibile per l'intero ciclo di vita dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-105">Throughout the model building process, a model lives in memory and is accessible throughout the application's lifecycle.</span></span> <span data-ttu-id="c5b5b-106">Tuttavia, quando l'esecuzione dell'applicazione viene arrestata, se il modello non viene salvato in una posizione locale o remota, il modello non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-106">However, once the application stops running, if the model is not saved somewhere locally or remotely, it's no longer accessible.</span></span> <span data-ttu-id="c5b5b-107">I modelli vengono in genere usati dopo il training in altre applicazioni per inferenza o per ripetere il training.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-107">Typically models are used at some point after training in other applications either for inference or re-training.</span></span> <span data-ttu-id="c5b5b-108">Per questa ragione, è importante archiviare il modello.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-108">Therefore, it's important to store the model.</span></span> <span data-ttu-id="c5b5b-109">Salvare e caricare i modelli usando le procedure descritte nelle sezioni successive di questo documento quando si usano pipeline di preparazione dei dati e training dei modelli simili a quella illustrata di seguito.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-109">Save and load models using the steps described in subsequent sections of this document when using data preparation and model training pipelines like the one detailed below.</span></span> <span data-ttu-id="c5b5b-110">Anche se in questo esempio viene usato un modello di regressione lineare, lo stesso processo è valido per altri algoritmi di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-110">Although this sample uses a linear regression model, the same process applies to other ML.NET algorithms.</span></span>

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

<span data-ttu-id="c5b5b-111">Poiché la maggior parte dei modelli e delle pipeline di preparazione dei dati ereditano dallo stesso set di classi, le firme del metodo di salvataggio e caricamento per questi componenti sono le stesse.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-111">Because most models and data preparation pipelines inherit from the same set of classes, the save and load method signatures for these components is the same.</span></span> <span data-ttu-id="c5b5b-112">A seconda del caso d'uso, è possibile combinare [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) la pipeline di [`ITransformer`](xref:Microsoft.ML.ITransformer) preparazione dei dati [`ITransformer`](xref:Microsoft.ML.ITransformer) e il modello in un unico che genererebbe un'output singola o separarli creando in modo separato per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-112">Depending on your use case, you can either combine the data preparation pipeline and model into a single [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) which would output a single [`ITransformer`](xref:Microsoft.ML.ITransformer) or separate them thus creating a separate [`ITransformer`](xref:Microsoft.ML.ITransformer) for each.</span></span>

## <a name="save-a-model-locally"></a><span data-ttu-id="c5b5b-113">Salvare un modello in locale</span><span class="sxs-lookup"><span data-stu-id="c5b5b-113">Save a model locally</span></span>

<span data-ttu-id="c5b5b-114">Quando si salva un modello sono necessari due elementi:</span><span class="sxs-lookup"><span data-stu-id="c5b5b-114">When saving a model you need two things:</span></span>

1. <span data-ttu-id="c5b5b-115">Il [`ITransformer`](xref:Microsoft.ML.ITransformer) del modello.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-115">The [`ITransformer`](xref:Microsoft.ML.ITransformer) of the model.</span></span>
2. <span data-ttu-id="c5b5b-116">L'dell'input [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) [`ITransformer`](xref:Microsoft.ML.ITransformer)previsto.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-116">The [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) of the [`ITransformer`](xref:Microsoft.ML.ITransformer)'s expected input.</span></span>

<span data-ttu-id="c5b5b-117">Dopo il training del [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) modello, usare il metodo `model.zip` per `DataViewSchema` salvare il modello sottoposto a training in un file chiamato usando il dati di input.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-117">After training the model, use the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) method to save the trained model to a file called `model.zip` using the `DataViewSchema` of the input data.</span></span>

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a><span data-ttu-id="c5b5b-118">Caricare un modello archiviato in locale</span><span class="sxs-lookup"><span data-stu-id="c5b5b-118">Load a model stored locally</span></span>

<span data-ttu-id="c5b5b-119">I modelli archiviati in locale possono essere usati in altri processi o applicazioni come `ASP.NET Core` e `Serverless Web Applications`.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-119">Models stored locally can be used in other processes or applications like `ASP.NET Core` and `Serverless Web Applications`.</span></span> <span data-ttu-id="c5b5b-120">Per altre informazioni, vedere gli articoli su come [usare ML.NET nell'API Web](./serve-model-web-api-ml-net.md) e [distribuire l'app Web serverless ML.NET](./serve-model-serverless-azure-functions-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="c5b5b-120">See [Use ML.NET in Web API](./serve-model-web-api-ml-net.md) and [Deploy ML.NET Serverless Web App](./serve-model-serverless-azure-functions-ml-net.md) how-to articles to learn more.</span></span>

<span data-ttu-id="c5b5b-121">In un'applicazione o un [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) processo separato, utilizzare il metodo insieme al percorso del file per ottenere il modello sottoposto a training nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-121">In a separate application or process, use the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method along with the file path to get the trained model into your application.</span></span>

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a><span data-ttu-id="c5b5b-122">Caricare un modello archiviato in remoto</span><span class="sxs-lookup"><span data-stu-id="c5b5b-122">Load a model stored remotely</span></span>

<span data-ttu-id="c5b5b-123">Per caricare pipeline di preparazione dei dati e modelli archiviati in una posizione remota nell'applicazione, utilizzare un [`Stream`](xref:System.IO.Stream) percorso di file anziché un percorso di [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) file nel metodo.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-123">To load data preparation pipelines and models stored in a remote location into your application, use a [`Stream`](xref:System.IO.Stream) instead of a file path in the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method.</span></span>

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

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a><span data-ttu-id="c5b5b-124">Usare pipeline di preparazione dei dati e di modello separate</span><span class="sxs-lookup"><span data-stu-id="c5b5b-124">Working with separate data preparation and model pipelines</span></span>

> [!NOTE]
> <span data-ttu-id="c5b5b-125">L'uso di pipeline di preparazione dei dati e di training del modello separate è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-125">Working with separate data preparation and model training pipelines is optional.</span></span> <span data-ttu-id="c5b5b-126">La separazione delle pipeline rende più semplice esaminare i parametri di modello appresi.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-126">Separation of pipelines makes it easier to inspect the learned model parameters.</span></span> <span data-ttu-id="c5b5b-127">Per le previsioni, risulta più semplice salvare e caricare una singola pipeline che include le operazioni di preparazione dei dati e di training del modello.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-127">For predictions, it's easier to save and load a single pipeline that includes the data preparation and model training operations.</span></span>

<span data-ttu-id="c5b5b-128">Quando si usano pipeline di preparazione dei dati e modelli separati, viene applicato lo stesso processo delle pipeline singole, a meno che entrambe le pipeline non debbano essere salvate e caricate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c5b5b-128">When working with separate data preparation pipelines and models, the same process as single pipelines applies; except now both pipelines need to be saved and loaded simultaneously.</span></span>

<span data-ttu-id="c5b5b-129">Dopo aver specificato pipeline di preparazione dei dati e di training del modello separate:</span><span class="sxs-lookup"><span data-stu-id="c5b5b-129">Given separate data preparation and model training pipelines:</span></span>

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

### <a name="save-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="c5b5b-130">Salvare la pipeline di preparazione dei dati e il modello con training</span><span class="sxs-lookup"><span data-stu-id="c5b5b-130">Save data preparation pipeline and trained model</span></span>

<span data-ttu-id="c5b5b-131">Per salvare la pipeline di preparazione dei dati e il modello con training, usare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5b5b-131">To save both the data preparation pipeline and trained model, use the following commands:</span></span>

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="c5b5b-132">Caricare la pipeline di preparazione dei dati e il modello con training</span><span class="sxs-lookup"><span data-stu-id="c5b5b-132">Load data preparation pipeline and trained model</span></span>

<span data-ttu-id="c5b5b-133">In un processo o un'applicazione separata, caricare la pipeline di preparazione dei dati e il modello con training contemporaneamente come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c5b5b-133">In a separate process or application, load the data preparation pipeline and trained model simultaneously as follows:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
