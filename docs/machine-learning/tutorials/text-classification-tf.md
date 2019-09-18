---
title: 'Esercitazione: Analizzare i sentimenti delle revisioni dei film usando un modello TensorFlow con training preliminare'
description: Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare i sentimenti nei commenti dei siti Web. Il classificatore dei sentimenti binari è C# un'applicazione console sviluppata con Visual Studio.
ms.date: 09/11/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 2dd10c0843b2bea4755d5f4f0aceea6509c7cf46
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054307"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a><span data-ttu-id="4b997-104">Esercitazione: Analizzare i sentimenti delle revisioni dei film usando un modello TensorFlow con training preliminare in ML.NET</span><span class="sxs-lookup"><span data-stu-id="4b997-104">Tutorial: Analyze sentiment of movie reviews using a pre-trained TensorFlow model in ML.NET</span></span>

<span data-ttu-id="4b997-105">Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare i sentimenti nei commenti dei siti Web.</span><span class="sxs-lookup"><span data-stu-id="4b997-105">This tutorial shows you how to use a pre-trained TensorFlow model to classify sentiment in website comments.</span></span> <span data-ttu-id="4b997-106">Il classificatore dei sentimenti binari è C# un'applicazione console sviluppata con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b997-106">The binary sentiment classifier is a C# console application developed using Visual Studio.</span></span>

<span data-ttu-id="4b997-107">Il modello TensorFlow usato in questa esercitazione è stato sottoposto a training con le revisioni dei film del database IMDB.</span><span class="sxs-lookup"><span data-stu-id="4b997-107">The TensorFlow model used in this tutorial was trained using movie reviews from the IMDB database.</span></span> <span data-ttu-id="4b997-108">Al termine dello sviluppo dell'applicazione, sarà possibile fornire il testo della revisione del film e l'applicazione indica se la revisione ha un sentimento positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4b997-108">Once you have finished developing the application, you will be able to supply movie review text and the application will tell you whether the review has positive or negative sentiment.</span></span>

<span data-ttu-id="4b997-109">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="4b997-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4b997-110">Caricare un modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="4b997-110">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="4b997-111">Trasforma il testo del commento del sito Web in funzionalità appropriate per il modello</span><span class="sxs-lookup"><span data-stu-id="4b997-111">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="4b997-112">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="4b997-112">Use the model to make a prediction</span></span>

<span data-ttu-id="4b997-113">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="4b997-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b997-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4b997-114">Prerequisites</span></span>

* <span data-ttu-id="4b997-115">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="4b997-115">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="setup"></a><span data-ttu-id="4b997-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="4b997-116">Setup</span></span>

### <a name="create-the-application"></a><span data-ttu-id="4b997-117">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="4b997-117">Create the application</span></span>

1. <span data-ttu-id="4b997-118">Creare un' **applicazione console .NET Core** denominata "TextClassificationTF".</span><span class="sxs-lookup"><span data-stu-id="4b997-118">Create a **.NET Core Console Application** called "TextClassificationTF".</span></span>

2. <span data-ttu-id="4b997-119">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="4b997-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="4b997-120">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="4b997-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="4b997-121">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="4b997-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="4b997-122">Scegliere "nuget.org" come origine pacchetto e selezionare la scheda **Sfoglia**. Cercare **Microsoft.ML**, selezionare il pacchetto desiderato e selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="4b997-122">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="4b997-123">Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto.</span><span class="sxs-lookup"><span data-stu-id="4b997-123">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="4b997-124">Ripetere questi passaggi per **Microsoft. ml. TensorFlow**.</span><span class="sxs-lookup"><span data-stu-id="4b997-124">Repeat these steps for **Microsoft.ML.TensorFlow**.</span></span>

### <a name="add-the-tensorflow-model-to-the-project"></a><span data-ttu-id="4b997-125">Aggiungere il modello TensorFlow al progetto</span><span class="sxs-lookup"><span data-stu-id="4b997-125">Add the TensorFlow model to the project</span></span>

> [!NOTE]
> <span data-ttu-id="4b997-126">Il modello per questa esercitazione è del repository GitHub [DotNet/machinelearning-TESTDATA](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) .</span><span class="sxs-lookup"><span data-stu-id="4b997-126">The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span></span> <span data-ttu-id="4b997-127">Il modello è in formato TensorFlow SavedModel.</span><span class="sxs-lookup"><span data-stu-id="4b997-127">The model is in TensorFlow SavedModel format.</span></span>

1. <span data-ttu-id="4b997-128">Scaricare il [file zip sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true)e decomprimere.</span><span class="sxs-lookup"><span data-stu-id="4b997-128">Download the [sentiment_model zip file](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true), and unzip.</span></span>

    <span data-ttu-id="4b997-129">Il file zip contiene:</span><span class="sxs-lookup"><span data-stu-id="4b997-129">The zip file contains:</span></span>

    * <span data-ttu-id="4b997-130">`saved_model.pb`: modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="4b997-130">`saved_model.pb`: the TensorFlow model itself.</span></span> <span data-ttu-id="4b997-131">Il modello accetta una matrice di valori interi di lunghezza fissa (dimensione 600) che rappresenta il testo in una stringa di revisione di IMDB e restituisce due probabilità che sommano a 1: la probabilità che la revisione di input abbia un sentimento positivo e la probabilità che la revisione di input abbia sentimento negativo.</span><span class="sxs-lookup"><span data-stu-id="4b997-131">The model takes a fixed length (size 600) integer array of features representing the text in an IMDB review string, and outputs two probabilities which sum to 1: the probability that the input review has positive sentiment, and the probability that the input review has negative sentiment.</span></span>
    * <span data-ttu-id="4b997-132">`imdb_word_index.csv`: un mapping da singole parole a un valore integer.</span><span class="sxs-lookup"><span data-stu-id="4b997-132">`imdb_word_index.csv`: a mapping from individual words to an integer value.</span></span> <span data-ttu-id="4b997-133">Il mapping viene utilizzato per generare le funzionalità di input per il modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="4b997-133">The mapping is used to generate the input features for the TensorFlow model.</span></span>

2. <span data-ttu-id="4b997-134">Copiare il contenuto della directory più `sentiment_model` interna nella directory del progetto `sentiment_model` *TextClassificationTF* .</span><span class="sxs-lookup"><span data-stu-id="4b997-134">Copy the contents of the innermost `sentiment_model` directory into your *TextClassificationTF* project `sentiment_model` directory.</span></span> <span data-ttu-id="4b997-135">Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="4b997-135">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![contenuto della directory sentiment_model](./media/text-classification-tf/sentiment-model-files.png)

3. <span data-ttu-id="4b997-137">In Esplora soluzioni fare clic con il pulsante destro del mouse su ogni `sentiment_model` file nella directory e nella sottodirectory e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4b997-137">In Solution Explorer, right-click each of the files in the `sentiment_model` directory and subdirectory and select **Properties**.</span></span> <span data-ttu-id="4b997-138">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="4b997-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="add-using-statements-and-global-variables"></a><span data-ttu-id="4b997-139">Aggiungere istruzioni using e variabili globali</span><span class="sxs-lookup"><span data-stu-id="4b997-139">Add using statements and global variables</span></span>

1. <span data-ttu-id="4b997-140">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="4b997-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="4b997-141">Creare due variabili globali al di sopra `Main` del metodo per conservare il percorso del file del modello salvato e la lunghezza del vettore di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4b997-141">Create two global variables right above the `Main` method to hold the saved model file path, and the feature vector length.</span></span>

   [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * <span data-ttu-id="4b997-142">`_modelPath`è il percorso del file del modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="4b997-142">`_modelPath` is the file path of the trained model.</span></span>
    * <span data-ttu-id="4b997-143">`FeatureLength`lunghezza della matrice di funzionalità Integer prevista per il modello.</span><span class="sxs-lookup"><span data-stu-id="4b997-143">`FeatureLength` is the length of the integer feature array that the model is expecting.</span></span>

### <a name="model-the-data"></a><span data-ttu-id="4b997-144">Modellare i dati</span><span class="sxs-lookup"><span data-stu-id="4b997-144">Model the data</span></span>

<span data-ttu-id="4b997-145">Le revisioni del film sono testo in formato libero.</span><span class="sxs-lookup"><span data-stu-id="4b997-145">Movie reviews are free form text.</span></span> <span data-ttu-id="4b997-146">L'applicazione converte il testo nel formato di input previsto dal modello in diverse fasi discrete.</span><span class="sxs-lookup"><span data-stu-id="4b997-146">Your application converts the text into the input format expected by the model in a number of discrete stages.</span></span>

<span data-ttu-id="4b997-147">Il primo consiste nel suddividere il testo in parole separate e utilizzare il file di mapping specificato per eseguire il mapping di ogni parola a una codifica di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="4b997-147">The first is to split the text into separate words and use the provided mapping file to map each word onto an integer encoding.</span></span> <span data-ttu-id="4b997-148">Il risultato di questa trasformazione è una matrice integer a lunghezza variabile con una lunghezza corrispondente al numero di parole nella frase.</span><span class="sxs-lookup"><span data-stu-id="4b997-148">The result of this transformation is a variable length integer array with a length corresponding to the number of words in the sentence.</span></span>

|<span data-ttu-id="4b997-149">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4b997-149">Property</span></span>| <span data-ttu-id="4b997-150">Value</span><span class="sxs-lookup"><span data-stu-id="4b997-150">Value</span></span>|<span data-ttu-id="4b997-151">Type</span><span class="sxs-lookup"><span data-stu-id="4b997-151">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="4b997-152">ReviewText</span><span class="sxs-lookup"><span data-stu-id="4b997-152">ReviewText</span></span>|<span data-ttu-id="4b997-153">Questo film è molto valido</span><span class="sxs-lookup"><span data-stu-id="4b997-153">this film is really good</span></span>|<span data-ttu-id="4b997-154">string</span><span class="sxs-lookup"><span data-stu-id="4b997-154">string</span></span>|
|<span data-ttu-id="4b997-155">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="4b997-155">VariableLengthFeatures</span></span>|<span data-ttu-id="4b997-156">14, 22, 9, 66, 78,...</span><span class="sxs-lookup"><span data-stu-id="4b997-156">14,22,9,66,78,...</span></span> |<span data-ttu-id="4b997-157">int []</span><span class="sxs-lookup"><span data-stu-id="4b997-157">int[]</span></span>|

<span data-ttu-id="4b997-158">La matrice di funzionalità a lunghezza variabile viene quindi ridimensionata a una lunghezza fissa di 600.</span><span class="sxs-lookup"><span data-stu-id="4b997-158">The variable length feature array is then resized to a fixed length of 600.</span></span> <span data-ttu-id="4b997-159">Si tratta della lunghezza prevista dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="4b997-159">This is the length that the TensorFlow model expects.</span></span>

|<span data-ttu-id="4b997-160">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4b997-160">Property</span></span>| <span data-ttu-id="4b997-161">Value</span><span class="sxs-lookup"><span data-stu-id="4b997-161">Value</span></span>|<span data-ttu-id="4b997-162">Type</span><span class="sxs-lookup"><span data-stu-id="4b997-162">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="4b997-163">ReviewText</span><span class="sxs-lookup"><span data-stu-id="4b997-163">ReviewText</span></span>|<span data-ttu-id="4b997-164">Questo film è molto valido</span><span class="sxs-lookup"><span data-stu-id="4b997-164">this film is really good</span></span>|<span data-ttu-id="4b997-165">string</span><span class="sxs-lookup"><span data-stu-id="4b997-165">string</span></span>|
|<span data-ttu-id="4b997-166">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="4b997-166">VariableLengthFeatures</span></span>|<span data-ttu-id="4b997-167">14, 22, 9, 66, 78,...</span><span class="sxs-lookup"><span data-stu-id="4b997-167">14,22,9,66,78,...</span></span> |<span data-ttu-id="4b997-168">int []</span><span class="sxs-lookup"><span data-stu-id="4b997-168">int[]</span></span>|
|<span data-ttu-id="4b997-169">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="4b997-169">Features</span></span>|<span data-ttu-id="4b997-170">14, 22, 9, 66, 78,...</span><span class="sxs-lookup"><span data-stu-id="4b997-170">14,22,9,66,78,...</span></span> |<span data-ttu-id="4b997-171">int [600]</span><span class="sxs-lookup"><span data-stu-id="4b997-171">int[600]</span></span>|

1. <span data-ttu-id="4b997-172">Creare una classe per i dati di input, dopo `Main` il metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-172">Create a class for your input data, after the `Main` method:</span></span>

    [!code-csharp[MovieReviewClass](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MovieReviewClass "Declare movie review type")]

    <span data-ttu-id="4b997-173">La classe `string` di dati di `MovieReview`input,, dispone di per i`ReviewText`Commenti degli utenti ().</span><span class="sxs-lookup"><span data-stu-id="4b997-173">The input data class, `MovieReview`, has a `string` for user comments (`ReviewText`).</span></span>

1. <span data-ttu-id="4b997-174">Creare una classe per le funzionalità a lunghezza variabile, dopo `Main` il metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-174">Create a class for the variable length features, after the `Main` method:</span></span>

    [!code-csharp[VariableLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    <span data-ttu-id="4b997-175">La `VariableLengthFeatures` proprietà dispone di un attributo [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) per designarlo come vettore.</span><span class="sxs-lookup"><span data-stu-id="4b997-175">The `VariableLengthFeatures` property has a [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) attribute to designate it as a vector.</span></span>  <span data-ttu-id="4b997-176">Tutti gli elementi Vector devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="4b997-176">All of the vector elements must be the same type.</span></span> <span data-ttu-id="4b997-177">Nei set di dati con un numero elevato di colonne, il caricamento di più colonne come un singolo vettore riduce il numero di passaggi di dati quando si applicano le trasformazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="4b997-177">In data sets with a large number of columns, loading multiple columns as a single vector reduces the number of data passes when you apply data transformations.</span></span>

    <span data-ttu-id="4b997-178">Questa classe viene utilizzata nell' `ResizeFeatures` azione.</span><span class="sxs-lookup"><span data-stu-id="4b997-178">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="4b997-179">I nomi delle proprietà (in questo caso solo uno) vengono utilizzati per indicare quali colonne del DataView possono essere utilizzate come _input_ per l'azione di mapping personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4b997-179">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _input_ to the custom mapping action.</span></span>

1. <span data-ttu-id="4b997-180">Creare una classe per le funzionalità a lunghezza fissa, dopo `Main` il metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-180">Create a class for the fixed length features, after the `Main` method:</span></span>

    [!code-csharp[FixedLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#FixedLengthFeatures)]

    <span data-ttu-id="4b997-181">Questa classe viene utilizzata nell' `ResizeFeatures` azione.</span><span class="sxs-lookup"><span data-stu-id="4b997-181">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="4b997-182">I nomi delle proprietà (in questo caso solo uno) vengono utilizzati per indicare quali colonne del DataView possono essere utilizzate come _output_ dell'azione di mapping personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4b997-182">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _output_ of the custom mapping action.</span></span>

    <span data-ttu-id="4b997-183">Si noti che il nome della proprietà `Features` è determinato dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="4b997-183">Note that the name of the property `Features` is determined by the TensorFlow model.</span></span> <span data-ttu-id="4b997-184">Non è possibile modificare questo nome di proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b997-184">You cannot change this property name.</span></span>

1. <span data-ttu-id="4b997-185">Creare una classe per la stima dopo il `Main` metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-185">Create a class for the prediction after the `Main` method:</span></span>

    [!code-csharp[Prediction](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Prediction "Declare prediction class")]

    <span data-ttu-id="4b997-186">`MovieReviewSentimentPrediction` è la classe di stima usata dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="4b997-186">`MovieReviewSentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="4b997-187">`MovieReviewSentimentPrediction`dispone di una `float` singola matrice`Prediction`() e `VectorType` di un attributo.</span><span class="sxs-lookup"><span data-stu-id="4b997-187">`MovieReviewSentimentPrediction` has a single `float` array (`Prediction`) and a `VectorType` attribute.</span></span>
    
### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a><span data-ttu-id="4b997-188">Creare il MLContext, il dizionario di ricerca e l'azione per ridimensionare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="4b997-188">Create the MLContext, lookup dictionary, and action to resize features</span></span>

<span data-ttu-id="4b997-189">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET.</span><span class="sxs-lookup"><span data-stu-id="4b997-189">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="4b997-190">L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="4b997-190">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="4b997-191">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="4b997-191">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

1. <span data-ttu-id="4b997-192">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:</span><span class="sxs-lookup"><span data-stu-id="4b997-192">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

   [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateMLContext "Create the ML Context")]

1. <span data-ttu-id="4b997-193">Creare un dizionario per codificare le parole come numeri interi [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) usando il metodo per caricare i dati di mapping da un file, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4b997-193">Create a dictionary to encode words as integers by using the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method to load mapping data from a file, as seen in the following table:</span></span>

    |<span data-ttu-id="4b997-194">Word</span><span class="sxs-lookup"><span data-stu-id="4b997-194">Word</span></span>     |<span data-ttu-id="4b997-195">Indice</span><span class="sxs-lookup"><span data-stu-id="4b997-195">Index</span></span>    |
    |---------|---------|
    |<span data-ttu-id="4b997-196">bambini</span><span class="sxs-lookup"><span data-stu-id="4b997-196">kids</span></span>     |  <span data-ttu-id="4b997-197">362</span><span class="sxs-lookup"><span data-stu-id="4b997-197">362</span></span>    |
    |<span data-ttu-id="4b997-198">desidera</span><span class="sxs-lookup"><span data-stu-id="4b997-198">want</span></span>     |  <span data-ttu-id="4b997-199">181</span><span class="sxs-lookup"><span data-stu-id="4b997-199">181</span></span>    |
    |<span data-ttu-id="4b997-200">errato</span><span class="sxs-lookup"><span data-stu-id="4b997-200">wrong</span></span>    |  <span data-ttu-id="4b997-201">355</span><span class="sxs-lookup"><span data-stu-id="4b997-201">355</span></span>    |
    |<span data-ttu-id="4b997-202">effetti</span><span class="sxs-lookup"><span data-stu-id="4b997-202">effects</span></span>  |  <span data-ttu-id="4b997-203">302</span><span class="sxs-lookup"><span data-stu-id="4b997-203">302</span></span>    |
    |<span data-ttu-id="4b997-204">ci si sente</span><span class="sxs-lookup"><span data-stu-id="4b997-204">feeling</span></span>  |  <span data-ttu-id="4b997-205">547</span><span class="sxs-lookup"><span data-stu-id="4b997-205">547</span></span>    |

    <span data-ttu-id="4b997-206">Aggiungere il codice seguente per creare la mappa di ricerca:</span><span class="sxs-lookup"><span data-stu-id="4b997-206">Add the code below to create the lookup map:</span></span>

    [!code-csharp[CreateLookupMap](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateLookupMap)]

1. <span data-ttu-id="4b997-207">Aggiungere un `Action` oggetto per ridimensionare la matrice di tipo Integer a lunghezza variabile in una matrice di numeri interi di dimensioni fisse, con le righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b997-207">Add an `Action` to resize the variable length word integer array to an integer array of fixed size, with the next lines of code:</span></span>

   [!code-csharp[ResizeFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a><span data-ttu-id="4b997-208">Caricare il modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="4b997-208">Load the pre-trained TensorFlow model</span></span>

1. <span data-ttu-id="4b997-209">Aggiungere codice per caricare il modello di TensorFlow:</span><span class="sxs-lookup"><span data-stu-id="4b997-209">Add code to load the TensorFlow model:</span></span>

    [!code-csharp[LoadTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#LoadTensorFlowModel)]

    <span data-ttu-id="4b997-210">Una volta caricato il modello, è possibile estrarne lo schema di input e di output.</span><span class="sxs-lookup"><span data-stu-id="4b997-210">Once the model is loaded, you can extract its input and output schema.</span></span> <span data-ttu-id="4b997-211">Gli schemi vengono visualizzati solo per interesse e apprendimento.</span><span class="sxs-lookup"><span data-stu-id="4b997-211">The schemas are displayed for interest and learning only.</span></span> <span data-ttu-id="4b997-212">Questo codice non è necessario per il funzionamento dell'applicazione finale:</span><span class="sxs-lookup"><span data-stu-id="4b997-212">You do not need this code for the final application to function:</span></span>

    [!code-csharp[GetModelSchema](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#GetModelSchema)]

    <span data-ttu-id="4b997-213">Lo schema di input è la matrice a lunghezza fissa di parole con codifica Integer.</span><span class="sxs-lookup"><span data-stu-id="4b997-213">The input schema is the fixed-length array of integer encoded words.</span></span> <span data-ttu-id="4b997-214">Lo schema di output è una matrice di probabilità float che indica se il sentimento di una verifica è negativo o positivo.</span><span class="sxs-lookup"><span data-stu-id="4b997-214">The output schema is a float array of probabilities indicating whether a review's sentiment is negative, or positive .</span></span> <span data-ttu-id="4b997-215">Questi valori vengono sommati a 1, in quanto la probabilità di essere positivi è il complemento della probabilità che il sentimento sia negativo.</span><span class="sxs-lookup"><span data-stu-id="4b997-215">These values sum to 1, as the probability of being positive is the complement of the probability of the sentiment being negative.</span></span>

## <a name="create-the-mlnet-pipeline"></a><span data-ttu-id="4b997-216">Creare la pipeline ML.NET</span><span class="sxs-lookup"><span data-stu-id="4b997-216">Create the ML.NET pipeline</span></span>

1. <span data-ttu-id="4b997-217">Creare la pipeline e suddividere il testo di input in parole usando la trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) per suddividere il testo in parole come riga di codice successiva:</span><span class="sxs-lookup"><span data-stu-id="4b997-217">Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span></span>

   [!code-csharp[TokenizeIntoWords](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#TokenizeIntoWords)]

   <span data-ttu-id="4b997-218">La trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) usa gli spazi per analizzare la stringa di testo in parole.</span><span class="sxs-lookup"><span data-stu-id="4b997-218">The [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform uses spaces to parse the text/string into words.</span></span> <span data-ttu-id="4b997-219">Crea una nuova colonna e suddivide ogni stringa di input in un vettore di sottostringhe in base al separatore definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4b997-219">It creates a new column and splits each input string to a vector of substrings based on the user-defined separator.</span></span>

1. <span data-ttu-id="4b997-220">Eseguire il mapping delle parole sulla codifica Integer usando la tabella di ricerca dichiarata in precedenza:</span><span class="sxs-lookup"><span data-stu-id="4b997-220">Map the words onto their integer encoding using the lookup table that you declared above:</span></span>

    [!code-csharp[MapValue](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MapValue)]

1. <span data-ttu-id="4b997-221">Ridimensionare le codifiche Integer a lunghezza variabile a una lunghezza fissa richiesta dal modello:</span><span class="sxs-lookup"><span data-stu-id="4b997-221">Resize the variable length integer encodings to the fixed-length one required by the model:</span></span>

    [!code-csharp[CustomMapping](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CustomMapping)]

1. <span data-ttu-id="4b997-222">Classificare l'input con il modello TensorFlow caricato:</span><span class="sxs-lookup"><span data-stu-id="4b997-222">Classify the input with the loaded TensorFlow model:</span></span>

    [!code-csharp[ScoreTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="4b997-223">Viene chiamato `Prediction/Softmax`l'output del modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="4b997-223">The TensorFlow model output is called `Prediction/Softmax`.</span></span> <span data-ttu-id="4b997-224">Si noti che il `Prediction/Softmax` nome è determinato dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="4b997-224">Note that the name `Prediction/Softmax` is determined by the TensorFlow model.</span></span> <span data-ttu-id="4b997-225">Non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="4b997-225">You cannot change this name.</span></span>

1. <span data-ttu-id="4b997-226">Crea una nuova colonna per la stima di output:</span><span class="sxs-lookup"><span data-stu-id="4b997-226">Create a new column for the output prediction:</span></span>

    [!code-csharp[SnippetCopyColumns](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCopyColumns)]

    <span data-ttu-id="4b997-227">È necessario copiare la `Prediction/Softmax` colonna in un oggetto con un nome che può essere usato come proprietà in una C# classe: `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="4b997-227">You need to copy the `Prediction/Softmax` column into one with a name that can be used as a property in a C# class: `Prediction`.</span></span> <span data-ttu-id="4b997-228">Il `/` carattere non è consentito in un C# nome di proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b997-228">The `/` character is not allowed in a C# property name.</span></span>

## <a name="create-the-mlnet-model-from-the-pipeline"></a><span data-ttu-id="4b997-229">Creare il modello ML.NET dalla pipeline</span><span class="sxs-lookup"><span data-stu-id="4b997-229">Create the ML.NET model from the pipeline</span></span>

1. <span data-ttu-id="4b997-230">Aggiungere il codice per creare il modello dalla pipeline:</span><span class="sxs-lookup"><span data-stu-id="4b997-230">Add the code to create the model from the pipeline:</span></span>

    [!code-csharp[SnippetCreateModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCreateModel)]  

    <span data-ttu-id="4b997-231">Un modello ml.NET viene creato dalla catena di estimatori nella pipeline chiamando il `Fit` metodo.</span><span class="sxs-lookup"><span data-stu-id="4b997-231">An ML.NET model is created from the chain of estimators in the pipeline by calling the `Fit` method.</span></span> <span data-ttu-id="4b997-232">In questo caso, i dati non vengono adattati per la creazione del modello, perché è già stato eseguito il training del modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="4b997-232">In this case, we are not fitting any data to create the model, as the TensorFlow model has already been previously trained.</span></span> <span data-ttu-id="4b997-233">Viene fornito un oggetto visualizzazione dati vuoto per soddisfare i requisiti del `Fit` metodo.</span><span class="sxs-lookup"><span data-stu-id="4b997-233">We supply an empty data view object to satisfy the requirements of the `Fit` method.</span></span>

## <a name="use-the-model-to-make-a-prediction"></a><span data-ttu-id="4b997-234">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="4b997-234">Use the model to make a prediction</span></span>

1. <span data-ttu-id="4b997-235">Aggiungere il `PredictSentiment` metodo sotto il `Main` metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-235">Add the `PredictSentiment` method below the `Main` method:</span></span>

    ```csharp
        public static void PredictSentiment(MLContext mlContext, ITransformer model)
        {

        }
    ```

1. <span data-ttu-id="4b997-236">Aggiungere il codice seguente per creare `PredictionEngine` come prima riga `PredictSentiment()` nel metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-236">Add the following code to create the `PredictionEngine` as the first line in the `PredictSentiment()` method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreatePredictionEngine)]

    <span data-ttu-id="4b997-237">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="4b997-237">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to make a prediction on a single instance of data.</span></span>

1. <span data-ttu-id="4b997-238">Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict()` creando un'istanza di `MovieReview`:</span><span class="sxs-lookup"><span data-stu-id="4b997-238">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `MovieReview`:</span></span>

    [!code-csharp[CreateTestData](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateTestData)]

1. <span data-ttu-id="4b997-239">Passare i dati del commento di test `Prediction Engine` a aggiungendo le righe di codice seguenti `PredictSentiment()` nel metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-239">Pass the test comment data to the `Prediction Engine` by adding the next lines of code in the `PredictSentiment()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Predict)]

1. <span data-ttu-id="4b997-240">La funzione [Predict ()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola riga di dati:</span><span class="sxs-lookup"><span data-stu-id="4b997-240">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

    |<span data-ttu-id="4b997-241">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4b997-241">Property</span></span>| <span data-ttu-id="4b997-242">Value</span><span class="sxs-lookup"><span data-stu-id="4b997-242">Value</span></span>|<span data-ttu-id="4b997-243">Type</span><span class="sxs-lookup"><span data-stu-id="4b997-243">Type</span></span>|
    |-------------|-----------------------|------|
    |<span data-ttu-id="4b997-244">Previsione</span><span class="sxs-lookup"><span data-stu-id="4b997-244">Prediction</span></span>|<span data-ttu-id="4b997-245">[0,5459937, 0,454006255]</span><span class="sxs-lookup"><span data-stu-id="4b997-245">[0.5459937, 0.454006255]</span></span>|<span data-ttu-id="4b997-246">float []</span><span class="sxs-lookup"><span data-stu-id="4b997-246">float[]</span></span>|

1. <span data-ttu-id="4b997-247">Visualizzare la stima del sentimento usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4b997-247">Display sentiment prediction using the following code:</span></span>

    [!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DisplayPredictions)]

1. <span data-ttu-id="4b997-248">Aggiungere una chiamata a `PredictSentiment` alla fine `Main` del metodo:</span><span class="sxs-lookup"><span data-stu-id="4b997-248">Add a call to `PredictSentiment` at the end of the `Main` method:</span></span>

    [!code-csharp[CallPredictSentiment](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CallPredictSentiment)]

## <a name="results"></a><span data-ttu-id="4b997-249">Risultati</span><span class="sxs-lookup"><span data-stu-id="4b997-249">Results</span></span>

<span data-ttu-id="4b997-250">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b997-250">Build and run your application.</span></span>

<span data-ttu-id="4b997-251">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4b997-251">Your results should be similar to the following.</span></span> <span data-ttu-id="4b997-252">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="4b997-252">During processing, messages are displayed.</span></span> <span data-ttu-id="4b997-253">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="4b997-253">You may see warnings, or processing messages.</span></span> <span data-ttu-id="4b997-254">Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="4b997-254">These messages have been removed from the following results for clarity.</span></span>

```console
   Number of classes: 2
   Is sentiment/review positive ? Yes
```

<span data-ttu-id="4b997-255">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="4b997-255">Congratulations!</span></span> <span data-ttu-id="4b997-256">A questo punto, è stato creato un modello di apprendimento automatico per la classificazione e la stima del sentimento dei messaggi riutilizzando un modello con training `TensorFlow` preliminare in ml.NET.</span><span class="sxs-lookup"><span data-stu-id="4b997-256">You've now successfully built a machine learning model for classifying and predicting messages sentiment by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="4b997-257">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="4b997-257">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

<span data-ttu-id="4b997-258">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="4b997-258">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4b997-259">Caricare un modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="4b997-259">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="4b997-260">Trasforma il testo del commento del sito Web in funzionalità appropriate per il modello</span><span class="sxs-lookup"><span data-stu-id="4b997-260">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="4b997-261">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="4b997-261">Use the model to make a prediction</span></span>
