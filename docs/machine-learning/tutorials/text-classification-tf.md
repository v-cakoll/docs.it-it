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
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a><span data-ttu-id="7d028-104">Esercitazione: Analizzare il sentiment delle recensioni dei film utilizzando un modello TensorFlow pre-addestrato in ML.NET</span><span class="sxs-lookup"><span data-stu-id="7d028-104">Tutorial: Analyze sentiment of movie reviews using a pre-trained TensorFlow model in ML.NET</span></span>

<span data-ttu-id="7d028-105">Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare il sentiment nei commenti del sito Web.</span><span class="sxs-lookup"><span data-stu-id="7d028-105">This tutorial shows you how to use a pre-trained TensorFlow model to classify sentiment in website comments.</span></span> <span data-ttu-id="7d028-106">Il classificatore di valutazione binaria è un'applicazione console di C, sviluppata con Visual Studio.The binary sentiment classifier is a C'è console application developed using Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7d028-106">The binary sentiment classifier is a C# console application developed using Visual Studio.</span></span>

<span data-ttu-id="7d028-107">Il modello TensorFlow utilizzato in questa esercitazione è stato eseguito il training utilizzando recensioni di filmati dal database IMDB.</span><span class="sxs-lookup"><span data-stu-id="7d028-107">The TensorFlow model used in this tutorial was trained using movie reviews from the IMDB database.</span></span> <span data-ttu-id="7d028-108">Una volta che hai finito di sviluppare l'applicazione, sarai in grado di fornire il testo della recensione del film e l'applicazione ti dirà se la recensione ha un sentimento positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="7d028-108">Once you have finished developing the application, you will be able to supply movie review text and the application will tell you whether the review has positive or negative sentiment.</span></span>

<span data-ttu-id="7d028-109">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="7d028-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="7d028-110">Caricare un modello TensorFlow pre-addestrato</span><span class="sxs-lookup"><span data-stu-id="7d028-110">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="7d028-111">Trasformare il testo del commento del sito Web in funzioni adatte al modello</span><span class="sxs-lookup"><span data-stu-id="7d028-111">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="7d028-112">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="7d028-112">Use the model to make a prediction</span></span>

<span data-ttu-id="7d028-113">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="7d028-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d028-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="7d028-114">Prerequisites</span></span>

* <span data-ttu-id="7d028-115">[Visual Studio 2017 versione 15.6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro ".NET Core cross-platform development" installato.</span><span class="sxs-lookup"><span data-stu-id="7d028-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="setup"></a><span data-ttu-id="7d028-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7d028-116">Setup</span></span>

### <a name="create-the-application"></a><span data-ttu-id="7d028-117">Creazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7d028-117">Create the application</span></span>

1. <span data-ttu-id="7d028-118">Creare **un'applicazione console .NET Core** denominata "TextClassificationTF".</span><span class="sxs-lookup"><span data-stu-id="7d028-118">Create a **.NET Core Console Application** called "TextClassificationTF".</span></span>

2. <span data-ttu-id="7d028-119">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="7d028-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="7d028-120">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="7d028-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="7d028-121">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="7d028-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="7d028-122">Scegliere "nuget.org" come origine del pacchetto, quindi selezionare la scheda **Sfoglia.** Cerca **Microsoft.ML**, selezionare il pacchetto desiderato, quindi fare clic sul pulsante **Installa.**</span><span class="sxs-lookup"><span data-stu-id="7d028-122">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="7d028-123">Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto.</span><span class="sxs-lookup"><span data-stu-id="7d028-123">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="7d028-124">Ripetere questi passaggi per **Microsoft.ML.TensorFlow** e **SciSharp.TensorFlow.Redist**.</span><span class="sxs-lookup"><span data-stu-id="7d028-124">Repeat these steps for **Microsoft.ML.TensorFlow** and **SciSharp.TensorFlow.Redist**.</span></span>

### <a name="add-the-tensorflow-model-to-the-project"></a><span data-ttu-id="7d028-125">Aggiungere il modello TensorFlow al progetto</span><span class="sxs-lookup"><span data-stu-id="7d028-125">Add the TensorFlow model to the project</span></span>

> [!NOTE]
> <span data-ttu-id="7d028-126">Il modello per questa esercitazione è dal repository dotnet/machinelearning-testdata GitHub.The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span><span class="sxs-lookup"><span data-stu-id="7d028-126">The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span></span> <span data-ttu-id="7d028-127">Il modello è in formato TensorFlow SavedModel.</span><span class="sxs-lookup"><span data-stu-id="7d028-127">The model is in TensorFlow SavedModel format.</span></span>

1. <span data-ttu-id="7d028-128">Scaricare il [file zip sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true)e decomprimere.</span><span class="sxs-lookup"><span data-stu-id="7d028-128">Download the [sentiment_model zip file](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true), and unzip.</span></span>

    <span data-ttu-id="7d028-129">Il file zip contiene:</span><span class="sxs-lookup"><span data-stu-id="7d028-129">The zip file contains:</span></span>

    * <span data-ttu-id="7d028-130">`saved_model.pb`: il modello TensorFlow stesso.</span><span class="sxs-lookup"><span data-stu-id="7d028-130">`saved_model.pb`: the TensorFlow model itself.</span></span> <span data-ttu-id="7d028-131">Il modello accetta una matrice integer di lunghezza fissa (dimensione 600) di feature che rappresentano il testo in una stringa di revisione IMDB e restituisce due probabilità che sommano 1: la probabilità che la revisione dell'input abbia un sentiment positivo e la probabilità che la revisione dell'input sentimento negativo.</span><span class="sxs-lookup"><span data-stu-id="7d028-131">The model takes a fixed length (size 600) integer array of features representing the text in an IMDB review string, and outputs two probabilities which sum to 1: the probability that the input review has positive sentiment, and the probability that the input review has negative sentiment.</span></span>
    * <span data-ttu-id="7d028-132">`imdb_word_index.csv`: mapping da singole parole a un valore intero.</span><span class="sxs-lookup"><span data-stu-id="7d028-132">`imdb_word_index.csv`: a mapping from individual words to an integer value.</span></span> <span data-ttu-id="7d028-133">Il mapping viene utilizzato per generare le funzionalità di input per il modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="7d028-133">The mapping is used to generate the input features for the TensorFlow model.</span></span>

2. <span data-ttu-id="7d028-134">Copiare il contenuto `sentiment_model` della directory più interna `sentiment_model` nella directory del progetto *TextClassificationTF.*</span><span class="sxs-lookup"><span data-stu-id="7d028-134">Copy the contents of the innermost `sentiment_model` directory into your *TextClassificationTF* project `sentiment_model` directory.</span></span> <span data-ttu-id="7d028-135">Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="7d028-135">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![sentiment_model del contenuto della directory](./media/text-classification-tf/sentiment-model-files.png)

3. <span data-ttu-id="7d028-137">In Esplora soluzioni fare clic con `sentiment_model` il pulsante destro del mouse su ognuno dei file nella directory e nella sottodirectory e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7d028-137">In Solution Explorer, right-click each of the files in the `sentiment_model` directory and subdirectory and select **Properties**.</span></span> <span data-ttu-id="7d028-138">In **Avanzate**, modificare il valore di **Copia nella directory** di output in Copia se **più recente**.</span><span class="sxs-lookup"><span data-stu-id="7d028-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="add-using-statements-and-global-variables"></a><span data-ttu-id="7d028-139">Aggiungere istruzioni using e variabili globaliAdd using statements and global variables</span><span class="sxs-lookup"><span data-stu-id="7d028-139">Add using statements and global variables</span></span>

1. <span data-ttu-id="7d028-140">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: </span><span class="sxs-lookup"><span data-stu-id="7d028-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

   [!code-csharp[AddUsings](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="7d028-141">Creare due variabili globali `Main` proprio sopra il metodo per contenere il percorso del file del modello salvato e la lunghezza del vettore di entità geografiche.</span><span class="sxs-lookup"><span data-stu-id="7d028-141">Create two global variables right above the `Main` method to hold the saved model file path, and the feature vector length.</span></span>

   [!code-csharp[DeclareGlobalVariables](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * <span data-ttu-id="7d028-142">`_modelPath`è il percorso del file del modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="7d028-142">`_modelPath` is the file path of the trained model.</span></span>
    * <span data-ttu-id="7d028-143">`FeatureLength`è la lunghezza della matrice di entità geografiche integer prevista dal modello.</span><span class="sxs-lookup"><span data-stu-id="7d028-143">`FeatureLength` is the length of the integer feature array that the model is expecting.</span></span>

### <a name="model-the-data"></a><span data-ttu-id="7d028-144">Modellare i dati</span><span class="sxs-lookup"><span data-stu-id="7d028-144">Model the data</span></span>

<span data-ttu-id="7d028-145">Le recensioni dei film sono testo in forma libera.</span><span class="sxs-lookup"><span data-stu-id="7d028-145">Movie reviews are free form text.</span></span> <span data-ttu-id="7d028-146">L'applicazione converte il testo nel formato di input previsto dal modello in una serie di fasi discrete.</span><span class="sxs-lookup"><span data-stu-id="7d028-146">Your application converts the text into the input format expected by the model in a number of discrete stages.</span></span>

<span data-ttu-id="7d028-147">Il primo consiste nel dividere il testo in parole separate e utilizzare il file di mapping fornito per mappare ogni parola su una codifica intera.</span><span class="sxs-lookup"><span data-stu-id="7d028-147">The first is to split the text into separate words and use the provided mapping file to map each word onto an integer encoding.</span></span> <span data-ttu-id="7d028-148">Il risultato di questa trasformazione è una matrice di integer a lunghezza variabile con una lunghezza corrispondente al numero di parole nella frase.</span><span class="sxs-lookup"><span data-stu-id="7d028-148">The result of this transformation is a variable length integer array with a length corresponding to the number of words in the sentence.</span></span>

|<span data-ttu-id="7d028-149">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7d028-149">Property</span></span>| <span data-ttu-id="7d028-150">valore</span><span class="sxs-lookup"><span data-stu-id="7d028-150">Value</span></span>|<span data-ttu-id="7d028-151">Type</span><span class="sxs-lookup"><span data-stu-id="7d028-151">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="7d028-152">Testorevisione</span><span class="sxs-lookup"><span data-stu-id="7d028-152">ReviewText</span></span>|<span data-ttu-id="7d028-153">questo film è davvero buono</span><span class="sxs-lookup"><span data-stu-id="7d028-153">this film is really good</span></span>|<span data-ttu-id="7d028-154">string</span><span class="sxs-lookup"><span data-stu-id="7d028-154">string</span></span>|
|<span data-ttu-id="7d028-155">VariableLengthCaratteristiche</span><span class="sxs-lookup"><span data-stu-id="7d028-155">VariableLengthFeatures</span></span>|<span data-ttu-id="7d028-156">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="7d028-156">14,22,9,66,78,...</span></span> |<span data-ttu-id="7d028-157">int[]</span><span class="sxs-lookup"><span data-stu-id="7d028-157">int[]</span></span>|

<span data-ttu-id="7d028-158">La matrice di feature a lunghezza variabile viene quindi ridimensionata a una lunghezza fissa di 600.</span><span class="sxs-lookup"><span data-stu-id="7d028-158">The variable length feature array is then resized to a fixed length of 600.</span></span> <span data-ttu-id="7d028-159">Questa è la lunghezza prevista dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="7d028-159">This is the length that the TensorFlow model expects.</span></span>

|<span data-ttu-id="7d028-160">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7d028-160">Property</span></span>| <span data-ttu-id="7d028-161">valore</span><span class="sxs-lookup"><span data-stu-id="7d028-161">Value</span></span>|<span data-ttu-id="7d028-162">Type</span><span class="sxs-lookup"><span data-stu-id="7d028-162">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="7d028-163">Testorevisione</span><span class="sxs-lookup"><span data-stu-id="7d028-163">ReviewText</span></span>|<span data-ttu-id="7d028-164">questo film è davvero buono</span><span class="sxs-lookup"><span data-stu-id="7d028-164">this film is really good</span></span>|<span data-ttu-id="7d028-165">string</span><span class="sxs-lookup"><span data-stu-id="7d028-165">string</span></span>|
|<span data-ttu-id="7d028-166">VariableLengthCaratteristiche</span><span class="sxs-lookup"><span data-stu-id="7d028-166">VariableLengthFeatures</span></span>|<span data-ttu-id="7d028-167">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="7d028-167">14,22,9,66,78,...</span></span> |<span data-ttu-id="7d028-168">int[]</span><span class="sxs-lookup"><span data-stu-id="7d028-168">int[]</span></span>|
|<span data-ttu-id="7d028-169">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="7d028-169">Features</span></span>|<span data-ttu-id="7d028-170">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="7d028-170">14,22,9,66,78,...</span></span> |<span data-ttu-id="7d028-171">int[600]</span><span class="sxs-lookup"><span data-stu-id="7d028-171">int[600]</span></span>|

1. <span data-ttu-id="7d028-172">Creare una classe per i `Main` dati di input, dopo il metodo:Create a class for your input data, after the method:</span><span class="sxs-lookup"><span data-stu-id="7d028-172">Create a class for your input data, after the `Main` method:</span></span>

    [!code-csharp[MovieReviewClass](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MovieReviewClass "Declare movie review type")]

    <span data-ttu-id="7d028-173">La classe di `MovieReview`dati `string` di input,`ReviewText`, dispone di un per i commenti dell'utente ( ).</span><span class="sxs-lookup"><span data-stu-id="7d028-173">The input data class, `MovieReview`, has a `string` for user comments (`ReviewText`).</span></span>

1. <span data-ttu-id="7d028-174">Creare una classe per le funzioni `Main` di lunghezza variabile, dopo il metodo:</span><span class="sxs-lookup"><span data-stu-id="7d028-174">Create a class for the variable length features, after the `Main` method:</span></span>

    [!code-csharp[VariableLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    <span data-ttu-id="7d028-175">La `VariableLengthFeatures` proprietà dispone di un attributo [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) per designarlo come vettore.</span><span class="sxs-lookup"><span data-stu-id="7d028-175">The `VariableLengthFeatures` property has a [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) attribute to designate it as a vector.</span></span>  <span data-ttu-id="7d028-176">Tutti gli elementi vettoriali devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="7d028-176">All of the vector elements must be the same type.</span></span> <span data-ttu-id="7d028-177">Nei set di dati con un numero elevato di colonne, il caricamento di più colonne come vettore singolo riduce il numero di passaggi di dati quando si applicano trasformazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="7d028-177">In data sets with a large number of columns, loading multiple columns as a single vector reduces the number of data passes when you apply data transformations.</span></span>

    <span data-ttu-id="7d028-178">Questa classe viene `ResizeFeatures` utilizzata nell'azione.</span><span class="sxs-lookup"><span data-stu-id="7d028-178">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="7d028-179">I nomi delle relative proprietà (in questo caso solo una) vengono utilizzati per indicare quali colonne nel DataView possono essere utilizzate come _input_ per l'azione di mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7d028-179">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _input_ to the custom mapping action.</span></span>

1. <span data-ttu-id="7d028-180">Creare una classe per le feature `Main` a lunghezza fissa, dopo il metodo:</span><span class="sxs-lookup"><span data-stu-id="7d028-180">Create a class for the fixed length features, after the `Main` method:</span></span>

    [!code-csharp[FixedLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#FixedLengthFeatures)]

    <span data-ttu-id="7d028-181">Questa classe viene `ResizeFeatures` utilizzata nell'azione.</span><span class="sxs-lookup"><span data-stu-id="7d028-181">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="7d028-182">I nomi delle relative proprietà (in questo caso solo una) vengono utilizzati per indicare quali colonne nel DataView possono essere utilizzate come _output_ dell'azione di mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7d028-182">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _output_ of the custom mapping action.</span></span>

    <span data-ttu-id="7d028-183">Si noti che `Features` il nome della proprietà è determinato dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="7d028-183">Note that the name of the property `Features` is determined by the TensorFlow model.</span></span> <span data-ttu-id="7d028-184">Non è possibile modificare il nome di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="7d028-184">You cannot change this property name.</span></span>

1. <span data-ttu-id="7d028-185">Creare una classe per `Main` la stima dopo il metodo:Create a class for the prediction after the method:</span><span class="sxs-lookup"><span data-stu-id="7d028-185">Create a class for the prediction after the `Main` method:</span></span>

    [!code-csharp[Prediction](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Prediction "Declare prediction class")]

    <span data-ttu-id="7d028-186">`MovieReviewSentimentPrediction` è la classe di stima usata dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="7d028-186">`MovieReviewSentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="7d028-187">`MovieReviewSentimentPrediction`dispone di `float` una`Prediction`singola `VectorType` matrice ( ) e di un attributo .</span><span class="sxs-lookup"><span data-stu-id="7d028-187">`MovieReviewSentimentPrediction` has a single `float` array (`Prediction`) and a `VectorType` attribute.</span></span>

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a><span data-ttu-id="7d028-188">Creare MLContext, dizionario di ricerca e azione per ridimensionare le featureCreate the MLContext, lookup dictionary, and action to resize features</span><span class="sxs-lookup"><span data-stu-id="7d028-188">Create the MLContext, lookup dictionary, and action to resize features</span></span>

<span data-ttu-id="7d028-189">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7d028-189">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="7d028-190">L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="7d028-190">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="7d028-191">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="7d028-191">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

1. <span data-ttu-id="7d028-192">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:</span><span class="sxs-lookup"><span data-stu-id="7d028-192">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

   [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateMLContext "Create the ML Context")]

1. <span data-ttu-id="7d028-193">Creare un dizionario per codificare le [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) parole come numeri interi utilizzando il metodo per caricare i dati di mapping da un file, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="7d028-193">Create a dictionary to encode words as integers by using the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method to load mapping data from a file, as seen in the following table:</span></span>

    |<span data-ttu-id="7d028-194">Word</span><span class="sxs-lookup"><span data-stu-id="7d028-194">Word</span></span>     |<span data-ttu-id="7d028-195">Indice</span><span class="sxs-lookup"><span data-stu-id="7d028-195">Index</span></span>    |
    |---------|---------|
    |<span data-ttu-id="7d028-196">Bambini</span><span class="sxs-lookup"><span data-stu-id="7d028-196">kids</span></span>     |  <span data-ttu-id="7d028-197">362</span><span class="sxs-lookup"><span data-stu-id="7d028-197">362</span></span>    |
    |<span data-ttu-id="7d028-198">want</span><span class="sxs-lookup"><span data-stu-id="7d028-198">want</span></span>     |  <span data-ttu-id="7d028-199">181</span><span class="sxs-lookup"><span data-stu-id="7d028-199">181</span></span>    |
    |<span data-ttu-id="7d028-200">Sbagliato</span><span class="sxs-lookup"><span data-stu-id="7d028-200">wrong</span></span>    |  <span data-ttu-id="7d028-201">355</span><span class="sxs-lookup"><span data-stu-id="7d028-201">355</span></span>    |
    |<span data-ttu-id="7d028-202">effects</span><span class="sxs-lookup"><span data-stu-id="7d028-202">effects</span></span>  |  <span data-ttu-id="7d028-203">302</span><span class="sxs-lookup"><span data-stu-id="7d028-203">302</span></span>    |
    |<span data-ttu-id="7d028-204">Sensazione</span><span class="sxs-lookup"><span data-stu-id="7d028-204">feeling</span></span>  |  <span data-ttu-id="7d028-205">547</span><span class="sxs-lookup"><span data-stu-id="7d028-205">547</span></span>    |

    <span data-ttu-id="7d028-206">Aggiungere il codice seguente per creare la mappa di ricerca:Add the code below to create the lookup map:</span><span class="sxs-lookup"><span data-stu-id="7d028-206">Add the code below to create the lookup map:</span></span>

    [!code-csharp[CreateLookupMap](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateLookupMap)]

1. <span data-ttu-id="7d028-207">Aggiungere `Action` un per ridimensionare la matrice integer word a lunghezza variabile a una matrice di interi di dimensioni fisse, con le righe di codice successive:</span><span class="sxs-lookup"><span data-stu-id="7d028-207">Add an `Action` to resize the variable length word integer array to an integer array of fixed size, with the next lines of code:</span></span>

   [!code-csharp[ResizeFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a><span data-ttu-id="7d028-208">Caricare il modello TensorFlow pre-addestrato</span><span class="sxs-lookup"><span data-stu-id="7d028-208">Load the pre-trained TensorFlow model</span></span>

1. <span data-ttu-id="7d028-209">Aggiungere il codice per caricare il modello TensorFlow:Add code to load the TensorFlow model:</span><span class="sxs-lookup"><span data-stu-id="7d028-209">Add code to load the TensorFlow model:</span></span>

    [!code-csharp[LoadTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#LoadTensorFlowModel)]

    <span data-ttu-id="7d028-210">Una volta caricato il modello, è possibile estrarne l'input e lo schema di output.</span><span class="sxs-lookup"><span data-stu-id="7d028-210">Once the model is loaded, you can extract its input and output schema.</span></span> <span data-ttu-id="7d028-211">Gli schemi vengono visualizzati solo per interessi e per l'apprendimento.</span><span class="sxs-lookup"><span data-stu-id="7d028-211">The schemas are displayed for interest and learning only.</span></span> <span data-ttu-id="7d028-212">Questo codice non è necessario per il funzionamento dell'applicazione finale:You do not need this code for the final application to function:</span><span class="sxs-lookup"><span data-stu-id="7d028-212">You do not need this code for the final application to function:</span></span>

    [!code-csharp[GetModelSchema](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#GetModelSchema)]

    <span data-ttu-id="7d028-213">Lo schema di input è la matrice a lunghezza fissa di parole con codifica integer.</span><span class="sxs-lookup"><span data-stu-id="7d028-213">The input schema is the fixed-length array of integer encoded words.</span></span> <span data-ttu-id="7d028-214">Lo schema di output è una matrice float di probabilità che indica se il sentiment di una revisione è negativo o positivo.</span><span class="sxs-lookup"><span data-stu-id="7d028-214">The output schema is a float array of probabilities indicating whether a review's sentiment is negative, or positive .</span></span> <span data-ttu-id="7d028-215">Questi valori sommano a 1, poiché la probabilità di essere positivi è il complemento della probabilità che il sentimento sia negativo.</span><span class="sxs-lookup"><span data-stu-id="7d028-215">These values sum to 1, as the probability of being positive is the complement of the probability of the sentiment being negative.</span></span>

## <a name="create-the-mlnet-pipeline"></a><span data-ttu-id="7d028-216">Creare la pipeline di ML.NETCreate the ML.NET pipeline</span><span class="sxs-lookup"><span data-stu-id="7d028-216">Create the ML.NET pipeline</span></span>

1. <span data-ttu-id="7d028-217">Creare la pipeline e dividere il testo di input in parole usando la trasformazione TokenizeIntoWords per suddividere il testo in parole come riga di codice successiva:Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span><span class="sxs-lookup"><span data-stu-id="7d028-217">Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span></span>

   [!code-csharp[TokenizeIntoWords](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#TokenizeIntoWords)]

   <span data-ttu-id="7d028-218">La trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) utilizza spazi per analizzare il testo/stringa in parole.</span><span class="sxs-lookup"><span data-stu-id="7d028-218">The [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform uses spaces to parse the text/string into words.</span></span> <span data-ttu-id="7d028-219">Crea una nuova colonna e divide ogni stringa di input in un vettore di sottostringhe in base al separatore definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7d028-219">It creates a new column and splits each input string to a vector of substrings based on the user-defined separator.</span></span>

1. <span data-ttu-id="7d028-220">Mappare le parole sulla codifica integer utilizzando la tabella di ricerca dichiarata in precedenza:</span><span class="sxs-lookup"><span data-stu-id="7d028-220">Map the words onto their integer encoding using the lookup table that you declared above:</span></span>

    [!code-csharp[MapValue](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MapValue)]

1. <span data-ttu-id="7d028-221">Ridimensionare le codifiche intere a lunghezza variabile in quella a lunghezza fissa richiesta dal modello:</span><span class="sxs-lookup"><span data-stu-id="7d028-221">Resize the variable length integer encodings to the fixed-length one required by the model:</span></span>

    [!code-csharp[CustomMapping](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CustomMapping)]

1. <span data-ttu-id="7d028-222">Classificare l'input con il modello TensorFlow caricato:</span><span class="sxs-lookup"><span data-stu-id="7d028-222">Classify the input with the loaded TensorFlow model:</span></span>

    [!code-csharp[ScoreTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="7d028-223">Viene chiamato `Prediction/Softmax`l'output del modello TensorFlow .</span><span class="sxs-lookup"><span data-stu-id="7d028-223">The TensorFlow model output is called `Prediction/Softmax`.</span></span> <span data-ttu-id="7d028-224">Si noti `Prediction/Softmax` che il nome è determinato dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="7d028-224">Note that the name `Prediction/Softmax` is determined by the TensorFlow model.</span></span> <span data-ttu-id="7d028-225">Non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="7d028-225">You cannot change this name.</span></span>

1. <span data-ttu-id="7d028-226">Creare una nuova colonna per la stima di output:Create a new column for the output prediction:</span><span class="sxs-lookup"><span data-stu-id="7d028-226">Create a new column for the output prediction:</span></span>

    [!code-csharp[SnippetCopyColumns](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCopyColumns)]

    <span data-ttu-id="7d028-227">È necessario copiare la `Prediction/Softmax` colonna in una con un nome che può `Prediction`essere utilizzato come proprietà in una classe C: .</span><span class="sxs-lookup"><span data-stu-id="7d028-227">You need to copy the `Prediction/Softmax` column into one with a name that can be used as a property in a C# class: `Prediction`.</span></span> <span data-ttu-id="7d028-228">Il `/` carattere non è consentito in un nome di proprietà di C.</span><span class="sxs-lookup"><span data-stu-id="7d028-228">The `/` character is not allowed in a C# property name.</span></span>

## <a name="create-the-mlnet-model-from-the-pipeline"></a><span data-ttu-id="7d028-229">Creare il modello di ML.NET dalla pipelineCreate the ML.NET model from the pipeline</span><span class="sxs-lookup"><span data-stu-id="7d028-229">Create the ML.NET model from the pipeline</span></span>

1. <span data-ttu-id="7d028-230">Aggiungere il codice per creare il modello dalla pipeline:Add the code to create the model from the pipeline:</span><span class="sxs-lookup"><span data-stu-id="7d028-230">Add the code to create the model from the pipeline:</span></span>

    [!code-csharp[SnippetCreateModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCreateModel)]

    <span data-ttu-id="7d028-231">Un modello ML.NET viene creato dalla catena di stimanella `Fit` nella pipeline chiamando il metodo .</span><span class="sxs-lookup"><span data-stu-id="7d028-231">An ML.NET model is created from the chain of estimators in the pipeline by calling the `Fit` method.</span></span> <span data-ttu-id="7d028-232">In questo caso, non è stato adattato alcun dato per creare il modello, poiché il modello TensorFlow è già stato sottoposto a training in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7d028-232">In this case, we are not fitting any data to create the model, as the TensorFlow model has already been previously trained.</span></span> <span data-ttu-id="7d028-233">Forniamo un oggetto visualizzazione dati vuoto `Fit` per soddisfare i requisiti del metodo.</span><span class="sxs-lookup"><span data-stu-id="7d028-233">We supply an empty data view object to satisfy the requirements of the `Fit` method.</span></span>

## <a name="use-the-model-to-make-a-prediction"></a><span data-ttu-id="7d028-234">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="7d028-234">Use the model to make a prediction</span></span>

1. <span data-ttu-id="7d028-235">Aggiungere `PredictSentiment` il metodo `Main` sotto il metodo:</span><span class="sxs-lookup"><span data-stu-id="7d028-235">Add the `PredictSentiment` method below the `Main` method:</span></span>

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="7d028-236">Aggiungere il codice seguente `PredictionEngine` per creare la `PredictSentiment()` prima riga nel metodo:</span><span class="sxs-lookup"><span data-stu-id="7d028-236">Add the following code to create the `PredictionEngine` as the first line in the `PredictSentiment()` method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreatePredictionEngine)]

    <span data-ttu-id="7d028-237">Il [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di convenienza, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="7d028-237">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="7d028-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="7d028-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="7d028-239">È accettabile utilizzare in ambienti a thread singolo o prototipi.</span><span class="sxs-lookup"><span data-stu-id="7d028-239">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="7d028-240">Per migliorare le prestazioni e la `PredictionEnginePool` thread safety negli [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ambienti di produzione, usare il servizio, che crea un oggetto da utilizzare in tutta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d028-240">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="7d028-241">Vedere questa guida su come [utilizzare `PredictionEnginePool` in un'API Web di base di ASP.NET.](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)</span><span class="sxs-lookup"><span data-stu-id="7d028-241">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d028-242">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="7d028-242">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="7d028-243">Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict()` creando un'istanza di `MovieReview`:</span><span class="sxs-lookup"><span data-stu-id="7d028-243">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `MovieReview`:</span></span>

    [!code-csharp[CreateTestData](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateTestData)]

1. <span data-ttu-id="7d028-244">Passare i dati del `Prediction Engine` commento di test a `PredictSentiment()` e aggiungendo le righe di codice successive nel metodo:</span><span class="sxs-lookup"><span data-stu-id="7d028-244">Pass the test comment data to the `Prediction Engine` by adding the next lines of code in the `PredictSentiment()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Predict)]

1. <span data-ttu-id="7d028-245">La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) effettua una stima su una singola riga di dati:</span><span class="sxs-lookup"><span data-stu-id="7d028-245">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

    |<span data-ttu-id="7d028-246">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7d028-246">Property</span></span>| <span data-ttu-id="7d028-247">valore</span><span class="sxs-lookup"><span data-stu-id="7d028-247">Value</span></span>|<span data-ttu-id="7d028-248">Type</span><span class="sxs-lookup"><span data-stu-id="7d028-248">Type</span></span>|
    |-------------|-----------------------|------|
    |<span data-ttu-id="7d028-249">Previsione</span><span class="sxs-lookup"><span data-stu-id="7d028-249">Prediction</span></span>|<span data-ttu-id="7d028-250">[0.5459937, 0.454006255]</span><span class="sxs-lookup"><span data-stu-id="7d028-250">[0.5459937, 0.454006255]</span></span>|<span data-ttu-id="7d028-251">galleggiante[]</span><span class="sxs-lookup"><span data-stu-id="7d028-251">float[]</span></span>|

1. <span data-ttu-id="7d028-252">Visualizzare la stima del sentiment usando il codice seguente:Display sentiment prediction using the following code:</span><span class="sxs-lookup"><span data-stu-id="7d028-252">Display sentiment prediction using the following code:</span></span>

    [!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DisplayPredictions)]

1. <span data-ttu-id="7d028-253">Aggiungere una `PredictSentiment` chiamata a alla `Main` fine del metodo:</span><span class="sxs-lookup"><span data-stu-id="7d028-253">Add a call to `PredictSentiment` at the end of the `Main` method:</span></span>

    [!code-csharp[CallPredictSentiment](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CallPredictSentiment)]

## <a name="results"></a><span data-ttu-id="7d028-254">Risultati</span><span class="sxs-lookup"><span data-stu-id="7d028-254">Results</span></span>

<span data-ttu-id="7d028-255">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d028-255">Build and run your application.</span></span>

<span data-ttu-id="7d028-256">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7d028-256">Your results should be similar to the following.</span></span> <span data-ttu-id="7d028-257">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="7d028-257">During processing, messages are displayed.</span></span> <span data-ttu-id="7d028-258">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="7d028-258">You may see warnings, or processing messages.</span></span> <span data-ttu-id="7d028-259">Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="7d028-259">These messages have been removed from the following results for clarity.</span></span>

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

<span data-ttu-id="7d028-260">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="7d028-260">Congratulations!</span></span> <span data-ttu-id="7d028-261">È stato creato correttamente un modello di apprendimento automatico per classificare e `TensorFlow` prevedere il sentiment dei messaggi riutilizzando un modello con training preliminare in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7d028-261">You've now successfully built a machine learning model for classifying and predicting messages sentiment by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="7d028-262">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="7d028-262">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

<span data-ttu-id="7d028-263">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="7d028-263">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="7d028-264">Caricare un modello TensorFlow pre-addestrato</span><span class="sxs-lookup"><span data-stu-id="7d028-264">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="7d028-265">Trasformare il testo del commento del sito Web in funzioni adatte al modello</span><span class="sxs-lookup"><span data-stu-id="7d028-265">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="7d028-266">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="7d028-266">Use the model to make a prediction</span></span>
