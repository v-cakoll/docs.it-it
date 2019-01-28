---
title: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment
description: Informazioni su come usare ML.NET in uno scenario di classificazione binaria per comprendere come usare la stima del sentiment al fine di eseguire l'azione appropriata.
ms.date: 01/15/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 47cf9deb9452d15aee8cf4c1ebc5e3d0f1aa10ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628007"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Esercitazione: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore del sentiment tramite un'applicazione console .NET Core con C# in Visual Studio 2017.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> * Informazioni sul problema
> * Selezionare l'attività di apprendimento automatico appropriata
> * Preparare i dati
> * Creare la pipeline di apprendimento
> * Caricare un classificatore
> * Eseguire il training del modello
> * Valutare il modello con un set di dati diverso
> * Eseguire una stima relativa a una singola istanza del risultato dei dati di test con il modello
> * Eseguire una stima dei risultati dei dati di test con un modello caricato

## <a name="sentiment-analysis-sample-overview"></a>Panoramica dell'esempio di analisi del sentiment

L'esempio è un'app console che usa ML.NET per eseguire il training di un modello che classifica e stima il sentiment come positivo o negativo. Valuta inoltre il modello con un secondo set di dati per l'analisi della qualità. I set di dati per il sentiment provengono dal progetto WikiDetox.

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

* [File con valori delimitati da tabulazioni Wikipedia detox line data (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).
* [File con valori delimitati da tabulazioni Wikipedia detox line test (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).

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
4. **Run**
   * **Utilizzare il modello**

### <a name="understand-the-problem"></a>Informazioni sul problema

È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello. La suddivisione del problema consente di stimare e valutare i risultati.

Il problema per questa esercitazione consiste nel comprendere il sentiment dei commenti in un sito Web per eseguire l'azione appropriata.

È possibile suddividere il problema nel testo del sentiment e nel valore del sentiment per i dati con cui si vuole eseguire il training del modello e un valore del sentiment stimato che è possibile valutare e quindi usare a livello operativo.

Sarà quindi necessario **determinare** il sentiment, che consente di selezionare l'attività di apprendimento automatico.

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

Per questo problema, sono noti i fatti seguenti:

Dati di training: i commenti nel sito Web possono essere positivi (1) o negativi (0) (**sentiment**).
Stimare il **sentiment** di un nuovo commento nel sito Web, positivo o negativo, come negli esempi seguenti:

* Per favore evita di aggiungere cose insensate a Wikipedia.
* È il migliore, e l'articolo dovrebbe indicarlo.

L'attività di apprendimento automatico tramite classificazione è la più adatta per questo scenario.

### <a name="about-the-classification-task"></a>Informazioni sull'attività di classificazione

La classificazione è un'attività di apprendimento automatico che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati. È ad esempio possibile usare la classificazione per:

* Identificare il sentiment come positivo o negativo.
* Classificare messaggi di posta elettronica come posta indesiderata o legittima.
* Determinare se le analisi di laboratorio di un paziente indicano la presenza di cellule tumorali.
* Suddividere in categorie i clienti in base alla relativa propensione a rispondere a una campagna di vendita.

Le attività di classificazione sono spesso di uno dei tipi seguenti:

* Binarie: A o B.
* Multiclasse: più categorie che possono essere stimate tramite un singolo modello.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

### <a name="prepare-your-data"></a>Preparare i dati

1. Scaricare i set di dati [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) e [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) e salvarli nella cartella *Data* creata in precedenza. Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

È necessario creare tre campi globali per i percorsi dei file scaricati di recente e una variabile globale per l'istanza di `TextLoader`:

* `_trainDataPath` contiene il percorso del set di dati usato per il training del modello.
* `_testDataPath` contiene il percorso del set di dati usato per valutare il modello.
* `_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.
* `_textLoader` è l'istanza della classe <xref:Microsoft.ML.Data.TextLoader> usata per caricare e trasformare i set di dati.

Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi e la variabile `_textLoader`:

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

`SentimentData` è la classe dataset di input e dispone di un valore `float` (`Sentiment`) per il sentiment positivo o negativo e una stringa per il commento (`SentimentText`). A entrambi i campi sono associati attributi `Column`. Questo attributo descrive l'ordine di ogni campo nel file di dati e indica qual è il campo `Label`. `SentimentPrediction` è la classe usata per la stima dopo il training del modello. Dispone di un singolo valore booleano (`Sentiment`) e un attributo `ColumnName` `PredictedLabel`. `Label` viene usato per creare il modello ed eseguirne il training, nonché con un secondo set di dati per valutare il modello. `PredictedLabel` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

Quando si crea un modello con ML.NET, si inizia creando un'istanza di `MLContext`. A livello concettuale questa operazione è paragonabile all'uso di `DbContext` in Entity Framework. L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Creare una variabile denominata `mlContext` e inizializzarla con una nuova istanza di `MLContext`.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

Successivamente, per configurare il caricamento dei dati, inizializzare la variabile globale `_textLoader` in modo da poterla riutilizzare.  Si noti che si sta usando un'istanza di `TextReader`. Quando si crea un'istanza di `TextLoader` con `TextReader`, si passa il contesto necessario e la classe <xref:Microsoft.ML.Data.TextLoader.Arguments> che consente la personalizzazione.

 Specificare lo schema di dati passando una matrice di oggetti <xref:Microsoft.ML.Data.TextLoader.Column> al caricatore contenente tutti i nomi delle colonne e i relativi tipi. Lo schema di dati è stato definito in precedenza quando si è creata la classe `SentimentData`. Per lo schema, la prima colonna (Label) è un valore <xref:System.Boolean> (la stima) e la seconda colonna (SentimentText) è la caratteristica di tipo testo/stringa usata per la stima del sentiment.
La classe `TextReader` restituisce un'istanza di <xref:Microsoft.ML.Data.TextLoader> completamente inizializzata.  

Per inizializzare la variabile globale `_textLoader` in modo da riutilizzarla per i set di dati necessari, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:

[!code-csharp[initTextReader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextReader")]

Aggiungere il codice seguente al metodo `Main` come riga successiva:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

Il metodo `Train` esegue le attività seguenti:

* Carica i dati.
* Estrae e trasforma i dati.
* Esegue il training del modello.
* Esegue la stima del sentiment in base ai dati di test.
* Restituisce il modello.

Creare il metodo `Train` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

Si noti che vengono passati due parametri al metodo Train: `MLContext` per il contesto (`mlContext`) e <xref:System.String> per il percorso del set di dati (`dataPath`). Si userà questo metodo più volte per il training e i test.

## <a name="load-the-data"></a>Caricare i dati

Si caricheranno i dati usando la variabile globale `_textLoader` con il parametro `dataPath`. Verrà restituita un'istanza di <xref:Microsoft.ML.Data.IDataView>. Come input e output di `Transforms`, una `DataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.

In ML.NET i dati sono simili a una visualizzazione SQL. Vengono valutati in modalità differita, sono schematizzati ed eterogenei. L'oggetto è la prima parte della pipeline e carica i dati. Per questa esercitazione, carica un set di dati con commenti e il sentiment positivo o negativo corrispondente. Queste informazioni vengono usate per creare il modello ed eseguirne il training.

 Aggiungere il codice seguente come prima riga del metodo `Train`:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a>Estrarre e trasformare i dati

La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico. I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti. L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.

Le pipeline di trasformazione di ML.NET compongono un set personalizzato di trasformazioni che vengono applicate ai dati prima di eseguire il training o i test. Lo scopo principale delle trasformazioni è l'[estrazione delle caratteristiche](../resources/glossary.md#feature-engineering) dai dati. Gli algoritmi di apprendimento automatico sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) in modo da trasformare successivamente i dati testuali in un formato riconoscibile da tali algoritmi. Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).

Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` che estrae le caratteristiche della colonna di testo (`SentimentText`) e le trasforma in un vettore numerico denominato `Features` che viene usato dall'algoritmo di apprendimento automatico. Questa è una chiamata di wrapper che restituisce un oggetto <xref:Microsoft.ML.Data.EstimatorChain%601> che sarà effettivamente una pipeline. Assegnare un nome a questa `pipeline` poiché successivamente si aggiungerà l'algoritmo di training all'oggetto `EstimatorChain`. Aggiungere il codice seguente come riga successiva:

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

Questo è il passaggio di pre-elaborazione/estrazione delle funzionalità. Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

Per aggiungere l'algoritmo di training, chiamare il metodo wrapper `mlContext.Transforms.Text.FeaturizeText` che restituisce un oggetto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>, un algoritmo di apprendimento basato su un albero delle decisioni che si userà in questa pipeline. L'oggetto `FastTreeBinaryClassificationTrainer` viene aggiunto alla `pipeline` e accetta l'oggetto `SentimentText` (`Features`) da cui sono state estratte le caratteristiche e i parametri di input `Label` per l'apprendimento in base ai dati cronologici.

Aggiungere al metodo `Train` il codice seguente:

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Eseguire il training del modello

Il training del modello, <xref:Microsoft.ML.Data.TransformerChain%601>, viene eseguito in base al set di dati caricato e trasformato. Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain`1.Fit*> e fornendo i dati di training già caricati. Viene così restituito un modello da usare per le stime. `pipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata. L'esperimento non viene eseguito finché questa operazione non è stata completata.

Aggiungere al metodo `Train` il codice seguente:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Salvare e restituire il modello sottoposto a training da usare per la valutazione

A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain%601> che può essere integrato nelle applicazioni .NET nuove o esistenti. Restituire il modello alla fine del metodo `Train`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a>Valutare il modello

Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida. Nel metodo `Evaluate` viene passato il modello creato in `Train` per la valutazione. Creare il metodo `Evaluate` subito dopo `Train`, come nel codice seguente:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `Evaluate` esegue le attività seguenti:

* Carica il set di dati di test.
* Crea l'analizzatore binario.
* Valuta il modello e crea le metriche.
* Visualizza le metriche.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

Si caricherà il set di dati di test usando la variabile globale `_textLoader` inizializzata in precedenza con il campo globale `_testDataPath`. È possibile valutare il modello usando questo set di dati come controllo di qualità. Aggiungere al metodo `Evaluate` il codice seguente:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

Si userà quindi il parametro `model` di apprendimento automatico (un oggetto Transformer) per l'input di caratteristiche e la generazione di stime. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

Il metodo `BinaryClassificationContext.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato. Restituisce un oggetto `BinaryClassificationEvaluator.CalibratedResult` che contiene le metriche complessive calcolate dagli analizzatori della classificazione binaria. Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Visualizzazione delle metriche per la convalida del modello

Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

Per salvare il modello in un file con estensione zip prima della restituzione, aggiungere il codice seguente per chiamare il metodo `SaveModelAsFile` come riga successiva in `Evaluate`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

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

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]

È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a>Stimare il risultato dei dati di test con il modello e un singolo commento

Creare il metodo `Predict` subito dopo il metodo `Evaluate`, usando il codice seguente:

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `Predict` esegue le attività seguenti:

* Crea un singolo commento di dati di test.
* Esegue la stima del sentiment in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

`model` è un oggetto `transformer` che opera su molte righe di dati, ma in un ambiente produzione è spesso necessario eseguire stime su singoli esempi. <xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`. A questo punto si aggiunge il codice seguente per creare l'istanza di `PredictionEngine` come prima riga nel metodo `Predict`:

[!code-csharp[CreatePredictionFunction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionFunction")]
  
Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `SentimentData`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]

 È possibile usare questo commento per eseguire una stima del sentiment positivo o negativo di una singola istanza dei dati relativi ai commenti. Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="model-operationalization-prediction"></a>Operazionalizzazione del modello: stima

Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza. Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi. Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="predict-the-test-data-outcomes-with-the-saved-model"></a>Stimare i risultati dei dati di test con il modello salvato

Creare il metodo `PredictWithModelLoadedFromFile` subito prima del metodo `SaveModelAsFile`, con il codice seguente:

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

Il metodo `PredictWithModelLoadedFromFile` esegue le attività seguenti:

* Crea i dati di test in batch.
* Esegue la stima del sentiment in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Predict`, usando il codice seguente:

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `PredictWithModelLoadedFromFile`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

Caricare il modello

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

Dopo aver creato un modello, è possibile usarlo per stimare il sentiment positivo o negativo dei dati relativi ai commenti usando il metodo <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Data.IDataView)>. Per ottenere una stima, usare `Predict` sui nuovi dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta. Aggiungere il codice seguente al metodo `PredictWithModelLoadedFromFile` per le stime:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a>Operazionalizzazione del modello: stima

Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza. Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi. Creare un'intestazione per i risultati con il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

Prima di visualizzare i risultati stimati, combinare il sentiment e la stima per visualizzare il commento originale con il sentiment stimato. Il codice seguente usa il metodo <xref:System.Linq.Enumerable.Zip%2A> per eseguire tale operazione. Aggiungere pertanto il codice seguente:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

Ora che `SentimentText` e `Sentiment` sono stati combinati in una classe, è possibile visualizzare i risultati usando il metodo <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

Poiché i nomi degli elementi di tupla dedotti sono una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.
A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva). Selezionare il pulsante **OK** .

## <a name="results"></a>Risultati

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione della pipeline, vengono visualizzati messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.0\Data\Model.zip

=============== Prediction Test of loaded model with a multiple sample ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: He is the best, and the article should say that. | Prediction: Not Toxic | Probability: 0.9924279

```

La procedura è stata completata. A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi. È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> * Informazioni sul problema
> * Selezionare l'attività di apprendimento automatico appropriata
> * Preparare i dati
> * Creare la pipeline di apprendimento
> * Caricare un classificatore
> * Eseguire il training del modello
> * Valutare il modello con un set di dati diverso
> * Stimare i risultati dei dati di test con il modello

Passare all'esercitazione successiva per altre informazioni
> [!div class="nextstepaction"]
> [Classificazione del problema](github-issue-classification.md)
