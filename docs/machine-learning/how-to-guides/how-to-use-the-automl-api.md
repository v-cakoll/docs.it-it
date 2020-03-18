---
title: Come usare l'API di Machine Learning automatizzato per ML.NET
description: L'API di Machine Learning automatizzato per ML.NET consente di automatizzare il processo di compilazione del modello e genera un modello pronto per la distribuzione. Sono disponibili varie opzioni per configurare attività di Machine Learning automatizzato.
ms.date: 12/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b322c484282d025033d747d2093f7b5b4d216fde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75636562"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a>Come usare l'API di Machine Learning automatizzato per ML.NET

Il Machine Learning automatizzato (AutoML) consente di automatizzare il processo di applicazione dell'apprendimento automatico ai dati. A partire da un set di dati è possibile eseguire un **esperimento** AutoML per eseguire l'iterazione su varie estrazioni delle caratteristiche dei dati, algoritmi di apprendimento automatico e iperparametri, allo scopo di selezionare il modello ottimale.

> [!NOTE]
> Questo argomento riguarda l'API di Machine Learning automatizzato per ML.NET, che è attualmente in anteprima. Il materiale potrà essere soggetto a modifiche.

## <a name="load-data"></a>Caricare dati

Il Machine Learning automatizzato supporta il caricamento di un set di dati in un elemento [IDataView](xref:Microsoft.ML.IDataView). I dati possono essere sotto forma di file di valori delimitati da tabulazioni (con estensione tsv) e file di valori delimitati da virgole (con estensione csv).

Esempio:

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a>Selezionare il tipo di attività di apprendimento automatico

Prima di creare un esperimento, determinare il tipo di problema di apprendimento automatico da risolvere. Il Machine Learning automatizzato supporta le seguenti attività di apprendimento automatico:

* Classificazione binaria
* Classificazione multiclasse
* Regressione
* Recommendation

## <a name="create-experiment-settings"></a>Creare le impostazioni dell'esperimento

Creare le impostazioni dell'esperimento per il tipo specifico di attività di apprendimento automatico:

* Classificazione binaria

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* Classificazione multiclasse

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* Regressione

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

* Recommendation

  ```csharp
  var experimentSettings = new RecommendationExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a>Configurare le impostazioni dell'esperimento

Gli esperimenti sono ampiamente configurabili. Vedere la [documentazione dell'API AutoML](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) per un elenco completo delle impostazioni di configurazione.

Di seguito sono riportati alcuni esempi:

1. Specificare il tempo massimo per il quale eseguire l'esperimento.

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. Usare un token di annullamento per annullare l'esperimento prima della fine pianificata.

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. Specificare una metrica di ottimizzazione diversa.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. L'impostazione `CacheDirectory` è un puntatore a una directory in cui verranno salvati tutti i modelli sottoposti a training durante l'attività AutoML. Se `CacheDirectory` è null i modelli verranno mantenuti nella memoria anziché salvati su disco.

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. Indicare al Machine Learning automatizzato di non usare determinati algoritmi di training.

    Per ogni attività viene preso in esame un elenco predefinito di algoritmi di training per l'ottimizzazione. Questo elenco può essere modificato per ogni esperimento. Ad esempio gli algoritmi di training che vengono eseguiti troppo lentamente sul set di dati possono essere rimossi dall'elenco. Per eseguire l'ottimizzazione relativa a un algoritmo di training specifico chiamare `experimentSettings.Trainers.Clear()`, quindi aggiungere l'algoritmo di training che si vuole usare.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

L'elenco degli algoritmi di training supportati per ogni attività di apprendimento automatico è disponibile nel collegamento corrispondente riportato di seguito:

* [Algoritmi di classificazione binaria supportati](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [Algoritmi di classificazione multiclasse supportati](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [Algoritmi di regressione supportati](xref:Microsoft.ML.AutoML.RegressionTrainer)
* [Algoritmi di raccomandazione supportatiSupported Recommendation Algorithms](xref:Microsoft.ML.AutoML.RecommendationTrainer)

## <a name="optimizing-metric"></a>Metrica di ottimizzazione

Come illustrato nell'esempio precedente, la metrica di ottimizzazione determina la metrica da ottimizzare durante il training del modello. La metrica di ottimizzazione selezionabile è determinata dal tipo di attività scelto. Ecco un elenco delle metriche disponibili.

|[Classificazione binaria](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [Classificazione multiclasse](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[Raccomandazione & di regressione](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|Accuratezza| LogLoss | RSquared
|AreaUnderPrecisionRecallCurve | LogLossReduction | MeanAbsoluteError
|AreaUnderRocCurve | MacroAccuracy | MeanSquaredError
|F1Score | MicroAccuracy | RootMeanSquaredError
|NegativePrecision | TopKAccuracy
|NegativeRecall |
|PositivePrecision
|PositiveRecall

## <a name="data-pre-processing-and-featurization"></a>Definizione delle caratteristiche e pre-elaborazione dei dati

> [!NOTE]
> La colonna di entità <xref:System.Boolean> <xref:System.Single>geografiche <xref:System.String>supporta solo i tipi di , e .

La preelaborazione dei dati si verifica per impostazione predefinita e i passaggi seguenti vengono eseguiti automaticamente:

1. Rimozione delle caratteristiche prive di informazioni utili

    Vengono eliminate le caratteristiche senza informazioni utili dai set di training e convalida. Queste includono le caratteristiche con tutti i valori mancanti, con lo stesso valore in tutte le righe o con cardinalità molto elevata, ad esempio hash, ID o GUID.

1. Indicazione e marcatura dei valori mancanti

    Riempimento delle celle con valore mancante con il valore predefinito per il tipo di dati. Aggiunta di caratteristiche indicatore con lo stesso numero di slot della colonna di input. Il valore nelle caratteristiche indicatore accodate è `1` se il valore nella colonna di input è mancante e `0` negli altri casi.

1. Generazione di caratteristiche aggiuntive

    Per le caratteristiche di testo: Bag-of-word caratteristiche che utilizzano unigrammi e tri-carattere-grammi.

    Per le funzionalità categoriche: codifica one-hot per le funzionalità di cardinalità bassa e codifica hash a un solo punto per le funzionalità categoriche ad alta cardinalità.

1. Trasformazioni e codifiche

    Caratteristiche di testo con un numero molto ridotto di valori univoci trasformate in caratteristiche categoriche. A seconda della cardinalità delle caratteristiche categoriche, viene eseguita la codifica one-hot o la codifica hash one-hot.

## <a name="exit-criteria"></a>Criteri uscita

Definire i criteri per completare l'attività:

1. Uscita dopo un periodo di tempo: se si usa `MaxExperimentTimeInSeconds` nelle impostazioni dell'esperimento, è possibile definire la durata dell'esecuzione dell'attività in secondi.

1. Uscita in corrispondenza di un token di annullamento:  è possibile usare un  token di annullamento che consente di annullare l'attività prima della fine pianificata.

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a>Creare un esperimento

Dopo aver configurato le impostazioni dell'esperimento si è pronti per creare l'esperimento.

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a>Eseguire l'esperimento

L'esecuzione dell'esperimento attiva la preelaborazione dei dati, la selezione dell'algoritmo di apprendimento e l'ottimizzazione degli iperparametri. AutoML continua a generare combinazioni di estrazione caratteristiche, algoritmi di apprendimento automatico e iperparametri fino a quando non viene raggiunto `MaxExperimentTimeInSeconds` o viene terminato l'esperimento.

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

Esplorare altri overload per `Execute()` se si vuole passare dati di convalida, informazioni di colonna che indicano lo scopo della colonna o preestrattori di caratteristiche.

## <a name="training-modes"></a>Modalità di training

### <a name="training-dataset"></a>Dataset di training

AutoML include un metodo di esecuzione dell'esperimento con overload che consente di specificare dati di training. A livello interno, il Machine Learning automatizzato suddivide i dati in gruppi train-validate (training-convalida).

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a>Set di dati di convalida personalizzato

Se la suddivisione casuale non è accettabile, come avviene in genere con i dati di serie temporali, usare un set di dati di convalida personalizzato. È possibile specificare il proprio set di dati di convalida. Il modello verrà valutato rispetto al set di dati di convalida specificato anziché rispetto a uno o più set di dati casuali.

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a>Esplorare le metriche del modello

Dopo ogni iterazione di un esperimento ML vengono archiviate le metriche relative a tale attività.

Ad esempio è possibile accedere alle metriche di convalida dalla migliore esecuzione:

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

Di seguito sono elencate tutte le metriche disponibili per attività ML:

* [Metriche di classificazione binaria](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [Metriche di classificazione multiclasse](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [Metriche di raccomandazione & di regressione](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a>Vedere anche

Per esempi di codice completi e altro ancora, visitare il repository GitHub [machinelearning-dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).
