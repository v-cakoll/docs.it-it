---
title: 'Esercitazione: ML.NET modello di classificazione delle immagini da TensorFlowTutorial: ML.NET image classification model from TensorFlow'
description: Informazioni su come trasferire le conoscenze da un modello TensorFlow esistente in un nuovo modello di classificazione delle immagini ML.NET. Il modello TensorFlow è stato sottoposto a training per classificare le immagini in mille categorie. Il modello ML.NET utilizza l'apprendimento dei trasferimenti per classificare le immagini in categorie meno più ampie.
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 1e5478f53c82f36ddafe19e3659e2234ff9687b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78241026"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a>Esercitazione: Generare un modello di classificazione delle immagini ML.NET da un modello TensorFlow pre-addestratoTutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model

Informazioni su come trasferire le conoscenze da un modello TensorFlow esistente in un nuovo modello di classificazione delle immagini ML.NET.

Il modello TensorFlow è stato sottoposto a training per classificare le immagini in mille categorie. Il modello ML.NET utilizza parte del modello TensorFlow nella pipeline per eseguire il training di un modello per classificare le immagini in 3 categorie.

Il training di un modello di [classificazione delle immagini](https://en.wikipedia.org/wiki/Outline_of_object_recognition) da zero richiede l'impostazione di milioni di parametri, di una considerevole quantità di dati di training con etichetta e di un notevole importo di risorse di calcolo (centinaia di ore di GPU). Anche se non è così efficace come il training di un modello personalizzato da zero, l'apprendimento trasferito consente di semplificare questo processo usando migliaia di immagini anziché milioni di immagini con etichetta e di creare un modello personalizzato abbastanza rapidamente (entro un'ora in un computer senza GPU). Questa esercitazione ridimensiona ulteriormente il processo, usando solo una dozzina di immagini di training.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Incorporare il modello TensorFlow pre-addestrato nella pipeline ML.NET
> * Eseguire il training e la valutazione del modello ML.NET
> * Classificare un'immagine di prova

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF). Si noti che per impostazione predefinita il progetto .NET per questa esercitazione è configurato per .NET Core 2.2.

## <a name="what-is-transfer-learning"></a>Che cos'è l'apprendimento trasferito?

Trasferire l'apprendimento è il processo di utilizzo delle conoscenze acquisite durante la risoluzione di un problema e l'applicazione a un problema diverso ma correlato.

Per questa esercitazione, si usa parte di un modello TensorFlow, addestrato per classificare le immagini in mille categorie, in un modello di ML.NET che classifica le immagini in 3 categorie.

## <a name="prerequisites"></a>Prerequisites

* [Visual Studio 2017 versione 15.6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro ".NET Core cross-platform development" installato.
* [File ZIP della directory assets dell'esercitazione](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)
* [Modello di Machine Learning InceptionV1](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico corretta

### <a name="deep-learning"></a>Deep Learning

Il [Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) è un subset di Machine Learning che sta rivoluzionando aree quali Visione artificiale e Riconoscimento vocale.

I modelli di Deep Learning vengono sottoposti a training con set di grandi dimensioni di [dati con etichetta](https://en.wikipedia.org/wiki/Labeled_data) e [reti neurali](https://en.wikipedia.org/wiki/Artificial_neural_network) contenenti più livelli di apprendimento. Il Deep Learning:

* Offre prestazioni ottimali per alcune attività come Visione artificiale.
* Richiede enormi quantità di dati di training.

La classificazione delle immagini è un'attività comune di Machine Learning che consente di classificare automaticamente le immagini in categorie quali:Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:

* Rilevamento di un volto umano in un'immagine.
* Rilevamento di gatti contro cani.

 Oppure, come nelle immagini seguenti, determinare se un'immagine è un(n) cibo, giocattolo o apparecchio:

![immagine di una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![immagine di un orsetto](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![immagine di un tostapane](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Le immagini precedenti appartengono a Wikimedia Commons, con gli attributi seguenti:
>
> * "220px-Pepperoni_pizza.jpg" pubblico dominio, https://commons.wikimedia.org/w/index.php?curid=79505,
> * "119px-Nalle_-_a_small_brown_teddy_bear.jpg" di [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Fotografia autoprodotta, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.
> * "193px-Broodrooster.jpg" di [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Opera propria, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403

Il `Inception model` è addestrato per classificare le immagini in mille categorie, ma per questa esercitazione, è necessario classificare le immagini in un set di categorie più piccolo e solo quelle categorie. Specificare la parte `transfer` di `transfer learning`. È possibile trasferire la capacità del `Inception model` di riconoscere e classificare le immagini alle nuove categorie limitate del classificatore di immagini personalizzato.

* Food
* Giocattoli
* Elettrodomestici

Questa esercitazione usa il modello di deep learning del modello TensorFlow `ImageNet` [Inception,](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) un modello di riconoscimento delle immagini comune sottoposto a training sul set di dati. Il modello TensorFlow classifica intere immagini in mille classi, come "Umbrella", "Jersey" e "Dishwasher".

Poiché `Inception model` l'oggetto è già stato preaddestrato su migliaia di immagini diverse, internamente contiene le caratteristiche dell'immagine necessarie per [l'identificazione dell'immagine.](https://en.wikipedia.org/wiki/Feature_(computer_vision)) Possiamo usare queste funzionalità dell'immagine interna nel modello per eseguire il training di un nuovo modello con un numero molto inferiore di classi.

Come illustrato nel diagramma seguente, viene aggiunto un riferimento ai pacchetti NuGet ML.NET nelle applicazioni .NET Core o .NET Framework. Sotto le coperte, ML.NET `TensorFlow` include e fa riferimento alla libreria `TensorFlow` nativa che consente di scrivere codice che carica un file di modello sottoposto a training esistente.

![Diagramma dell'architettura ML.NET per la trasformazione TensorFlow](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a>Classificazione multiclasse

Dopo aver utilizzato il modello di inizio TensorFlow per estrarre le funzionalità adatte come input per un algoritmo di apprendimento automatico classico, viene aggiunto un classificatore ML.NET [multiclasse](../resources/tasks.md#multiclass-classification).

Il formatore specifico utilizzato in questo caso è l'algoritmo di [regressione logistica multinomiale](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).

L'algoritmo implementato da questo trainer si comporta bene sui problemi con un gran numero di funzionalità, come nel caso di un modello di deep learning che opera sui dati immagine.

### <a name="data"></a>Data

Ci sono due origini dati: il file `.tsv` e i file di immagine.  Il file `tags.tsv` contiene due colonne: la prima è definita come `ImagePath` e la seconda è l'oggetto `Label` corrispondente all'immagine. Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

Le immagini di training e di test si trovano nelle cartelle assets che verranno scaricate in un file ZIP. Queste immagini appartengono a Wikimedia Commons.
> *[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), il repository di file multimediali gratuiti.* Recuperato 10:48, 17 ottobre 2018 da: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toasterhttps://commons.wikimedia.org/wiki/Teddy_bear

## <a name="setup"></a>Configurazione

### <a name="create-a-project"></a>Creare un progetto

1. Creare un'**applicazione console di .NET Core** con nome "TransferLearningTF".

1. Installare il **pacchetto NuGet Microsoft.ML**:

    * In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.
    * Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**.
    * Fare clic sull'elenco a discesa **Versione,** selezionare il pacchetto **1.4.0** nell'elenco e selezionare il pulsante **Installa.**
    * Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche.**
    * Selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione licenza** se si è soddisfatti delle condizioni di licenza per i pacchetti elencati.
    * Ripetere questi passaggi per **Microsoft.ML.ImageAnalytics v1.4.0**, **SciSharp.TensorFlow.Redist v1.15.0** e **Microsoft.ML.TensorFlow v1.4.0**.

### <a name="download-assets"></a>Scaricare gli asset

1. Scaricare [il file zip della directory delle risorse](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)del progetto e decomprimere.

1. Copiare la directory `assets` nella directory del progetto *TransferLearningTF*. Questa directory e le relative sottodirectory contengono i file di dati e supporto (fatta eccezione per il modello Inception, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.

1. Scaricare il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) e decomprimere il file.

1. Copiare il contenuto della directory `inception5h` appena decompressa nella directory `assets/inception` del progetto *TransferLearningTF*. Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:

   ![Contenuto della directory Inception](./media/image-classification/inception-files.png)

1. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**. In **Avanzate**, modificare il valore di **Copia nella directory** di output in Copia se **più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

1. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: 

    [!code-csharp[AddUsings](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#AddUsings)]

1. Aggiungete il codice seguente alla `Main` riga destra sopra il metodo per specificare i percorsi degli asset:

    [!code-csharp[DeclareGlobalVariables](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DeclareGlobalVariables)]

1. Creare classi per i dati di input e le stime.

    [!code-csharp[DeclareImageData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DeclareImageData)]

    `ImageData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:

    * `ImagePath` contiene il nome del file di immagine.
    * `Label` contiene un valore per l'etichetta dell'immagine.

1. Aggiungere una nuova classe al progetto per `ImagePrediction`:

    [!code-csharp[DeclareImagePrediction](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DeclareImagePrediction)]

    `ImagePrediction` è la classe di stima delle immagini e ha i campi seguenti:

    * `Score` contiene la percentuale di probabilità per una data classificazione dell'immagine.
    * `PredictedLabelValue` contiene un valore per l'etichetta di classificazione dell'immagine stimata.

    `ImagePrediction` è la classe usata per la stima dopo il training del modello. Ha un oggetto `string` (`ImagePath`) per il percorso dell'immagine. Il `Label` viene utilizzato per riutilizzare ed eseguire il training del modello. `PredictedLabelValue` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

1. Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext`.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

    [!code-csharp[CreateMLContext](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#CreateMLContext)]

    La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

### <a name="create-a-struct-for-inception-model-parameters"></a>Creare uno struct per i parametri del modello InceptionCreate a struct for Inception model parameters

1. Il modello Inception dispone di diversi parametri che è necessario passare. Creare uno struct per eseguire il mapping dei valori dei `Main()` parametri ai nomi descrittivi con il codice seguente, subito dopo il metodo:

    [!code-csharp[InceptionSettings](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Creare un metodo dell'utilità di visualizzazione

Poiché i dati dell'immagine e le relative stime verranno visualizzati più volte, creare un metodo dell'utilità di visualizzazione per gestire la visualizzazione dell'immagine e dei risultati delle stime.

1. Creare il metodo `DisplayResults()` subito dopo lo struct `InceptionSettings`, usando il codice seguente:

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. Compilare il corpo `DisplayResults` del metodo:

    [!code-csharp[DisplayPredictions](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a>Creare un metodo dell'utilità con file TSV

1. Creare il metodo `ReadFromTsv()` subito dopo il metodo `DisplayResults()`, usando il codice seguente:

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. Compilare il corpo `ReadFromTsv` del metodo:

    [!code-csharp[ReadFromTsv](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ReadFromTsv)]

    Il codice analizza `tags.tsv` il file per aggiungere il percorso del `ImagePath` file al nome `Label` del `ImageData` file di immagine per la proprietà e caricarlo e in un oggetto .

### <a name="create-a-method-to-make-a-prediction"></a>Creare un metodo per eseguire una stimaCreate a method to make a prediction

1. Creare il metodo `ClassifySingleImage()` subito prima del metodo `DisplayResults()`, con il codice seguente:

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Creare `ImageData` un oggetto contenente il percorso completo e `ImagePath`il nome del file di immagine per il singolo file . Aggiungere il codice seguente al metodo `ClassifySingleImage()` come righe successive:

    [!code-csharp[LoadImageData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#LoadImageData)]

1. Eseguire una singola stima, aggiungendo il codice seguente `ClassifySingleImage` come riga successiva nel metodo:

    [!code-csharp[PredictSingle](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#PredictSingle)]

    Per ottenere la stima, utilizzate il metodo [Predict().](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) Il [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di convenienza, che consente di eseguire una stima su una singola istanza di dati. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe. È accettabile utilizzare in ambienti a thread singolo o prototipi. Per migliorare le prestazioni e la `PredictionEnginePool` thread safety negli [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ambienti di produzione, usare il servizio, che crea un oggetto da utilizzare in tutta l'applicazione. Vedere questa guida su come [utilizzare `PredictionEnginePool` in un'API Web di base di ASP.NET.](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)

    > [!NOTE]
    > L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

1. Visualizzare i risultati della stima come riga di codice successiva nel metodo `ClassifySingleImage()`:

   [!code-csharp[DisplayPrediction](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a>Costruire la pipeline del modello di ML.NET

Una pipeline di ML.NET modello è una catena di stimatori. Si noti che non viene eseguita alcuna esecuzione durante la costruzione della pipeline. Gli oggetti dello stimatore vengono creati ma non eseguiti.

1. Aggiungere un metodo per generare il modelloAdd a method to generate the model

    Questo metodo è il cuore del tutorial. Crea una pipeline per il modello ed esegue il training della pipeline per produrre il modello ML.NET. Valuta inoltre il modello rispetto ad alcuni dati di test non visti in precedenza.

    Creare il metodo `GenerateModel()`, subito dopo lo struct `InceptionSettings` e subito prima del metodo `DisplayResults()`, usando il codice seguente:

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. Aggiungi gli stimatori per caricare, ridimensionare ed estrarre i pixel dai dati dell'immagine:

    [!code-csharp[ImageTransforms](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ImageTransforms)]

    I dati dell'immagine devono essere elaborati nel formato previsto dal modello TensorFlow. In questo caso, le immagini vengono caricate in memoria, ridimensionate in modo coerente e i pixel vengono estratti in un vettore numerico.

1. Aggiungere lo stimatore per caricare il modello TensorFlow e assegnargli un punteggio:

    [!code-csharp[ScoreTensorFlowModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ScoreTensorFlowModel)]

    Questa fase nella pipeline carica il modello TensorFlow in memoria, quindi elabora il vettore dei valori di pixel tramite la rete del modello TensorFlow.This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network. L'applicazione di input a un modello di deep learning e la generazione di un output tramite il modello vengono definiti **Assegnazione punteggio**. Quando si usa il modello nella sua interezza, il punteggio fa un'inferenza o una stima.

    In questo caso, si utilizza tutto il modello TensorFlow ad eccezione dell'ultimo layer, ovvero il livello che effettua l'inferenza. L'output del penultimo livello `softmax_2_preactivation`è etichettato . L'output di questo layer è in effetti un vettore di feature che caratterizzano le immagini di input originali.

    Questo vettore di entità geografiche generato dal modello TensorFlow verrà usato come input per un algoritmo di training ML.NET.

1. Aggiungere lo stimatore per eseguire il mapping delle etichette di stringa nei dati di training a valori di chiave integer:Add the estimator to map the string labels in the training data to integer key values:

    [!code-csharp[MapValueToKey](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#MapValueToKey)]

    Il formatore ML.NET che viene aggiunto successivamente `key` richiede che le etichette siano in formato anziché stringhe arbitrarie. Una chiave è un numero che ha un mapping uno a uno a un valore stringa.

1. Aggiungere l'algoritmo di formazione per il ML.NET:Add the ML.NET training algorithm:

    [!code-csharp[AddTrainer](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#AddTrainer)]

1. Aggiungere lo stimatore per eseguire nuovamente il mapping del valore della chiave stimato in una stringa:Add the estimator to map the predicted key value back into a string:

    [!code-csharp[MapKeyToValue](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a>Eseguire il training del modello

1. Caricare i dati di training usando il wrapper [LoadFromTextFile.Load](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) the training data using the LoadFromTextFile wrapper. Aggiungere il codice seguente al metodo `GenerateModel()` come riga successiva:

    [!code-csharp[LoadData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#LoadData "Load the data")]

    I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView). `IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo). È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.

1. Eseguire il training del modello con i dati caricati in precedenza:Train the model with the data loaded above:

    [!code-csharp[TrainModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#TrainModel)]

    Il `Fit()` metodo esegue il training del modello applicando il set di dati di training alla pipeline.

## <a name="evaluate-the-accuracy-of-the-model"></a>Valutare l'accuratezza del modello

1. Caricare e trasformare i dati di test aggiungendo il `GenerateModel` codice seguente alla riga successiva del metodo:

    [!code-csharp[LoadAndTransformTestData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    Esistono alcune immagini di esempio che è possibile utilizzare per valutare il modello. Analogamente ai dati di training, questi devono essere caricati in un `IDataView`oggetto , in modo che possano essere trasformati dal modello.

1. Aggiungere il codice `GenerateModel()` seguente al metodo per valutare il modello:Add the following code to the method to evaluate the model:

    [!code-csharp[Evaluate](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#Evaluate)]

    Dopo aver impostato la stima, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):

    * Valuta il modello (confronta i valori stimati `labels`con il set di dati di test).
    * Restituisce le metriche relative alle prestazioni del modello.

1. Visualizzare le metriche di accuratezza del modello

    Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

    [!code-csharp[DisplayMetrics](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DisplayMetrics)]

    Le metriche seguenti vengono valutate per la classificazione delle immagini:

    * `Log-loss`: vedere [Perdita di log](../resources/glossary.md#log-loss). Il valore desiderato per LogLoss è il valore più prossimo a 0.
    * `Per class Log-loss`. Il valore desiderato per LogLoss per classe è il valore più prossimo a 0.

1. Aggiungere il codice seguente per restituire il modello sottoposto a training come riga successiva:

    [!code-csharp[SaveModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ReturnModel)]

## <a name="run-the-application"></a>Eseguire l'applicazione.

1. Aggiungere la `GenerateModel` chiamata `Main` a nel metodo dopo la creazione della classe MLContext:

    [!code-csharp[CallGenerateModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#CallGenerateModel)]

1. Aggiungere la chiamata `ClassifySingleImage()` al metodo come riga `Main` di codice successiva nel metodo:

    [!code-csharp[CallClassifySingleImage](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#CallClassifySingleImage)]

1. Eseguire l'app console (CTRL e F5). I risultati saranno simili all'output seguente.  È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.

    ```console
    =============== Training classification model ===============
    Image: broccoli2.jpg predicted as: food with score: 0.8955513
    Image: pizza3.jpg predicted as: food with score: 0.9667718
    Image: teddy6.jpg predicted as: toy with score: 0.9797683
    =============== Classification metrics ===============
    LogLoss is: 0.0653774699265059
    PerClassLogLoss is: 0.110315812569315 , 0.0204391272836966 , 0
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9646884
    ```

Congratulazioni! È stato creato correttamente un modello di apprendimento automatico per `TensorFlow` la classificazione delle immagini applicando l'apprendimento di trasferimento a un modello in ML.NET.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Incorporare il modello TensorFlow pre-addestrato nella pipeline ML.NET
> * Eseguire il training e la valutazione del modello ML.NET
> * Classificare un'immagine di prova

Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di classificazione delle immagini esteso.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/)
