---
title: 'Esercitazione: Analizzare il sentiment delle revisioni usando un modello TensorFlowTutorial: Analyze review sentiment using a TensorFlow model'
description: Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare il sentiment nei commenti del sito Web. Il classificatore di valutazione binaria è un'applicazione console di C, sviluppata con Visual Studio.The binary sentiment classifier is a C'è console application developed using Visual Studio.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 688c5b83cef8f21eef8fa24521a85449a9cfbd48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78241117"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a>Esercitazione: Analizzare il sentiment delle recensioni dei film utilizzando un modello TensorFlow pre-addestrato in ML.NET

Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare il sentiment nei commenti del sito Web. Il classificatore di valutazione binaria è un'applicazione console di C, sviluppata con Visual Studio.The binary sentiment classifier is a C'è console application developed using Visual Studio.

Il modello TensorFlow utilizzato in questa esercitazione è stato eseguito il training utilizzando recensioni di filmati dal database IMDB. Una volta che hai finito di sviluppare l'applicazione, sarai in grado di fornire il testo della recensione del film e l'applicazione ti dirà se la recensione ha un sentimento positivo o negativo.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> * Caricare un modello TensorFlow pre-addestrato
> * Trasformare il testo del commento del sito Web in funzioni adatte al modello
> * Usare il modello per eseguire una stima

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

## <a name="prerequisites"></a>Prerequisites

* [Visual Studio 2017 versione 15.6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro ".NET Core cross-platform development" installato.

## <a name="setup"></a>Configurazione

### <a name="create-the-application"></a>Creazione dell'applicazione

1. Creare **un'applicazione console .NET Core** denominata "TextClassificationTF".

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, quindi selezionare la scheda **Sfoglia.** Cerca **Microsoft.ML**, selezionare il pacchetto desiderato, quindi fare clic sul pulsante **Installa.** Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto. Ripetere questi passaggi per **Microsoft.ML.TensorFlow** e **SciSharp.TensorFlow.Redist**.

### <a name="add-the-tensorflow-model-to-the-project"></a>Aggiungere il modello TensorFlow al progetto

> [!NOTE]
> Il modello per questa esercitazione è dal repository dotnet/machinelearning-testdata GitHub.The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo. Il modello è in formato TensorFlow SavedModel.

1. Scaricare il [file zip sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true)e decomprimere.

    Il file zip contiene:

    * `saved_model.pb`: il modello TensorFlow stesso. Il modello accetta una matrice integer di lunghezza fissa (dimensione 600) di feature che rappresentano il testo in una stringa di revisione IMDB e restituisce due probabilità che sommano 1: la probabilità che la revisione dell'input abbia un sentiment positivo e la probabilità che la revisione dell'input sentimento negativo.
    * `imdb_word_index.csv`: mapping da singole parole a un valore intero. Il mapping viene utilizzato per generare le funzionalità di input per il modello TensorFlow.

2. Copiare il contenuto `sentiment_model` della directory più interna `sentiment_model` nella directory del progetto *TextClassificationTF.* Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:

   ![sentiment_model del contenuto della directory](./media/text-classification-tf/sentiment-model-files.png)

3. In Esplora soluzioni fare clic con `sentiment_model` il pulsante destro del mouse su ognuno dei file nella directory e nella sottodirectory e scegliere **Proprietà**. In **Avanzate**, modificare il valore di **Copia nella directory** di output in Copia se **più recente**.

### <a name="add-using-statements-and-global-variables"></a>Aggiungere istruzioni using e variabili globaliAdd using statements and global variables

1. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: 

   [!code-csharp[AddUsings](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#AddUsings "Add necessary usings")]

1. Creare due variabili globali `Main` proprio sopra il metodo per contenere il percorso del file del modello salvato e la lunghezza del vettore di entità geografiche.

   [!code-csharp[DeclareGlobalVariables](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * `_modelPath`è il percorso del file del modello sottoposto a training.
    * `FeatureLength`è la lunghezza della matrice di entità geografiche integer prevista dal modello.

### <a name="model-the-data"></a>Modellare i dati

Le recensioni dei film sono testo in forma libera. L'applicazione converte il testo nel formato di input previsto dal modello in una serie di fasi discrete.

Il primo consiste nel dividere il testo in parole separate e utilizzare il file di mapping fornito per mappare ogni parola su una codifica intera. Il risultato di questa trasformazione è una matrice di integer a lunghezza variabile con una lunghezza corrispondente al numero di parole nella frase.

|Proprietà| valore|Type|
|-------------|-----------------------|------|
|Testorevisione|questo film è davvero buono|string|
|VariableLengthCaratteristiche|14,22,9,66,78,... |int[]|

La matrice di feature a lunghezza variabile viene quindi ridimensionata a una lunghezza fissa di 600. Questa è la lunghezza prevista dal modello TensorFlow.

|Proprietà| valore|Type|
|-------------|-----------------------|------|
|Testorevisione|questo film è davvero buono|string|
|VariableLengthCaratteristiche|14,22,9,66,78,... |int[]|
|Funzionalità|14,22,9,66,78,... |int[600]|

1. Creare una classe per i `Main` dati di input, dopo il metodo:Create a class for your input data, after the method:

    [!code-csharp[MovieReviewClass](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MovieReviewClass "Declare movie review type")]

    La classe di `MovieReview`dati `string` di input,`ReviewText`, dispone di un per i commenti dell'utente ( ).

1. Creare una classe per le funzioni `Main` di lunghezza variabile, dopo il metodo:

    [!code-csharp[VariableLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    La `VariableLengthFeatures` proprietà dispone di un attributo [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) per designarlo come vettore.  Tutti gli elementi vettoriali devono essere dello stesso tipo. Nei set di dati con un numero elevato di colonne, il caricamento di più colonne come vettore singolo riduce il numero di passaggi di dati quando si applicano trasformazioni di dati.

    Questa classe viene `ResizeFeatures` utilizzata nell'azione. I nomi delle relative proprietà (in questo caso solo una) vengono utilizzati per indicare quali colonne nel DataView possono essere utilizzate come _input_ per l'azione di mapping personalizzato.

1. Creare una classe per le feature `Main` a lunghezza fissa, dopo il metodo:

    [!code-csharp[FixedLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#FixedLengthFeatures)]

    Questa classe viene `ResizeFeatures` utilizzata nell'azione. I nomi delle relative proprietà (in questo caso solo una) vengono utilizzati per indicare quali colonne nel DataView possono essere utilizzate come _output_ dell'azione di mapping personalizzato.

    Si noti che `Features` il nome della proprietà è determinato dal modello TensorFlow. Non è possibile modificare il nome di questa proprietà.

1. Creare una classe per `Main` la stima dopo il metodo:Create a class for the prediction after the method:

    [!code-csharp[Prediction](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Prediction "Declare prediction class")]

    `MovieReviewSentimentPrediction` è la classe di stima usata dopo il training del modello. `MovieReviewSentimentPrediction`dispone di `float` una`Prediction`singola `VectorType` matrice ( ) e di un attributo .

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a>Creare MLContext, dizionario di ricerca e azione per ridimensionare le featureCreate the MLContext, lookup dictionary, and action to resize features

La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET. L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

1. Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:

   [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateMLContext "Create the ML Context")]

1. Creare un dizionario per codificare le [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) parole come numeri interi utilizzando il metodo per caricare i dati di mapping da un file, come illustrato nella tabella seguente:

    |Word     |Indice    |
    |---------|---------|
    |Bambini     |  362    |
    |want     |  181    |
    |Sbagliato    |  355    |
    |effects  |  302    |
    |Sensazione  |  547    |

    Aggiungere il codice seguente per creare la mappa di ricerca:Add the code below to create the lookup map:

    [!code-csharp[CreateLookupMap](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateLookupMap)]

1. Aggiungere `Action` un per ridimensionare la matrice integer word a lunghezza variabile a una matrice di interi di dimensioni fisse, con le righe di codice successive:

   [!code-csharp[ResizeFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a>Caricare il modello TensorFlow pre-addestrato

1. Aggiungere il codice per caricare il modello TensorFlow:Add code to load the TensorFlow model:

    [!code-csharp[LoadTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#LoadTensorFlowModel)]

    Una volta caricato il modello, è possibile estrarne l'input e lo schema di output. Gli schemi vengono visualizzati solo per interessi e per l'apprendimento. Questo codice non è necessario per il funzionamento dell'applicazione finale:You do not need this code for the final application to function:

    [!code-csharp[GetModelSchema](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#GetModelSchema)]

    Lo schema di input è la matrice a lunghezza fissa di parole con codifica integer. Lo schema di output è una matrice float di probabilità che indica se il sentiment di una revisione è negativo o positivo. Questi valori sommano a 1, poiché la probabilità di essere positivi è il complemento della probabilità che il sentimento sia negativo.

## <a name="create-the-mlnet-pipeline"></a>Creare la pipeline di ML.NETCreate the ML.NET pipeline

1. Creare la pipeline e dividere il testo di input in parole usando la trasformazione TokenizeIntoWords per suddividere il testo in parole come riga di codice successiva:Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:

   [!code-csharp[TokenizeIntoWords](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#TokenizeIntoWords)]

   La trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) utilizza spazi per analizzare il testo/stringa in parole. Crea una nuova colonna e divide ogni stringa di input in un vettore di sottostringhe in base al separatore definito dall'utente.

1. Mappare le parole sulla codifica integer utilizzando la tabella di ricerca dichiarata in precedenza:

    [!code-csharp[MapValue](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MapValue)]

1. Ridimensionare le codifiche intere a lunghezza variabile in quella a lunghezza fissa richiesta dal modello:

    [!code-csharp[CustomMapping](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CustomMapping)]

1. Classificare l'input con il modello TensorFlow caricato:

    [!code-csharp[ScoreTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ScoreTensorFlowModel)]

    Viene chiamato `Prediction/Softmax`l'output del modello TensorFlow . Si noti `Prediction/Softmax` che il nome è determinato dal modello TensorFlow. Non è possibile modificare questo nome.

1. Creare una nuova colonna per la stima di output:Create a new column for the output prediction:

    [!code-csharp[SnippetCopyColumns](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCopyColumns)]

    È necessario copiare la `Prediction/Softmax` colonna in una con un nome che può `Prediction`essere utilizzato come proprietà in una classe C: . Il `/` carattere non è consentito in un nome di proprietà di C.

## <a name="create-the-mlnet-model-from-the-pipeline"></a>Creare il modello di ML.NET dalla pipelineCreate the ML.NET model from the pipeline

1. Aggiungere il codice per creare il modello dalla pipeline:Add the code to create the model from the pipeline:

    [!code-csharp[SnippetCreateModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCreateModel)]

    Un modello ML.NET viene creato dalla catena di stimanella `Fit` nella pipeline chiamando il metodo . In questo caso, non è stato adattato alcun dato per creare il modello, poiché il modello TensorFlow è già stato sottoposto a training in precedenza. Forniamo un oggetto visualizzazione dati vuoto `Fit` per soddisfare i requisiti del metodo.

## <a name="use-the-model-to-make-a-prediction"></a>Usare il modello per eseguire una stima

1. Aggiungere `PredictSentiment` il metodo `Main` sotto il metodo:

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Aggiungere il codice seguente `PredictionEngine` per creare la `PredictSentiment()` prima riga nel metodo:

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreatePredictionEngine)]

    Il [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di convenienza, che consente di eseguire una stima su una singola istanza di dati. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe. È accettabile utilizzare in ambienti a thread singolo o prototipi. Per migliorare le prestazioni e la `PredictionEnginePool` thread safety negli [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ambienti di produzione, usare il servizio, che crea un oggetto da utilizzare in tutta l'applicazione. Vedere questa guida su come [utilizzare `PredictionEnginePool` in un'API Web di base di ASP.NET.](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)

    > [!NOTE]
    > L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

1. Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict()` creando un'istanza di `MovieReview`:

    [!code-csharp[CreateTestData](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateTestData)]

1. Passare i dati del `Prediction Engine` commento di test a `PredictSentiment()` e aggiungendo le righe di codice successive nel metodo:

    [!code-csharp[Predict](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Predict)]

1. La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) effettua una stima su una singola riga di dati:

    |Proprietà| valore|Type|
    |-------------|-----------------------|------|
    |Previsione|[0.5459937, 0.454006255]|galleggiante[]|

1. Visualizzare la stima del sentiment usando il codice seguente:Display sentiment prediction using the following code:

    [!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DisplayPredictions)]

1. Aggiungere una `PredictSentiment` chiamata a alla `Main` fine del metodo:

    [!code-csharp[CallPredictSentiment](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CallPredictSentiment)]

## <a name="results"></a>Risultati

Compilare ed eseguire l'applicazione.

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione, vengono visualizzati alcuni messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

Congratulazioni! È stato creato correttamente un modello di apprendimento automatico per classificare e `TensorFlow` prevedere il sentiment dei messaggi riutilizzando un modello con training preliminare in ML.NET.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> * Caricare un modello TensorFlow pre-addestrato
> * Trasformare il testo del commento del sito Web in funzioni adatte al modello
> * Usare il modello per eseguire una stima
