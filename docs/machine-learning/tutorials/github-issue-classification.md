---
title: 'Esercitazione: categorizzare i problemi di supporto-classificazione multiclasse'
description: Informazioni su come usare ML.NET in uno scenario di classificazione multiclasse per assegnare i problemi di GitHub a un'area specifica.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 5233924dab063fd1ba0232672613f9701f637385
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803729"
---
# <a name="tutorial-categorize-support-issues-using-multiclass-classification-with-mlnet"></a><span data-ttu-id="595db-103">Esercitazione: categorizzare i problemi di supporto usando la classificazione multiclasse con ML.NET</span><span class="sxs-lookup"><span data-stu-id="595db-103">Tutorial: Categorize support issues using multiclass classification with ML.NET</span></span>

<span data-ttu-id="595db-104">Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore di problemi di GitHub per eseguire il training di un modello che classifica e stima l'etichetta Area per un problema di GitHub tramite un'applicazione console .NET Core con C# in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="595db-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier to train a model that classifies and predicts the Area label for a GitHub issue via a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="595db-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="595db-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="595db-106">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="595db-106">Prepare your data</span></span>
> * <span data-ttu-id="595db-107">Trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="595db-107">Transform the data</span></span>
> * <span data-ttu-id="595db-108">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="595db-108">Train the model</span></span>
> * <span data-ttu-id="595db-109">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="595db-109">Evaluate the model</span></span>
> * <span data-ttu-id="595db-110">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="595db-110">Predict with the trained model</span></span>
> * <span data-ttu-id="595db-111">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="595db-111">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="595db-112">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="595db-112">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="595db-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="595db-113">Prerequisites</span></span>

* <span data-ttu-id="595db-114">[Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o visual studio 2017 versione 15,6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="595db-114">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
* <span data-ttu-id="595db-115">File con valori [delimitati da tabulazioni di GitHub (issues_train. TSV)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="595db-115">The [GitHub issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="595db-116">Il [file con valori delimitati da tabulazioni dei test di GitHub (issues_test. TSV)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="595db-116">The [GitHub issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="595db-117">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="595db-117">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="595db-118">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="595db-118">Create a project</span></span>

1. <span data-ttu-id="595db-119">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="595db-119">Open Visual Studio 2017.</span></span> <span data-ttu-id="595db-120">Scegliere **file**  >  **nuovo**  >  **progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="595db-120">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="595db-121">Nella finestra di dialogo **nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="595db-121">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="595db-122">Selezionare quindi il modello di progetto **App Console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="595db-122">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="595db-123">Nella casella di testo **Nome** digitare "GitHubIssueClassification" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="595db-123">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="595db-124">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:</span><span class="sxs-lookup"><span data-stu-id="595db-124">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="595db-125">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="595db-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="595db-126">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="595db-126">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="595db-127">Creare una directory denominata *Models* nel progetto per salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="595db-127">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="595db-128">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="595db-128">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="595db-129">Digitare "Models" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="595db-129">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="595db-130">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="595db-130">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="595db-131">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="595db-131">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="595db-132">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ml** e selezionare il pulsante **Installa** .</span><span class="sxs-lookup"><span data-stu-id="595db-132">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="595db-133">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="595db-133">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="595db-134">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="595db-134">Prepare your data</span></span>

1. <span data-ttu-id="595db-135">Scaricare i set di dati [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) e salvarli nella cartella *Data* creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="595db-135">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="595db-136">Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="595db-136">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="595db-137">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="595db-137">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="595db-138">In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="595db-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="595db-139">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="595db-139">Create classes and define paths</span></span>

<span data-ttu-id="595db-140">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: </span><span class="sxs-lookup"><span data-stu-id="595db-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddUsings)]

<span data-ttu-id="595db-141">Creare tre campi globali per i percorsi dei file scaricati di recente e variabili globali per `MLContext`,`DataView` e `PredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="595db-141">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, and `PredictionEngine`:</span></span>

* <span data-ttu-id="595db-142">`_trainDataPath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="595db-142">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="595db-143">`_testDataPath` contiene il percorso del set di dati usato per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="595db-143">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="595db-144">`_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="595db-144">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="595db-145">`_mlContext` è l'elemento <xref:Microsoft.ML.MLContext> che specifica il contesto di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="595db-145">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="595db-146">`_trainingDataView` è l'elemento <xref:Microsoft.ML.IDataView> usato per elaborare il set di dati di training.</span><span class="sxs-lookup"><span data-stu-id="595db-146">`_trainingDataView` is the <xref:Microsoft.ML.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="595db-147">`_predEngine` è l'elemento <xref:Microsoft.ML.PredictionEngine%602> usato per le stime singole.</span><span class="sxs-lookup"><span data-stu-id="595db-147">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>

<span data-ttu-id="595db-148">Aggiungere il codice seguente nella riga subito sopra il metodo `Main` per specificare questi percorsi e le altre variabili:</span><span class="sxs-lookup"><span data-stu-id="595db-148">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="595db-149">Creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="595db-149">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="595db-150">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="595db-150">Add a new class to your project:</span></span>

1. <span data-ttu-id="595db-151">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi selezionare **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="595db-151">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="595db-152">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** impostando *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="595db-152">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="595db-153">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="595db-153">Then, select the **Add** button.</span></span>

    <span data-ttu-id="595db-154">Il file *GitHubIssueData.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="595db-154">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="595db-155">Aggiungere l'istruzione `using` seguente all'inizio del file *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="595db-155">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="595db-156">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `GitHubIssue` e `IssuePrediction`, al file *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="595db-156">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="595db-157">`label` è la colonna sulla quale eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="595db-157">The `label` is the column you want to predict.</span></span> <span data-ttu-id="595db-158">Gli elementi `Features` identificati sono gli input indicati al modello per stimare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="595db-158">The identified `Features` are the inputs you give the model to predict the Label.</span></span>

<span data-ttu-id="595db-159">Usare [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) per specificare gli indici delle colonne di origine nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="595db-159">Use the [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="595db-160">`GitHubIssue` è la classe del set di dati input e ha i seguenti campi <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="595db-160">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="595db-161">La prima colonna `ID` (ID problema di GitHub)</span><span class="sxs-lookup"><span data-stu-id="595db-161">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="595db-162">La seconda colonna `Area` (stima per il training)</span><span class="sxs-lookup"><span data-stu-id="595db-162">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="595db-163">La terza colonna `Title` (titolo del problema GitHub) è la prima `feature` usata per la stima di `Area`</span><span class="sxs-lookup"><span data-stu-id="595db-163">the third column `Title` (GitHub issue title) is the first `feature` used for predicting the `Area`</span></span>
* <span data-ttu-id="595db-164">La quarta colonna `Description` è la seconda `feature` usata per la stima di `Area`</span><span class="sxs-lookup"><span data-stu-id="595db-164">the fourth column  `Description` is the second `feature` used for predicting the `Area`</span></span>

<span data-ttu-id="595db-165">`IssuePrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="595db-165">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="595db-166">Dispone di un singolo `string` ( `Area` ) e di un `PredictedLabel` `ColumnName` attributo.</span><span class="sxs-lookup"><span data-stu-id="595db-166">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span>  <span data-ttu-id="595db-167">`PredictedLabel` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="595db-167">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="595db-168">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="595db-168">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="595db-169">Tutte le operazioni di ML.NET vengono avviate nella classe [MLContext](xref:Microsoft.ML.MLContext) .</span><span class="sxs-lookup"><span data-stu-id="595db-169">All ML.NET operations start in the [MLContext](xref:Microsoft.ML.MLContext) class.</span></span> <span data-ttu-id="595db-170">L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="595db-170">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="595db-171">Dal punto di vista concettuale è simile a `DBContext` in `Entity Framework`.</span><span class="sxs-lookup"><span data-stu-id="595db-171">It's similar, conceptually, to `DBContext` in `Entity Framework`.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="595db-172">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="595db-172">Initialize variables in Main</span></span>

<span data-ttu-id="595db-173">Inizializzare la variabile globale `_mlContext` con una nuova istanza di `MLContext` con un valore di inizializzazione casuale (`seed: 0`) per risultati ripetibili/deterministici in più training.</span><span class="sxs-lookup"><span data-stu-id="595db-173">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="595db-174">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="595db-174">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="595db-175">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="595db-175">Load the data</span></span>

<span data-ttu-id="595db-176">ML.NET usa la [classe IDataView](xref:Microsoft.ML.IDataView) come un modo efficiente e flessibile per descrivere i dati tabulari numerici o di testo.</span><span class="sxs-lookup"><span data-stu-id="595db-176">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="595db-177">`IDataView` può caricare file testo o in tempo reale (ad esempio, file di database SQL o di log).</span><span class="sxs-lookup"><span data-stu-id="595db-177">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span>

<span data-ttu-id="595db-178">Per inizializzare e caricare la variabile globale `_trainingDataView` in modo da riusarla per la pipeline, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="595db-178">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTrainData)]

<span data-ttu-id="595db-179">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="595db-179">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="595db-180">Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="595db-180">It takes in the data path variables and returns an `IDataView`.</span></span>

<span data-ttu-id="595db-181">Aggiungere il codice seguente al metodo `Main` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="595db-181">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallProcessData)]

<span data-ttu-id="595db-182">Il metodo `ProcessData` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="595db-182">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="595db-183">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="595db-183">Extracts and transforms the data.</span></span>
* <span data-ttu-id="595db-184">Restituisce la pipeline di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="595db-184">Returns the processing pipeline.</span></span>

<span data-ttu-id="595db-185">Creare il metodo `ProcessData` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-185">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="595db-186">Estrarre le funzionalità e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="595db-186">Extract Features and transform the data</span></span>

<span data-ttu-id="595db-187">Dato che si vuole stimare l'etichetta GitHub Area per un `GitHubIssue`, usare il metodo [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) per trasformare la colonna `Area` in una colonna `Label` di tipo chiave numerica (un formato accettato dagli algoritmi di classificazione) e aggiungerla come nuova colonna del set di dati:</span><span class="sxs-lookup"><span data-stu-id="595db-187">As you want to predict the Area GitHub label for a `GitHubIssue`, use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform the `Area` column into a numeric key type `Label` column (a format accepted by classification algorithms) and add it as a new dataset column:</span></span>

[!code-csharp[MapValueToKey](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#MapValueToKey)]

<span data-ttu-id="595db-188">Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` , che trasforma le colonne di testo ( `Title` e `Description` ) in un vettore numerico per ogni oggetto chiamato `TitleFeaturized` e `DescriptionFeaturized` .</span><span class="sxs-lookup"><span data-stu-id="595db-188">Next, call `mlContext.Transforms.Text.FeaturizeText`, which transforms the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="595db-189">Aggiungere l'estrazione delle funzionalità per entrambe le colonne alla pipeline con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-189">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#FeaturizeText)]

<span data-ttu-id="595db-190">L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando il metodo [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A).</span><span class="sxs-lookup"><span data-stu-id="595db-190">The last step in data preparation combines all of the feature columns into the **Features** column using the [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) method.</span></span> <span data-ttu-id="595db-191">Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**.</span><span class="sxs-lookup"><span data-stu-id="595db-191">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="595db-192">Aggiungere questa trasformazione alla pipeline con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-192">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Concatenate)]

 <span data-ttu-id="595db-193">Aggiungere quindi <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> per memorizzare nella cache la vista dati e ottenere prestazioni migliori quando si esegue più volte l'iterazione dei dati usando la cache, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-193">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="595db-194">Usare AppendCacheCheckpoint per i set di dati di piccole e medie dimensioni per ridurre i tempi di training.</span><span class="sxs-lookup"><span data-stu-id="595db-194">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="595db-195">NON usarlo (rimuovere. AppendCacheCheckpoint()) durante la gestione di set di dati molto grandi.</span><span class="sxs-lookup"><span data-stu-id="595db-195">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="595db-196">Applicare return alla pipeline alla fine del metodo `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="595db-196">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnPipeline)]

<span data-ttu-id="595db-197">Questo passaggio gestisce la pre-elaborazione/estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="595db-197">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="595db-198">Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.</span><span class="sxs-lookup"><span data-stu-id="595db-198">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="595db-199">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="595db-199">Build and train the model</span></span>

<span data-ttu-id="595db-200">Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="595db-200">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="595db-201">Il metodo `BuildAndTrainModel` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="595db-201">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="595db-202">Crea la classe di algoritmo di training.</span><span class="sxs-lookup"><span data-stu-id="595db-202">Creates the training algorithm class.</span></span>
* <span data-ttu-id="595db-203">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="595db-203">Trains the model.</span></span>
* <span data-ttu-id="595db-204">Esegue la stima dell'area sulla base dei dati di training.</span><span class="sxs-lookup"><span data-stu-id="595db-204">Predicts area based on training data.</span></span>
* <span data-ttu-id="595db-205">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="595db-205">Returns the model.</span></span>

<span data-ttu-id="595db-206">Creare il metodo `BuildAndTrainModel` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-206">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

### <a name="about-the-classification-task"></a><span data-ttu-id="595db-207">Informazioni sull'attività di classificazione</span><span class="sxs-lookup"><span data-stu-id="595db-207">About the classification task</span></span>

<span data-ttu-id="595db-208">La classificazione è un'attività di apprendimento automatico che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati ed è spesso di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="595db-208">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data and is frequently one of the following types:</span></span>

* <span data-ttu-id="595db-209">Binarie: A o B.</span><span class="sxs-lookup"><span data-stu-id="595db-209">Binary: either A or B.</span></span>
* <span data-ttu-id="595db-210">Multiclasse: più categorie che possono essere stimate tramite un singolo modello.</span><span class="sxs-lookup"><span data-stu-id="595db-210">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="595db-211">Per questo tipo di problema, usare un algoritmo di Machine Learning di classificazione multiclasse, poiché la stima della categoria di problemi può essere una tra più categorie (multiclasse) anziché solo due categorie (binarie).</span><span class="sxs-lookup"><span data-stu-id="595db-211">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

<span data-ttu-id="595db-212">Aggiungere l'algoritmo di apprendimento automatico alle definizioni di trasformazione dei dati aggiungendo il codice seguente come prima riga di codice in `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="595db-212">Append the machine learning algorithm to the data transformation definitions by adding the following as the first line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddTrainer](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTrainer)]

<span data-ttu-id="595db-213">[SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) è l'algoritmo di training di classificazione multiclasse.</span><span class="sxs-lookup"><span data-stu-id="595db-213">The [SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) is your multiclass classification training algorithm.</span></span> <span data-ttu-id="595db-214">Viene aggiunto a `pipeline` e accetta gli elementi `Title` e `Description` (`Features`) con estrazione di funzionalità e i parametri di input `Label` per l'apprendimento dai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="595db-214">This is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="595db-215">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="595db-215">Train the model</span></span>

<span data-ttu-id="595db-216">Eseguire il fit del modello ai dati `splitTrainSet` e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="595db-216">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#TrainModel)]

<span data-ttu-id="595db-217">Il metodo `Fit()` esegue il training del modello trasformando il set di dati e applicando il training.</span><span class="sxs-lookup"><span data-stu-id="595db-217">The `Fit()`method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="595db-218">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di servizio che consente di passare e quindi effettuare una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="595db-218">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span> <span data-ttu-id="595db-219">Aggiungere il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="595db-219">Add this as the next line in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[CreatePredictionEngine1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="595db-220">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="595db-220">Predict with the trained model</span></span>

<span data-ttu-id="595db-221">Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="595db-221">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateTestIssue1)]

<span data-ttu-id="595db-222">Usare la funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) per eseguire una stima su una singola colonna di dati:</span><span class="sxs-lookup"><span data-stu-id="595db-222">Use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="595db-223">Uso del modello: risultati della stima</span><span class="sxs-lookup"><span data-stu-id="595db-223">Using the model: prediction results</span></span>

<span data-ttu-id="595db-224">Visualizzare `GitHubIssue` e la stima dell'etichetta `Area` corrispondente per condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="595db-224">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="595db-225">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-225">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="595db-226">Restituire il modello di cui è stato eseguito il training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="595db-226">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="595db-227">Restituire il modello alla fine del metodo `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="595db-227">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="595db-228">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="595db-228">Evaluate the model</span></span>

<span data-ttu-id="595db-229">Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida.</span><span class="sxs-lookup"><span data-stu-id="595db-229">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="595db-230">Nel metodo `Evaluate` viene passato il modello creato in `BuildAndTrainModel` per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="595db-230">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="595db-231">Creare il metodo `Evaluate` subito dopo `BuildAndTrainModel`, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-231">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(DataViewSchema trainingDataViewSchema)
{

}
```

<span data-ttu-id="595db-232">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="595db-232">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="595db-233">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="595db-233">Loads the test dataset.</span></span>
* <span data-ttu-id="595db-234">Crea l'analizzatore multiclasse.</span><span class="sxs-lookup"><span data-stu-id="595db-234">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="595db-235">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="595db-235">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="595db-236">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="595db-236">Displays the metrics.</span></span>

<span data-ttu-id="595db-237">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `BuildAndTrainModel`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-237">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallEvaluate)]

<span data-ttu-id="595db-238">Come in precedenza con il training set, caricare il set di dati di test aggiungendo il codice seguente al metodo `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="595db-238">As you did previously with the training dataset, load the test dataset by adding the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTestDataset)]

<span data-ttu-id="595db-239">Il metodo [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) calcola le metriche di qualità per il modello usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="595db-239">The [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) method computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="595db-240">Restituisce un oggetto <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> che contiene le metriche complessive calcolate dagli analizzatori della classificazione multiclasse.</span><span class="sxs-lookup"><span data-stu-id="595db-240">It returns a <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="595db-241">Per visualizzare la metrica per determinare la qualità del modello, è prima necessario ottenerla.</span><span class="sxs-lookup"><span data-stu-id="595db-241">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="595db-242">Osservare l'uso del metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) della variabile globale `_trainedModel` di apprendimento automatico (un oggetto [ITransformer](xref:Microsoft.ML.ITransformer)) per l'input di funzionalità e la generazione di stime.</span><span class="sxs-lookup"><span data-stu-id="595db-242">Notice the use of the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the machine learning `_trainedModel` global variable (an [ITransformer](xref:Microsoft.ML.ITransformer)) to input the features and return predictions.</span></span> <span data-ttu-id="595db-243">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="595db-243">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Evaluate)]

<span data-ttu-id="595db-244">Le metriche seguenti vengono valutate per la classificazione multiclasse:</span><span class="sxs-lookup"><span data-stu-id="595db-244">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="595db-245">MicroAccuracy (Accuratezza micro): ogni coppia campione-classe contribuisce nello stesso modo alla metrica di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="595db-245">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="595db-246">Si vuole che la micro precisione sia la più vicina possibile.</span><span class="sxs-lookup"><span data-stu-id="595db-246">You want Micro Accuracy to be as close to one as possible.</span></span>

* <span data-ttu-id="595db-247">MacroAccuracy (Accuratezza macro): ogni classe contribuisce nello stesso modo alla metrica di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="595db-247">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="595db-248">Alle classi di minoranza viene assegnato un peso uguale a quello delle classi più grandi.</span><span class="sxs-lookup"><span data-stu-id="595db-248">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="595db-249">Si vuole che l'accuratezza della macro sia il più vicino possibile.</span><span class="sxs-lookup"><span data-stu-id="595db-249">You want Macro Accuracy to be as close to one as possible.</span></span>

* <span data-ttu-id="595db-250">LogLoss (Perdita di log): vedere [Perdita di log](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="595db-250">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="595db-251">Il valore desiderato per LogLoss è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="595db-251">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="595db-252">Riduzione della perdita di log: intervalli da [-inf, 1,00], dove 1,00 è una stima perfetta e 0 indica stime significative.</span><span class="sxs-lookup"><span data-stu-id="595db-252">Log-loss reduction - Ranges from [-inf, 1.00], where 1.00 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="595db-253">Si vuole che la riduzione della perdita di log sia il più vicino possibile.</span><span class="sxs-lookup"><span data-stu-id="595db-253">You want Log-loss reduction to be as close to one as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="595db-254">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="595db-254">Displaying the metrics for model validation</span></span>

<span data-ttu-id="595db-255">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="595db-255">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayMetrics)]

### <a name="save-the-model-to-a-file"></a><span data-ttu-id="595db-256">Salvare il modello in un file</span><span class="sxs-lookup"><span data-stu-id="595db-256">Save the model to a file</span></span>

<span data-ttu-id="595db-257">Quando si è soddisfatti con il modello ottenuto, salvarlo in un file per poter effettuare stime in un secondo momento o in un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="595db-257">Once satisfied with your model, save it to a file to make predictions at a later time or in another application.</span></span> <span data-ttu-id="595db-258">Aggiungere il codice seguente al metodo `Evaluate` .</span><span class="sxs-lookup"><span data-stu-id="595db-258">Add the following code to the `Evaluate` method.</span></span>

[!code-csharp[SnippetCallSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetCallSaveModel)]

<span data-ttu-id="595db-259">Creare il metodo `SaveModelAsFile` sotto il metodo `Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="595db-259">Create the `SaveModelAsFile` method below your `Evaluate` method.</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext,DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

<span data-ttu-id="595db-260">Aggiungere il codice seguente al metodo `SaveModelAsFile`.</span><span class="sxs-lookup"><span data-stu-id="595db-260">Add the following code to your `SaveModelAsFile` method.</span></span> <span data-ttu-id="595db-261">Questo codice usa il [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) metodo per serializzare e archiviare il modello sottoposto a training come file zip.</span><span class="sxs-lookup"><span data-stu-id="595db-261">This code uses the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) method to serialize and store the trained model as a zip file.</span></span>

[!code-csharp[SnippetSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetSaveModel)]

## <a name="deploy-and-predict-with-a-model"></a><span data-ttu-id="595db-262">Eseguire distribuzione e stime con un modello</span><span class="sxs-lookup"><span data-stu-id="595db-262">Deploy and Predict with a model</span></span>

<span data-ttu-id="595db-263">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-263">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallPredictIssue)]

<span data-ttu-id="595db-264">Creare il metodo `PredictIssue`, subito dopo il metodo `Evaluate` e subito prima del metodo `SaveModelAsFile`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-264">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="595db-265">Il metodo `PredictIssue` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="595db-265">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="595db-266">Carica il modello salvato</span><span class="sxs-lookup"><span data-stu-id="595db-266">Loads the saved model</span></span>
* <span data-ttu-id="595db-267">Crea un singolo problema con dati di test.</span><span class="sxs-lookup"><span data-stu-id="595db-267">Creates a single issue of test data.</span></span>
* <span data-ttu-id="595db-268">Esegue la stima dell'Area in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="595db-268">Predicts Area based on test data.</span></span>
* <span data-ttu-id="595db-269">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="595db-269">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="595db-270">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="595db-270">Displays the predicted results.</span></span>

<span data-ttu-id="595db-271">Caricare il modello salvato nell'applicazione aggiungendo il codice seguente al metodo `PredictIssue`:</span><span class="sxs-lookup"><span data-stu-id="595db-271">Load the saved model into your application by adding the following code to the `PredictIssue` method:</span></span>

[!code-csharp[SnippetLoadModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetLoadModel)]

<span data-ttu-id="595db-272">Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="595db-272">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTestIssue)]

<span data-ttu-id="595db-273">Come in precedenza, creare un'istanza `PredictionEngine` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-273">As you did previously, create a `PredictionEngine` instance with the following code:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine)]

<span data-ttu-id="595db-274">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="595db-274">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="595db-275">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="595db-275">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="595db-276">È accettabile usare in ambienti a thread singolo o prototipi.</span><span class="sxs-lookup"><span data-stu-id="595db-276">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="595db-277">Per migliorare le prestazioni e thread safety negli ambienti di produzione, utilizzare il `PredictionEnginePool` servizio, che consente di creare un oggetto [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da utilizzare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="595db-277">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="595db-278">Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="595db-278">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="595db-279">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="595db-279">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="595db-280">Usare `PredictionEngine` per stimare l'etichetta di Area GitHub aggiungendo il codice seguente al metodo `PredictIssue` per la stima:</span><span class="sxs-lookup"><span data-stu-id="595db-280">Use the `PredictionEngine` to predict the Area GitHub label by adding the following code to the `PredictIssue` method for the prediction:</span></span>

[!code-csharp[PredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="595db-281">Uso del modello caricato per la stima</span><span class="sxs-lookup"><span data-stu-id="595db-281">Using the loaded model for prediction</span></span>

<span data-ttu-id="595db-282">Visualizzare `Area` per classificare il problema e agire su di esso di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="595db-282">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="595db-283">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="595db-283">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="595db-284">Risultati</span><span class="sxs-lookup"><span data-stu-id="595db-284">Results</span></span>

<span data-ttu-id="595db-285">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="595db-285">Your results should be similar to the following.</span></span> <span data-ttu-id="595db-286">Durante l'elaborazione della pipeline, vengono visualizzati messaggi.</span><span class="sxs-lookup"><span data-stu-id="595db-286">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="595db-287">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="595db-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="595db-288">Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="595db-288">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.738
*       MacroAccuracy:    0.668
*       LogLoss:          .919
*       LogLossReduction: .643
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="595db-289">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="595db-289">Congratulations!</span></span> <span data-ttu-id="595db-290">È stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima di un'etichetta Area per un problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="595db-290">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="595db-291">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="595db-291">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="595db-292">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="595db-292">Next steps</span></span>

<span data-ttu-id="595db-293">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="595db-293">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="595db-294">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="595db-294">Prepare your data</span></span>
> * <span data-ttu-id="595db-295">Trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="595db-295">Transform the data</span></span>
> * <span data-ttu-id="595db-296">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="595db-296">Train the model</span></span>
> * <span data-ttu-id="595db-297">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="595db-297">Evaluate the model</span></span>
> * <span data-ttu-id="595db-298">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="595db-298">Predict with the trained model</span></span>
> * <span data-ttu-id="595db-299">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="595db-299">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="595db-300">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="595db-300">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="595db-301">Previsione tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="595db-301">Taxi Fare Predictor</span></span>](predict-prices.md)
