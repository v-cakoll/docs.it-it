---
title: Come usare l'API di Machine Learning automatizzato per ML.NET
description: L'API di Machine Learning automatizzato per ML.NET consente di automatizzare il processo di compilazione del modello e genera un modello pronto per la distribuzione. Sono disponibili varie opzioni per configurare attività di Machine Learning automatizzato.
ms.date: 11/7/2019
ms.custom: mvc,how-to
ms.openlocfilehash: c1c18decc48bc1499aa55210becff305cdec4a53
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977126"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="da1ca-104">Come usare l'API di Machine Learning automatizzato per ML.NET</span><span class="sxs-lookup"><span data-stu-id="da1ca-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="da1ca-105">Il Machine Learning automatizzato (AutoML) consente di automatizzare il processo di applicazione dell'apprendimento automatico ai dati.</span><span class="sxs-lookup"><span data-stu-id="da1ca-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="da1ca-106">A partire da un set di dati è possibile eseguire un **esperimento** AutoML per eseguire l'iterazione su varie estrazioni delle caratteristiche dei dati, algoritmi di apprendimento automatico e iperparametri, allo scopo di selezionare il modello ottimale.</span><span class="sxs-lookup"><span data-stu-id="da1ca-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="da1ca-107">Questo argomento riguarda l'API di Machine Learning automatizzato per ML.NET, che è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="da1ca-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="da1ca-108">Il materiale potrà essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="da1ca-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="da1ca-109">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="da1ca-109">Load data</span></span>

<span data-ttu-id="da1ca-110">Il Machine Learning automatizzato supporta il caricamento di un set di dati in un elemento [IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="da1ca-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="da1ca-111">I dati possono essere sotto forma di file di valori delimitati da tabulazioni (con estensione tsv) e file di valori delimitati da virgole (con estensione csv).</span><span class="sxs-lookup"><span data-stu-id="da1ca-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="da1ca-112">Esempio:</span><span class="sxs-lookup"><span data-stu-id="da1ca-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="da1ca-113">Selezionare il tipo di attività di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="da1ca-113">Select the machine learning task type</span></span>

<span data-ttu-id="da1ca-114">Prima di creare un esperimento, determinare il tipo di problema di apprendimento automatico da risolvere.</span><span class="sxs-lookup"><span data-stu-id="da1ca-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="da1ca-115">Il Machine Learning automatizzato supporta le seguenti attività di apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="da1ca-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="da1ca-116">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="da1ca-116">Binary Classification</span></span>
* <span data-ttu-id="da1ca-117">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="da1ca-117">Multiclass Classification</span></span>
* <span data-ttu-id="da1ca-118">Regressione</span><span class="sxs-lookup"><span data-stu-id="da1ca-118">Regression</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="da1ca-119">Creare le impostazioni dell'esperimento</span><span class="sxs-lookup"><span data-stu-id="da1ca-119">Create experiment settings</span></span>

<span data-ttu-id="da1ca-120">Creare le impostazioni dell'esperimento per il tipo specifico di attività di apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="da1ca-120">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="da1ca-121">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="da1ca-121">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="da1ca-122">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="da1ca-122">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="da1ca-123">Regressione</span><span class="sxs-lookup"><span data-stu-id="da1ca-123">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="da1ca-124">Configurare le impostazioni dell'esperimento</span><span class="sxs-lookup"><span data-stu-id="da1ca-124">Configure experiment settings</span></span>

<span data-ttu-id="da1ca-125">Gli esperimenti sono ampiamente configurabili.</span><span class="sxs-lookup"><span data-stu-id="da1ca-125">Experiments are highly configurable.</span></span> <span data-ttu-id="da1ca-126">Vedere la [documentazione dell'API AutoML](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) per un elenco completo delle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="da1ca-126">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) for a full list of configuration settings.</span></span>

<span data-ttu-id="da1ca-127">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="da1ca-127">Some examples include:</span></span>

1. <span data-ttu-id="da1ca-128">Specificare il tempo massimo per il quale eseguire l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="da1ca-128">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="da1ca-129">Usare un token di annullamento per annullare l'esperimento prima della fine pianificata.</span><span class="sxs-lookup"><span data-stu-id="da1ca-129">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="da1ca-130">Specificare una metrica di ottimizzazione diversa.</span><span class="sxs-lookup"><span data-stu-id="da1ca-130">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="da1ca-131">L'impostazione `CacheDirectory` è un puntatore a una directory in cui verranno salvati tutti i modelli sottoposti a training durante l'attività AutoML.</span><span class="sxs-lookup"><span data-stu-id="da1ca-131">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="da1ca-132">Se `CacheDirectory` è null i modelli verranno mantenuti nella memoria anziché salvati su disco.</span><span class="sxs-lookup"><span data-stu-id="da1ca-132">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="da1ca-133">Indicare al Machine Learning automatizzato di non usare determinati algoritmi di training.</span><span class="sxs-lookup"><span data-stu-id="da1ca-133">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="da1ca-134">Per ogni attività viene preso in esame un elenco predefinito di algoritmi di training per l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="da1ca-134">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="da1ca-135">Questo elenco può essere modificato per ogni esperimento.</span><span class="sxs-lookup"><span data-stu-id="da1ca-135">This list can be modified for each experiment.</span></span> <span data-ttu-id="da1ca-136">Ad esempio gli algoritmi di training che vengono eseguiti troppo lentamente sul set di dati possono essere rimossi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="da1ca-136">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="da1ca-137">Per eseguire l'ottimizzazione relativa a un algoritmo di training specifico chiamare `experimentSettings.Trainers.Clear()`, quindi aggiungere l'algoritmo di training che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="da1ca-137">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="da1ca-138">L'elenco degli algoritmi di training supportati per ogni attività di apprendimento automatico è disponibile nel collegamento corrispondente riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="da1ca-138">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="da1ca-139">Algoritmi di classificazione binaria supportati</span><span class="sxs-lookup"><span data-stu-id="da1ca-139">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="da1ca-140">Algoritmi di classificazione multiclasse supportati</span><span class="sxs-lookup"><span data-stu-id="da1ca-140">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="da1ca-141">Algoritmi di regressione supportati</span><span class="sxs-lookup"><span data-stu-id="da1ca-141">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="da1ca-142">Metrica di ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="da1ca-142">Optimizing metric</span></span>

<span data-ttu-id="da1ca-143">Come illustrato nell'esempio precedente, la metrica di ottimizzazione determina la metrica da ottimizzare durante il training del modello.</span><span class="sxs-lookup"><span data-stu-id="da1ca-143">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="da1ca-144">La metrica di ottimizzazione selezionabile è determinata dal tipo di attività scelto.</span><span class="sxs-lookup"><span data-stu-id="da1ca-144">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="da1ca-145">Ecco un elenco delle metriche disponibili.</span><span class="sxs-lookup"><span data-stu-id="da1ca-145">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="da1ca-146">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="da1ca-146">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="da1ca-147">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="da1ca-147">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="da1ca-148">Regressione</span><span class="sxs-lookup"><span data-stu-id="da1ca-148">Regression</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="da1ca-149">Accuratezza</span><span class="sxs-lookup"><span data-stu-id="da1ca-149">Accuracy</span></span>| <span data-ttu-id="da1ca-150">LogLoss</span><span class="sxs-lookup"><span data-stu-id="da1ca-150">LogLoss</span></span> | <span data-ttu-id="da1ca-151">RSquared</span><span class="sxs-lookup"><span data-stu-id="da1ca-151">RSquared</span></span>
|<span data-ttu-id="da1ca-152">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="da1ca-152">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="da1ca-153">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="da1ca-153">LogLossReduction</span></span> | <span data-ttu-id="da1ca-154">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="da1ca-154">MeanAbsoluteError</span></span>
|<span data-ttu-id="da1ca-155">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="da1ca-155">AreaUnderRocCurve</span></span> | <span data-ttu-id="da1ca-156">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="da1ca-156">MacroAccuracy</span></span> | <span data-ttu-id="da1ca-157">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="da1ca-157">MeanSquaredError</span></span>
|<span data-ttu-id="da1ca-158">F1Score</span><span class="sxs-lookup"><span data-stu-id="da1ca-158">F1Score</span></span> | <span data-ttu-id="da1ca-159">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="da1ca-159">MicroAccuracy</span></span> | <span data-ttu-id="da1ca-160">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="da1ca-160">RootMeanSquaredError</span></span>
|<span data-ttu-id="da1ca-161">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="da1ca-161">NegativePrecision</span></span> | <span data-ttu-id="da1ca-162">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="da1ca-162">TopKAccuracy</span></span>
|<span data-ttu-id="da1ca-163">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="da1ca-163">NegativeRecall</span></span> |
|<span data-ttu-id="da1ca-164">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="da1ca-164">PositivePrecision</span></span>
|<span data-ttu-id="da1ca-165">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="da1ca-165">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="da1ca-166">Preelaborazione dati ed estrazione caratteristiche</span><span class="sxs-lookup"><span data-stu-id="da1ca-166">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="da1ca-167">La colonna feature supporta solo tipi di <xref:System.Boolean>, <xref:System.Single>e <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="da1ca-167">The feature column only supported types of <xref:System.Boolean>, <xref:System.Single>, and <xref:System.String>.</span></span>

<span data-ttu-id="da1ca-168">La preelaborazione dei dati si verifica per impostazione predefinita e i passaggi seguenti vengono eseguiti automaticamente:</span><span class="sxs-lookup"><span data-stu-id="da1ca-168">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="da1ca-169">Rimozione delle caratteristiche prive di informazioni utili</span><span class="sxs-lookup"><span data-stu-id="da1ca-169">Drop features with no useful information</span></span>

    <span data-ttu-id="da1ca-170">Le caratteristiche prive informazioni utili vengono rimosse da set di training e convalida.</span><span class="sxs-lookup"><span data-stu-id="da1ca-170">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="da1ca-171">Queste includono le caratteristiche con tutti i valori mancanti, con lo stesso valore in tutte le righe o con una cardinalità molto elevata (ad esempio hash, ID o GUID).</span><span class="sxs-lookup"><span data-stu-id="da1ca-171">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="da1ca-172">Indicazione e marcatura dei valori mancanti</span><span class="sxs-lookup"><span data-stu-id="da1ca-172">Missing value indication and imputation</span></span>

    <span data-ttu-id="da1ca-173">Riempimento delle celle con valore mancante con il valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="da1ca-173">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="da1ca-174">Aggiunta di caratteristiche indicatore con lo stesso numero di slot della colonna di input.</span><span class="sxs-lookup"><span data-stu-id="da1ca-174">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="da1ca-175">Il valore nelle caratteristiche indicatore accodate è `1` se il valore nella colonna di input è mancante e `0` negli altri casi.</span><span class="sxs-lookup"><span data-stu-id="da1ca-175">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="da1ca-176">Generare caratteristiche aggiuntive</span><span class="sxs-lookup"><span data-stu-id="da1ca-176">Generate additional features</span></span>

    <span data-ttu-id="da1ca-177">Per le funzionalità di testo: funzionalità del contenitore di Word che usano unigrammi e Tri-character-grams.</span><span class="sxs-lookup"><span data-stu-id="da1ca-177">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>

    <span data-ttu-id="da1ca-178">Per le funzionalità categoriche: codifica One-Hot per le funzionalità di cardinalità bassa e codifica One-Hot-hash per le funzionalità categoriche con cardinalità elevata.</span><span class="sxs-lookup"><span data-stu-id="da1ca-178">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="da1ca-179">Trasformazioni e codifiche</span><span class="sxs-lookup"><span data-stu-id="da1ca-179">Transformations and encodings</span></span>

    <span data-ttu-id="da1ca-180">Caratteristiche di testo con un numero molto ridotto di valori univoci trasformate in caratteristiche categoriche.</span><span class="sxs-lookup"><span data-stu-id="da1ca-180">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="da1ca-181">A seconda della cardinalità delle caratteristiche categoriche, viene eseguita la codifica one-hot o la codifica hash one-hot.</span><span class="sxs-lookup"><span data-stu-id="da1ca-181">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="da1ca-182">Criteri uscita</span><span class="sxs-lookup"><span data-stu-id="da1ca-182">Exit criteria</span></span>

<span data-ttu-id="da1ca-183">Definire i criteri per completare l'attività:</span><span class="sxs-lookup"><span data-stu-id="da1ca-183">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="da1ca-184">Uscita dopo un periodo di tempo: se si usa `MaxExperimentTimeInSeconds` nelle impostazioni dell'esperimento, è possibile definire la durata dell'esecuzione dell'attività in secondi.</span><span class="sxs-lookup"><span data-stu-id="da1ca-184">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="da1ca-185">Uscita in corrispondenza di un token di annullamento:  è possibile usare un  token di annullamento che consente di annullare l'attività prima della fine pianificata.</span><span class="sxs-lookup"><span data-stu-id="da1ca-185">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="da1ca-186">Creare un esperimento</span><span class="sxs-lookup"><span data-stu-id="da1ca-186">Create an experiment</span></span>

<span data-ttu-id="da1ca-187">Dopo aver configurato le impostazioni dell'esperimento si è pronti per creare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="da1ca-187">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="da1ca-188">Eseguire l'esperimento</span><span class="sxs-lookup"><span data-stu-id="da1ca-188">Run the experiment</span></span>

<span data-ttu-id="da1ca-189">L'esecuzione dell'esperimento attiva la preelaborazione dei dati, la selezione dell'algoritmo di apprendimento e l'ottimizzazione degli iperparametri.</span><span class="sxs-lookup"><span data-stu-id="da1ca-189">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="da1ca-190">AutoML continua a generare combinazioni di estrazione caratteristiche, algoritmi di apprendimento automatico e iperparametri fino a quando non viene raggiunto `MaxExperimentTimeInSeconds` o viene terminato l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="da1ca-190">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="da1ca-191">Esplorare altri overload per `Execute()` se si vuole passare dati di convalida, informazioni di colonna che indicano lo scopo della colonna o preestrattori di caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="da1ca-191">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="da1ca-192">Modalità di training</span><span class="sxs-lookup"><span data-stu-id="da1ca-192">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="da1ca-193">Dataset di training</span><span class="sxs-lookup"><span data-stu-id="da1ca-193">Training dataset</span></span>

<span data-ttu-id="da1ca-194">AutoML include un metodo di esecuzione dell'esperimento con overload che consente di specificare dati di training.</span><span class="sxs-lookup"><span data-stu-id="da1ca-194">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="da1ca-195">A livello interno, il Machine Learning automatizzato suddivide i dati in gruppi train-validate (training-convalida).</span><span class="sxs-lookup"><span data-stu-id="da1ca-195">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="da1ca-196">Set di dati di convalida personalizzato</span><span class="sxs-lookup"><span data-stu-id="da1ca-196">Custom validation dataset</span></span>

<span data-ttu-id="da1ca-197">Se la suddivisione casuale non è accettabile, come avviene in genere con i dati di serie temporali, usare un set di dati di convalida personalizzato.</span><span class="sxs-lookup"><span data-stu-id="da1ca-197">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="da1ca-198">È possibile specificare il proprio set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="da1ca-198">You can specify your own validation dataset.</span></span> <span data-ttu-id="da1ca-199">Il modello verrà valutato rispetto al set di dati di convalida specificato anziché rispetto a uno o più set di dati casuali.</span><span class="sxs-lookup"><span data-stu-id="da1ca-199">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a><span data-ttu-id="da1ca-200">Esplorare le metriche del modello</span><span class="sxs-lookup"><span data-stu-id="da1ca-200">Explore model metrics</span></span>

<span data-ttu-id="da1ca-201">Dopo ogni iterazione di un esperimento ML vengono archiviate le metriche relative a tale attività.</span><span class="sxs-lookup"><span data-stu-id="da1ca-201">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="da1ca-202">Ad esempio è possibile accedere alle metriche di convalida dalla migliore esecuzione:</span><span class="sxs-lookup"><span data-stu-id="da1ca-202">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="da1ca-203">Di seguito sono elencate tutte le metriche disponibili per attività ML:</span><span class="sxs-lookup"><span data-stu-id="da1ca-203">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="da1ca-204">Metriche di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="da1ca-204">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="da1ca-205">Metriche di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="da1ca-205">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="da1ca-206">Metriche di regressione</span><span class="sxs-lookup"><span data-stu-id="da1ca-206">Regression metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="da1ca-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da1ca-207">See also</span></span>

<span data-ttu-id="da1ca-208">Per esempi di codice completi e altro ancora, visitare il repository GitHub [machinelearning-dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).</span><span class="sxs-lookup"><span data-stu-id="da1ca-208">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
