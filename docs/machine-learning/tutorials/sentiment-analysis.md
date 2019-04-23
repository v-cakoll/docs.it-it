---
title: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment
description: Informazioni su come usare ML.NET in uno scenario di classificazione binaria per comprendere come usare la stima del sentiment al fine di eseguire l'azione appropriata.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: e88a85b96c1e5d33d748332991cb9480222a9c66
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612095"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Esercitazione: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment

Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore del sentiment per la stima del sentiment positivo o negativo tramite un'applicazione console .NET Core con C# in Visual Studio 2017. Nel mondo del machine learning, questo tipo di stima è noto come nella classificazione binaria.

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa esercitazione e l'esempio correlato usano attualmente **ML.NET versione 0.11**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> * Informazioni sul problema
> * Selezionare l'algoritmo di Machine Learning appropriato
> * Preparare i dati
> * Trasformare i dati
> * Eseguire il training del modello
> * Valutare il modello
> * Eseguire stime con il modello sottoposto a training
> * Eseguire distribuzione e stime con un modello caricato

## <a name="sentiment-analysis-sample-overview"></a>Panoramica dell'esempio di analisi del sentiment

L'esempio è un'app console che usa ML.NET per eseguire il training di un modello che classifica e stima il sentiment come positivo o negativo. Il set di dati del sentiment Yelp è prodotto dalla University of California, Irvine (UCI) ed è suddiviso in set di dati di training e set di dati di test. L'esempio consente di valutare il modello con il set di dati di test per l'analisi della qualità.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

* [File ZIP del set di dati Sentiment Labeled Sentences di UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a>Flusso di lavoro di apprendimento automatico

Questa esercitazione segue un flusso di lavoro di apprendimento automatico che consente l'esecuzione del processo in modo ordinato.

Le fasi del flusso di lavoro sono le seguenti:

1. **Informazioni sul problema**
2. **Preparare i dati**
   * **Caricare i dati**
   * **Estrarre le caratteristiche (trasformare i dati)**
3. **Compilare ed eseguire il training**
   * **Eseguire il training del modello**
   * **Valutazione del modello**
4. **Distribuire il modello**
   * **Usare il modello per le stime**

### <a name="understand-the-problem"></a>Informazioni sul problema

È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello. La suddivisione del problema consente di stimare e valutare i risultati.

Il problema per questa esercitazione consiste nel comprendere il sentiment dei commenti in un sito Web per eseguire l'azione appropriata.

È possibile suddividere il problema nel testo del sentiment e nel valore del sentiment per i dati con cui si vuole eseguire il training del modello e un valore del sentiment stimato che è possibile valutare e quindi usare a livello operativo.

Sarà quindi necessario **determinare** il sentiment, che consente di selezionare l'attività di apprendimento automatico.

## <a name="select-the-appropriate-machine-learning-algorithm"></a>Selezionare l'algoritmo di Machine Learning appropriato

Per questo problema, sono noti i fatti seguenti:

Dati di training: i commenti nel sito Web possono essere positivi (1) o negativi (0) (**sentiment**).

Stimare il **sentiment** di un nuovo commento nel sito Web (positivo o negativo), come negli esempi seguenti:

* Mi piace il personale. Sono veloci.
* Questo posto offre i primi peggiori.

L'algoritmo di Machine Learning di classificazione è il più adatto per questo scenario.

### <a name="about-the-classification-algorithm"></a>Informazioni sull'algoritmo di classificazione

La classificazione è un algoritmo di Machine Learning che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati. È ad esempio possibile usare la classificazione per:

* Identificare il sentiment come positivo o negativo.
* Classificare messaggi di posta elettronica come posta indesiderata o legittima.
* Determinare se le analisi di laboratorio di un paziente indicano la presenza di cellule tumorali.
* Suddividere in categorie i clienti in base alla relativa propensione a rispondere a una campagna di vendita.

Gli algoritmi di classificazione sono spesso di uno dei tipi seguenti:

* Binarie: A o B.
* Multiclasse: più categorie che possono essere stimate tramite un singolo modello.

Dato che i commenti nel sito Web devono essere classificati come positivi o negativi, si usa l'algoritmo di classificazione binaria.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

### <a name="prepare-your-data"></a>Preparare i dati

1. Scaricare il [file ZIP del set di dati Sentiment Labeled Sentences UCI (vedere le citazioni nella nota seguente)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) e decomprimere il file.

2. Copiare il file `yelp_labelled.txt` nella directory *Data* creata.

> [!NOTE]
> I set di dati usati in questa esercitazione provengono da 'From Group to Individual Labels using Deep Features', Kotzias et. al,. KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. e Karra Taniskidou, E. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

3. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file `yelp_labeled.txt` e scegliere **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

È necessario creare due campi globali per contenere il percorso del file del set di dati scaricato di recente e il percorso del file modello salvato:

* `_dataPath` contiene il percorso del set di dati usato per il training del modello.
* `_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.

Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

La classe del set di dati di input, `SentimentData`, include un valore `string` per il commento (`SentimentText`) e un valore `bool` (`Sentiment`) che include un valore per il sentiment positivo o negativo. A entrambi i campi sono associati attributi <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29>. Questo attributo descrive l'ordine di ogni campo nel file di dati.  Inoltre, la proprietà `Sentiment` include un elemento <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> per designarlo come il campo `Label`. `SentimentPrediction` è la classe usata per la stima dopo il training del modello. Dispone di un singolo valore booleano (`Sentiment`) e un attributo `ColumnName` `PredictedLabel`. `Label` viene usato per creare il modello ed eseguirne il training, nonché con il set di dati suddiviso per valutare il modello. `PredictedLabel` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

Quando si crea un modello con ML.NET, si inizia creando un'istanza di <xref:Microsoft.ML.MLContext>. A livello concettuale `MLContext` è paragonabile all'uso di `DbContext` in Entity Framework. L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Creare una variabile denominata `mlContext` e inizializzarla con una nuova istanza di `MLContext`.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

Aggiungere il codice seguente al metodo `Main` come riga successiva:

[!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

Il metodo `LoadData` esegue le attività seguenti:

* Carica i dati.
* Suddivide il set di dati caricati in set di dati di training e di test.
* Restituisce i set di dati di training e di test divisi.

Creare il metodo `LoadData` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
public static TrainCatalogBase.TrainTestData LoadData(MLContext mlContext)
{

}
```

## <a name="load-the-data"></a>Caricare i dati

Poiché il tipo di modello di dati `SentimentData` creato in precedenza corrisponde allo schema del set di dati, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati in un'unica riga di codice usando il wrapper `MLContext.Data.LoadFromTextFile` per il [metodo LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29). Verrà restituita un'istanza di <xref:Microsoft.Data.DataView.IDataView>.

Come input e output di `Transforms`, una `DataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.

In ML.NET i dati sono simili a una visualizzazione SQL. Vengono valutati in modalità differita, sono schematizzati ed eterogenei. L'oggetto è la prima parte della pipeline e carica i dati. Per questa esercitazione, carica un set di dati con commenti e il sentiment positivo o negativo corrispondente. Queste informazioni vengono usate per creare il modello ed eseguirne il training.

Aggiungere il codice seguente come prima riga del metodo `LoadData`:

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a>Dividere il set di dati per il training e il test del modello

Successivamente, è necessario sia un set di dati di training per il training del modello che un set di dati di test per valutare il modello. Usare `MLContext.BinaryClassification.TrainTestSplit` che esegue il wrapping di <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> per dividere il set di dati caricato in set di dati di training e di test e restituirli all'interno di un <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>. È possibile specificare la frazione di dati per il set di test con il parametro `testFraction`. Il valore predefinito è 10%, ma in questo caso si usa il 20% per usare più dati per la valutazione.

Per dividere i dati caricati nei set di dati necessari, aggiungere il codice seguente come riga successiva nel metodo `LoadData`:

[!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

Restituire `splitDataView` alla fine del metodo `LoadData`:

[!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>Compilare ed eseguire il training del modello

Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main`:

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

Il metodo `BuildAndTrainModel` esegue le attività seguenti:

* Estrae e trasforma i dati.
* Esegue il training del modello.
* Esegue la stima del sentiment in base ai dati di test.
* Restituisce il modello.

Creare il metodo `BuildAndTrainModel` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

Si noti che vengono passati due parametri al metodo Train: `MLContext` per il contesto (`mlContext`) e `IDataView` per il set di dati di training (`splitTrainSet`).

## <a name="extract-and-transform-the-data"></a>Estrarre e trasformare i dati

La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico. I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti. L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.

Le pipeline di trasformazione di ML.NET compongono un set personalizzato di trasformazioni che vengono applicate ai dati prima di eseguire il training o i test. Lo scopo principale delle trasformazioni è l'[estrazione delle caratteristiche](../resources/glossary.md#feature-engineering) dai dati. Gli algoritmi di apprendimento automatico sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) in modo da trasformare successivamente i dati testuali in un formato riconoscibile da tali algoritmi. Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).

Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` che estrae le caratteristiche della colonna di testo (`SentimentText`) e le trasforma in un vettore numerico denominato `Features` che viene usato dall'algoritmo di apprendimento automatico. Questa è una chiamata di wrapper che restituisce un oggetto <xref:Microsoft.ML.Data.EstimatorChain%601> che sarà effettivamente una pipeline. Assegnare un nome a questa `pipeline` poiché successivamente si aggiungerà l'algoritmo di training all'oggetto `EstimatorChain`. Aggiungere il codice seguente come riga successiva:

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> In ML.NET versione 0.10 è stato modificato l'ordine dei parametri Transforms. Non verranno segnalati errori fino a quando non si esegue l'applicazione e si compila il modello. Usare i nomi dei parametri per Transforms come illustrato nel frammento di codice precedente.

Questo è il passaggio di pre-elaborazione/estrazione delle funzionalità. Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

Per aggiungere l'algoritmo di training, chiamare il metodo wrapper `mlContext.BinaryClassification.Trainers.FastTree` che restituisce un oggetto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>, un algoritmo di apprendimento basato su un albero delle decisioni che si userà in questa pipeline. L'oggetto `FastTreeBinaryClassificationTrainer` viene aggiunto alla `pipeline` e accetta l'oggetto `SentimentText` (`Features`) da cui sono state estratte le caratteristiche e i parametri di input `Label` per l'apprendimento in base ai dati cronologici.

Aggiungere al metodo `BuildAndTrainModel` il codice seguente:

[!code-csharp[FastTreeBinaryClassificationTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Eseguire il training del modello

Il training del modello, <xref:Microsoft.ML.Data.TransformerChain%601>, viene eseguito in base al set di dati caricato e trasformato. Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati. Viene così restituito un modello da usare per le stime. `pipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata. L'esperimento non viene eseguito finché non viene eseguito il metodo `.Fit()`.

Aggiungere al metodo `BuildAndTrainModel` il codice seguente:

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Salvare e restituire il modello sottoposto a training da usare per la valutazione

A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain%601> che può essere integrato nelle applicazioni .NET nuove o esistenti. Restituire il modello alla fine del metodo `BuildAndTrainModel`.

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>Valutare il modello

Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida. Nel metodo `Evaluate` viene passato il modello creato in `BuildAndTrainModel` per la valutazione. Creare il metodo `Evaluate` subito dopo `BuildAndTrainModel`, come nel codice seguente:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

Il metodo `Evaluate` esegue le attività seguenti:

* Carica il set di dati di test.
* Crea l'analizzatore binaryclassification.
* Valuta il modello e crea le metriche.
* Visualizza le metriche.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

Si useranno quindi il parametro `model` di machine learning automatico (un oggetto Transformer) e il parametro `splitTestSet` per l'input di caratteristiche e la generazione di stime. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

Il metodo `mlContext.BinaryClassification.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato. Restituisce un oggetto <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> che contiene le metriche complessive calcolate dagli analizzatori della classificazione binaria. Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Visualizzazione delle metriche per la convalida del modello

Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

Per salvare il modello in un file con estensione zip prima della restituzione, aggiungere il codice seguente per chiamare il metodo `SaveModelAsFile` come riga successiva in `Evaluate`:

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a>Salvare il modello come file con estensione zip

Creare il metodo `SaveModelAsFile` subito dopo il metodo `Evaluate`, usando il codice seguente:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `SaveModelAsFile` esegue le attività seguenti:

* Salva il modello come file con estensione zip.

A questo punto, creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni. L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>. Per salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`. Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>Stimare il risultato dei dati di test con il modello salvato

Creare il metodo `UseModelWithSingleItem` subito dopo il metodo `Evaluate`, usando il codice seguente:

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `UseModelWithSingleItem` esegue le attività seguenti:

* Crea un singolo commento di dati di test.
* Esegue la stima del sentiment in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:

[!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

`model` è un oggetto `transformer` che opera su molte righe di dati, ma in un ambiente produzione è spesso necessario eseguire stime su singoli esempi. <xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`. A questo punto si aggiunge il codice seguente per creare l'istanza di `PredictionEngine` come prima riga nel metodo `Predict`:

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `SentimentData`:

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 È possibile usare questo commento per eseguire una stima del sentiment positivo o negativo di una singola istanza dei dati relativi ai commenti. Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a>Usare il modello: stima

Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza. Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi. Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Eseguire distribuzione e stime con un modello caricato

Creare il metodo `UseLoadedModelWithBatchItems` subito prima del metodo `SaveModelAsFile`, con il codice seguente:

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

Il metodo `UseLoadedModelWithBatchItems` esegue le attività seguenti:

* Crea i dati di test in batch.
* Esegue la stima del sentiment in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `UseModelWithSingleItem`, usando il codice seguente:

[!code-csharp[CallPredictModelLoaded](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `UseLoadedModelWithBatchItems`:

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

Caricare il modello

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

Dopo aver creato un modello, è possibile usarlo per stimare il sentiment positivo o negativo dei dati relativi ai commenti usando il metodo <xref:Microsoft.ML.ITransformer.Transform%2A>. Per ottenere una stima, usare `Predict` sui nuovi dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta. Aggiungere il codice seguente al metodo `UseLoadedModelWithBatchItems` per le stime:

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a>Usare il modello caricato per la stima

Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza. Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi. Creare un'intestazione per i risultati con il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

Prima di visualizzare i risultati stimati, combinare il sentiment e la stima per visualizzare il commento originale con il sentiment stimato. Il codice seguente usa il metodo <xref:System.Linq.Enumerable.Zip%2A> per eseguire tale operazione. Aggiungere pertanto il codice seguente:

[!code-csharp[BuildTuples](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

Ora che `SentimentText` e `Sentiment` sono stati combinati in una classe, è possibile visualizzare i risultati usando il metodo <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

Poiché i nomi degli elementi di tupla dedotti sono una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.
A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva). Selezionare il pulsante **OK** .

## <a name="results"></a>Risultati

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione della pipeline, vengono visualizzati messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

La procedura è stata completata. A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi.

La creazione di modelli efficaci è un processo iterativo. Questo modello ha inizialmente una qualità inferiore, perché l'esercitazione usa set di dati di dimensioni contenute per consentire il training rapido del modello. Se non si è soddisfatti della qualità del modello, è possibile provare a migliorarla fornendo set di dati di training più grandi o scegliendo algoritmi di training diversi con iperparametri diversi per ogni algoritmo.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:

> [!div class="checklist"]
> * Informazioni sul problema
> * Selezionare l'algoritmo di Machine Learning appropriato
> * Preparare i dati
> * Trasformare i dati
> * Eseguire il training del modello
> * Valutare il modello
> * Eseguire stime con il modello sottoposto a training
> * Eseguire distribuzione e stime con un modello caricato

Passare all'esercitazione successiva per altre informazioni

> [!div class="nextstepaction"]
> [Classificazione del problema](github-issue-classification.md)
