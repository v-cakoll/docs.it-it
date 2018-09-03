---
title: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment
description: Informazioni su come usare ML.NET in uno scenario di classificazione binaria per comprendere come usare la stima del sentiment al fine di eseguire l'azione appropriata.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 57ade448f5773bee3474cb46bec8ad33e3afbee3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391061"
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
> * Stimare i risultati dei dati di test con il modello

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
2. **Inserimento dei dati**
3. **Pre-elaborazione dei dati e progettazione delle funzionalità**
4. **Training e stima del modello**
5. **Valutazione del modello**
6. **Operazionalizzazione del modello**

### <a name="understand-the-problem"></a>Informazioni sul problema

È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello. La suddivisione del problema consente di stimare e valutare i risultati.

Il problema per questa esercitazione consiste nel comprendere il sentiment dei commenti in un sito Web per eseguire l'azione appropriata.

È possibile suddividere il problema nel testo del sentiment e nel valore del sentiment per i dati con cui si vuole eseguire il training del modello e un valore del sentiment stimato che è possibile valutare e quindi usare a livello operativo.

Sarà quindi necessario **determinare** il sentiment, che consente di selezionare l'attività di apprendimento automatico.

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

Per questo problema, sono noti i fatti seguenti:

Dati di training: i commenti nel sito Web possono essere positivi o negativi (**sentiment**).
Stimare il **sentiment** di un nuovo commento nel sito Web (positivo o negativo), come negli esempi seguenti:

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

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo *Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.

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

È necessario creare tre campi globali per contenere i percorsi dei file scaricati di recente:

* `_dataPath` contiene il percorso del set di dati usato per il training del modello.
* `_testDataPath` contiene il percorso del set di dati usato per valutare il modello.
* `_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.

Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

`SentimentData` è la classe dataset di input e dispone di un valore `float` (`Sentiment`) per il sentiment positivo o negativo e una stringa per il commento (`SentimentText`). A entrambi i campi sono associati attributi `Column`. Questo attributo descrive l'ordine di ogni campo nel file di dati e indica qual è il campo `Label`. `SentimentPrediction` è la classe usata per la stima dopo il training del modello. Dispone di un singolo valore booleano (`Sentiment`) e un attributo `ColumnName` `PredictedLabel`. `Label` viene usato per creare il modello ed eseguirne il training, nonché con un secondo set di dati per valutare il modello. `PredictedLabel` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

Nel file *Program.cs* modificare la firma del metodo `Main` sostituendo `void` con `async Task`, come nell'esempio seguente:

```csharp
static async Task Main(string[] args) 
{

}
```

Si aggiunge `async` a `Main` con un tipo restituito <xref:System.Threading.Tasks.Task> perché il modello verrà salvato in un file ZIP in un secondo momento e il programma deve attendere fino al completamento di tale attività esterna.

> [!NOTE]
> Un metodo *async main* consente di usare `await` nel proprio metodo `Main`. Per altre informazioni, vedere l'argomento relativo ad [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) nella Guida per programmatori C#.

Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

Il metodo `Train` esegue le attività seguenti:

* Carica o inserisce i dati.
* Esegue la pre-elaborazione dei dati ed estrae le funzionalità.
* Esegue il training del modello.
* Esegue la stima del sentiment in base ai dati di test.

Creare il metodo `Train` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a>Inserimento dei dati

Inizializzare una nuova istanza di <xref:Microsoft.ML.LearningPipeline> che includerà il caricamento dei dati, l'elaborazione dei dati/l'estrazione delle funzionalità e il modello. Aggiungere il codice seguente come prima riga del metodo `Train`:

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

L'oggetto <xref:Microsoft.ML.Data.TextLoader> è la prima parte della pipeline e carica i dati dei file di training.

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a>Pre-elaborazione dei dati e progettazione delle funzionalità

La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico. I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti. L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti. Le pipeline di trasformazione di ML.NET consentono di comporre un set personalizzato di trasformazioni che vengono applicate ai dati prima di eseguire il training o i test. Lo scopo principale delle trasformazioni è l'estrazione delle funzionalità dai dati. Il vantaggio di una pipeline di trasformazione è che dopo la definizione della pipeline di trasformazione, è possibile salvare la pipeline per applicarla ai dati di test.

Applicare un <xref:Microsoft.ML.Transforms.TextFeaturizer> per convertire la colonna `SentimentText` in un [vettore numerico](../resources/glossary.md#numerical-feature-vector) denominato `Features` usato dall'algoritmo di apprendimento automatico. Questo è il passaggio di pre-elaborazione/estrazione delle funzionalità. Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello. Aggiungere `TextFeaturizer` alla pipeline con la seguente riga di codice:

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

L'oggetto <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> è un algoritmo di apprendimento dell'albero delle decisioni da usare in questa pipeline. Come nel passaggio di estrazione delle funzionalità, l'uso dei diversi algoritmi di apprendimento disponibili in ML.NET e la modifica dei relativi parametri determinano risultati diversi. A scopo di ottimizzazione, è possibile impostare [iperparametri](../resources/glossary.md#hyperparameter) come <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> e <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>. Questi iperparametri vengono impostati prima che qualsiasi elemento possa influire sul modello e sono specifici del modello. Vengono usati per ottimizzare le prestazioni dell'albero delle decisioni, pertanto valori più grandi possono influire negativamente sulle prestazioni.

Aggiungere al metodo `Train` il codice seguente:

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a>Eseguire il training del modello

Il training del modello, <xref:Microsoft.ML.PredictionModel%602>, viene eseguito in base al set di dati caricato e trasformato. `pipeline.Train<SentimentData, SentimentPrediction>()` esegue il training della pipeline (carica i dati ed esegue il training dell'algoritmo di estrazione delle funzionalità e dell'algoritmo di apprendimento). L'esperimento non viene eseguito finché questa operazione non è stata completata.

Aggiungere al metodo `Train` il codice seguente:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Salvare e restituire il modello sottoposto a training da usare per la valutazione

A questo punto, è disponibile un modello che può essere integrato in tutte le applicazioni .NET nuove o esistenti. Per salvare il modello in un file ZIP prima della restituzione, aggiungere il codice seguente alla riga successiva in `Train`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

Restituire il modello alla fine del metodo `Train`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a>Valutare il modello

Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida. Nel metodo `Evaluate` viene passato il modello creato in `Train` per la valutazione. Creare il metodo `Evaluate` subito dopo `Train`, come nel codice seguente:

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

Il metodo `Evaluate` esegue le attività seguenti:

* Carica il set di dati di test.
* Crea l'analizzatore binario.
* Valuta il modello e crea le metriche.
* Visualizza le metriche.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

La classe <xref:Microsoft.ML.Data.TextLoader> carica il nuovo set di dati di test con lo stesso schema. È possibile valutare il modello usando questo set di dati come controllo di qualità. Aggiungere al metodo `Evaluate` il codice seguente:

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

L'oggetto <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> calcola le metriche di qualità per `PredictionModel` usando il set di dati specificato. Per visualizzare queste metriche, aggiungere l'analizzatore come riga successiva nel metodo `Evaluate`, con il codice seguente:

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<xref:Microsoft.ML.Models.BinaryClassificationMetrics> contiene le metriche complessive calcolate dagli analizzatori di classificazione binaria. Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche. Aggiungere il codice seguente:

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Visualizzazione delle metriche per la convalida del modello

Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a>Stimare i risultati dei dati di test con il modello

Creare il metodo `Predict` subito dopo il metodo `Evaluate`, usando il codice seguente:

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

Il metodo `Predict` esegue le attività seguenti:

* Crea i dati di test.
* Esegue la stima del sentiment in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `Predict`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

Dopo aver creato un modello, è possibile usarlo per stimare il sentiment positivo o negativo dei dati relativi ai commenti mediante il metodo <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType>. Per ottenere una stima, usare `Predict` sui nuovi dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a>Operazionalizzazione del modello: stima

Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza. Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi. Creare un'intestazione per i risultati con il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

Prima di visualizzare i risultati stimati, combinare il sentiment e la stima per visualizzare il commento originale con il sentiment stimato. Il codice seguente usa il metodo <xref:System.Linq.Enumerable.Zip%2A> per eseguire tale operazione. Aggiungere pertanto il codice seguente:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

Ora che `SentimentText` e `Sentiment` sono stati combinati in una classe, è possibile visualizzare i risultati usando il metodo <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

Poiché i nomi degli elementi di tupla dedotti sono una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.
A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva). Selezionare il pulsante **OK** .

## <a name="results"></a>Risultati

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione della pipeline, vengono visualizzati messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

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
> [Previsione tariffe dei taxi](taxi-fare.md)
