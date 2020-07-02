---
title: 'Esercitazione: analizzare i sentimenti di revisione usando un modello TensorFlow'
description: Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare i sentimenti nei commenti dei siti Web. Il classificatore dei sentimenti binari è un'applicazione console C# sviluppata con Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9c1e45f183bd5edc488e4f37bea648566d124c65
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803261"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a>Esercitazione: analizzare i sentimenti delle revisioni dei film usando un modello TensorFlow con training preliminare in ML.NET

Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare i sentimenti nei commenti dei siti Web. Il classificatore dei sentimenti binari è un'applicazione console C# sviluppata con Visual Studio.

Il modello TensorFlow usato in questa esercitazione è stato sottoposto a training con le revisioni dei film del database IMDB. Al termine dello sviluppo dell'applicazione, sarà possibile fornire il testo della revisione del film e l'applicazione indica se la revisione ha un sentimento positivo o negativo.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> * Caricare un modello di TensorFlow con training preliminare
> * Trasforma il testo del commento del sito Web in funzionalità appropriate per il modello
> * Usare il modello per eseguire una stima

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.

## <a name="setup"></a>Configurazione

### <a name="create-the-application"></a>Creazione dell'applicazione

1. Creare un' **applicazione console .NET Core** denominata "TextClassificationTF".

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, quindi selezionare la scheda **Sfoglia** . cercare **Microsoft.ml**, selezionare il pacchetto desiderato e quindi fare clic sul pulsante **Installa** . Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto. Ripetere questi passaggi per **Microsoft. ml. TensorFlow**, **Microsoft. ml. SampleUtils** e **SciSharp. TensorFlow. Redist**.

### <a name="add-the-tensorflow-model-to-the-project"></a>Aggiungere il modello TensorFlow al progetto

> [!NOTE]
> Il modello per questa esercitazione è del repository GitHub [DotNet/machinelearning-TESTDATA](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) . Il modello è in formato TensorFlow SavedModel.

1. Scaricare il [file zip di sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true)e decomprimere.

    Il file zip contiene:

    * `saved_model.pb`: modello TensorFlow. Il modello accetta una matrice di valori interi di lunghezza fissa (dimensione 600) che rappresenta il testo in una stringa di revisione di IMDB e restituisce due probabilità che sommano a 1: la probabilità che la revisione di input abbia un sentimento positivo e la probabilità che la revisione dell'input abbia un sentimento negativo.
    * `imdb_word_index.csv`: un mapping da singole parole a un valore integer. Il mapping viene utilizzato per generare le funzionalità di input per il modello TensorFlow.

2. Copiare il contenuto della directory più interna `sentiment_model` nella directory del progetto *TextClassificationTF* `sentiment_model` . Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:

   ![contenuto della directory sentiment_model](./media/text-classification-tf/sentiment-model-files.png)

3. In Esplora soluzioni fare clic con il pulsante destro del mouse su ogni file nella `sentiment_model` Directory e nella sottodirectory e selezionare **Proprietà**. In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.

### <a name="add-using-statements-and-global-variables"></a>Aggiungere istruzioni using e variabili globali

1. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: 

   [!code-csharp[AddUsings](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#AddUsings "Add necessary usings")]

1. Creare due variabili globali al di sopra del `Main` metodo per conservare il percorso del file del modello salvato e la lunghezza del vettore di funzionalità.

   [!code-csharp[DeclareGlobalVariables](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * `_modelPath`è il percorso del file del modello sottoposto a training.
    * `FeatureLength`lunghezza della matrice di funzionalità Integer prevista per il modello.

### <a name="model-the-data"></a>Modellare i dati

Le revisioni del film sono testo in formato libero. L'applicazione converte il testo nel formato di input previsto dal modello in diverse fasi discrete.

Il primo consiste nel suddividere il testo in parole separate e utilizzare il file di mapping specificato per eseguire il mapping di ogni parola a una codifica di tipo Integer. Il risultato di questa trasformazione è una matrice integer a lunghezza variabile con una lunghezza corrispondente al numero di parole nella frase.

|Proprietà| Valore|Type|
|-------------|-----------------------|------|
|ReviewText|Questo film è molto valido|string|
|VariableLengthFeatures|14, 22, 9, 66, 78,... |int []|

La matrice di funzionalità a lunghezza variabile viene quindi ridimensionata a una lunghezza fissa di 600. Si tratta della lunghezza prevista dal modello TensorFlow.

|Proprietà| Valore|Type|
|-------------|-----------------------|------|
|ReviewText|Questo film è molto valido|string|
|VariableLengthFeatures|14, 22, 9, 66, 78,... |int []|
|Funzionalità|14, 22, 9, 66, 78,... |int [600]|

1. Creare una classe per i dati di input, dopo il `Main` Metodo:

    [!code-csharp[MovieReviewClass](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MovieReviewClass "Declare movie review type")]

    La classe di dati di input, `MovieReview` , dispone di `string` per i commenti degli utenti ( `ReviewText` ).

1. Creare una classe per le funzionalità a lunghezza variabile, dopo il `Main` Metodo:

    [!code-csharp[VariableLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    La `VariableLengthFeatures` proprietà dispone di un attributo [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) per designarlo come vettore.  Tutti gli elementi Vector devono essere dello stesso tipo. Nei set di dati con un numero elevato di colonne, il caricamento di più colonne come un singolo vettore riduce il numero di passaggi di dati quando si applicano le trasformazioni dei dati.

    Questa classe viene utilizzata nell' `ResizeFeatures` azione. I nomi delle proprietà (in questo caso solo uno) vengono utilizzati per indicare quali colonne del DataView possono essere utilizzate come _input_ per l'azione di mapping personalizzata.

1. Creare una classe per le funzionalità a lunghezza fissa, dopo il `Main` Metodo:

    [!code-csharp[FixedLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#FixedLengthFeatures)]

    Questa classe viene utilizzata nell' `ResizeFeatures` azione. I nomi delle proprietà (in questo caso solo uno) vengono utilizzati per indicare quali colonne del DataView possono essere utilizzate come _output_ dell'azione di mapping personalizzata.

    Si noti che il nome della proprietà `Features` è determinato dal modello TensorFlow. Non è possibile modificare questo nome di proprietà.

1. Creare una classe per la stima dopo il `Main` Metodo:

    [!code-csharp[Prediction](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Prediction "Declare prediction class")]

    `MovieReviewSentimentPrediction` è la classe di stima usata dopo il training del modello. `MovieReviewSentimentPrediction`dispone di una singola `float` matrice ( `Prediction` ) e di un `VectorType` attributo.

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a>Creare il MLContext, il dizionario di ricerca e l'azione per ridimensionare le funzionalità

La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET. L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

1. Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:

   [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateMLContext "Create the ML Context")]

1. Creare un dizionario per codificare le parole come numeri interi usando il [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) metodo per caricare i dati di mapping da un file, come illustrato nella tabella seguente:

    |Word     |Indice    |
    |---------|---------|
    |bambini     |  362    |
    |want     |  181    |
    |errato    |  355    |
    |effects  |  302    |
    |ci si sente  |  547    |

    Aggiungere il codice seguente per creare la mappa di ricerca:

    [!code-csharp[CreateLookupMap](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateLookupMap)]

1. Aggiungere un oggetto `Action` per ridimensionare la matrice di tipo Integer a lunghezza variabile in una matrice di numeri interi di dimensioni fisse, con le righe di codice seguenti:

   [!code-csharp[ResizeFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a>Caricare il modello di TensorFlow con training preliminare

1. Aggiungere codice per caricare il modello di TensorFlow:

    [!code-csharp[LoadTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#LoadTensorFlowModel)]

    Una volta caricato il modello, è possibile estrarne lo schema di input e di output. Gli schemi vengono visualizzati solo per interesse e apprendimento. Questo codice non è necessario per il funzionamento dell'applicazione finale:

    [!code-csharp[GetModelSchema](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#GetModelSchema)]

    Lo schema di input è la matrice a lunghezza fissa di parole con codifica Integer. Lo schema di output è una matrice di probabilità float che indica se il sentimento di una verifica è negativo o positivo. Questi valori vengono sommati a 1, in quanto la probabilità di essere positivi è il complemento della probabilità che il sentimento sia negativo.

## <a name="create-the-mlnet-pipeline"></a>Creare la pipeline ML.NET

1. Creare la pipeline e suddividere il testo di input in parole usando la trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) per suddividere il testo in parole come riga di codice successiva:

   [!code-csharp[TokenizeIntoWords](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#TokenizeIntoWords)]

   La trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) usa gli spazi per analizzare la stringa di testo in parole. Crea una nuova colonna e suddivide ogni stringa di input in un vettore di sottostringhe in base al separatore definito dall'utente.

1. Eseguire il mapping delle parole sulla codifica Integer usando la tabella di ricerca dichiarata in precedenza:

    [!code-csharp[MapValue](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MapValue)]

1. Ridimensionare le codifiche Integer a lunghezza variabile a una lunghezza fissa richiesta dal modello:

    [!code-csharp[CustomMapping](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CustomMapping)]

1. Classificare l'input con il modello TensorFlow caricato:

    [!code-csharp[ScoreTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ScoreTensorFlowModel)]

    Viene chiamato l'output del modello TensorFlow `Prediction/Softmax` . Si noti che il nome `Prediction/Softmax` è determinato dal modello TensorFlow. Non è possibile modificare questo nome.

1. Crea una nuova colonna per la stima di output:

    [!code-csharp[SnippetCopyColumns](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCopyColumns)]

    È necessario copiare la `Prediction/Softmax` colonna in un oggetto con un nome che può essere usato come proprietà in una classe C#: `Prediction` . Il `/` carattere non è consentito in un nome di proprietà C#.

## <a name="create-the-mlnet-model-from-the-pipeline"></a>Creare il modello ML.NET dalla pipeline

1. Aggiungere il codice per creare il modello dalla pipeline:

    [!code-csharp[SnippetCreateModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCreateModel)]

    Un modello ML.NET viene creato dalla catena di estimatori nella pipeline chiamando il `Fit` metodo. In questo caso, i dati non vengono adattati per la creazione del modello, perché è già stato eseguito il training del modello TensorFlow. Viene fornito un oggetto visualizzazione dati vuoto per soddisfare i requisiti del `Fit` metodo.

## <a name="use-the-model-to-make-a-prediction"></a>Usare il modello per eseguire una stima

1. Aggiungere il `PredictSentiment` Metodo sotto il `Main` Metodo:

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Aggiungere il codice seguente per creare `PredictionEngine` come prima riga nel `PredictSentiment()` Metodo:

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreatePredictionEngine)]

    [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe. È accettabile usare in ambienti a thread singolo o prototipi. Per migliorare le prestazioni e thread safety negli ambienti di produzione, utilizzare il `PredictionEnginePool` servizio, che consente di creare un oggetto [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da utilizzare nell'applicazione. Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

    > [!NOTE]
    > L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

1. Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict()` creando un'istanza di `MovieReview`:

    [!code-csharp[CreateTestData](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateTestData)]

1. Passare i dati del commento di test a `Prediction Engine` aggiungendo le righe di codice seguenti nel `PredictSentiment()` Metodo:

    [!code-csharp[Predict](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Predict)]

1. La funzione [Predict ()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola riga di dati:

    |Proprietà| Valore|Type|
    |-------------|-----------------------|------|
    |Previsione|[0,5459937, 0,454006255]|float []|

1. Visualizzare la stima del sentimento usando il codice seguente:

    [!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DisplayPredictions)]

1. Aggiungere una chiamata a alla `PredictSentiment` fine del `Main` Metodo:

    [!code-csharp[CallPredictSentiment](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CallPredictSentiment)]

## <a name="results"></a>Risultati

Compilare ed eseguire l'applicazione.

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione, vengono visualizzati alcuni messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

Congratulazioni! A questo punto, è stato creato un modello di apprendimento automatico per la classificazione e la stima del sentimento dei messaggi riutilizzando un modello con training preliminare `TensorFlow` in ml.NET.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> * Caricare un modello di TensorFlow con training preliminare
> * Trasforma il testo del commento del sito Web in funzionalità appropriate per il modello
> * Usare il modello per eseguire una stima
