---
title: Usare ML.NET in uno scenario di classificazione multiclasse dei problemi in GitHub
description: Informazioni su come usare ML.NET in uno scenario di classificazione multiclasse per assegnare i problemi di GitHub a un'area specifica.
ms.date: 01/24/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a951e884a7494b0dcc808fc3dafbfadebc5577dc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254990"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a>Esercitazione: Usare ML.NET in uno scenario di classificazione multiclasse per classificare i problemi di GitHub.

Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore di problemi di GitHub tramite un'applicazione console .NET Core con C# in Visual Studio 2017.

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

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

## <a name="github-issue-sample-overview"></a>Panoramica di esempio di problema GitHub

L'esempio è un'app console che usa ML.NET per il training di un modello che classifica e stima l'etichetta Area associata a un problema di GitHub. Valuta inoltre il modello con un secondo set di dati per l'analisi della qualità. I set di dati del problema derivano dal repository GitHub dotnet/corefx.

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

* Il [file separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).
* Il [file di test separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).

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

L'oggetto della presente esercitazione è la definizione dell'area da cui provengono i problemi di GitHub in ingresso, per etichettarli correttamente ai fini dell'assegnazione della priorità e della pianificazione.

È possibile suddividere il problema nei seguenti componenti:

* testo del titolo del problema
* testo della descrizione del problema
* valore di area per i dati di training del modello
* valore di area stimato che è possibile valutare e quindi usare a livello operativo

È quindi necessario **determinare** l'area, che facilita la selezione dell'attività di apprendimento automatico.

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

Per questo problema, sono noti i fatti seguenti:

Dati di training:

I problemi di GitHub possono essere etichettati in aree diverse (**Area**), come negli esempi seguenti:

* area-System.Numerics
* area-System.Xml
* area-Infrastructure
* area-System.Linq
* area-System.IO

È possibile eseguire la stima del valore **Area** di un nuovo problema in GitHub, come negli esempi seguenti:

* Contract.Assert rispetto a Debug.Assert
* Rendere i campi di sola lettura in System.Xml

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

Per questo tipo di problema, usare un'attività di classificazione multiclasse, poiché la stima della categoria di problemi può essere una di più categorie (multiclasse) piuttosto che solo due (binarie).

## <a name="create-a-console-application"></a>Creare un'applicazione console

### <a name="create-a-project"></a>Creare un progetto

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

### <a name="prepare-your-data"></a>Preparare i dati

1. Scaricare i set di dati [issues_train.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) e salvarli nella cartella *Data* creata in precedenza. Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

È necessario creare tre campi globali per i percorsi dei file scaricati di recente e una variabile globale per l'istanza di `TextLoader`:

* `_trainDataPath` contiene il percorso del set di dati usato per il training del modello.
* `_testDataPath` contiene il percorso del set di dati usato per valutare il modello.
* `_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.
* `_mlContext` è l'elemento <xref:Microsoft.ML.MLContext> che specifica il contesto di elaborazione.
* `_trainingDataView` è l'elemento <xref:Microsoft.ML.Data.IDataView> usato per elaborare il set di dati di training.
* `_predEngine` è l'elemento <xref:Microsoft.ML.PredictionEngine%602> usato per le stime singole.
* `_reader` è l'istanza della classe <xref:Microsoft.ML.Data.TextLoader> usata per caricare e trasformare i set di dati.

Aggiungere il codice seguente nella riga subito sopra il metodo `Main` per specificare questi percorsi e le altre variabili:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** impostando *GitHubIssueData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *GitHubIssueData.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio del file *GitHubIssueData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `GitHubIssue` e `IssuePrediction`, al file *GitHubIssueData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

`GitHubIssue` è la classe del set di dati input e ha i seguenti campi <xref:System.String>:

* `ID` contiene un valore per l'ID del problema GitHub
* `Area` contiene un valore per l'etichetta `Area`
* `Title` contiene il titolo del problema GitHub
* `Description` contiene la descrizione del problema GitHub

`IssuePrediction` è la classe usata per la stima dopo il training del modello. Dispone di un `string` singolo (`Area`) e di un attributo `PredictedLabel` `ColumnName`. `Label` viene usato per creare il modello ed eseguirne il training, nonché con un secondo set di dati per valutare il modello. `PredictedLabel` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

Quando si crea un modello con ML.NET, si inizia creando un <xref:Microsoft.ML.MLContext>. A livello concettuale questa operazione è paragonabile all'uso di `DbContext` in Entity Framework. L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Inizializzare la variabile globale `_mlContext` con una nuova istanza di `MLContext` con un valore di inizializzazione casuale (`seed: 0`) per risultati ripetibili/deterministici in più training.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a>Caricare i dati

Quindi inizializzare la variabile globale `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> e caricare i dati con il parametro `_trainDataPath`.

 Come input e output di `Transforms`, una `DataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.

In ML.NET i dati sono simili a una `SQL view`. Vengono valutati in modalità differita, sono schematizzati ed eterogenei. L'oggetto è la prima parte della pipeline e carica i dati. Per questa esercitazione carica un set di dati con titoli e descrizioni di problemi e con l'etichetta GitHub dell'area corrispondente. L'elemento `DataView` viene usato per creare il modello ed eseguirne il training.

Poiché il tipo di modello di dati `GitHubIssue` creato in precedenza corrisponde allo schema del set di dati, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati in un'unica riga di codice.

La prima parte della riga (`CreateTextReader<GitHubIssue>(hasHeader: true)`) crea un <xref:Microsoft.ML.Data.TextLoader> tramite inferenza dello schema del set di dati dal tipo modello di dati `GitHubIssue` e usando l'intestazione del set di dati.

Lo schema di dati è stato definito in precedenza quando è stata creata la classe `GitHubIssue`. Per lo schema:

* La prima colonna `ID` (ID problema di GitHub)
* La seconda colonna `Area` (stima per il training)
* La terza colonna `Title` (titolo del problema GitHub) è la prima [funzionalità](../resources/glossary.md##feature) usata per la stima di `Area`
* La quarta colonna `Description` è la seconda funzionalità usata per la stima di `Area`

La seconda parte della riga (`.Read(_trainDataPath)`) usa il metodo <xref:Microsoft.ML.Data.TextLoader.Read%2A> per caricare il file di testo di training usando `_trainDataPath` nella variabile globale `IDataView` (`_trainingDataView`).  

Per inizializzare e caricare la variabile globale `_trainingDataView` in modo da riusarla per la pipeline, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


Aggiungere il codice seguente al metodo `Main` come riga successiva:

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

Il metodo `ProcessData` esegue le attività seguenti:

* Estrae e trasforma i dati.
* Restituisce la pipeline di elaborazione.

Creare il metodo `ProcessData` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-and-transform-the-data"></a>Estrarre e trasformare i dati

La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico. I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti. L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.

Le pipeline di trasformazione di ML.NET compongono un set personalizzato di trasformazioni che vengono applicate ai dati prima di eseguire il training o i test. Lo scopo principale delle trasformazioni è l'[estrazione delle caratteristiche](../resources/glossary.md#feature-engineering) dai dati. Gli algoritmi di apprendimento automatico sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) in modo da trasformare successivamente i dati testuali in un formato riconoscibile da tali algoritmi. Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).

Nei passaggi successivi si fa riferimento alle colonne in base ai nomi definiti nella classe `GitHubIssue`.

Quando vengono eseguiti il training e la valutazione del modello, i valori nella colonna **Label** vengono considerati per impostazione predefinita come valori corretti da stimare. Dato che si vuole stimare l'etichetta GitHub Area per un `GitHubIssue`, copiare la colonna `Area` nella colonna **Label**. A tale scopo usare `MLContext.Transforms.Conversion.MapValueToKey`, che è un wrapper per la classe di trasformazione <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.  `MapValueToKey` restituisce un oggetto <xref:Microsoft.ML.Data.EstimatorChain%601> che sarà effettivamente una pipeline. Assegnare un nome a questa `pipeline` poiché successivamente si aggiungerà l'algoritmo di training all'oggetto `EstimatorChain`. Aggiungere il codice seguente come riga successiva:

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

L'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, pertanto è necessario chiamare `mlContext.Transforms.Text.FeaturizeText`, che estrae le funzionalità delle colonne di testo (`Title` e `Description`) in vettori numerici corrispondenti con nome `TitleFeaturized` e `DescriptionFeaturized`. L'estrazione delle funzionalità assegna valori chiave numerici diversi ai diversi valori in ogni colonna ed è usata dall'algoritmo di apprendimento automatico.
Aggiungere l'estrazione delle funzionalità per entrambe le colonne alla pipeline con il codice seguente:

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione `Concatenate`. Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**. Aggiungere questa trasformazione alla pipeline con il codice seguente:

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 Aggiungere quindi <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> per memorizzare nella cache la vista dati e ottenere prestazioni migliori quando si scorrono i dati più volte usando la cache, ad esempio con il codice seguente:

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

Applicare return alla pipeline alla fine del metodo `ProcessData`.

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

Questo passaggio gestisce la pre-elaborazione/estrazione delle funzionalità. Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.

## <a name="build-and-train-the-model"></a>Compilare ed eseguire il training del modello

Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main`:

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

Il metodo `BuildAndTrainModel` esegue le attività seguenti:

* Crea la classe di algoritmo di training.
* Esegue il training del modello.
* Esegue la stima dell'area sulla base dei dati di training.
* Salva il modello in un file `.zip`.
* Restituisce il modello.

Creare il metodo `BuildAndTrainModel` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
public static void BuildAndTrainModel()
{

}
```

Si noti che nel metodo BuildAndTrainModel vengono passati due parametri, un `IDataView` per il set di dati di training (`trainingDataView`) e un <xref:Microsoft.ML.Data.EstimatorChain%601> per la pipeline di elaborazione creata in ProcessData (`pipeline`).

 Aggiungere il codice seguente come prima riga del metodo `BuildAndTrainModel`:

### <a name="choose-a-trainer-algorithm"></a>Scegliere un algoritmo di training

Per aggiungere l'algoritmo di training chiamare il metodo wrapper `mlContext.Transforms.Text.FeaturizeText`, che restituisce un oggetto <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>, un algoritmo di apprendimento basato su un albero delle decisioni che si userà in questa pipeline. L'oggetto `SdcaMultiClassTrainer` viene aggiunto a `pipeline` e accetta gli elementi `Title` e `Description` (`Features`) con estrazione di funzionalità e i parametri di input `Label` per l'apprendimento dai dati cronologici.

Aggiungere al metodo `BuildAndTrainModel` il codice seguente:

[!code-csharp[SdcaMultiClassTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SdcaMultiClassTrainer)]

Ora che è stata completata la creazione dell'algoritmo di training, aggiungerlo a `pipeline`. È anche necessario eseguire il mapping dell'etichetta al valore per restituirlo allo stato leggibile originale. Eseguire entrambe le operazioni con il codice seguente:

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a>Eseguire il training del modello

Il training del modello, <xref:Microsoft.ML.Data.TransformerChain%601>, viene eseguito in base al set di dati caricato e trasformato. Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati. Viene così restituito un modello da usare per le stime. `trainingPipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata. L'esperimento non viene eseguito finché questa operazione non è stata completata.

Aggiungere al metodo `BuildAndTrainModel` il codice seguente:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

`model` è un oggetto `transformer` che opera su molte righe di dati, ma in un ambiente produzione è spesso necessario eseguire stime su singoli esempi. <xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`. A questo punto si aggiunge il codice seguente per creare `PredictionEngine` come riga successiva nel metodo `BuildAndTrainModel`:

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]

Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

È possibile usare quanto sopra per eseguire la stima dell'etichetta `Area` di una singola istanza dei dati del problema. Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="model-operationalization-prediction"></a>Operazionalizzazione del modello: stima

Visualizzare `GitHubIssue` e la stima dell'etichetta `Area` corrispondente per condividere i risultati e agire su di essi di conseguenza. Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi. Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Salvare e restituire il modello sottoposto a training da usare per la valutazione

A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain%601> che può essere integrato nelle applicazioni .NET nuove o esistenti. Per salvare il modello sottoposto a training in un file con estensione zip, aggiungere il codice seguente per chiamare il metodo `SaveModelAsFile` come riga successiva in `BuildAndTrainModel`:

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

Restituire il modello alla fine del metodo `BuildAndTrainModel`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="save-the-model-as-azip-file"></a>Salvare il modello come file con estensione zip

Creare il metodo `SaveModelAsFile` subito dopo il metodo `BuildAndTrainModel`, usando il codice seguente:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `SaveModelAsFile` esegue le attività seguenti:

* Salva il modello come file con estensione zip.

A questo punto, creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni. L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>. Per salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`. Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a>Valutare il modello

Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida. Nel metodo `Evaluate` viene passato il modello creato in `BuildAndTrainModel` per la valutazione. Creare il metodo `Evaluate` subito dopo `BuildAndTrainModel`, come nel codice seguente:

```csharp
public static void Evaluate()
{

}
```

Il metodo `Evaluate` esegue le attività seguenti:

* Carica il set di dati di test.
* Crea l'analizzatore multiclasse.
* Valuta il modello e crea le metriche.
* Visualizza le metriche.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `BuildAndTrainModel`, usando il codice seguente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

Come in precedenza con il set di dati di training, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati di test in una sola riga di codice. È possibile valutare il modello usando questo set di dati come controllo di qualità. Aggiungere al metodo `Evaluate` il codice seguente:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

`MulticlassClassificationContext.Evaluate` è un wrapper del metodo <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> che calcola le metriche di qualità per il modello usando il set di dati specificato. Restituisce un oggetto <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> che contiene le metriche complessive calcolate dagli analizzatori della classificazione multiclasse.
Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche.
Osservare l'uso del metodo `Transform` della variabile globale di apprendimento automatico `_trainedModel` (un oggetto Transformer) per l'input di funzionalità e la generazione di stime. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

Le metriche seguenti vengono valutate per la classificazione multiclasse:

* MicroAccuracy (Accuratezza micro): ogni coppia campione-classe contribuisce nello stesso modo alla metrica di accuratezza.  Il valore desiderato per MicroAccuracy è il valore più prossimo a 1.

* MacroAccuracy (Accuratezza macro): ogni classe contribuisce nello stesso modo alla metrica di accuratezza. Alle classi di minoranza viene assegnato un peso uguale a quello delle classi più grandi. Il valore desiderato per MacroAccuracy è il valore più prossimo a 1.

* LogLoss (Perdita di log): vedere [Perdita di log](../resources/glossary.md#log-loss). Il valore desiderato per LogLoss è il valore più prossimo a 0.

* LogLossReduction (Riduzione della perdita di log): è compreso nell'intervallo [-inf, 100], dove 100 corrisponde a stime perfette e 0 indica stime medie. Il valore desiderato per LogLossReduction è il valore più prossimo a 0.

### <a name="displaying-the-metrics-for-model-validation"></a>Visualizzazione delle metriche per la convalida del modello

Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>Stimare il risultato dei dati di test con il modello salvato

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

Creare il metodo `PredictIssue` subito dopo il metodo `Evaluate`, usando il codice seguente:

```csharp
private static void PredictIssue()
{

}
```

Il metodo `PredictIssue` esegue le attività seguenti:

* Crea un singolo problema con dati di test.
* Esegue la stima dell'Area in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

In primo luogo caricare il modello salvato in precedenza con il codice seguente:

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
Ora che è presente un modello, è possibile usarlo per stimare l'etichetta GitHub Area di una singola istanza dei dati del problema di GitHub. Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta. Aggiungere il codice seguente al metodo `PredictIssue` per le stime:

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]

### <a name="model-operationalization-prediction"></a>Operazionalizzazione del modello: stima

Visualizzare `Area` per classificare il problema e agire su di esso di conseguenza. Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi. Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a>Risultati

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione della pipeline, vengono visualizzati messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

La procedura è stata completata. È stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima di un'etichetta Area per un problema di GitHub. È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

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
