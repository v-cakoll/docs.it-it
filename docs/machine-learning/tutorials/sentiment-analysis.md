---
title: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment
description: Informazioni su come usare ML.NET in uno scenario di classificazione binaria per comprendere come usare la stima del sentiment al fine di eseguire l'azione appropriata.
ms.date: 12/20/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: c6ef4da7f429b92591c90daa3fb06f367d8a578a
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2019
ms.locfileid: "54030164"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="12d9e-103">Esercitazione: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="12d9e-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="12d9e-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="12d9e-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="12d9e-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="12d9e-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="12d9e-106">Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore del sentiment tramite un'applicazione console .NET Core con C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="12d9e-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="12d9e-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="12d9e-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="12d9e-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="12d9e-108">Understand the problem</span></span>
> * <span data-ttu-id="12d9e-109">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="12d9e-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="12d9e-110">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="12d9e-110">Prepare your data</span></span>
> * <span data-ttu-id="12d9e-111">Creare la pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="12d9e-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="12d9e-112">Caricare un classificatore</span><span class="sxs-lookup"><span data-stu-id="12d9e-112">Load a classifier</span></span>
> * <span data-ttu-id="12d9e-113">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-113">Train the model</span></span>
> * <span data-ttu-id="12d9e-114">Valutare il modello con un set di dati diverso</span><span class="sxs-lookup"><span data-stu-id="12d9e-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="12d9e-115">Eseguire una stima relativa a una singola istanza del risultato dei dati di test con il modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-115">Predict a single instance of test data outcome with the model</span></span>
> * <span data-ttu-id="12d9e-116">Eseguire una stima dei risultati dei dati di test con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="12d9e-116">Predict the test data outcomes with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="12d9e-117">Panoramica dell'esempio di analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="12d9e-117">Sentiment analysis sample overview</span></span>

<span data-ttu-id="12d9e-118">L'esempio è un'app console che usa ML.NET per eseguire il training di un modello che classifica e stima il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="12d9e-118">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="12d9e-119">Valuta inoltre il modello con un secondo set di dati per l'analisi della qualità.</span><span class="sxs-lookup"><span data-stu-id="12d9e-119">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="12d9e-120">I set di dati per il sentiment provengono dal progetto WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="12d9e-120">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12d9e-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="12d9e-121">Prerequisites</span></span>

* <span data-ttu-id="12d9e-122">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="12d9e-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="12d9e-123">[File con valori delimitati da tabulazioni Wikipedia detox line data (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="12d9e-123">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="12d9e-124">[File con valori delimitati da tabulazioni Wikipedia detox line test (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="12d9e-124">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="12d9e-125">Flusso di lavoro di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="12d9e-125">Machine learning workflow</span></span>

<span data-ttu-id="12d9e-126">Questa esercitazione segue un flusso di lavoro di apprendimento automatico che consente l'esecuzione del processo in modo ordinato.</span><span class="sxs-lookup"><span data-stu-id="12d9e-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="12d9e-127">Le fasi del flusso di lavoro sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="12d9e-128">**Informazioni sul problema**</span><span class="sxs-lookup"><span data-stu-id="12d9e-128">**Understand the problem**</span></span>
2. <span data-ttu-id="12d9e-129">**Preparare i dati**</span><span class="sxs-lookup"><span data-stu-id="12d9e-129">**Prepare your data**</span></span>
   * <span data-ttu-id="12d9e-130">**Caricare i dati**</span><span class="sxs-lookup"><span data-stu-id="12d9e-130">**Load the data**</span></span>
   * <span data-ttu-id="12d9e-131">**Estrarre le caratteristiche (trasformare i dati)**</span><span class="sxs-lookup"><span data-stu-id="12d9e-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="12d9e-132">**Compilare ed eseguire il training**</span><span class="sxs-lookup"><span data-stu-id="12d9e-132">**Build and train**</span></span> 
   * <span data-ttu-id="12d9e-133">**Eseguire il training del modello**</span><span class="sxs-lookup"><span data-stu-id="12d9e-133">**Train the model**</span></span>
   * <span data-ttu-id="12d9e-134">**Valutazione del modello**</span><span class="sxs-lookup"><span data-stu-id="12d9e-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="12d9e-135">**Run**</span><span class="sxs-lookup"><span data-stu-id="12d9e-135">**Run**</span></span>
   * <span data-ttu-id="12d9e-136">**Utilizzare il modello**</span><span class="sxs-lookup"><span data-stu-id="12d9e-136">**Model consumption**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="12d9e-137">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="12d9e-137">Understand the problem</span></span>

<span data-ttu-id="12d9e-138">È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="12d9e-139">La suddivisione del problema consente di stimare e valutare i risultati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-139">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="12d9e-140">Il problema per questa esercitazione consiste nel comprendere il sentiment dei commenti in un sito Web per eseguire l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="12d9e-140">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="12d9e-141">È possibile suddividere il problema nel testo del sentiment e nel valore del sentiment per i dati con cui si vuole eseguire il training del modello e un valore del sentiment stimato che è possibile valutare e quindi usare a livello operativo.</span><span class="sxs-lookup"><span data-stu-id="12d9e-141">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="12d9e-142">Sarà quindi necessario **determinare** il sentiment, che consente di selezionare l'attività di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="12d9e-142">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="12d9e-143">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="12d9e-143">Select the appropriate machine learning task</span></span>

<span data-ttu-id="12d9e-144">Per questo problema, sono noti i fatti seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-144">With this problem, you know the following facts:</span></span>

<span data-ttu-id="12d9e-145">Dati di training: i commenti nel sito Web possono essere positivi (1) o negativi (0) (**sentiment**).</span><span class="sxs-lookup"><span data-stu-id="12d9e-145">Training data: website comments can be toxic (1) or not toxic (0) (**sentiment**).</span></span>
<span data-ttu-id="12d9e-146">Stimare il **sentiment** di un nuovo commento nel sito Web, positivo o negativo, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-146">Predict the **sentiment** of a new website comment, either toxic or not toxic, such as in the following examples:</span></span>

* <span data-ttu-id="12d9e-147">Per favore evita di aggiungere cose insensate a Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="12d9e-147">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="12d9e-148">È il migliore, e l'articolo dovrebbe indicarlo.</span><span class="sxs-lookup"><span data-stu-id="12d9e-148">He is the best, and the article should say that.</span></span>

<span data-ttu-id="12d9e-149">L'attività di apprendimento automatico tramite classificazione è la più adatta per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="12d9e-149">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="12d9e-150">Informazioni sull'attività di classificazione</span><span class="sxs-lookup"><span data-stu-id="12d9e-150">About the classification task</span></span>

<span data-ttu-id="12d9e-151">La classificazione è un'attività di apprendimento automatico che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-151">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="12d9e-152">È ad esempio possibile usare la classificazione per:</span><span class="sxs-lookup"><span data-stu-id="12d9e-152">For example, you can use classification to:</span></span>

* <span data-ttu-id="12d9e-153">Identificare il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="12d9e-153">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="12d9e-154">Classificare messaggi di posta elettronica come posta indesiderata o legittima.</span><span class="sxs-lookup"><span data-stu-id="12d9e-154">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="12d9e-155">Determinare se le analisi di laboratorio di un paziente indicano la presenza di cellule tumorali.</span><span class="sxs-lookup"><span data-stu-id="12d9e-155">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="12d9e-156">Suddividere in categorie i clienti in base alla relativa propensione a rispondere a una campagna di vendita.</span><span class="sxs-lookup"><span data-stu-id="12d9e-156">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="12d9e-157">Le attività di classificazione sono spesso di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-157">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="12d9e-158">Binarie: A o B.</span><span class="sxs-lookup"><span data-stu-id="12d9e-158">Binary: either A or B.</span></span>
* <span data-ttu-id="12d9e-159">Multiclasse: più categorie che possono essere stimate tramite un singolo modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-159">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="12d9e-160">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="12d9e-160">Create a console application</span></span>

1. <span data-ttu-id="12d9e-161">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="12d9e-161">Open Visual Studio 2017.</span></span> <span data-ttu-id="12d9e-162">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="12d9e-162">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="12d9e-163">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-163">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="12d9e-164">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-164">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="12d9e-165">Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-165">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="12d9e-166">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:</span><span class="sxs-lookup"><span data-stu-id="12d9e-166">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="12d9e-167">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-167">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="12d9e-168">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="12d9e-168">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="12d9e-169">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="12d9e-169">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="12d9e-170">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-170">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="12d9e-171">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-171">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="12d9e-172">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-172">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="12d9e-173">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="12d9e-173">Prepare your data</span></span>

1. <span data-ttu-id="12d9e-174">Scaricare i set di dati [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) e [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) e salvarli nella cartella *Data* creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="12d9e-174">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="12d9e-175">Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-175">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="12d9e-176">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-176">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="12d9e-177">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-177">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="12d9e-178">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="12d9e-178">Create classes and define paths</span></span>

<span data-ttu-id="12d9e-179">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="12d9e-179">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="12d9e-180">È necessario creare tre campi globali per i percorsi dei file scaricati di recente e una variabile globale per l'istanza di `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-180">You need to create three global fields to hold the paths to the recently downloaded files, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="12d9e-181">`_trainDataPath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-181">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="12d9e-182">`_testDataPath` contiene il percorso del set di dati usato per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-182">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="12d9e-183">`_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="12d9e-183">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="12d9e-184">`_textLoader` è l'istanza della classe <xref:Microsoft.ML.Runtime.Data.TextLoader> usata per caricare e trasformare i set di dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-184">`_textLoader` is the <xref:Microsoft.ML.Runtime.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="12d9e-185">Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi e la variabile `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-185">Add the following code to the line right above the `Main` method to specify those paths and the `_textLoader` variable:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

<span data-ttu-id="12d9e-186">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="12d9e-186">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="12d9e-187">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="12d9e-187">Add a new class to your project:</span></span>

1. <span data-ttu-id="12d9e-188">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-188">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="12d9e-189">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="12d9e-189">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="12d9e-190">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-190">Then, select the **Add** button.</span></span>

    <span data-ttu-id="12d9e-191">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="12d9e-191">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="12d9e-192">Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="12d9e-192">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="12d9e-193">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="12d9e-193">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="12d9e-194">`SentimentData` è la classe dataset di input e dispone di un valore `float` (`Sentiment`) per il sentiment positivo o negativo e una stringa per il commento (`SentimentText`).</span><span class="sxs-lookup"><span data-stu-id="12d9e-194">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="12d9e-195">A entrambi i campi sono associati attributi `Column`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-195">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="12d9e-196">Questo attributo descrive l'ordine di ogni campo nel file di dati e indica qual è il campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-196">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="12d9e-197">`SentimentPrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-197">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="12d9e-198">Dispone di un singolo valore booleano (`Sentiment`) e un attributo `ColumnName` `PredictedLabel`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-198">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="12d9e-199">`Label` viene usato per creare il modello ed eseguirne il training, nonché con un secondo set di dati per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-199">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="12d9e-200">`PredictedLabel` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="12d9e-200">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="12d9e-201">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-201">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="12d9e-202">Quando si crea un modello con ML.NET, si inizia creando un'istanza di `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-202">When building a model with ML.NET you start by creating an `MLContext`.</span></span> <span data-ttu-id="12d9e-203">A livello concettuale questa operazione è paragonabile all'uso di `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="12d9e-203">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="12d9e-204">L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="12d9e-204">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="12d9e-205">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="12d9e-205">Initialize variables in Main</span></span>

<span data-ttu-id="12d9e-206">Creare una variabile denominata `mlContext` e inizializzarla con una nuova istanza di `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-206">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="12d9e-207">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-207">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="12d9e-208">Successivamente, per configurare il caricamento dei dati, inizializzare la variabile globale `_textLoader` in modo da poterla riutilizzare.</span><span class="sxs-lookup"><span data-stu-id="12d9e-208">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span>  <span data-ttu-id="12d9e-209">Si noti che si sta usando un'istanza di `TextReader`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-209">Notice that you're using a `TextReader`.</span></span> <span data-ttu-id="12d9e-210">Quando si crea un'istanza di `TextLoader` con `TextReader`, si passa il contesto necessario e la classe <xref:Microsoft.ML.Runtime.Data.TextLoader.Arguments> che consente la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="12d9e-210">When you create a `TextLoader` using a `TextReader`, you pass in the context needed and the <xref:Microsoft.ML.Runtime.Data.TextLoader.Arguments> class which enables customization.</span></span>

 <span data-ttu-id="12d9e-211">Specificare lo schema di dati passando una matrice di oggetti <xref:Microsoft.ML.Runtime.Data.TextLoader.Column> al caricatore contenente tutti i nomi delle colonne e i relativi tipi.</span><span class="sxs-lookup"><span data-stu-id="12d9e-211">Specify the data schema by passing an array of <xref:Microsoft.ML.Runtime.Data.TextLoader.Column> objects to the loader containing all the column names and their types.</span></span> <span data-ttu-id="12d9e-212">Lo schema di dati è stato definito in precedenza quando si è creata la classe `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-212">You defined the data schema previously when you created our `SentimentData` class.</span></span> <span data-ttu-id="12d9e-213">Per lo schema, la prima colonna (Label) è un valore <xref:System.Boolean> (la stima) e la seconda colonna (SentimentText) è la caratteristica di tipo testo/stringa usata per la stima del sentiment.</span><span class="sxs-lookup"><span data-stu-id="12d9e-213">For our schema, the first column (Label) is a <xref:System.Boolean> (the prediction) and the second column (SentimentText) is the feature of type text/string used for predicting the sentiment.</span></span>
<span data-ttu-id="12d9e-214">La classe `TextReader` restituisce un'istanza di <xref:Microsoft.ML.Runtime.Data.TextLoader> completamente inizializzata.</span><span class="sxs-lookup"><span data-stu-id="12d9e-214">The `TextReader` class returns a fully initialized <xref:Microsoft.ML.Runtime.Data.TextLoader></span></span>  

<span data-ttu-id="12d9e-215">Per inizializzare la variabile globale `_textLoader` in modo da riutilizzarla per i set di dati necessari, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-215">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextReader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextReader")]

<span data-ttu-id="12d9e-216">Aggiungere il codice seguente al metodo `Main` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="12d9e-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

<span data-ttu-id="12d9e-217">Il metodo `Train` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-217">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="12d9e-218">Carica i dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-218">Loads the data.</span></span>
* <span data-ttu-id="12d9e-219">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-219">Extracts and transforms the data.</span></span>
* <span data-ttu-id="12d9e-220">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-220">Trains the model.</span></span>
* <span data-ttu-id="12d9e-221">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="12d9e-221">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="12d9e-222">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-222">Returns the model.</span></span>

<span data-ttu-id="12d9e-223">Creare il metodo `Train` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-223">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="12d9e-224">Si noti che vengono passati due parametri al metodo Train: `MLContext` per il contesto (`mlContext`) e <xref:System.String> per il percorso del set di dati (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="12d9e-224">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and a <xref:System.String> for the dataset path (`dataPath`).</span></span> <span data-ttu-id="12d9e-225">Si userà questo metodo più volte per il training e i test.</span><span class="sxs-lookup"><span data-stu-id="12d9e-225">You're going to use this method more than once for training and testing.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="12d9e-226">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="12d9e-226">Load the data</span></span>

<span data-ttu-id="12d9e-227">Si caricheranno i dati usando la variabile globale `_textLoader` con il parametro `dataPath`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-227">You'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="12d9e-228">Verrà restituita un'istanza di <xref:Microsoft.ML.Runtime.Data.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="12d9e-228">It returns a <xref:Microsoft.ML.Runtime.Data.IDataView>.</span></span> <span data-ttu-id="12d9e-229">Come input e output di `Transforms`, una `DataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-229">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="12d9e-230">In ML.NET i dati sono simili a una visualizzazione SQL.</span><span class="sxs-lookup"><span data-stu-id="12d9e-230">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="12d9e-231">Vengono valutati in modalità differita, sono schematizzati ed eterogenei.</span><span class="sxs-lookup"><span data-stu-id="12d9e-231">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="12d9e-232">L'oggetto è la prima parte della pipeline e carica i dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-232">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="12d9e-233">Per questa esercitazione, carica un set di dati con commenti e il sentiment positivo o negativo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="12d9e-233">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="12d9e-234">Queste informazioni vengono usate per creare il modello ed eseguirne il training.</span><span class="sxs-lookup"><span data-stu-id="12d9e-234">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="12d9e-235">Aggiungere il codice seguente come prima riga del metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-235">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="12d9e-236">Estrarre e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="12d9e-236">Extract and transform the data</span></span>

<span data-ttu-id="12d9e-237">La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="12d9e-237">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="12d9e-238">I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="12d9e-238">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="12d9e-239">L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.</span><span class="sxs-lookup"><span data-stu-id="12d9e-239">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="12d9e-240">Le pipeline di trasformazione di ML.NET compongono un set personalizzato di trasformazioni che vengono applicate ai dati prima di eseguire il training o i test.</span><span class="sxs-lookup"><span data-stu-id="12d9e-240">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="12d9e-241">Lo scopo principale delle trasformazioni è l'[estrazione delle caratteristiche](../resources/glossary.md#feature-engineering) dai dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-241">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="12d9e-242">Gli algoritmi di apprendimento automatico sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) in modo da trasformare successivamente i dati testuali in un formato riconoscibile da tali algoritmi.</span><span class="sxs-lookup"><span data-stu-id="12d9e-242">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="12d9e-243">Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="12d9e-243">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="12d9e-244">Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` che estrae le caratteristiche della colonna di testo (`SentimentText`) e le trasforma in un vettore numerico denominato `Features` che viene usato dall'algoritmo di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="12d9e-244">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="12d9e-245">Questa è una chiamata di wrapper che restituisce un oggetto <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601> che sarà effettivamente una pipeline.</span><span class="sxs-lookup"><span data-stu-id="12d9e-245">This is a wrapper call that returns an <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="12d9e-246">Assegnare un nome a questa `pipeline` poiché successivamente si aggiungerà l'algoritmo di training all'oggetto `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-246">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="12d9e-247">Aggiungere il codice seguente come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="12d9e-247">Add this as the next line of code:</span></span>

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

<span data-ttu-id="12d9e-248">Questo è il passaggio di pre-elaborazione/estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="12d9e-248">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="12d9e-249">Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.</span><span class="sxs-lookup"><span data-stu-id="12d9e-249">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="12d9e-250">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="12d9e-250">Choose a learning algorithm</span></span>

<span data-ttu-id="12d9e-251">Per aggiungere l'algoritmo di training, chiamare il metodo wrapper `mlContext.Transforms.Text.FeaturizeText` che restituisce un oggetto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>,</span><span class="sxs-lookup"><span data-stu-id="12d9e-251">To add the trainer, call the `mlContext.Transforms.Text.FeaturizeText` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="12d9e-252">un algoritmo di apprendimento basato su un albero delle decisioni che si userà in questa pipeline.</span><span class="sxs-lookup"><span data-stu-id="12d9e-252">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="12d9e-253">L'oggetto `FastTreeBinaryClassificationTrainer` viene aggiunto alla `pipeline` e accetta l'oggetto `SentimentText` (`Features`) da cui sono state estratte le caratteristiche e i parametri di input `Label` per l'apprendimento in base ai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="12d9e-253">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="12d9e-254">Aggiungere al metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-254">Add the following code to the `Train` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="12d9e-255">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-255">Train the model</span></span>

<span data-ttu-id="12d9e-256">Il training del modello, <xref:Microsoft.ML.Data.TransformerChain%601>, viene eseguito in base al set di dati caricato e trasformato.</span><span class="sxs-lookup"><span data-stu-id="12d9e-256">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="12d9e-257">Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-257">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="12d9e-258">Viene così restituito un modello da usare per le stime.</span><span class="sxs-lookup"><span data-stu-id="12d9e-258">This returns a model to use for predictions.</span></span> <span data-ttu-id="12d9e-259">`pipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata.</span><span class="sxs-lookup"><span data-stu-id="12d9e-259">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="12d9e-260">L'esperimento non viene eseguito finché questa operazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="12d9e-260">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="12d9e-261">Aggiungere al metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-261">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="12d9e-262">Salvare e restituire il modello sottoposto a training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="12d9e-262">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="12d9e-263">A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain%601> che può essere integrato nelle applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="12d9e-263">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="12d9e-264">Restituire il modello alla fine del metodo `Train`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-264">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="12d9e-265">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-265">Evaluate the model</span></span>

<span data-ttu-id="12d9e-266">Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida.</span><span class="sxs-lookup"><span data-stu-id="12d9e-266">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="12d9e-267">Nel metodo `Evaluate` viene passato il modello creato in `Train` per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="12d9e-267">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="12d9e-268">Creare il metodo `Evaluate` subito dopo `Train`, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-268">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="12d9e-269">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-269">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="12d9e-270">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="12d9e-270">Loads the test dataset.</span></span>
* <span data-ttu-id="12d9e-271">Crea l'analizzatore binario.</span><span class="sxs-lookup"><span data-stu-id="12d9e-271">Creates the binary evaluator.</span></span>
* <span data-ttu-id="12d9e-272">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="12d9e-272">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="12d9e-273">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="12d9e-273">Displays the metrics.</span></span>

<span data-ttu-id="12d9e-274">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-274">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

<span data-ttu-id="12d9e-275">Si caricherà il set di dati di test usando la variabile globale `_textLoader` inizializzata in precedenza con il campo globale `_testDataPath`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-275">You'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="12d9e-276">È possibile valutare il modello usando questo set di dati come controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="12d9e-276">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="12d9e-277">Aggiungere al metodo `Evaluate` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-277">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

<span data-ttu-id="12d9e-278">Si userà quindi il parametro `model` di apprendimento automatico (un oggetto Transformer) per l'input di caratteristiche e la generazione di stime.</span><span class="sxs-lookup"><span data-stu-id="12d9e-278">Next, you'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="12d9e-279">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="12d9e-279">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

<span data-ttu-id="12d9e-280">Il metodo `BinaryClassificationContext.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="12d9e-280">The `BinaryClassificationContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="12d9e-281">Restituisce un oggetto `BinaryClassificationEvaluator.CalibratedResult` che contiene le metriche complessive calcolate dagli analizzatori della classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="12d9e-281">It returns a `BinaryClassificationEvaluator.CalibratedResult` object contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="12d9e-282">Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche.</span><span class="sxs-lookup"><span data-stu-id="12d9e-282">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="12d9e-283">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="12d9e-283">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="12d9e-284">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-284">Displaying the metrics for model validation</span></span>

<span data-ttu-id="12d9e-285">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="12d9e-285">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

<span data-ttu-id="12d9e-286">Per salvare il modello in un file con estensione zip prima della restituzione, aggiungere il codice seguente per chiamare il metodo `SaveModelAsFile` come riga successiva in `TrainFinalModel`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-286">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `TrainFinalModel`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="12d9e-287">Salvare il modello come file con estensione zip</span><span class="sxs-lookup"><span data-stu-id="12d9e-287">Save the model as a.zip file</span></span>

<span data-ttu-id="12d9e-288">Creare il metodo `SaveModelAsFile` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-288">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="12d9e-289">Il metodo `SaveModelAsFile` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-289">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="12d9e-290">Salva il modello come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="12d9e-290">Saves the model as a .zip file.</span></span>

<span data-ttu-id="12d9e-291">A questo punto, creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="12d9e-291">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="12d9e-292">L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.Runtime.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="12d9e-292">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.Runtime.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="12d9e-293">Per salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-293">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="12d9e-294">Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="12d9e-294">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]

<span data-ttu-id="12d9e-295">È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-295">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="12d9e-296">Stimare il risultato dei dati di test con il modello e un singolo commento</span><span class="sxs-lookup"><span data-stu-id="12d9e-296">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="12d9e-297">Creare il metodo `Predict` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-297">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="12d9e-298">Il metodo `Predict` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-298">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="12d9e-299">Crea un singolo commento di dati di test.</span><span class="sxs-lookup"><span data-stu-id="12d9e-299">Creates a single comment of test data.</span></span>
* <span data-ttu-id="12d9e-300">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="12d9e-300">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="12d9e-301">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="12d9e-301">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="12d9e-302">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-302">Displays the predicted results.</span></span>

<span data-ttu-id="12d9e-303">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-303">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

<span data-ttu-id="12d9e-304">`model` è un oggetto `transformer` che opera su molte righe di dati, ma in un ambiente produzione è spesso necessario eseguire stime su singoli esempi.</span><span class="sxs-lookup"><span data-stu-id="12d9e-304">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="12d9e-305"><xref:Microsoft.ML.Runtime.Data.PredictionFunction%602> è un wrapper che viene restituito dal metodo `MakePredictionFunction`.</span><span class="sxs-lookup"><span data-stu-id="12d9e-305">The <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602> is a wrapper that is returned from the `MakePredictionFunction` method.</span></span> <span data-ttu-id="12d9e-306">A questo punto si aggiunge il codice seguente per creare l'istanza di PredictionFunction come prima riga nel metodo `Predict`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-306">Let's add the following code to create the PredictionFunction as the first line in the `Predict` Method:</span></span>

[!code-csharp[MakePredictionFunction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionFunction")]
  
<span data-ttu-id="12d9e-307">Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-307">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]


 <span data-ttu-id="12d9e-308">È possibile usare questo commento per eseguire una stima del sentiment positivo o negativo di una singola istanza dei dati relativi ai commenti.</span><span class="sxs-lookup"><span data-stu-id="12d9e-308">You can use that to predict the Toxic or Non Toxic sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="12d9e-309">Per ottenere una stima, usare <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602.Predict(%600)> sui dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-309">To get a prediction, use <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602.Predict(%600)> on the data.</span></span> <span data-ttu-id="12d9e-310">Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="12d9e-310">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="12d9e-311">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="12d9e-311">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="12d9e-312">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="12d9e-312">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="12d9e-313">Operazionalizzazione del modello: stima</span><span class="sxs-lookup"><span data-stu-id="12d9e-313">Model operationalization: prediction</span></span>

<span data-ttu-id="12d9e-314">Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="12d9e-314">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="12d9e-315">Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi.</span><span class="sxs-lookup"><span data-stu-id="12d9e-315">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="12d9e-316">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-316">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="predict-the-test-data-outcomes-with-the-saved-model"></a><span data-ttu-id="12d9e-317">Stimare i risultati dei dati di test con il modello salvato</span><span class="sxs-lookup"><span data-stu-id="12d9e-317">Predict the test data outcomes with the saved model</span></span>

<span data-ttu-id="12d9e-318">Creare il metodo `PredictWithModelLoadedFromFile` subito prima del metodo `SaveModelAsFile`, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-318">Create the `PredictWithModelLoadedFromFile` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

<span data-ttu-id="12d9e-319">Il metodo `PredictWithModelLoadedFromFile` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d9e-319">The `PredictWithModelLoadedFromFile` method executes the following tasks:</span></span>

* <span data-ttu-id="12d9e-320">Crea i dati di test in batch.</span><span class="sxs-lookup"><span data-stu-id="12d9e-320">Creates batch test data.</span></span>
* <span data-ttu-id="12d9e-321">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="12d9e-321">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="12d9e-322">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="12d9e-322">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="12d9e-323">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-323">Displays the predicted results.</span></span>

<span data-ttu-id="12d9e-324">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Predict`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-324">Add a call to the new method from the `Main` method, right under the `Predict` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

<span data-ttu-id="12d9e-325">Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `PredictWithModelLoadedFromFile`:</span><span class="sxs-lookup"><span data-stu-id="12d9e-325">Add some comments to test the trained model's predictions in the `PredictWithModelLoadedFromFile` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

<span data-ttu-id="12d9e-326">Caricare il modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-326">Load the model</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

<span data-ttu-id="12d9e-327">Dopo aver creato un modello, è possibile usarlo per stimare il sentiment positivo o negativo dei dati relativi ai commenti usando il metodo <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Runtime.Data.IDataView)>.</span><span class="sxs-lookup"><span data-stu-id="12d9e-327">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Runtime.Data.IDataView)> method.</span></span> <span data-ttu-id="12d9e-328">Per ottenere una stima, usare `Predict` sui nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="12d9e-328">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="12d9e-329">Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="12d9e-329">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="12d9e-330">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="12d9e-330">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="12d9e-331">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="12d9e-331">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="12d9e-332">Aggiungere il codice seguente al metodo `PredictWithModelLoadedFromFile` per le stime:</span><span class="sxs-lookup"><span data-stu-id="12d9e-332">Add the following code to the `PredictWithModelLoadedFromFile` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="12d9e-333">Operazionalizzazione del modello: stima</span><span class="sxs-lookup"><span data-stu-id="12d9e-333">Model operationalization: prediction</span></span>

<span data-ttu-id="12d9e-334">Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="12d9e-334">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="12d9e-335">Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi.</span><span class="sxs-lookup"><span data-stu-id="12d9e-335">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="12d9e-336">Creare un'intestazione per i risultati con il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-336">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

<span data-ttu-id="12d9e-337">Prima di visualizzare i risultati stimati, combinare il sentiment e la stima per visualizzare il commento originale con il sentiment stimato.</span><span class="sxs-lookup"><span data-stu-id="12d9e-337">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="12d9e-338">Il codice seguente usa il metodo <xref:System.Linq.Enumerable.Zip%2A> per eseguire tale operazione. Aggiungere pertanto il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="12d9e-338">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="12d9e-339">Ora che `SentimentText` e `Sentiment` sono stati combinati in una classe, è possibile visualizzare i risultati usando il metodo <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="12d9e-339">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

<span data-ttu-id="12d9e-340">Poiché i nomi degli elementi di tupla dedotti sono una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="12d9e-340">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="12d9e-341">A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-341">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="12d9e-342">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="12d9e-342">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="12d9e-343">Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="12d9e-343">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="12d9e-344">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="12d9e-344">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="12d9e-345">Risultati</span><span class="sxs-lookup"><span data-stu-id="12d9e-345">Results</span></span>

<span data-ttu-id="12d9e-346">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="12d9e-346">Your results should be similar to the following.</span></span> <span data-ttu-id="12d9e-347">Durante l'elaborazione della pipeline, vengono visualizzati messaggi.</span><span class="sxs-lookup"><span data-stu-id="12d9e-347">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="12d9e-348">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="12d9e-348">You may see warnings, or processing messages.</span></span> <span data-ttu-id="12d9e-349">Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="12d9e-349">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.0\Data\Model.zip

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: He is the best, and the article should say that. | Prediction: Not Toxic | Probability: 0.9924279

```

<span data-ttu-id="12d9e-350">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="12d9e-350">Congratulations!</span></span> <span data-ttu-id="12d9e-351">A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="12d9e-351">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="12d9e-352">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="12d9e-352">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="12d9e-353">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="12d9e-353">Next steps</span></span>

<span data-ttu-id="12d9e-354">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="12d9e-354">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="12d9e-355">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="12d9e-355">Understand the problem</span></span>
> * <span data-ttu-id="12d9e-356">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="12d9e-356">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="12d9e-357">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="12d9e-357">Prepare your data</span></span>
> * <span data-ttu-id="12d9e-358">Creare la pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="12d9e-358">Create the learning pipeline</span></span>
> * <span data-ttu-id="12d9e-359">Caricare un classificatore</span><span class="sxs-lookup"><span data-stu-id="12d9e-359">Load a classifier</span></span>
> * <span data-ttu-id="12d9e-360">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-360">Train the model</span></span>
> * <span data-ttu-id="12d9e-361">Valutare il modello con un set di dati diverso</span><span class="sxs-lookup"><span data-stu-id="12d9e-361">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="12d9e-362">Stimare i risultati dei dati di test con il modello</span><span class="sxs-lookup"><span data-stu-id="12d9e-362">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="12d9e-363">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="12d9e-363">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="12d9e-364">Previsione tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="12d9e-364">Taxi Fare Predictor</span></span>](taxi-fare.md)
