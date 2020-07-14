---
title: 'Esercitazione: analizzare i commenti del sito Web-classificazione binaria'
description: In questa esercitazione viene illustrato come creare un'applicazione console .NET Core che classifica le valutazioni dei commenti di un sito web ed esegue l'azione appropriata. La funzione di classificazione binaria delle valutazioni usa C# in Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: de8ea511b3d421e391b182a6de079b854d3f2390
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281757"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a>Esercitazione: analizzare i sentimenti dei commenti del sito Web con classificazione binaria in ML.NET

In questa esercitazione viene illustrato come creare un'applicazione console .NET Core che classifica le valutazioni dei commenti di un sito web ed esegue l'azione appropriata. La funzione di classificazione binaria delle valutazioni usa C# in Visual Studio 2017.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un'applicazione console
> - Preparazione dei dati
> - Caricare i dati
> - Compilare ed eseguire il training del modello
> - Valutare il modello
> - Usare il modello per eseguire una stima
> - Visualizzare i risultati

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato

- [Set di dati Sentiment Labeled Sentences di UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (file con estensione zip)

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare un'**applicazione console di .NET Core** con nome "SentimentAnalysis".

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, quindi selezionare la scheda **Sfoglia** . cercare **Microsoft.ml**, selezionare il pacchetto desiderato e quindi fare clic sul pulsante **Installa** . Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto.

## <a name="prepare-your-data"></a>Preparare i dati

> [!NOTE]
> I set di dati usati in questa esercitazione provengono da "From Group to Individual Labels using Deep Features", Kotzias et. al,. KDD 2015 e ospitato nel repository di Machine Learning UCI-Dua, D. e Karra Taniskidou, E. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

1. Scaricare il [file con estensione zip del set di dati Sentiment Labeled Sentences di UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) e decomprimerlo.

2. Copiare il file `yelp_labelled.txt` nella directory *Data* creata.

3. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file `yelp_labeled.txt` e scegliere **Proprietà**. In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

1. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: 

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. Aggiungere il codice seguente alla riga immediatamente sopra il `Main` metodo per creare un campo che contenga il percorso del file del set di dati scaricato di recente:

    [!code-csharp[Declare global variables](./snippets/sentiment-analysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. Successivamente, creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

    - In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi selezionare **Aggiungi** > **Nuovo elemento**.

    - Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**.

1. Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:

    [!code-csharp[DeclareTypes](./snippets/sentiment-analysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a>Come sono stati preparati i dati

La classe di set di dati di input, `SentimentData`, dispone di un `string` per i commenti utente (`SentimentText`) e di un valore `bool` (`Sentiment`) pari a 1 (positivo) o 0 (negativo) per la valutazione. Entrambi i campi hanno attributi [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) associati, che descrivono l'ordine di file di dati di ogni campo.  Inoltre, la proprietà `Sentiment` include un attributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) per designarlo come campo `Label`. Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:

|SentimentText                         |Valutazione (etichetta) |
|--------------------------------------|----------|
|La cameriera era un po' lenta a servire.|    0     |
|Crust is not good.                    |    0     |
|Wow... Questo posto è stato apprezzato.              |    1     |
|Il servizio è stato molto rapido.              |    1     |

`SentimentPrediction` è la classe di stima usata dopo il training del modello. Questa classe eredita da `SentimentData` in modo che l'input `SentimentText` sia visualizzabile insieme alla stima di output. Il valore booleano `Prediction` è il valore di cui il modello esegue la stima quando riceve un nuovo input `SentimentText`.

La classe di output `SentimentPrediction` contiene altre due proprietà calcolate dal modello: `Score`, che è il punteggio non elaborato calcolato dal modello e `Probability`, che è il punteggio calibrato sulla probabilità che il testo esprima un sentiment positivo.

Per questa esercitazione la proprietà più importante è `Prediction`.

## <a name="load-the-data"></a>Caricare i dati

I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView). `IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo). È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.

La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET. L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

Preparare l'app, quindi caricare i dati:

1. Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:

    [!code-csharp[CreateMLContext](./snippets/sentiment-analysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. Aggiungere il codice seguente al metodo `Main()` come riga successiva:

    [!code-csharp[CallLoadData](./snippets/sentiment-analysis/csharp/Program.cs#CallLoadData)]

3. Creare il metodo `LoadData()` subito dopo il metodo `Main()`, usando il codice seguente:

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    Il metodo `LoadData()` esegue le attività seguenti:

    - Carica i dati.
    - Suddivide il set di dati caricati in set di dati di training e di test.
    - Restituisce i set di dati di training e di test divisi.

4. Aggiungere il codice seguente come prima riga del metodo `LoadData()`:

    [!code-csharp[LoadData](./snippets/sentiment-analysis/csharp/Program.cs#LoadData "loading dataset")]

    Il metodo [LoadFromTextFile ()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema di dati e legge il file. Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.

### <a name="split-the-dataset-for-model-training-and-testing"></a>Dividere il set di dati per il training e il test del modello

Quando si prepara un modello, usare parte del set di dati per il training e parte del set di dati per testare l'accuratezza del modello.

1. Per dividere i dati caricati nei set di dati necessari, aggiungere il codice seguente come riga successiva nel metodo `LoadData()`:

    [!code-csharp[SplitData](./snippets/sentiment-analysis/csharp/Program.cs#SplitData "Split the Data")]

    Il codice precedente usa il metodo [TrainTestSplit ()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) per suddividere il set di dati caricato in set di dati di training e di test e restituirli nella <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> classe. Specificare la percentuale di dati del set di test con il parametro `testFraction`. Il valore predefinito è 10%, in questo caso usare il 20% per valutare più dati.

2. Restituire `splitDataView` alla fine del metodo `LoadData()`:

    [!code-csharp[ReturnSplitData](./snippets/sentiment-analysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>Compilare ed eseguire il training del modello

1. Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main()`:

    [!code-csharp[CallBuildAndTrainModel](./snippets/sentiment-analysis/csharp/Program.cs#CallBuildAndTrainModel)]

    Il metodo `BuildAndTrainModel()` esegue le attività seguenti:

    - Estrae e trasforma i dati.
    - Esegue il training del modello.
    - Esegue la stima del sentiment in base ai dati di test.
    - Restituisce il modello.

2. Creare il metodo `BuildAndTrainModel()` subito dopo il metodo `Main()`, usando il codice seguente:

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a>Estrarre e trasformare i dati

1. Chiamare `FeaturizeText` quale riga di codice successiva:

    [!code-csharp[FeaturizeText](./snippets/sentiment-analysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    Il metodo `FeaturizeText()` nel codice precedente consente di convertire la colonna di testo (`SentimentText`) in una colonna `Features` di tipo di chiave numerica usata dall'algoritmo di apprendimento automatico e di aggiungerla come nuova colonna del set di dati:

    |SentimentText                         |Valutazione |Funzionalità              |
    |--------------------------------------|----------|----------------------|
    |La cameriera era un po' lenta a servire.|    0     |[0.76, 0.65, 0.44, …] |
    |Crust is not good.                    |    0     |[0.98, 0.43, 0.54, …] |
    |Wow... Questo posto è stato apprezzato.              |    1     |[0.35, 0.73, 0.46, …] |
    |Il servizio è stato molto rapido.              |    1     |[0.39, 0, 0.75, …]    |

### <a name="add-a-learning-algorithm"></a>Aggiungere un algoritmo di apprendimento

Questa app usa un algoritmo di classificazione che classifica gli elementi o le righe di dati. L'app consente di classificare i commenti di un sito web come positivi o negativi, quindi di usare l'attività di classificazione binaria.

Aggiungere l'attività di Machine Learning alle definizioni di trasformazione dei dati aggiungendo il codice seguente come riga successiva di codice in `BuildAndTrainModel()`:

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](./snippets/sentiment-analysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) è l'algoritmo del training di classificazione. Viene aggiunto alla `estimator` e accetta l'oggetto `SentimentText` (`Features`) da cui sono state estratte le caratteristiche e i parametri di input `Label` per l'apprendimento in base ai dati cronologici.

### <a name="train-the-model"></a>Eseguire il training del modello

Eseguire il fit del modello ai dati `splitTrainSet` e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:

[!code-csharp[TrainModel](./snippets/sentiment-analysis/csharp/Program.cs#TrainModel "Train the model")]

Il metodo [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) esegue il training del modello trasformando il set di dati e applicando il training.

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Restituire il modello di cui è stato eseguito il training da usare per la valutazione

 Restituire il modello alla fine del metodo `BuildAndTrainModel()`:

[!code-csharp[ReturnModel](./snippets/sentiment-analysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>Valutare il modello

Dopo che viene eseguito il training del modello, usare i dati di test per convalidare le prestazioni del modello.

1. Creare il metodo `Evaluate()` subito dopo `BuildAndTrainModel()` con il codice seguente:

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    Il metodo `Evaluate()` esegue le attività seguenti:

    - Carica il set di dati di test.
    - Crea l'analizzatore BinaryClassification.
    - Valuta il modello e crea le metriche.
    - Visualizza le metriche.

2. Aggiungere una chiamata al nuovo metodo dal metodo `Main()`, subito sotto la chiamata al metodo `BuildAndTrainModel()`, usando il codice seguente:

    [!code-csharp[CallEvaluate](./snippets/sentiment-analysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. Trasformare i dati `splitTestSet` aggiungendo il codice seguente a `Evaluate()`:

    [!code-csharp[PredictWithTransformer](./snippets/sentiment-analysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    Il codice precedente usa il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) per effettuare previsioni per più righe di input specificate di un set di dati di test.

4. Valutare il modello aggiungendo il codice seguente come riga successiva nel metodo `Evaluate()`:

    [!code-csharp[ComputeMetrics](./snippets/sentiment-analysis/csharp/Program.cs#Evaluate "Compute Metrics")]

Dopo aver impostato la stima (`predictions`), il metodo [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) valuta il modello confrontando i valori stimati con gli oggetti `Labels` effettivi presenti nel set di dati di test e restituisce un oggetto [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) relativo alle prestazioni del modello.

### <a name="displaying-the-metrics-for-model-validation"></a>Visualizzazione delle metriche per la convalida del modello

Usare il codice seguente per visualizzare le metriche:

[!code-csharp[DisplayMetrics](./snippets/sentiment-analysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- La metrica `Accuracy` ottiene l'accuratezza di un modello, che è la percentuale di stime corrette nel set di test.

- La metrica `AreaUnderRocCurve` indica con quale affidabilità il modello classifica correttamente le classi positive e negative. `AreaUnderRocCurve` deve avvicinarsi il più possibile a 1.

- La metrica `F1Score` produce il punteggio F1 del modello, che è una misura di equilibrio tra [precisione](../resources/glossary.md#precision) e [richiamo](../resources/glossary.md#recall).  `F1Score` deve avvicinarsi il più possibile a 1.

### <a name="predict-the-test-data-outcome"></a>Stimare i risultati dei dati di test

1. Creare il metodo `UseModelWithSingleItem()` subito dopo il metodo `Evaluate()`, usando il codice seguente:

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    Il metodo `UseModelWithSingleItem()` esegue le attività seguenti:

    - Crea un singolo commento di dati di test.
    - Esegue la stima del sentiment in base ai dati di test.
    - Combina i dati di test e le stime per i report.
    - Visualizza i risultati stimati.

2. Aggiungere una chiamata al nuovo metodo dal metodo `Main()`, subito sotto la chiamata al metodo `Evaluate()`, usando il codice seguente:

    [!code-csharp[CallUseModelWithSingleItem](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. Aggiungere il codice seguente per creare come prima riga nel metodo `UseModelWithSingleItem()`:

    [!code-csharp[CreatePredictionEngine](./snippets/sentiment-analysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe. È accettabile usare in ambienti a thread singolo o prototipi. Per migliorare le prestazioni e thread safety negli ambienti di produzione, utilizzare il `PredictionEnginePool` servizio, che consente di creare un oggetto [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da utilizzare nell'applicazione. Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

    > [!NOTE]
    > L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

4. Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `UseModelWithSingleItem()` creando un'istanza di `SentimentData`:

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. Passare i dati del commento di test a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) aggiungendo quanto segue come righe successive di codice nel `UseModelWithSingleItem()` Metodo:

    [!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola colonna di dati.

6. Visualizzare `SentimentText` e la corrispondente stima della valutazione tramite il codice seguente:

    [!code-csharp[OutputPrediction](./snippets/sentiment-analysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a>Usare il modello per le stime

### <a name="deploy-and-predict-batch-items"></a>Distribuire e prevedere gli elementi del batch

1. Creare il metodo `UseModelWithBatchItems()` subito dopo il metodo `UseModelWithSingleItem()`, usando il codice seguente:

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    Il metodo `UseModelWithBatchItems()` esegue le attività seguenti:

    - Crea i dati di test in batch.
    - Esegue la stima del sentiment in base ai dati di test.
    - Combina i dati di test e le stime per i report.
    - Visualizza i risultati stimati.

2. Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `UseModelWithSingleItem()`, usando il codice seguente:

    [!code-csharp[CallPredictModelBatchItems](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `UseModelWithBatchItems()`:

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a>Prevedere la valutazione del commento

Usare il modello per stimare la valutazione dei dati del commento usando il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A):

[!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a>Combinare e visualizzare le stime

Creare un'intestazione per le stime con il codice seguente:

[!code-csharp[OutputHeaders](./snippets/sentiment-analysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

Poiché `SentimentPrediction` viene ereditato da `SentimentData`, il metodo `Transform()` ha compilato `SentimentText` con i campi previsti. Mentre il processo ML.NET elabora, ogni componente aggiunge colonne e ciò rende più facile visualizzare i risultati:

[!code-csharp[DisplayPredictions](./snippets/sentiment-analysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a>Risultati

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione, vengono visualizzati alcuni messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

Congratulazioni! A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi.

La creazione di modelli efficaci è un processo iterativo. Questo modello ha inizialmente una qualità inferiore, perché l'esercitazione usa set di dati di dimensioni contenute per consentire il training rapido del modello. Se non si è soddisfatti della qualità del modello, è possibile provare a migliorarlo fornendo set di impostazioni di training di dimensioni maggiori o scegliendo algoritmi di training diversi con diversi [parametri ipertestuali](../resources/glossary.md#hyperparameter) per ogni algoritmo.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un'applicazione console
> - Preparazione dei dati
> - Caricare i dati
> - Compilare ed eseguire il training del modello
> - Valutare il modello
> - Usare il modello per eseguire una stima
> - Visualizzare i risultati

Passare all'esercitazione successiva per altre informazioni
> [!div class="nextstepaction"]
> [Classificazione dei problemi](github-issue-classification.md)
