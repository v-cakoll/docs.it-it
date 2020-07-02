---
title: 'Esercitazione: analizzare i commenti del sito Web-classificazione binaria'
description: In questa esercitazione viene illustrato come creare un'applicazione console .NET Core che classifica le valutazioni dei commenti di un sito web ed esegue l'azione appropriata. La funzione di classificazione binaria delle valutazioni usa C# in Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b193752437c3e84476858bb3b70ba642d8562769
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803248"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="89397-104">Esercitazione: analizzare i sentimenti dei commenti del sito Web con classificazione binaria in ML.NET</span><span class="sxs-lookup"><span data-stu-id="89397-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="89397-105">In questa esercitazione viene illustrato come creare un'applicazione console .NET Core che classifica le valutazioni dei commenti di un sito web ed esegue l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="89397-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="89397-106">La funzione di classificazione binaria delle valutazioni usa C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="89397-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="89397-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="89397-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="89397-108">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="89397-108">Create a console application</span></span>
> - <span data-ttu-id="89397-109">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="89397-109">Prepare data</span></span>
> - <span data-ttu-id="89397-110">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="89397-110">Load the data</span></span>
> - <span data-ttu-id="89397-111">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="89397-111">Build and train the model</span></span>
> - <span data-ttu-id="89397-112">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="89397-112">Evaluate the model</span></span>
> - <span data-ttu-id="89397-113">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="89397-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="89397-114">Visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="89397-114">See the results</span></span>

<span data-ttu-id="89397-115">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="89397-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89397-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="89397-116">Prerequisites</span></span>

- <span data-ttu-id="89397-117">[Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato</span><span class="sxs-lookup"><span data-stu-id="89397-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="89397-118">[Set di dati Sentiment Labeled Sentences di UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (file con estensione zip)</span><span class="sxs-lookup"><span data-stu-id="89397-118">[UCI Sentiment Labeled Sentences dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="89397-119">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="89397-119">Create a console application</span></span>

1. <span data-ttu-id="89397-120">Creare un'**applicazione console di .NET Core** con nome "SentimentAnalysis".</span><span class="sxs-lookup"><span data-stu-id="89397-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="89397-121">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="89397-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="89397-122">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="89397-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="89397-123">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="89397-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="89397-124">Scegliere "nuget.org" come origine del pacchetto, quindi selezionare la scheda **Sfoglia** . cercare **Microsoft.ml**, selezionare il pacchetto desiderato e quindi fare clic sul pulsante **Installa** .</span><span class="sxs-lookup"><span data-stu-id="89397-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="89397-125">Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto.</span><span class="sxs-lookup"><span data-stu-id="89397-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="89397-126">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="89397-126">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="89397-127">I set di dati usati in questa esercitazione provengono da "From Group to Individual Labels using Deep Features", Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="89397-127">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="89397-128">al,.</span><span class="sxs-lookup"><span data-stu-id="89397-128">al,.</span></span> <span data-ttu-id="89397-129">KDD 2015 e ospitato nel repository di Machine Learning UCI-Dua, D. e Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="89397-129">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="89397-130">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="89397-130">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="89397-131">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="89397-131">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="89397-132">Scaricare il [file con estensione zip del set di dati Sentiment Labeled Sentences di UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) e decomprimerlo.</span><span class="sxs-lookup"><span data-stu-id="89397-132">Download [UCI Sentiment Labeled Sentences dataset ZIP file](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="89397-133">Copiare il file `yelp_labelled.txt` nella directory *Data* creata.</span><span class="sxs-lookup"><span data-stu-id="89397-133">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="89397-134">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file `yelp_labeled.txt` e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="89397-134">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="89397-135">In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="89397-135">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="89397-136">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="89397-136">Create classes and define paths</span></span>

1. <span data-ttu-id="89397-137">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: </span><span class="sxs-lookup"><span data-stu-id="89397-137">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="89397-138">Aggiungere il codice seguente alla riga immediatamente sopra il `Main` metodo per creare un campo che contenga il percorso del file del set di dati scaricato di recente:</span><span class="sxs-lookup"><span data-stu-id="89397-138">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="89397-139">Successivamente, creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="89397-139">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="89397-140">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="89397-140">Add a new class to your project:</span></span>

    - <span data-ttu-id="89397-141">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi selezionare **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="89397-141">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="89397-142">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="89397-142">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="89397-143">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="89397-143">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="89397-144">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="89397-144">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="89397-145">Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="89397-145">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="89397-146">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="89397-146">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="89397-147">Come sono stati preparati i dati</span><span class="sxs-lookup"><span data-stu-id="89397-147">How the data was prepared</span></span>

<span data-ttu-id="89397-148">La classe di set di dati di input, `SentimentData`, dispone di un `string` per i commenti utente (`SentimentText`) e di un valore `bool` (`Sentiment`) pari a 1 (positivo) o 0 (negativo) per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="89397-148">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="89397-149">Entrambi i campi hanno attributi [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) associati, che descrivono l'ordine di file di dati di ogni campo.</span><span class="sxs-lookup"><span data-stu-id="89397-149">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="89397-150">Inoltre, la proprietà `Sentiment` include un attributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) per designarlo come campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="89397-150">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="89397-151">Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-151">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="89397-152">SentimentText</span><span class="sxs-lookup"><span data-stu-id="89397-152">SentimentText</span></span>                         |<span data-ttu-id="89397-153">Valutazione (etichetta)</span><span class="sxs-lookup"><span data-stu-id="89397-153">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="89397-154">La cameriera era un po' lenta a servire.</span><span class="sxs-lookup"><span data-stu-id="89397-154">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="89397-155">0</span><span class="sxs-lookup"><span data-stu-id="89397-155">0</span></span>     |
|<span data-ttu-id="89397-156">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="89397-156">Crust is not good.</span></span>                    |    <span data-ttu-id="89397-157">0</span><span class="sxs-lookup"><span data-stu-id="89397-157">0</span></span>     |
|<span data-ttu-id="89397-158">Wow... Questo posto è stato apprezzato.</span><span class="sxs-lookup"><span data-stu-id="89397-158">Wow... Loved this place.</span></span>              |    <span data-ttu-id="89397-159">1</span><span class="sxs-lookup"><span data-stu-id="89397-159">1</span></span>     |
|<span data-ttu-id="89397-160">Il servizio è stato molto rapido.</span><span class="sxs-lookup"><span data-stu-id="89397-160">Service was very prompt.</span></span>              |    <span data-ttu-id="89397-161">1</span><span class="sxs-lookup"><span data-stu-id="89397-161">1</span></span>     |

<span data-ttu-id="89397-162">`SentimentPrediction` è la classe di stima usata dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="89397-162">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="89397-163">Questa classe eredita da `SentimentData` in modo che l'input `SentimentText` sia visualizzabile insieme alla stima di output.</span><span class="sxs-lookup"><span data-stu-id="89397-163">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="89397-164">Il valore booleano `Prediction` è il valore di cui il modello esegue la stima quando riceve un nuovo input `SentimentText`.</span><span class="sxs-lookup"><span data-stu-id="89397-164">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="89397-165">La classe di output `SentimentPrediction` contiene altre due proprietà calcolate dal modello: `Score`, che è il punteggio non elaborato calcolato dal modello e `Probability`, che è il punteggio calibrato sulla probabilità che il testo esprima un sentiment positivo.</span><span class="sxs-lookup"><span data-stu-id="89397-165">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="89397-166">Per questa esercitazione la proprietà più importante è `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="89397-166">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="89397-167">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="89397-167">Load the data</span></span>

<span data-ttu-id="89397-168">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="89397-168">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="89397-169">`IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="89397-169">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="89397-170">È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="89397-170">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="89397-171">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET.</span><span class="sxs-lookup"><span data-stu-id="89397-171">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="89397-172">L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="89397-172">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="89397-173">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="89397-173">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="89397-174">Preparare l'app, quindi caricare i dati:</span><span class="sxs-lookup"><span data-stu-id="89397-174">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="89397-175">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:</span><span class="sxs-lookup"><span data-stu-id="89397-175">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="89397-176">Aggiungere il codice seguente al metodo `Main()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="89397-176">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallLoadData)]

3. <span data-ttu-id="89397-177">Creare il metodo `LoadData()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-177">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="89397-178">Il metodo `LoadData()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89397-178">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="89397-179">Carica i dati.</span><span class="sxs-lookup"><span data-stu-id="89397-179">Loads the data.</span></span>
    - <span data-ttu-id="89397-180">Suddivide il set di dati caricati in set di dati di training e di test.</span><span class="sxs-lookup"><span data-stu-id="89397-180">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="89397-181">Restituisce i set di dati di training e di test divisi.</span><span class="sxs-lookup"><span data-stu-id="89397-181">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="89397-182">Aggiungere il codice seguente come prima riga del metodo `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="89397-182">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="89397-183">Il metodo [LoadFromTextFile ()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema di dati e legge il file.</span><span class="sxs-lookup"><span data-stu-id="89397-183">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) method defines the data schema and reads in the file.</span></span> <span data-ttu-id="89397-184">Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="89397-184">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="89397-185">Dividere il set di dati per il training e il test del modello</span><span class="sxs-lookup"><span data-stu-id="89397-185">Split the dataset for model training and testing</span></span>

<span data-ttu-id="89397-186">Quando si prepara un modello, usare parte del set di dati per il training e parte del set di dati per testare l'accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="89397-186">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="89397-187">Per dividere i dati caricati nei set di dati necessari, aggiungere il codice seguente come riga successiva nel metodo `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="89397-187">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="89397-188">Il codice precedente usa il metodo [TrainTestSplit ()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) per suddividere il set di dati caricato in set di dati di training e di test e restituirli nella <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> classe.</span><span class="sxs-lookup"><span data-stu-id="89397-188">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> class.</span></span> <span data-ttu-id="89397-189">Specificare la percentuale di dati del set di test con il parametro `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="89397-189">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="89397-190">Il valore predefinito è 10%, in questo caso usare il 20% per valutare più dati.</span><span class="sxs-lookup"><span data-stu-id="89397-190">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="89397-191">Restituire `splitDataView` alla fine del metodo `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="89397-191">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="89397-192">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="89397-192">Build and train the model</span></span>

1. <span data-ttu-id="89397-193">Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="89397-193">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="89397-194">Il metodo `BuildAndTrainModel()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89397-194">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="89397-195">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="89397-195">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="89397-196">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="89397-196">Trains the model.</span></span>
    - <span data-ttu-id="89397-197">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="89397-197">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="89397-198">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="89397-198">Returns the model.</span></span>

2. <span data-ttu-id="89397-199">Creare il metodo `BuildAndTrainModel()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-199">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="89397-200">Estrarre e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="89397-200">Extract and transform the data</span></span>

1. <span data-ttu-id="89397-201">Chiamare `FeaturizeText` quale riga di codice successiva:</span><span class="sxs-lookup"><span data-stu-id="89397-201">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="89397-202">Il metodo `FeaturizeText()` nel codice precedente consente di convertire la colonna di testo (`SentimentText`) in una colonna `Features` di tipo di chiave numerica usata dall'algoritmo di apprendimento automatico e di aggiungerla come nuova colonna del set di dati:</span><span class="sxs-lookup"><span data-stu-id="89397-202">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="89397-203">SentimentText</span><span class="sxs-lookup"><span data-stu-id="89397-203">SentimentText</span></span>                         |<span data-ttu-id="89397-204">Valutazione</span><span class="sxs-lookup"><span data-stu-id="89397-204">Sentiment</span></span> |<span data-ttu-id="89397-205">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="89397-205">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="89397-206">La cameriera era un po' lenta a servire.</span><span class="sxs-lookup"><span data-stu-id="89397-206">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="89397-207">0</span><span class="sxs-lookup"><span data-stu-id="89397-207">0</span></span>     |<span data-ttu-id="89397-208">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="89397-208">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="89397-209">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="89397-209">Crust is not good.</span></span>                    |    <span data-ttu-id="89397-210">0</span><span class="sxs-lookup"><span data-stu-id="89397-210">0</span></span>     |<span data-ttu-id="89397-211">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="89397-211">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="89397-212">Wow... Questo posto è stato apprezzato.</span><span class="sxs-lookup"><span data-stu-id="89397-212">Wow... Loved this place.</span></span>              |    <span data-ttu-id="89397-213">1</span><span class="sxs-lookup"><span data-stu-id="89397-213">1</span></span>     |<span data-ttu-id="89397-214">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="89397-214">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="89397-215">Il servizio è stato molto rapido.</span><span class="sxs-lookup"><span data-stu-id="89397-215">Service was very prompt.</span></span>              |    <span data-ttu-id="89397-216">1</span><span class="sxs-lookup"><span data-stu-id="89397-216">1</span></span>     |<span data-ttu-id="89397-217">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="89397-217">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="89397-218">Aggiungere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="89397-218">Add a learning algorithm</span></span>

<span data-ttu-id="89397-219">Questa app usa un algoritmo di classificazione che classifica gli elementi o le righe di dati.</span><span class="sxs-lookup"><span data-stu-id="89397-219">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="89397-220">L'app consente di classificare i commenti di un sito web come positivi o negativi, quindi di usare l'attività di classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="89397-220">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="89397-221">Aggiungere l'attività di Machine Learning alle definizioni di trasformazione dei dati aggiungendo il codice seguente come riga successiva di codice in `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="89397-221">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="89397-222">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) è l'algoritmo del training di classificazione.</span><span class="sxs-lookup"><span data-stu-id="89397-222">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="89397-223">Viene aggiunto alla `estimator` e accetta l'oggetto `SentimentText` (`Features`) da cui sono state estratte le caratteristiche e i parametri di input `Label` per l'apprendimento in base ai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="89397-223">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="89397-224">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="89397-224">Train the model</span></span>

<span data-ttu-id="89397-225">Eseguire il fit del modello ai dati `splitTrainSet` e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="89397-225">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="89397-226">Il metodo [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) esegue il training del modello trasformando il set di dati e applicando il training.</span><span class="sxs-lookup"><span data-stu-id="89397-226">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="89397-227">Restituire il modello di cui è stato eseguito il training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="89397-227">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="89397-228">Restituire il modello alla fine del metodo `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="89397-228">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="89397-229">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="89397-229">Evaluate the model</span></span>

<span data-ttu-id="89397-230">Dopo che viene eseguito il training del modello, usare i dati di test per convalidare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="89397-230">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="89397-231">Creare il metodo `Evaluate()` subito dopo `BuildAndTrainModel()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-231">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="89397-232">Il metodo `Evaluate()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89397-232">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="89397-233">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="89397-233">Loads the test dataset.</span></span>
    - <span data-ttu-id="89397-234">Crea l'analizzatore BinaryClassification.</span><span class="sxs-lookup"><span data-stu-id="89397-234">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="89397-235">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="89397-235">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="89397-236">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="89397-236">Displays the metrics.</span></span>

2. <span data-ttu-id="89397-237">Aggiungere una chiamata al nuovo metodo dal metodo `Main()`, subito sotto la chiamata al metodo `BuildAndTrainModel()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-237">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="89397-238">Trasformare i dati `splitTestSet` aggiungendo il codice seguente a `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="89397-238">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="89397-239">Il codice precedente usa il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) per effettuare previsioni per più righe di input specificate di un set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="89397-239">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="89397-240">Valutare il modello aggiungendo il codice seguente come riga successiva nel metodo `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="89397-240">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="89397-241">Dopo aver impostato la stima (`predictions`), il metodo [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) valuta il modello confrontando i valori stimati con gli oggetti `Labels` effettivi presenti nel set di dati di test e restituisce un oggetto [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) relativo alle prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="89397-241">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="89397-242">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="89397-242">Displaying the metrics for model validation</span></span>

<span data-ttu-id="89397-243">Usare il codice seguente per visualizzare le metriche:</span><span class="sxs-lookup"><span data-stu-id="89397-243">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="89397-244">La metrica `Accuracy` ottiene l'accuratezza di un modello, che è la percentuale di stime corrette nel set di test.</span><span class="sxs-lookup"><span data-stu-id="89397-244">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="89397-245">La metrica `AreaUnderRocCurve` indica con quale affidabilità il modello classifica correttamente le classi positive e negative.</span><span class="sxs-lookup"><span data-stu-id="89397-245">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="89397-246">`AreaUnderRocCurve` deve avvicinarsi il più possibile a 1.</span><span class="sxs-lookup"><span data-stu-id="89397-246">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="89397-247">La metrica `F1Score` produce il punteggio F1 del modello, che è una misura di equilibrio tra [precisione](../resources/glossary.md#precision) e [richiamo](../resources/glossary.md#recall).</span><span class="sxs-lookup"><span data-stu-id="89397-247">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="89397-248">`F1Score` deve avvicinarsi il più possibile a 1.</span><span class="sxs-lookup"><span data-stu-id="89397-248">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="89397-249">Stimare i risultati dei dati di test</span><span class="sxs-lookup"><span data-stu-id="89397-249">Predict the test data outcome</span></span>

1. <span data-ttu-id="89397-250">Creare il metodo `UseModelWithSingleItem()` subito dopo il metodo `Evaluate()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-250">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="89397-251">Il metodo `UseModelWithSingleItem()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89397-251">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="89397-252">Crea un singolo commento di dati di test.</span><span class="sxs-lookup"><span data-stu-id="89397-252">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="89397-253">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="89397-253">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="89397-254">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="89397-254">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="89397-255">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="89397-255">Displays the predicted results.</span></span>

2. <span data-ttu-id="89397-256">Aggiungere una chiamata al nuovo metodo dal metodo `Main()`, subito sotto la chiamata al metodo `Evaluate()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-256">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="89397-257">Aggiungere il codice seguente per creare come prima riga nel metodo `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="89397-257">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="89397-258">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="89397-258">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="89397-259">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="89397-259">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="89397-260">È accettabile usare in ambienti a thread singolo o prototipi.</span><span class="sxs-lookup"><span data-stu-id="89397-260">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="89397-261">Per migliorare le prestazioni e thread safety negli ambienti di produzione, utilizzare il `PredictionEnginePool` servizio, che consente di creare un oggetto [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da utilizzare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="89397-261">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="89397-262">Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="89397-262">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="89397-263">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="89397-263">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="89397-264">Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `UseModelWithSingleItem()` creando un'istanza di `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="89397-264">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="89397-265">Passare i dati del commento di test a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) aggiungendo quanto segue come righe successive di codice nel `UseModelWithSingleItem()` Metodo:</span><span class="sxs-lookup"><span data-stu-id="89397-265">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="89397-266">La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="89397-266">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="89397-267">Visualizzare `SentimentText` e la corrispondente stima della valutazione tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-267">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="89397-268">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="89397-268">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="89397-269">Distribuire e prevedere gli elementi del batch</span><span class="sxs-lookup"><span data-stu-id="89397-269">Deploy and predict batch items</span></span>

1. <span data-ttu-id="89397-270">Creare il metodo `UseModelWithBatchItems()` subito dopo il metodo `UseModelWithSingleItem()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-270">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="89397-271">Il metodo `UseModelWithBatchItems()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89397-271">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="89397-272">Crea i dati di test in batch.</span><span class="sxs-lookup"><span data-stu-id="89397-272">Creates batch test data.</span></span>
    - <span data-ttu-id="89397-273">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="89397-273">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="89397-274">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="89397-274">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="89397-275">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="89397-275">Displays the predicted results.</span></span>

2. <span data-ttu-id="89397-276">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `UseModelWithSingleItem()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-276">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="89397-277">Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `UseModelWithBatchItems()`:</span><span class="sxs-lookup"><span data-stu-id="89397-277">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="89397-278">Prevedere la valutazione del commento</span><span class="sxs-lookup"><span data-stu-id="89397-278">Predict comment sentiment</span></span>

<span data-ttu-id="89397-279">Usare il modello per stimare la valutazione dei dati del commento usando il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A):</span><span class="sxs-lookup"><span data-stu-id="89397-279">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="89397-280">Combinare e visualizzare le stime</span><span class="sxs-lookup"><span data-stu-id="89397-280">Combine and display the predictions</span></span>

<span data-ttu-id="89397-281">Creare un'intestazione per le stime con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89397-281">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="89397-282">Poiché `SentimentPrediction` viene ereditato da `SentimentData`, il metodo `Transform()` ha compilato `SentimentText` con i campi previsti.</span><span class="sxs-lookup"><span data-stu-id="89397-282">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="89397-283">Mentre il processo ML.NET elabora, ogni componente aggiunge colonne e ciò rende più facile visualizzare i risultati:</span><span class="sxs-lookup"><span data-stu-id="89397-283">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="89397-284">Risultati</span><span class="sxs-lookup"><span data-stu-id="89397-284">Results</span></span>

<span data-ttu-id="89397-285">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="89397-285">Your results should be similar to the following.</span></span> <span data-ttu-id="89397-286">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="89397-286">During processing, messages are displayed.</span></span> <span data-ttu-id="89397-287">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="89397-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="89397-288">Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="89397-288">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="89397-289">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="89397-289">Congratulations!</span></span> <span data-ttu-id="89397-290">A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="89397-290">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="89397-291">La creazione di modelli efficaci è un processo iterativo.</span><span class="sxs-lookup"><span data-stu-id="89397-291">Building successful models is an iterative process.</span></span> <span data-ttu-id="89397-292">Questo modello ha inizialmente una qualità inferiore, perché l'esercitazione usa set di dati di dimensioni contenute per consentire il training rapido del modello.</span><span class="sxs-lookup"><span data-stu-id="89397-292">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="89397-293">Se non si è soddisfatti della qualità del modello, è possibile provare a migliorarlo fornendo set di impostazioni di training di dimensioni maggiori o scegliendo algoritmi di training diversi con diversi [parametri ipertestuali](../resources/glossary.md#hyperparameter) per ogni algoritmo.</span><span class="sxs-lookup"><span data-stu-id="89397-293">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="89397-294">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="89397-294">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89397-295">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="89397-295">Next steps</span></span>

<span data-ttu-id="89397-296">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="89397-296">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="89397-297">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="89397-297">Create a console application</span></span>
> - <span data-ttu-id="89397-298">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="89397-298">Prepare data</span></span>
> - <span data-ttu-id="89397-299">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="89397-299">Load the data</span></span>
> - <span data-ttu-id="89397-300">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="89397-300">Build and train the model</span></span>
> - <span data-ttu-id="89397-301">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="89397-301">Evaluate the model</span></span>
> - <span data-ttu-id="89397-302">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="89397-302">Use the model to make a prediction</span></span>
> - <span data-ttu-id="89397-303">Visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="89397-303">See the results</span></span>

<span data-ttu-id="89397-304">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="89397-304">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="89397-305">Classificazione dei problemi</span><span class="sxs-lookup"><span data-stu-id="89397-305">Issue Classification</span></span>](github-issue-classification.md)
