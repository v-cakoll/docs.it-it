---
title: 'Esercitazione: analizzare i sentimenti di revisione usando un modello TensorFlow'
description: Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare i sentimenti nei commenti dei siti Web. Il classificatore dei sentimenti binari è un'applicazione console C# sviluppata con Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9a2e7f72d59e31cfd7db5b89bfad55bccb063cea
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281407"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a><span data-ttu-id="d2629-104">Esercitazione: analizzare i sentimenti delle revisioni dei film usando un modello TensorFlow con training preliminare in ML.NET</span><span class="sxs-lookup"><span data-stu-id="d2629-104">Tutorial: Analyze sentiment of movie reviews using a pre-trained TensorFlow model in ML.NET</span></span>

<span data-ttu-id="d2629-105">Questa esercitazione illustra come usare un modello TensorFlow con training preliminare per classificare i sentimenti nei commenti dei siti Web.</span><span class="sxs-lookup"><span data-stu-id="d2629-105">This tutorial shows you how to use a pre-trained TensorFlow model to classify sentiment in website comments.</span></span> <span data-ttu-id="d2629-106">Il classificatore dei sentimenti binari è un'applicazione console C# sviluppata con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2629-106">The binary sentiment classifier is a C# console application developed using Visual Studio.</span></span>

<span data-ttu-id="d2629-107">Il modello TensorFlow usato in questa esercitazione è stato sottoposto a training con le revisioni dei film del database IMDB.</span><span class="sxs-lookup"><span data-stu-id="d2629-107">The TensorFlow model used in this tutorial was trained using movie reviews from the IMDB database.</span></span> <span data-ttu-id="d2629-108">Al termine dello sviluppo dell'applicazione, sarà possibile fornire il testo della revisione del film e l'applicazione indica se la revisione ha un sentimento positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="d2629-108">Once you have finished developing the application, you will be able to supply movie review text and the application will tell you whether the review has positive or negative sentiment.</span></span>

<span data-ttu-id="d2629-109">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="d2629-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="d2629-110">Caricare un modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="d2629-110">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="d2629-111">Trasforma il testo del commento del sito Web in funzionalità appropriate per il modello</span><span class="sxs-lookup"><span data-stu-id="d2629-111">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="d2629-112">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="d2629-112">Use the model to make a prediction</span></span>

<span data-ttu-id="d2629-113">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="d2629-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d2629-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d2629-114">Prerequisites</span></span>

* <span data-ttu-id="d2629-115">[Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="d2629-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="setup"></a><span data-ttu-id="d2629-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="d2629-116">Setup</span></span>

### <a name="create-the-application"></a><span data-ttu-id="d2629-117">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="d2629-117">Create the application</span></span>

1. <span data-ttu-id="d2629-118">Creare un' **applicazione console .NET Core** denominata "TextClassificationTF".</span><span class="sxs-lookup"><span data-stu-id="d2629-118">Create a **.NET Core Console Application** called "TextClassificationTF".</span></span>

2. <span data-ttu-id="d2629-119">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="d2629-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="d2629-120">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="d2629-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="d2629-121">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="d2629-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d2629-122">Scegliere "nuget.org" come origine del pacchetto, quindi selezionare la scheda **Sfoglia** . cercare **Microsoft.ml**, selezionare il pacchetto desiderato e quindi fare clic sul pulsante **Installa** .</span><span class="sxs-lookup"><span data-stu-id="d2629-122">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="d2629-123">Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto.</span><span class="sxs-lookup"><span data-stu-id="d2629-123">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="d2629-124">Ripetere questi passaggi per **Microsoft. ml. TensorFlow**, **Microsoft. ml. SampleUtils** e **SciSharp. TensorFlow. Redist**.</span><span class="sxs-lookup"><span data-stu-id="d2629-124">Repeat these steps for **Microsoft.ML.TensorFlow**, **Microsoft.ML.SampleUtils** and **SciSharp.TensorFlow.Redist**.</span></span>

### <a name="add-the-tensorflow-model-to-the-project"></a><span data-ttu-id="d2629-125">Aggiungere il modello TensorFlow al progetto</span><span class="sxs-lookup"><span data-stu-id="d2629-125">Add the TensorFlow model to the project</span></span>

> [!NOTE]
> <span data-ttu-id="d2629-126">Il modello per questa esercitazione è del repository GitHub [DotNet/machinelearning-TESTDATA](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) .</span><span class="sxs-lookup"><span data-stu-id="d2629-126">The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span></span> <span data-ttu-id="d2629-127">Il modello è in formato TensorFlow SavedModel.</span><span class="sxs-lookup"><span data-stu-id="d2629-127">The model is in TensorFlow SavedModel format.</span></span>

1. <span data-ttu-id="d2629-128">Scaricare il [file zip di sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true)e decomprimere.</span><span class="sxs-lookup"><span data-stu-id="d2629-128">Download the [sentiment_model zip file](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true), and unzip.</span></span>

    <span data-ttu-id="d2629-129">Il file zip contiene:</span><span class="sxs-lookup"><span data-stu-id="d2629-129">The zip file contains:</span></span>

    * <span data-ttu-id="d2629-130">`saved_model.pb`: modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="d2629-130">`saved_model.pb`: the TensorFlow model itself.</span></span> <span data-ttu-id="d2629-131">Il modello accetta una matrice di valori interi di lunghezza fissa (dimensione 600) che rappresenta il testo in una stringa di revisione di IMDB e restituisce due probabilità che sommano a 1: la probabilità che la revisione di input abbia un sentimento positivo e la probabilità che la revisione dell'input abbia un sentimento negativo.</span><span class="sxs-lookup"><span data-stu-id="d2629-131">The model takes a fixed length (size 600) integer array of features representing the text in an IMDB review string, and outputs two probabilities which sum to 1: the probability that the input review has positive sentiment, and the probability that the input review has negative sentiment.</span></span>
    * <span data-ttu-id="d2629-132">`imdb_word_index.csv`: un mapping da singole parole a un valore integer.</span><span class="sxs-lookup"><span data-stu-id="d2629-132">`imdb_word_index.csv`: a mapping from individual words to an integer value.</span></span> <span data-ttu-id="d2629-133">Il mapping viene utilizzato per generare le funzionalità di input per il modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="d2629-133">The mapping is used to generate the input features for the TensorFlow model.</span></span>

2. <span data-ttu-id="d2629-134">Copiare il contenuto della directory più interna `sentiment_model` nella directory del progetto *TextClassificationTF* `sentiment_model` .</span><span class="sxs-lookup"><span data-stu-id="d2629-134">Copy the contents of the innermost `sentiment_model` directory into your *TextClassificationTF* project `sentiment_model` directory.</span></span> <span data-ttu-id="d2629-135">Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="d2629-135">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![contenuto della directory sentiment_model](./media/text-classification-tf/sentiment-model-files.png)

3. <span data-ttu-id="d2629-137">In Esplora soluzioni fare clic con il pulsante destro del mouse su ogni file nella `sentiment_model` Directory e nella sottodirectory e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d2629-137">In Solution Explorer, right-click each of the files in the `sentiment_model` directory and subdirectory and select **Properties**.</span></span> <span data-ttu-id="d2629-138">In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="d2629-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="add-using-statements-and-global-variables"></a><span data-ttu-id="d2629-139">Aggiungere istruzioni using e variabili globali</span><span class="sxs-lookup"><span data-stu-id="d2629-139">Add using statements and global variables</span></span>

1. <span data-ttu-id="d2629-140">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: </span><span class="sxs-lookup"><span data-stu-id="d2629-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

   [!code-csharp[AddUsings](./snippets/text-classification-tf/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="d2629-141">Creare due variabili globali al di sopra del `Main` metodo per conservare il percorso del file del modello salvato e la lunghezza del vettore di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d2629-141">Create two global variables right above the `Main` method to hold the saved model file path, and the feature vector length.</span></span>

   [!code-csharp[DeclareGlobalVariables](./snippets/text-classification-tf/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * <span data-ttu-id="d2629-142">`_modelPath`è il percorso del file del modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="d2629-142">`_modelPath` is the file path of the trained model.</span></span>
    * <span data-ttu-id="d2629-143">`FeatureLength`lunghezza della matrice di funzionalità Integer prevista per il modello.</span><span class="sxs-lookup"><span data-stu-id="d2629-143">`FeatureLength` is the length of the integer feature array that the model is expecting.</span></span>

### <a name="model-the-data"></a><span data-ttu-id="d2629-144">Modellare i dati</span><span class="sxs-lookup"><span data-stu-id="d2629-144">Model the data</span></span>

<span data-ttu-id="d2629-145">Le revisioni del film sono testo in formato libero.</span><span class="sxs-lookup"><span data-stu-id="d2629-145">Movie reviews are free form text.</span></span> <span data-ttu-id="d2629-146">L'applicazione converte il testo nel formato di input previsto dal modello in diverse fasi discrete.</span><span class="sxs-lookup"><span data-stu-id="d2629-146">Your application converts the text into the input format expected by the model in a number of discrete stages.</span></span>

<span data-ttu-id="d2629-147">Il primo consiste nel suddividere il testo in parole separate e utilizzare il file di mapping specificato per eseguire il mapping di ogni parola a una codifica di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="d2629-147">The first is to split the text into separate words and use the provided mapping file to map each word onto an integer encoding.</span></span> <span data-ttu-id="d2629-148">Il risultato di questa trasformazione è una matrice integer a lunghezza variabile con una lunghezza corrispondente al numero di parole nella frase.</span><span class="sxs-lookup"><span data-stu-id="d2629-148">The result of this transformation is a variable length integer array with a length corresponding to the number of words in the sentence.</span></span>

|<span data-ttu-id="d2629-149">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d2629-149">Property</span></span>| <span data-ttu-id="d2629-150">valore</span><span class="sxs-lookup"><span data-stu-id="d2629-150">Value</span></span>|<span data-ttu-id="d2629-151">Type</span><span class="sxs-lookup"><span data-stu-id="d2629-151">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="d2629-152">ReviewText</span><span class="sxs-lookup"><span data-stu-id="d2629-152">ReviewText</span></span>|<span data-ttu-id="d2629-153">Questo film è molto valido</span><span class="sxs-lookup"><span data-stu-id="d2629-153">this film is really good</span></span>|<span data-ttu-id="d2629-154">string</span><span class="sxs-lookup"><span data-stu-id="d2629-154">string</span></span>|
|<span data-ttu-id="d2629-155">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="d2629-155">VariableLengthFeatures</span></span>|<span data-ttu-id="d2629-156">14, 22, 9, 66, 78,...</span><span class="sxs-lookup"><span data-stu-id="d2629-156">14,22,9,66,78,...</span></span> |<span data-ttu-id="d2629-157">int []</span><span class="sxs-lookup"><span data-stu-id="d2629-157">int[]</span></span>|

<span data-ttu-id="d2629-158">La matrice di funzionalità a lunghezza variabile viene quindi ridimensionata a una lunghezza fissa di 600.</span><span class="sxs-lookup"><span data-stu-id="d2629-158">The variable length feature array is then resized to a fixed length of 600.</span></span> <span data-ttu-id="d2629-159">Si tratta della lunghezza prevista dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="d2629-159">This is the length that the TensorFlow model expects.</span></span>

|<span data-ttu-id="d2629-160">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d2629-160">Property</span></span>| <span data-ttu-id="d2629-161">valore</span><span class="sxs-lookup"><span data-stu-id="d2629-161">Value</span></span>|<span data-ttu-id="d2629-162">Type</span><span class="sxs-lookup"><span data-stu-id="d2629-162">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="d2629-163">ReviewText</span><span class="sxs-lookup"><span data-stu-id="d2629-163">ReviewText</span></span>|<span data-ttu-id="d2629-164">Questo film è molto valido</span><span class="sxs-lookup"><span data-stu-id="d2629-164">this film is really good</span></span>|<span data-ttu-id="d2629-165">string</span><span class="sxs-lookup"><span data-stu-id="d2629-165">string</span></span>|
|<span data-ttu-id="d2629-166">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="d2629-166">VariableLengthFeatures</span></span>|<span data-ttu-id="d2629-167">14, 22, 9, 66, 78,...</span><span class="sxs-lookup"><span data-stu-id="d2629-167">14,22,9,66,78,...</span></span> |<span data-ttu-id="d2629-168">int []</span><span class="sxs-lookup"><span data-stu-id="d2629-168">int[]</span></span>|
|<span data-ttu-id="d2629-169">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="d2629-169">Features</span></span>|<span data-ttu-id="d2629-170">14, 22, 9, 66, 78,...</span><span class="sxs-lookup"><span data-stu-id="d2629-170">14,22,9,66,78,...</span></span> |<span data-ttu-id="d2629-171">int [600]</span><span class="sxs-lookup"><span data-stu-id="d2629-171">int[600]</span></span>|

1. <span data-ttu-id="d2629-172">Creare una classe per i dati di input, dopo il `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-172">Create a class for your input data, after the `Main` method:</span></span>

    [!code-csharp[MovieReviewClass](./snippets/text-classification-tf/csharp/Program.cs#MovieReviewClass "Declare movie review type")]

    <span data-ttu-id="d2629-173">La classe di dati di input, `MovieReview` , dispone di `string` per i commenti degli utenti ( `ReviewText` ).</span><span class="sxs-lookup"><span data-stu-id="d2629-173">The input data class, `MovieReview`, has a `string` for user comments (`ReviewText`).</span></span>

1. <span data-ttu-id="d2629-174">Creare una classe per le funzionalità a lunghezza variabile, dopo il `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-174">Create a class for the variable length features, after the `Main` method:</span></span>

    [!code-csharp[VariableLengthFeatures](./snippets/text-classification-tf/csharp/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    <span data-ttu-id="d2629-175">La `VariableLengthFeatures` proprietà dispone di un attributo [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) per designarlo come vettore.</span><span class="sxs-lookup"><span data-stu-id="d2629-175">The `VariableLengthFeatures` property has a [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) attribute to designate it as a vector.</span></span>  <span data-ttu-id="d2629-176">Tutti gli elementi Vector devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="d2629-176">All of the vector elements must be the same type.</span></span> <span data-ttu-id="d2629-177">Nei set di dati con un numero elevato di colonne, il caricamento di più colonne come un singolo vettore riduce il numero di passaggi di dati quando si applicano le trasformazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="d2629-177">In data sets with a large number of columns, loading multiple columns as a single vector reduces the number of data passes when you apply data transformations.</span></span>

    <span data-ttu-id="d2629-178">Questa classe viene utilizzata nell' `ResizeFeatures` azione.</span><span class="sxs-lookup"><span data-stu-id="d2629-178">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="d2629-179">I nomi delle proprietà (in questo caso solo uno) vengono utilizzati per indicare quali colonne del DataView possono essere utilizzate come _input_ per l'azione di mapping personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d2629-179">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _input_ to the custom mapping action.</span></span>

1. <span data-ttu-id="d2629-180">Creare una classe per le funzionalità a lunghezza fissa, dopo il `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-180">Create a class for the fixed length features, after the `Main` method:</span></span>

    [!code-csharp[FixedLengthFeatures](./snippets/text-classification-tf/csharp/Program.cs#FixedLengthFeatures)]

    <span data-ttu-id="d2629-181">Questa classe viene utilizzata nell' `ResizeFeatures` azione.</span><span class="sxs-lookup"><span data-stu-id="d2629-181">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="d2629-182">I nomi delle proprietà (in questo caso solo uno) vengono utilizzati per indicare quali colonne del DataView possono essere utilizzate come _output_ dell'azione di mapping personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d2629-182">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _output_ of the custom mapping action.</span></span>

    <span data-ttu-id="d2629-183">Si noti che il nome della proprietà `Features` è determinato dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="d2629-183">Note that the name of the property `Features` is determined by the TensorFlow model.</span></span> <span data-ttu-id="d2629-184">Non è possibile modificare questo nome di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d2629-184">You cannot change this property name.</span></span>

1. <span data-ttu-id="d2629-185">Creare una classe per la stima dopo il `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-185">Create a class for the prediction after the `Main` method:</span></span>

    [!code-csharp[Prediction](./snippets/text-classification-tf/csharp/Program.cs#Prediction "Declare prediction class")]

    <span data-ttu-id="d2629-186">`MovieReviewSentimentPrediction` è la classe di stima usata dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="d2629-186">`MovieReviewSentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="d2629-187">`MovieReviewSentimentPrediction`dispone di una singola `float` matrice ( `Prediction` ) e di un `VectorType` attributo.</span><span class="sxs-lookup"><span data-stu-id="d2629-187">`MovieReviewSentimentPrediction` has a single `float` array (`Prediction`) and a `VectorType` attribute.</span></span>

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a><span data-ttu-id="d2629-188">Creare il MLContext, il dizionario di ricerca e l'azione per ridimensionare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="d2629-188">Create the MLContext, lookup dictionary, and action to resize features</span></span>

<span data-ttu-id="d2629-189">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d2629-189">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="d2629-190">L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="d2629-190">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="d2629-191">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d2629-191">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

1. <span data-ttu-id="d2629-192">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:</span><span class="sxs-lookup"><span data-stu-id="d2629-192">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

   [!code-csharp[CreateMLContext](./snippets/text-classification-tf/csharp/Program.cs#CreateMLContext "Create the ML Context")]

1. <span data-ttu-id="d2629-193">Creare un dizionario per codificare le parole come numeri interi usando il [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) metodo per caricare i dati di mapping da un file, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="d2629-193">Create a dictionary to encode words as integers by using the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method to load mapping data from a file, as seen in the following table:</span></span>

    |<span data-ttu-id="d2629-194">Parola</span><span class="sxs-lookup"><span data-stu-id="d2629-194">Word</span></span>     |<span data-ttu-id="d2629-195">Indice</span><span class="sxs-lookup"><span data-stu-id="d2629-195">Index</span></span>    |
    |---------|---------|
    |<span data-ttu-id="d2629-196">bambini</span><span class="sxs-lookup"><span data-stu-id="d2629-196">kids</span></span>     |  <span data-ttu-id="d2629-197">362</span><span class="sxs-lookup"><span data-stu-id="d2629-197">362</span></span>    |
    |<span data-ttu-id="d2629-198">want</span><span class="sxs-lookup"><span data-stu-id="d2629-198">want</span></span>     |  <span data-ttu-id="d2629-199">181</span><span class="sxs-lookup"><span data-stu-id="d2629-199">181</span></span>    |
    |<span data-ttu-id="d2629-200">errato</span><span class="sxs-lookup"><span data-stu-id="d2629-200">wrong</span></span>    |  <span data-ttu-id="d2629-201">355</span><span class="sxs-lookup"><span data-stu-id="d2629-201">355</span></span>    |
    |<span data-ttu-id="d2629-202">effects</span><span class="sxs-lookup"><span data-stu-id="d2629-202">effects</span></span>  |  <span data-ttu-id="d2629-203">302</span><span class="sxs-lookup"><span data-stu-id="d2629-203">302</span></span>    |
    |<span data-ttu-id="d2629-204">ci si sente</span><span class="sxs-lookup"><span data-stu-id="d2629-204">feeling</span></span>  |  <span data-ttu-id="d2629-205">547</span><span class="sxs-lookup"><span data-stu-id="d2629-205">547</span></span>    |

    <span data-ttu-id="d2629-206">Aggiungere il codice seguente per creare la mappa di ricerca:</span><span class="sxs-lookup"><span data-stu-id="d2629-206">Add the code below to create the lookup map:</span></span>

    [!code-csharp[CreateLookupMap](./snippets/text-classification-tf/csharp/Program.cs#CreateLookupMap)]

1. <span data-ttu-id="d2629-207">Aggiungere un oggetto `Action` per ridimensionare la matrice di tipo Integer a lunghezza variabile in una matrice di numeri interi di dimensioni fisse, con le righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2629-207">Add an `Action` to resize the variable length word integer array to an integer array of fixed size, with the next lines of code:</span></span>

   [!code-csharp[ResizeFeatures](./snippets/text-classification-tf/csharp/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a><span data-ttu-id="d2629-208">Caricare il modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="d2629-208">Load the pre-trained TensorFlow model</span></span>

1. <span data-ttu-id="d2629-209">Aggiungere codice per caricare il modello di TensorFlow:</span><span class="sxs-lookup"><span data-stu-id="d2629-209">Add code to load the TensorFlow model:</span></span>

    [!code-csharp[LoadTensorFlowModel](./snippets/text-classification-tf/csharp/Program.cs#LoadTensorFlowModel)]

    <span data-ttu-id="d2629-210">Una volta caricato il modello, è possibile estrarne lo schema di input e di output.</span><span class="sxs-lookup"><span data-stu-id="d2629-210">Once the model is loaded, you can extract its input and output schema.</span></span> <span data-ttu-id="d2629-211">Gli schemi vengono visualizzati solo per interesse e apprendimento.</span><span class="sxs-lookup"><span data-stu-id="d2629-211">The schemas are displayed for interest and learning only.</span></span> <span data-ttu-id="d2629-212">Questo codice non è necessario per il funzionamento dell'applicazione finale:</span><span class="sxs-lookup"><span data-stu-id="d2629-212">You do not need this code for the final application to function:</span></span>

    [!code-csharp[GetModelSchema](./snippets/text-classification-tf/csharp/Program.cs#GetModelSchema)]

    <span data-ttu-id="d2629-213">Lo schema di input è la matrice a lunghezza fissa di parole con codifica Integer.</span><span class="sxs-lookup"><span data-stu-id="d2629-213">The input schema is the fixed-length array of integer encoded words.</span></span> <span data-ttu-id="d2629-214">Lo schema di output è una matrice di probabilità float che indica se il sentimento di una verifica è negativo o positivo.</span><span class="sxs-lookup"><span data-stu-id="d2629-214">The output schema is a float array of probabilities indicating whether a review's sentiment is negative, or positive .</span></span> <span data-ttu-id="d2629-215">Questi valori vengono sommati a 1, in quanto la probabilità di essere positivi è il complemento della probabilità che il sentimento sia negativo.</span><span class="sxs-lookup"><span data-stu-id="d2629-215">These values sum to 1, as the probability of being positive is the complement of the probability of the sentiment being negative.</span></span>

## <a name="create-the-mlnet-pipeline"></a><span data-ttu-id="d2629-216">Creare la pipeline ML.NET</span><span class="sxs-lookup"><span data-stu-id="d2629-216">Create the ML.NET pipeline</span></span>

1. <span data-ttu-id="d2629-217">Creare la pipeline e suddividere il testo di input in parole usando la trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) per suddividere il testo in parole come riga di codice successiva:</span><span class="sxs-lookup"><span data-stu-id="d2629-217">Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span></span>

   [!code-csharp[TokenizeIntoWords](./snippets/text-classification-tf/csharp/Program.cs#TokenizeIntoWords)]

   <span data-ttu-id="d2629-218">La trasformazione [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) usa gli spazi per analizzare la stringa di testo in parole.</span><span class="sxs-lookup"><span data-stu-id="d2629-218">The [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform uses spaces to parse the text/string into words.</span></span> <span data-ttu-id="d2629-219">Crea una nuova colonna e suddivide ogni stringa di input in un vettore di sottostringhe in base al separatore definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d2629-219">It creates a new column and splits each input string to a vector of substrings based on the user-defined separator.</span></span>

1. <span data-ttu-id="d2629-220">Eseguire il mapping delle parole sulla codifica Integer usando la tabella di ricerca dichiarata in precedenza:</span><span class="sxs-lookup"><span data-stu-id="d2629-220">Map the words onto their integer encoding using the lookup table that you declared above:</span></span>

    [!code-csharp[MapValue](./snippets/text-classification-tf/csharp/Program.cs#MapValue)]

1. <span data-ttu-id="d2629-221">Ridimensionare le codifiche Integer a lunghezza variabile a una lunghezza fissa richiesta dal modello:</span><span class="sxs-lookup"><span data-stu-id="d2629-221">Resize the variable length integer encodings to the fixed-length one required by the model:</span></span>

    [!code-csharp[CustomMapping](./snippets/text-classification-tf/csharp/Program.cs#CustomMapping)]

1. <span data-ttu-id="d2629-222">Classificare l'input con il modello TensorFlow caricato:</span><span class="sxs-lookup"><span data-stu-id="d2629-222">Classify the input with the loaded TensorFlow model:</span></span>

    [!code-csharp[ScoreTensorFlowModel](./snippets/text-classification-tf/csharp/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="d2629-223">Viene chiamato l'output del modello TensorFlow `Prediction/Softmax` .</span><span class="sxs-lookup"><span data-stu-id="d2629-223">The TensorFlow model output is called `Prediction/Softmax`.</span></span> <span data-ttu-id="d2629-224">Si noti che il nome `Prediction/Softmax` è determinato dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="d2629-224">Note that the name `Prediction/Softmax` is determined by the TensorFlow model.</span></span> <span data-ttu-id="d2629-225">Non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="d2629-225">You cannot change this name.</span></span>

1. <span data-ttu-id="d2629-226">Crea una nuova colonna per la stima di output:</span><span class="sxs-lookup"><span data-stu-id="d2629-226">Create a new column for the output prediction:</span></span>

    [!code-csharp[SnippetCopyColumns](./snippets/text-classification-tf/csharp/Program.cs#SnippetCopyColumns)]

    <span data-ttu-id="d2629-227">È necessario copiare la `Prediction/Softmax` colonna in un oggetto con un nome che può essere usato come proprietà in una classe C#: `Prediction` .</span><span class="sxs-lookup"><span data-stu-id="d2629-227">You need to copy the `Prediction/Softmax` column into one with a name that can be used as a property in a C# class: `Prediction`.</span></span> <span data-ttu-id="d2629-228">Il `/` carattere non è consentito in un nome di proprietà C#.</span><span class="sxs-lookup"><span data-stu-id="d2629-228">The `/` character is not allowed in a C# property name.</span></span>

## <a name="create-the-mlnet-model-from-the-pipeline"></a><span data-ttu-id="d2629-229">Creare il modello ML.NET dalla pipeline</span><span class="sxs-lookup"><span data-stu-id="d2629-229">Create the ML.NET model from the pipeline</span></span>

1. <span data-ttu-id="d2629-230">Aggiungere il codice per creare il modello dalla pipeline:</span><span class="sxs-lookup"><span data-stu-id="d2629-230">Add the code to create the model from the pipeline:</span></span>

    [!code-csharp[SnippetCreateModel](./snippets/text-classification-tf/csharp/Program.cs#SnippetCreateModel)]

    <span data-ttu-id="d2629-231">Un modello ML.NET viene creato dalla catena di estimatori nella pipeline chiamando il `Fit` metodo.</span><span class="sxs-lookup"><span data-stu-id="d2629-231">An ML.NET model is created from the chain of estimators in the pipeline by calling the `Fit` method.</span></span> <span data-ttu-id="d2629-232">In questo caso, i dati non vengono adattati per la creazione del modello, perché è già stato eseguito il training del modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="d2629-232">In this case, we are not fitting any data to create the model, as the TensorFlow model has already been previously trained.</span></span> <span data-ttu-id="d2629-233">Viene fornito un oggetto visualizzazione dati vuoto per soddisfare i requisiti del `Fit` metodo.</span><span class="sxs-lookup"><span data-stu-id="d2629-233">We supply an empty data view object to satisfy the requirements of the `Fit` method.</span></span>

## <a name="use-the-model-to-make-a-prediction"></a><span data-ttu-id="d2629-234">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="d2629-234">Use the model to make a prediction</span></span>

1. <span data-ttu-id="d2629-235">Aggiungere il `PredictSentiment` Metodo sotto il `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-235">Add the `PredictSentiment` method below the `Main` method:</span></span>

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="d2629-236">Aggiungere il codice seguente per creare `PredictionEngine` come prima riga nel `PredictSentiment()` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-236">Add the following code to create the `PredictionEngine` as the first line in the `PredictSentiment()` method:</span></span>

    [!code-csharp[CreatePredictionEngine](./snippets/text-classification-tf/csharp/Program.cs#CreatePredictionEngine)]

    <span data-ttu-id="d2629-237">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="d2629-237">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="d2629-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="d2629-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="d2629-239">È accettabile usare in ambienti a thread singolo o prototipi.</span><span class="sxs-lookup"><span data-stu-id="d2629-239">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="d2629-240">Per migliorare le prestazioni e thread safety negli ambienti di produzione, utilizzare il `PredictionEnginePool` servizio, che consente di creare un oggetto [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da utilizzare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d2629-240">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="d2629-241">Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="d2629-241">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2629-242">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="d2629-242">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="d2629-243">Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict()` creando un'istanza di `MovieReview`:</span><span class="sxs-lookup"><span data-stu-id="d2629-243">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `MovieReview`:</span></span>

    [!code-csharp[CreateTestData](./snippets/text-classification-tf/csharp/Program.cs#CreateTestData)]

1. <span data-ttu-id="d2629-244">Passare i dati del commento di test a `Prediction Engine` aggiungendo le righe di codice seguenti nel `PredictSentiment()` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-244">Pass the test comment data to the `Prediction Engine` by adding the next lines of code in the `PredictSentiment()` method:</span></span>

    [!code-csharp[Predict](./snippets/text-classification-tf/csharp/Program.cs#Predict)]

1. <span data-ttu-id="d2629-245">La funzione [Predict ()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola riga di dati:</span><span class="sxs-lookup"><span data-stu-id="d2629-245">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

    |<span data-ttu-id="d2629-246">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d2629-246">Property</span></span>| <span data-ttu-id="d2629-247">valore</span><span class="sxs-lookup"><span data-stu-id="d2629-247">Value</span></span>|<span data-ttu-id="d2629-248">Type</span><span class="sxs-lookup"><span data-stu-id="d2629-248">Type</span></span>|
    |-------------|-----------------------|------|
    |<span data-ttu-id="d2629-249">Stima</span><span class="sxs-lookup"><span data-stu-id="d2629-249">Prediction</span></span>|<span data-ttu-id="d2629-250">[0,5459937, 0,454006255]</span><span class="sxs-lookup"><span data-stu-id="d2629-250">[0.5459937, 0.454006255]</span></span>|<span data-ttu-id="d2629-251">float []</span><span class="sxs-lookup"><span data-stu-id="d2629-251">float[]</span></span>|

1. <span data-ttu-id="d2629-252">Visualizzare la stima del sentimento usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d2629-252">Display sentiment prediction using the following code:</span></span>

    [!code-csharp[DisplayPredictions](./snippets/text-classification-tf/csharp/Program.cs#DisplayPredictions)]

1. <span data-ttu-id="d2629-253">Aggiungere una chiamata a alla `PredictSentiment` fine del `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="d2629-253">Add a call to `PredictSentiment` at the end of the `Main` method:</span></span>

    [!code-csharp[CallPredictSentiment](./snippets/text-classification-tf/csharp/Program.cs#CallPredictSentiment)]

## <a name="results"></a><span data-ttu-id="d2629-254">Risultati</span><span class="sxs-lookup"><span data-stu-id="d2629-254">Results</span></span>

<span data-ttu-id="d2629-255">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d2629-255">Build and run your application.</span></span>

<span data-ttu-id="d2629-256">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d2629-256">Your results should be similar to the following.</span></span> <span data-ttu-id="d2629-257">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="d2629-257">During processing, messages are displayed.</span></span> <span data-ttu-id="d2629-258">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d2629-258">You may see warnings, or processing messages.</span></span> <span data-ttu-id="d2629-259">Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="d2629-259">These messages have been removed from the following results for clarity.</span></span>

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

<span data-ttu-id="d2629-260">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="d2629-260">Congratulations!</span></span> <span data-ttu-id="d2629-261">A questo punto, è stato creato un modello di apprendimento automatico per la classificazione e la stima del sentimento dei messaggi riutilizzando un modello con training preliminare `TensorFlow` in ml.NET.</span><span class="sxs-lookup"><span data-stu-id="d2629-261">You've now successfully built a machine learning model for classifying and predicting messages sentiment by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="d2629-262">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="d2629-262">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

<span data-ttu-id="d2629-263">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="d2629-263">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="d2629-264">Caricare un modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="d2629-264">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="d2629-265">Trasforma il testo del commento del sito Web in funzionalità appropriate per il modello</span><span class="sxs-lookup"><span data-stu-id="d2629-265">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="d2629-266">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="d2629-266">Use the model to make a prediction</span></span>
