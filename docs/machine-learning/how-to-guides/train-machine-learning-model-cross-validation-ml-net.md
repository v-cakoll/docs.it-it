---
title: Eseguire il training di un modello di Machine Learning tramite convalida incrociata
description: Di seguito viene descritto come usare la convalida incrociata per creare modelli di Machine Learning più affidabili in ML.NET. La convalida incrociata è una tecnica di training e valutazione del modello che suddivide i dati in più partizioni ed esegue il training di più algoritmi nelle partizioni.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 87eae789478752423f3e682d4db6cead0391aa6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976920"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a><span data-ttu-id="7045e-104">Eseguire il training di un modello di Machine Learning tramite convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="7045e-104">Train a machine learning model using cross validation</span></span>

<span data-ttu-id="7045e-105">Di seguito viene descritto come usare la convalida incrociata per eseguire il training di modelli di Machine Learning più affidabili in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7045e-105">Learn how to use cross validation to train more robust machine learning models in ML.NET.</span></span>

<span data-ttu-id="7045e-106">La convalida incrociata è una tecnica di training e valutazione del modello che suddivide i dati in più partizioni ed esegue il training di più algoritmi nelle partizioni.</span><span class="sxs-lookup"><span data-stu-id="7045e-106">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="7045e-107">Questa tecnica consente di migliorare l'affidabilità del modello offrendo dati provenienti dal processo di training.</span><span class="sxs-lookup"><span data-stu-id="7045e-107">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="7045e-108">Oltre a migliorare le prestazioni sulle osservazioni non visibili, in ambienti con limiti di dati può rappresentare uno strumento efficace per il training di modelli con set di dati di dimensioni minori.</span><span class="sxs-lookup"><span data-stu-id="7045e-108">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

## <a name="the-data-and-data-model"></a><span data-ttu-id="7045e-109">Dati e modello di dati</span><span class="sxs-lookup"><span data-stu-id="7045e-109">The data and data model</span></span>

<span data-ttu-id="7045e-110">Si considerino i dati di un file con il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="7045e-110">Given data from a file that has the following format:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

<span data-ttu-id="7045e-111">I dati possono essere modellati `HousingData` da una [`IDataView`](xref:Microsoft.ML.IDataView)classe come e caricati in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="7045e-111">The data can be modeled by a class like `HousingData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

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

## <a name="prepare-the-data"></a><span data-ttu-id="7045e-112">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="7045e-112">Prepare the data</span></span>

<span data-ttu-id="7045e-113">Pre-elaborare i dati prima di usarli per creare il modello di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="7045e-113">Pre-process the data before using it to build the machine learning model.</span></span> <span data-ttu-id="7045e-114">In questo `Size` esempio, `HistoricalPrices` le colonne e vengono combinate in un singolo `Features` vettore di funzionalità, che viene restituito in una nuova colonna denominata using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method .</span><span class="sxs-lookup"><span data-stu-id="7045e-114">In this sample, the `Size` and `HistoricalPrices` columns are combined into a single feature vector,  which is output to a new column called `Features` using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method.</span></span> <span data-ttu-id="7045e-115">Oltre a ottenere i dati nel formato previsto dagli algoritmi di ML.NET, il concatenamento delle colonne consente di ottimizzare le operazioni successive nella pipeline applicando l'operazione una sola volta per la colonna concatenata anziché per ogni colonna separata.</span><span class="sxs-lookup"><span data-stu-id="7045e-115">In addition to getting the data into the format expected by ML.NET algorithms, concatenating columns optimizes subsequent operations in the pipeline by applying the operation once for the concatenated column instead of each of the separate columns.</span></span>

<span data-ttu-id="7045e-116">Una volta che le colonne [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) vengono combinate `Features` in `Size` un `HistoricalPrices` singolo vettore, viene applicato alla colonna per ottenere e nello stesso intervallo compreso tra 0-1.</span><span class="sxs-lookup"><span data-stu-id="7045e-116">Once the columns are combined into a single vector, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) is applied to the `Features` column to get `Size` and `HistoricalPrices` in the same range between 0-1.</span></span>

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

## <a name="train-model-with-cross-validation"></a><span data-ttu-id="7045e-117">Eseguire il training del modello con la convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="7045e-117">Train model with cross validation</span></span>

<span data-ttu-id="7045e-118">Dopo aver pre-elaborato i dati, è possibile procedere al training del modello.</span><span class="sxs-lookup"><span data-stu-id="7045e-118">Once the data has been pre-processed, it's time to train the model.</span></span> <span data-ttu-id="7045e-119">Selezionare innanzitutto l'algoritmo più allineato all'attività di Machine Learning da eseguire.</span><span class="sxs-lookup"><span data-stu-id="7045e-119">First, select the algorithm that most closely aligns with the machine learning task to be performed.</span></span> <span data-ttu-id="7045e-120">Poiché il valore previsto è un valore numerico continuo, l'attività è una regressione.</span><span class="sxs-lookup"><span data-stu-id="7045e-120">Because the predicted value is a numerically continuous value, the task is regression.</span></span> <span data-ttu-id="7045e-121">Uno degli algoritmi di regressione [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) implementati da ML.NET è l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="7045e-121">One of the regression algorithms implemented by ML.NET is the [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) algorithm.</span></span> <span data-ttu-id="7045e-122">Per eseguire il training del [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) modello con la convalida incrociata, utilizzare il metodo .</span><span class="sxs-lookup"><span data-stu-id="7045e-122">To train the model with cross-validation use the [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) method.</span></span>

> [!NOTE]
> <span data-ttu-id="7045e-123">Anche se questo esempio usa un modello di regressione lineare, CrossValidate è applicabile a tutte le altre attività di Machine Learning in ML.NET, ad eccezione del rilevamento delle anomalie.</span><span class="sxs-lookup"><span data-stu-id="7045e-123">Although this sample uses a linear regression model, CrossValidate is applicable to all other machine learning tasks in ML.NET except Anomaly Detection.</span></span>

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

<span data-ttu-id="7045e-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*)esegue le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7045e-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) performs the following operations:</span></span>

1. <span data-ttu-id="7045e-125">Partiziona i dati in un numero di partizioni corrispondente al valore specificato nel parametro `numberOfFolds`.</span><span class="sxs-lookup"><span data-stu-id="7045e-125">Partitions the data into a number of partitions equal to the value specified in the `numberOfFolds` parameter.</span></span> <span data-ttu-id="7045e-126">Il risultato di [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) ogni partizione è un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7045e-126">The result of each partition is a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object.</span></span>
1. <span data-ttu-id="7045e-127">Viene eseguito il training di un modello in ogni partizione usando lo strumento di previsione dell'algoritmo di Machine Learning specificato nel training set.</span><span class="sxs-lookup"><span data-stu-id="7045e-127">A model is trained on each of the partitions using the specified machine learning algorithm estimator on the training data set.</span></span>
1. <span data-ttu-id="7045e-128">Le prestazioni di ogni modello [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) vengono valutate utilizzando il metodo nel set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="7045e-128">Each model's performance is evaluated using the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) method on the test data set.</span></span>
1. <span data-ttu-id="7045e-129">Ogni modello viene restituito con le relative metriche.</span><span class="sxs-lookup"><span data-stu-id="7045e-129">The model along with its metrics are returned for each of the models.</span></span>

<span data-ttu-id="7045e-130">Il risultato `cvResults` archiviato [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) in è una raccolta di oggetti.</span><span class="sxs-lookup"><span data-stu-id="7045e-130">The result stored in `cvResults` is a collection of [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) objects.</span></span> <span data-ttu-id="7045e-131">Questo oggetto include il modello sottoposto a training [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) e le metriche che sono entrambe accessibili rispettivamente nelle proprietà e .</span><span class="sxs-lookup"><span data-stu-id="7045e-131">This object includes the trained model as well as metrics which are both accessible form the [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) and [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) properties respectively.</span></span> <span data-ttu-id="7045e-132">In questo esempio `Model` la proprietà [`ITransformer`](xref:Microsoft.ML.ITransformer) è `Metrics` di tipo [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics)e la proprietà è di tipo .</span><span class="sxs-lookup"><span data-stu-id="7045e-132">In this sample, the `Model` property is of type [`ITransformer`](xref:Microsoft.ML.ITransformer) and the `Metrics` property is of type [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="7045e-133">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="7045e-133">Evaluate the model</span></span>

<span data-ttu-id="7045e-134">È possibile accedere alle metriche `Metrics` per i [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) diversi modelli sottoposti a training tramite la proprietà del singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="7045e-134">Metrics for the different trained models can be accessed through the `Metrics` property of the individual [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) object.</span></span> <span data-ttu-id="7045e-135">In questo caso la [metrica R quadrato](https://en.wikipedia.org/wiki/Coefficient_of_determination) è accessibile e archiviata nella variabile `rSquared`.</span><span class="sxs-lookup"><span data-stu-id="7045e-135">In this case, the [R-Squared metric](https://en.wikipedia.org/wiki/Coefficient_of_determination) is accessed and stored in the variable `rSquared`.</span></span>

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

<span data-ttu-id="7045e-136">Se si esamina il contenuto della variabile `rSquared`, l'output dovrebbe essere di cinque valori compresi tra 0 e 1, dove il valore più prossimo a 1 rappresenta l'elemento migliore.</span><span class="sxs-lookup"><span data-stu-id="7045e-136">If you inspect the contents of the `rSquared` variable, the output should be five values ranging from 0-1 where closer to 1 means best.</span></span> <span data-ttu-id="7045e-137">Usando le metriche come R quadrato, selezionare i modelli dal modello con le prestazioni migliori al modello con le prestazioni peggiori.</span><span class="sxs-lookup"><span data-stu-id="7045e-137">Using metrics like R-Squared, select the models from best to worst performing.</span></span> <span data-ttu-id="7045e-138">Quindi, selezionare il modello migliore con cui eseguire le previsioni o altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="7045e-138">Then, select the top model to make predictions or perform additional operations with.</span></span>

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
