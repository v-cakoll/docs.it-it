---
title: 'Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model'
description: Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model. The TensorFlow model was trained to classify images into a thousand categories. The ML.NET model makes use of transfer learning to classify images into fewer broader categories.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
author: natke
ms.author: nakersha
ms.openlocfilehash: 952ce5c52bcd09b8c4e4e40d5ddf85835a26478d
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204995"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a>Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model

Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.

The TensorFlow model was trained to classify images into a thousand categories. The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.

Il training di un modello di [classificazione delle immagini](https://en.wikipedia.org/wiki/Outline_of_object_recognition) da zero richiede l'impostazione di milioni di parametri, di una considerevole quantità di dati di training con etichetta e di un notevole importo di risorse di calcolo (centinaia di ore di GPU). Anche se non è così efficace come il training di un modello personalizzato da zero, l'apprendimento trasferito consente di semplificare questo processo usando migliaia di immagini anziché milioni di immagini con etichetta e di creare un modello personalizzato abbastanza rapidamente (entro un'ora in un computer senza GPU). This tutorial scales that process down even further, using only a dozen training images.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Incorporate the pre-trained TensorFlow model into the ML.NET pipeline
> * Train and evaluate the ML.NET model
> * Classify a test image

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF). Si noti che per impostazione predefinita il progetto .NET per questa esercitazione è configurato per .NET Core 2.2.

## <a name="what-is-transfer-learning"></a>Che cos'è l'apprendimento trasferito?

Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.

For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.

## <a name="prerequisites"></a>Prerequisites

* [Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.
* [File ZIP della directory assets dell'esercitazione](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)
* [Modello di Machine Learning InceptionV1](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a>Select the right machine learning task

### <a name="deep-learning"></a>Deep Learning

Il [Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) è un subset di Machine Learning che sta rivoluzionando aree quali Visione artificiale e Riconoscimento vocale.

I modelli di Deep Learning vengono sottoposti a training con set di grandi dimensioni di [dati con etichetta](https://en.wikipedia.org/wiki/Labeled_data) e [reti neurali](https://en.wikipedia.org/wiki/Artificial_neural_network) contenenti più livelli di apprendimento. Il Deep Learning:

* Offre prestazioni ottimali per alcune attività come Visione artificiale.
* Requires huge amounts of training data.

Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:

* Rilevamento di un volto umano in un'immagine.
* Detecting cats vs. dogs.

 Or as in the following images, determining if an image is a(n)  food, toy, or appliance:

![immagine di una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![immagine di un orsetto](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![immagine di un tostapane](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Le immagini precedenti appartengono a Wikimedia Commons, con gli attributi seguenti:
>
> * "220px-Pepperoni_pizza.jpg" pubblico dominio, https://commons.wikimedia.org/w/index.php?curid=79505,
> * "119px-Nalle_-_a_small_brown_teddy_bear.jpg" di [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Fotografia autoprodotta, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.
> * "193px-Broodrooster.jpg" di [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Opera propria, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403

The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories. Specificare la parte `transfer` di `transfer learning`. È possibile trasferire la capacità del `Inception model` di riconoscere e classificare le immagini alle nuove categorie limitate del classificatore di immagini personalizzato.

* Cibo
* Giocattoli
* Elettrodomestici

This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset. The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.

Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification. We can make use of these internal image features in the model to train a new model with far fewer classes.

Come illustrato nel diagramma seguente, viene aggiunto un riferimento ai pacchetti NuGet ML.NET nelle applicazioni .NET Core o .NET Framework. Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.

![Diagramma dell'architettura ML.NET per la trasformazione TensorFlow](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a>Classificazione multiclasse

After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).

The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).

The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.

### <a name="data"></a>Dati

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
> *[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), il repository di file multimediali gratuiti.* Retrieved 10:48, October 17, 2018 from: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear

## <a name="setup"></a>Configurazione

### <a name="create-a-project"></a>Creare un progetto

1. Creare un'**applicazione console di .NET Core** con nome "TransferLearningTF".

1. Installare il **pacchetto NuGet Microsoft.ML**:

    * In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.
    * Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**.
    * Click on the **Version** drop-down, select the **1.4.0** package in the list, and select the **Install** button.
    * Select the **OK** button on the **Preview Changes** dialog.
    * Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.
    * Repeat these steps for **Microsoft.ML.ImageAnalytics v1.4.0**, **SciSharp.TensorFlow.Redist v1.15.0** and **Microsoft.ML.TensorFlow v1.4.0**.

### <a name="download-assets"></a>Download assets

1. Scaricare il [file ZIP della directory assets del progetto](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip) e decomprimerlo.

1. Copiare la directory `assets` nella directory del progetto *TransferLearningTF*. Questa directory e le relative sottodirectory contengono i file di dati e supporto (fatta eccezione per il modello Inception, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.

1. Scaricare il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) e decomprimere il file.

1. Copiare il contenuto della directory `inception5h` appena decompressa nella directory `assets/inception` del progetto *TransferLearningTF*. Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:

   ![Contenuto della directory Inception](./media/image-classification/inception-files.png)

1. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

1. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

    [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

1. Add the following code to the line right above the `Main` method to specify the asset paths:

    [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

1. Create classes for your input data, and predictions.

    [!code-csharp[DeclareImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImageData)]

    `ImageData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:

    * `ImagePath` contiene il nome del file di immagine.
    * `Label` contiene un valore per l'etichetta dell'immagine.

1. Aggiungere una nuova classe al progetto per `ImagePrediction`:

    [!code-csharp[DeclareImagePrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImagePrediction)]

    `ImagePrediction` è la classe di stima delle immagini e ha i campi seguenti:

    * `Score` contiene la percentuale di probabilità per una data classificazione dell'immagine.
    * `PredictedLabelValue` contiene un valore per l'etichetta di classificazione dell'immagine stimata.

    `ImagePrediction` è la classe usata per la stima dopo il training del modello. Ha un oggetto `string` (`ImagePath`) per il percorso dell'immagine. The `Label` is used to reuse and train the model. `PredictedLabelValue` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

1. Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext`.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

    [!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

    La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

### <a name="create-a-struct-for-inception-model-parameters"></a>Create a struct for Inception model parameters

1. The Inception model has several parameters you need to pass in. Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:

    [!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Creare un metodo dell'utilità di visualizzazione

Poiché i dati dell'immagine e le relative stime verranno visualizzati più volte, creare un metodo dell'utilità di visualizzazione per gestire la visualizzazione dell'immagine e dei risultati delle stime.

1. Creare il metodo `DisplayResults()` subito dopo lo struct `InceptionSettings`, usando il codice seguente:

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. Fill in the body of the `DisplayResults` method:

    [!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a>Creare un metodo dell'utilità con file TSV

1. Creare il metodo `ReadFromTsv()` subito dopo il metodo `DisplayResults()`, usando il codice seguente:

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. Fill in the body of the `ReadFromTsv` method:

    [!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]

    The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.

### <a name="create-a-method-to-make-a-prediction"></a>Create a method to make a prediction

1. Creare il metodo `ClassifySingleImage()` subito prima del metodo `DisplayResults()`, con il codice seguente:

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`. Aggiungere il codice seguente al metodo `ClassifySingleImage()` come righe successive:

    [!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

1. Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:

    [!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

    To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method. The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe. It's acceptable to use in single-threaded or prototype environments. For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application. See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

    > [!NOTE]
    > L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

1. Visualizzare i risultati della stima come riga di codice successiva nel metodo `ClassifySingleImage()`:

   [!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a>Construct the ML.NET model pipeline

An ML.NET model pipeline is a chain of estimators. Note that no execution happens during pipeline construction. The estimator objects are created but not executed.

1. Add a method to generate the model

    This method is the heart of the tutorial. It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model. It also evaluates the model against some previously unseen test data.

    Creare il metodo `GenerateModel()`, subito dopo lo struct `InceptionSettings` e subito prima del metodo `DisplayResults()`, usando il codice seguente:

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. Add the estimators to load, resize and extract the pixels from the image data:

    [!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

    The image data needs to be processed into the format that the TensorFlow model expects. In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.

1. Add the estimator to load the TensorFlow model, and score it:

    [!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

    This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network. Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**. When using the model in its entirety, scoring makes an inference, or prediction.

    In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference. The output of the penultimate layer is labeled `softmax_2_preactivation`. The output of this layer is effectively a vector of features that characterize the original input images.

    This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.

1. Add the estimator to map the string labels in the training data to integer key values:

    [!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey)]

    The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings. A key is a number that has a one to one mapping to a string value.

1. Add the ML.NET training algorithm:

    [!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

1. Add the estimator to map the predicted key value back into a string:

    [!code-csharp[MapKeyToValue](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a>Eseguire il training del modello

1. Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper. Aggiungere il codice seguente al metodo `GenerateModel()` come riga successiva:

    [!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

    I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView). `IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo). È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.

1. Train the model with the data loaded above:

    [!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

    The `Fit()` method trains your model by applying the training dataset to the pipeline.

## <a name="evaluate-the-accuracy-of-the-model"></a>Evaluate the accuracy of the model

1. Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:

    [!code-csharp[LoadAndTransformTestData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    There are a few sample images that you can use to evaluate the model. Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.

1. Add the following code to the `GenerateModel()` method to evaluate the model:

    [!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

    Dopo aver impostato la stima, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):

    * Assesses the model (compares the predicted values with the test dataset `labels`).
    * Restituisce le metriche relative alle prestazioni del modello.

1. Display the model accuracy metrics

    Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

    [!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

    Le metriche seguenti vengono valutate per la classificazione delle immagini:

    * `Log-loss`: vedere [Perdita di log](../resources/glossary.md#log-loss). Il valore desiderato per LogLoss è il valore più prossimo a 0.
    * `Per class Log-loss` Il valore desiderato per LogLoss per classe è il valore più prossimo a 0.

1. Aggiungere il codice seguente per restituire il modello sottoposto a training come riga successiva:

    [!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="run-the-application"></a>Run the application!

1. Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:

    [!code-csharp[CallGenerateModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallGenerateModel)]

1. Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:

    [!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

1. Run your console app (Ctrl + F5). I risultati saranno simili all'output seguente.  È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.

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

La procedura è stata completata. You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

In questa esercitazione si è appreso come:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Incorporate the pre-trained TensorFlow model into the ML.NET pipeline
> * Train and evaluate the ML.NET model
> * Classify a test image

Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di classificazione delle immagini esteso.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/)
