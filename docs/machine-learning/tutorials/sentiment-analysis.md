---
title: 'Esercitazione: analizzare i commenti del sito Web-classificazione binaria'
description: In questa esercitazione viene illustrato come creare un'applicazione console .NET Core che classifica le valutazioni dei commenti di un sito web ed esegue l'azione appropriata. La funzione di classificazione binaria delle valutazioni usa C# in Visual Studio.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 4fec19c6d7a83ba4e5b2bd0cd6e196ee19c49ce8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344953"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="8173d-104">Esercitazione: analizzare i sentimenti dei commenti del sito Web con classificazione binaria in ML.NET</span><span class="sxs-lookup"><span data-stu-id="8173d-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="8173d-105">In questa esercitazione viene illustrato come creare un'applicazione console .NET Core che classifica le valutazioni dei commenti di un sito web ed esegue l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="8173d-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="8173d-106">La funzione di classificazione binaria delle valutazioni usa C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8173d-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="8173d-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="8173d-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8173d-108">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="8173d-108">Create a console application</span></span>
> - <span data-ttu-id="8173d-109">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-109">Prepare data</span></span>
> - <span data-ttu-id="8173d-110">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-110">Load the data</span></span>
> - <span data-ttu-id="8173d-111">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="8173d-111">Build and train the model</span></span>
> - <span data-ttu-id="8173d-112">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="8173d-112">Evaluate the model</span></span>
> - <span data-ttu-id="8173d-113">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="8173d-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="8173d-114">Visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="8173d-114">See the results</span></span>

<span data-ttu-id="8173d-115">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="8173d-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8173d-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8173d-116">Prerequisites</span></span>

- <span data-ttu-id="8173d-117">[Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato</span><span class="sxs-lookup"><span data-stu-id="8173d-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="8173d-118">[Set di dati Sentiment Labeled Sentences di UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (file con estensione zip)</span><span class="sxs-lookup"><span data-stu-id="8173d-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="8173d-119">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="8173d-119">Create a console application</span></span>

1. <span data-ttu-id="8173d-120">Creare un'**applicazione console di .NET Core** con nome "SentimentAnalysis".</span><span class="sxs-lookup"><span data-stu-id="8173d-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="8173d-121">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="8173d-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="8173d-122">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="8173d-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="8173d-123">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="8173d-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8173d-124">Scegliere "nuget.org" come origine del pacchetto, quindi selezionare la scheda **Sfoglia** . cercare **Microsoft.ml**, selezionare il pacchetto desiderato e quindi fare clic sul pulsante **Installa** .</span><span class="sxs-lookup"><span data-stu-id="8173d-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="8173d-125">Procedere con l'installazione accettando le condizioni di licenza per il pacchetto scelto.</span><span class="sxs-lookup"><span data-stu-id="8173d-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="8173d-126">Eseguire la stessa operazione per il pacchetto NuGet **Microsoft.ML.FastTree**.</span><span class="sxs-lookup"><span data-stu-id="8173d-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="8173d-127">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="8173d-128">I set di dati usati in questa esercitazione provengono da "From Group to Individual Labels using Deep Features", Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="8173d-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="8173d-129">al,.</span><span class="sxs-lookup"><span data-stu-id="8173d-129">al,.</span></span> <span data-ttu-id="8173d-130">KDD 2015 e ospitato nel repository di Machine Learning UCI-Dua, D. e Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="8173d-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="8173d-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="8173d-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="8173d-132">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="8173d-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="8173d-133">Scaricare il [file con estensione zip del set di dati Sentiment Labeled Sentences di UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) e decomprimerlo.</span><span class="sxs-lookup"><span data-stu-id="8173d-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="8173d-134">Copiare il file `yelp_labelled.txt` nella directory *Data* creata.</span><span class="sxs-lookup"><span data-stu-id="8173d-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="8173d-135">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file `yelp_labeled.txt` e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8173d-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="8173d-136">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="8173d-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="8173d-137">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="8173d-137">Create classes and define paths</span></span>

1. <span data-ttu-id="8173d-138">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="8173d-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="8173d-139">Aggiungere il codice seguente alla riga immediatamente sopra il metodo `Main` per creare un campo che contenga il percorso del file del set di dati scaricato di recente:</span><span class="sxs-lookup"><span data-stu-id="8173d-139">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="8173d-140">Successivamente, creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="8173d-140">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="8173d-141">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="8173d-141">Add a new class to your project:</span></span>

    - <span data-ttu-id="8173d-142">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8173d-142">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="8173d-143">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="8173d-143">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="8173d-144">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8173d-144">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="8173d-145">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="8173d-145">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="8173d-146">Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="8173d-146">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="8173d-147">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="8173d-147">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="8173d-148">Come sono stati preparati i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-148">How the data was prepared</span></span>

<span data-ttu-id="8173d-149">La classe di set di dati di input, `SentimentData`, dispone di un `string` per i commenti utente (`SentimentText`) e di un valore `bool` (`Sentiment`) pari a 1 (positivo) o 0 (negativo) per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="8173d-149">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="8173d-150">Entrambi i campi hanno attributi [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) associati, che descrivono l'ordine di file di dati di ogni campo.</span><span class="sxs-lookup"><span data-stu-id="8173d-150">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="8173d-151">Inoltre, la proprietà `Sentiment` include un attributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) per designarlo come campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="8173d-151">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="8173d-152">Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-152">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="8173d-153">SentimentText</span><span class="sxs-lookup"><span data-stu-id="8173d-153">SentimentText</span></span>                         |<span data-ttu-id="8173d-154">Valutazione (etichetta)</span><span class="sxs-lookup"><span data-stu-id="8173d-154">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="8173d-155">La cameriera era un po' lenta a servire.</span><span class="sxs-lookup"><span data-stu-id="8173d-155">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="8173d-156">0</span><span class="sxs-lookup"><span data-stu-id="8173d-156">0</span></span>     |
|<span data-ttu-id="8173d-157">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="8173d-157">Crust is not good.</span></span>                    |    <span data-ttu-id="8173d-158">0</span><span class="sxs-lookup"><span data-stu-id="8173d-158">0</span></span>     |
|<span data-ttu-id="8173d-159">Wow... Questo posto è stato apprezzato.</span><span class="sxs-lookup"><span data-stu-id="8173d-159">Wow... Loved this place.</span></span>              |    <span data-ttu-id="8173d-160">1</span><span class="sxs-lookup"><span data-stu-id="8173d-160">1</span></span>     |
|<span data-ttu-id="8173d-161">Il servizio è stato molto rapido.</span><span class="sxs-lookup"><span data-stu-id="8173d-161">Service was very prompt.</span></span>              |    <span data-ttu-id="8173d-162">1</span><span class="sxs-lookup"><span data-stu-id="8173d-162">1</span></span>     |

<span data-ttu-id="8173d-163">`SentimentPrediction` è la classe di stima usata dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-163">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="8173d-164">Questa classe eredita da `SentimentData` in modo che l'input `SentimentText` sia visualizzabile insieme alla stima di output.</span><span class="sxs-lookup"><span data-stu-id="8173d-164">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="8173d-165">Il valore booleano `Prediction` è il valore di cui il modello esegue la stima quando riceve un nuovo input `SentimentText`.</span><span class="sxs-lookup"><span data-stu-id="8173d-165">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="8173d-166">La classe di output `SentimentPrediction` contiene altre due proprietà calcolate dal modello: `Score`, che è il punteggio non elaborato calcolato dal modello e `Probability`, che è il punteggio calibrato sulla probabilità che il testo esprima un sentiment positivo.</span><span class="sxs-lookup"><span data-stu-id="8173d-166">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="8173d-167">Per questa esercitazione la proprietà più importante è `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="8173d-167">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="8173d-168">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-168">Load the data</span></span>

<span data-ttu-id="8173d-169">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="8173d-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="8173d-170">`IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="8173d-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="8173d-171">È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="8173d-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="8173d-172">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET.</span><span class="sxs-lookup"><span data-stu-id="8173d-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="8173d-173">L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="8173d-174">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8173d-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="8173d-175">Preparare l'app, quindi caricare i dati:</span><span class="sxs-lookup"><span data-stu-id="8173d-175">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="8173d-176">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile mlContext:</span><span class="sxs-lookup"><span data-stu-id="8173d-176">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="8173d-177">Aggiungere il codice seguente al metodo `Main()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="8173d-177">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

3. <span data-ttu-id="8173d-178">Creare il metodo `LoadData()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-178">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="8173d-179">Il metodo `LoadData()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8173d-179">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8173d-180">Carica i dati.</span><span class="sxs-lookup"><span data-stu-id="8173d-180">Loads the data.</span></span>
    - <span data-ttu-id="8173d-181">Suddivide il set di dati caricati in set di dati di training e di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-181">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="8173d-182">Restituisce i set di dati di training e di test divisi.</span><span class="sxs-lookup"><span data-stu-id="8173d-182">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="8173d-183">Aggiungere il codice seguente come prima riga del metodo `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-183">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="8173d-184">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="8173d-184">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="8173d-185">Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="8173d-185">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="8173d-186">Dividere il set di dati per il training e il test del modello</span><span class="sxs-lookup"><span data-stu-id="8173d-186">Split the dataset for model training and testing</span></span>

<span data-ttu-id="8173d-187">Quando si prepara un modello, usare parte del set di dati per il training e parte del set di dati per testare l'accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-187">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="8173d-188">Per dividere i dati caricati nei set di dati necessari, aggiungere il codice seguente come riga successiva nel metodo `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-188">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="8173d-189">Il codice precedente usa il metodo [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) per suddividere il set di dati caricati in set di dati di training e di test e restituirli nella classe [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData).</span><span class="sxs-lookup"><span data-stu-id="8173d-189">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="8173d-190">Specificare la percentuale di dati del set di test con il parametro `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="8173d-190">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="8173d-191">Il valore predefinito è 10%, in questo caso usare il 20% per valutare più dati.</span><span class="sxs-lookup"><span data-stu-id="8173d-191">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="8173d-192">Restituire `splitDataView` alla fine del metodo `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-192">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="8173d-193">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="8173d-193">Build and train the model</span></span>

1. <span data-ttu-id="8173d-194">Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-194">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="8173d-195">Il metodo `BuildAndTrainModel()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8173d-195">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8173d-196">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="8173d-196">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="8173d-197">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-197">Trains the model.</span></span>
    - <span data-ttu-id="8173d-198">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-198">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="8173d-199">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-199">Returns the model.</span></span>

2. <span data-ttu-id="8173d-200">Creare il metodo `BuildAndTrainModel()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-200">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="8173d-201">Estrarre e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-201">Extract and transform the data</span></span>

1. <span data-ttu-id="8173d-202">Chiamare `FeaturizeText` quale riga di codice successiva:</span><span class="sxs-lookup"><span data-stu-id="8173d-202">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="8173d-203">Il metodo `FeaturizeText()` nel codice precedente consente di convertire la colonna di testo (`SentimentText`) in una colonna `Features` di tipo di chiave numerica usata dall'algoritmo di apprendimento automatico e di aggiungerla come nuova colonna del set di dati:</span><span class="sxs-lookup"><span data-stu-id="8173d-203">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="8173d-204">SentimentText</span><span class="sxs-lookup"><span data-stu-id="8173d-204">SentimentText</span></span>                         |<span data-ttu-id="8173d-205">Valutazione</span><span class="sxs-lookup"><span data-stu-id="8173d-205">Sentiment</span></span> |<span data-ttu-id="8173d-206">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="8173d-206">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="8173d-207">La cameriera era un po' lenta a servire.</span><span class="sxs-lookup"><span data-stu-id="8173d-207">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="8173d-208">0</span><span class="sxs-lookup"><span data-stu-id="8173d-208">0</span></span>     |<span data-ttu-id="8173d-209">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="8173d-209">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="8173d-210">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="8173d-210">Crust is not good.</span></span>                    |    <span data-ttu-id="8173d-211">0</span><span class="sxs-lookup"><span data-stu-id="8173d-211">0</span></span>     |<span data-ttu-id="8173d-212">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="8173d-212">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="8173d-213">Wow... Questo posto è stato apprezzato.</span><span class="sxs-lookup"><span data-stu-id="8173d-213">Wow... Loved this place.</span></span>              |    <span data-ttu-id="8173d-214">1</span><span class="sxs-lookup"><span data-stu-id="8173d-214">1</span></span>     |<span data-ttu-id="8173d-215">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="8173d-215">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="8173d-216">Il servizio è stato molto rapido.</span><span class="sxs-lookup"><span data-stu-id="8173d-216">Service was very prompt.</span></span>              |    <span data-ttu-id="8173d-217">1</span><span class="sxs-lookup"><span data-stu-id="8173d-217">1</span></span>     |<span data-ttu-id="8173d-218">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="8173d-218">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="8173d-219">Aggiungere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="8173d-219">Add a learning algorithm</span></span>

<span data-ttu-id="8173d-220">Questa app usa un algoritmo di classificazione che classifica gli elementi o le righe di dati.</span><span class="sxs-lookup"><span data-stu-id="8173d-220">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="8173d-221">L'app consente di classificare i commenti di un sito web come positivi o negativi, quindi di usare l'attività di classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="8173d-221">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="8173d-222">Aggiungere l'attività di Machine Learning alle definizioni di trasformazione dei dati aggiungendo il codice seguente come riga successiva di codice in `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-222">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="8173d-223">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) è l'algoritmo del training di classificazione.</span><span class="sxs-lookup"><span data-stu-id="8173d-223">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="8173d-224">Viene aggiunto alla `estimator` e accetta l'oggetto `SentimentText` (`Features`) da cui sono state estratte le caratteristiche e i parametri di input `Label` per l'apprendimento in base ai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="8173d-224">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="8173d-225">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="8173d-225">Train the model</span></span>

<span data-ttu-id="8173d-226">Eseguire il fit del modello ai dati `splitTrainSet` e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-226">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="8173d-227">Il metodo [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) esegue il training del modello trasformando il set di dati e applicando il training.</span><span class="sxs-lookup"><span data-stu-id="8173d-227">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="8173d-228">Restituire il modello di cui è stato eseguito il training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="8173d-228">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="8173d-229">Restituire il modello alla fine del metodo `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-229">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="8173d-230">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="8173d-230">Evaluate the model</span></span>

<span data-ttu-id="8173d-231">Dopo che viene eseguito il training del modello, usare i dati di test per convalidare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-231">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="8173d-232">Creare il metodo `Evaluate()` subito dopo `BuildAndTrainModel()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-232">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="8173d-233">Il metodo `Evaluate()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8173d-233">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8173d-234">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-234">Loads the test dataset.</span></span>
    - <span data-ttu-id="8173d-235">Crea l'analizzatore BinaryClassification.</span><span class="sxs-lookup"><span data-stu-id="8173d-235">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="8173d-236">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="8173d-236">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="8173d-237">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="8173d-237">Displays the metrics.</span></span>

2. <span data-ttu-id="8173d-238">Aggiungere una chiamata al nuovo metodo dal metodo `Main()`, subito sotto la chiamata al metodo `BuildAndTrainModel()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-238">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="8173d-239">Trasformare i dati `splitTestSet` aggiungendo il codice seguente a `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-239">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="8173d-240">Il codice precedente usa il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) per effettuare previsioni per più righe di input specificate di un set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-240">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="8173d-241">Valutare il modello aggiungendo il codice seguente come riga successiva nel metodo `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-241">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="8173d-242">Dopo aver impostato la stima (`predictions`), il metodo [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) valuta il modello confrontando i valori stimati con gli oggetti `Labels` effettivi presenti nel set di dati di test e restituisce un oggetto [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) relativo alle prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-242">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="8173d-243">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="8173d-243">Displaying the metrics for model validation</span></span>

<span data-ttu-id="8173d-244">Usare il codice seguente per visualizzare le metriche:</span><span class="sxs-lookup"><span data-stu-id="8173d-244">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="8173d-245">La metrica `Accuracy` ottiene l'accuratezza di un modello, che è la percentuale di stime corrette nel set di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-245">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="8173d-246">La metrica `AreaUnderRocCurve` indica con quale affidabilità il modello classifica correttamente le classi positive e negative.</span><span class="sxs-lookup"><span data-stu-id="8173d-246">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="8173d-247">`AreaUnderRocCurve` deve avvicinarsi il più possibile a 1.</span><span class="sxs-lookup"><span data-stu-id="8173d-247">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="8173d-248">La metrica `F1Score` produce il punteggio F1 del modello, che è una misura di equilibrio tra [precisione](../resources/glossary.md#precision) e [richiamo](../resources/glossary.md#recall).</span><span class="sxs-lookup"><span data-stu-id="8173d-248">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="8173d-249">`F1Score` deve avvicinarsi il più possibile a 1.</span><span class="sxs-lookup"><span data-stu-id="8173d-249">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="8173d-250">Stimare i risultati dei dati di test</span><span class="sxs-lookup"><span data-stu-id="8173d-250">Predict the test data outcome</span></span>

1. <span data-ttu-id="8173d-251">Creare il metodo `UseModelWithSingleItem()` subito dopo il metodo `Evaluate()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-251">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="8173d-252">Il metodo `UseModelWithSingleItem()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8173d-252">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8173d-253">Crea un singolo commento di dati di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-253">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="8173d-254">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-254">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="8173d-255">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="8173d-255">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="8173d-256">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="8173d-256">Displays the predicted results.</span></span>

2. <span data-ttu-id="8173d-257">Aggiungere una chiamata al nuovo metodo dal metodo `Main()`, subito sotto la chiamata al metodo `Evaluate()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-257">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="8173d-258">Aggiungere il codice seguente per creare come prima riga nel metodo `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-258">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="8173d-259">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="8173d-259">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="8173d-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="8173d-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="8173d-261">È accettabile usare in ambienti a thread singolo o prototipi.</span><span class="sxs-lookup"><span data-stu-id="8173d-261">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="8173d-262">Per migliorare le prestazioni e thread safety negli ambienti di produzione, usare il servizio `PredictionEnginePool`, che consente di creare un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da usare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8173d-262">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="8173d-263">Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="8173d-263">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8173d-264">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="8173d-264">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="8173d-265">Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `UseModelWithSingleItem()` creando un'istanza di `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="8173d-265">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="8173d-266">Passare i dati di commento del test al [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) aggiungendo quanto segue come righe successive di codice nel metodo `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-266">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="8173d-267">La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="8173d-267">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="8173d-268">Visualizzare `SentimentText` e la corrispondente stima della valutazione tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-268">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="8173d-269">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="8173d-269">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="8173d-270">Distribuire e prevedere gli elementi del batch</span><span class="sxs-lookup"><span data-stu-id="8173d-270">Deploy and predict batch items</span></span>

1. <span data-ttu-id="8173d-271">Creare il metodo `UseModelWithBatchItems()` subito dopo il metodo `UseModelWithSingleItem()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-271">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="8173d-272">Il metodo `UseModelWithBatchItems()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8173d-272">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8173d-273">Crea i dati di test in batch.</span><span class="sxs-lookup"><span data-stu-id="8173d-273">Creates batch test data.</span></span>
    - <span data-ttu-id="8173d-274">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="8173d-274">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="8173d-275">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="8173d-275">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="8173d-276">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="8173d-276">Displays the predicted results.</span></span>

2. <span data-ttu-id="8173d-277">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `UseModelWithSingleItem()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-277">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="8173d-278">Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `UseModelWithBatchItems()`:</span><span class="sxs-lookup"><span data-stu-id="8173d-278">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="8173d-279">Prevedere la valutazione del commento</span><span class="sxs-lookup"><span data-stu-id="8173d-279">Predict comment sentiment</span></span>

<span data-ttu-id="8173d-280">Usare il modello per stimare la valutazione dei dati del commento usando il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A):</span><span class="sxs-lookup"><span data-stu-id="8173d-280">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="8173d-281">Combinare e visualizzare le stime</span><span class="sxs-lookup"><span data-stu-id="8173d-281">Combine and display the predictions</span></span>

<span data-ttu-id="8173d-282">Creare un'intestazione per le stime con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8173d-282">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="8173d-283">Poiché `SentimentPrediction` viene ereditato da `SentimentData`, il metodo `Transform()` ha compilato `SentimentText` con i campi previsti.</span><span class="sxs-lookup"><span data-stu-id="8173d-283">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="8173d-284">Mentre il processo ML.NET elabora, ogni componente aggiunge colonne e ciò rende più facile visualizzare i risultati:</span><span class="sxs-lookup"><span data-stu-id="8173d-284">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="8173d-285">Risultati</span><span class="sxs-lookup"><span data-stu-id="8173d-285">Results</span></span>

<span data-ttu-id="8173d-286">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8173d-286">Your results should be similar to the following.</span></span> <span data-ttu-id="8173d-287">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="8173d-287">During processing, messages are displayed.</span></span> <span data-ttu-id="8173d-288">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="8173d-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="8173d-289">Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="8173d-289">These have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="8173d-290">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8173d-290">Congratulations!</span></span> <span data-ttu-id="8173d-291">A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="8173d-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="8173d-292">La creazione di modelli efficaci è un processo iterativo.</span><span class="sxs-lookup"><span data-stu-id="8173d-292">Building successful models is an iterative process.</span></span> <span data-ttu-id="8173d-293">Questo modello ha inizialmente una qualità inferiore, perché l'esercitazione usa set di dati di dimensioni contenute per consentire il training rapido del modello.</span><span class="sxs-lookup"><span data-stu-id="8173d-293">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="8173d-294">Se non si è soddisfatti della qualità del modello, è possibile provare a migliorarla fornendo set di dati di training più grandi o scegliendo algoritmi di training diversi con [iperparametri](../resources/glossary.md#hyperparameter) diversi per ogni algoritmo.</span><span class="sxs-lookup"><span data-stu-id="8173d-294">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="8173d-295">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="8173d-295">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8173d-296">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8173d-296">Next steps</span></span>

<span data-ttu-id="8173d-297">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="8173d-297">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8173d-298">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="8173d-298">Create a console application</span></span>
> - <span data-ttu-id="8173d-299">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-299">Prepare data</span></span>
> - <span data-ttu-id="8173d-300">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8173d-300">Load the data</span></span>
> - <span data-ttu-id="8173d-301">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="8173d-301">Build and train the model</span></span>
> - <span data-ttu-id="8173d-302">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="8173d-302">Evaluate the model</span></span>
> - <span data-ttu-id="8173d-303">Usare il modello per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="8173d-303">Use the model to make a prediction</span></span>
> - <span data-ttu-id="8173d-304">Visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="8173d-304">See the results</span></span>

<span data-ttu-id="8173d-305">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="8173d-305">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="8173d-306">Classificazione del problema</span><span class="sxs-lookup"><span data-stu-id="8173d-306">Issue Classification</span></span>](github-issue-classification.md)
