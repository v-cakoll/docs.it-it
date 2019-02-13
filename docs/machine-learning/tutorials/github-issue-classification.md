---
title: Usare ML.NET in uno scenario di classificazione multiclasse dei problemi in GitHub
description: Informazioni su come usare ML.NET in uno scenario di classificazione multiclasse per assegnare i problemi di GitHub a un'area specifica.
ms.date: 02/01/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 79c0ae1ba38b410c0709659a4e5ee1ac2308b983
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739423"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="2a491-103">Esercitazione: Usare ML.NET in uno scenario di classificazione multiclasse per classificare i problemi di GitHub</span><span class="sxs-lookup"><span data-stu-id="2a491-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="2a491-104">Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore di problemi di GitHub tramite un'applicazione console .NET Core con C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2a491-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="2a491-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="2a491-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2a491-106">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="2a491-106">Understand the problem</span></span>
> * <span data-ttu-id="2a491-107">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="2a491-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="2a491-108">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="2a491-108">Prepare your data</span></span>
> * <span data-ttu-id="2a491-109">Estrarre le funzionalità e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="2a491-109">Extract Features and transform the data</span></span>
> * <span data-ttu-id="2a491-110">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2a491-110">Train the model</span></span>
> * <span data-ttu-id="2a491-111">Valutare il modello con un set di dati diverso</span><span class="sxs-lookup"><span data-stu-id="2a491-111">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="2a491-112">Eseguire una stima relativa a una singola istanza del risultato dei dati di test con il modello di cui è stato eseguito il training</span><span class="sxs-lookup"><span data-stu-id="2a491-112">Predict a single instance of test data outcome with the trained model</span></span>
> * <span data-ttu-id="2a491-113">Eseguire una stima relativa a una singola istanza dei dati di test con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="2a491-113">Predict a single instance of test data with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="2a491-114">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="2a491-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="2a491-115">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2a491-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="2a491-116">Panoramica di esempio di problema GitHub</span><span class="sxs-lookup"><span data-stu-id="2a491-116">GitHub issue sample overview</span></span>

<span data-ttu-id="2a491-117">L'esempio è un'app console che usa ML.NET per il training di un modello che classifica e stima l'etichetta Area associata a un problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="2a491-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="2a491-118">Valuta inoltre il modello con un secondo set di dati per l'analisi della qualità.</span><span class="sxs-lookup"><span data-stu-id="2a491-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="2a491-119">I set di dati del problema derivano dal repository GitHub dotnet/corefx.</span><span class="sxs-lookup"><span data-stu-id="2a491-119">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="2a491-120">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="2a491-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a491-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2a491-121">Prerequisites</span></span>

* <span data-ttu-id="2a491-122">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="2a491-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="2a491-123">Il [file separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="2a491-123">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="2a491-124">Il [file di test separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="2a491-124">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="2a491-125">Flusso di lavoro di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="2a491-125">Machine learning workflow</span></span>

<span data-ttu-id="2a491-126">Questa esercitazione segue un flusso di lavoro di apprendimento automatico che consente l'esecuzione del processo in modo ordinato.</span><span class="sxs-lookup"><span data-stu-id="2a491-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="2a491-127">Le fasi del flusso di lavoro sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="2a491-128">**Informazioni sul problema**</span><span class="sxs-lookup"><span data-stu-id="2a491-128">**Understand the problem**</span></span>
2. <span data-ttu-id="2a491-129">**Preparare i dati**</span><span class="sxs-lookup"><span data-stu-id="2a491-129">**Prepare your data**</span></span>
   * <span data-ttu-id="2a491-130">**Caricare i dati**</span><span class="sxs-lookup"><span data-stu-id="2a491-130">**Load the data**</span></span>
   * <span data-ttu-id="2a491-131">**Estrarre le caratteristiche (trasformare i dati)**</span><span class="sxs-lookup"><span data-stu-id="2a491-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="2a491-132">**Compilare ed eseguire il training**</span><span class="sxs-lookup"><span data-stu-id="2a491-132">**Build and train**</span></span> 
   * <span data-ttu-id="2a491-133">**Eseguire il training del modello**</span><span class="sxs-lookup"><span data-stu-id="2a491-133">**Train the model**</span></span>
   * <span data-ttu-id="2a491-134">**Valutazione del modello**</span><span class="sxs-lookup"><span data-stu-id="2a491-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="2a491-135">**Run**</span><span class="sxs-lookup"><span data-stu-id="2a491-135">**Run**</span></span>
   * <span data-ttu-id="2a491-136">**Utilizzare il modello**</span><span class="sxs-lookup"><span data-stu-id="2a491-136">**Model consumption**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="2a491-137">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="2a491-137">Understand the problem</span></span>

<span data-ttu-id="2a491-138">È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="2a491-139">La suddivisione del problema consente di stimare e valutare i risultati.</span><span class="sxs-lookup"><span data-stu-id="2a491-139">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="2a491-140">L'oggetto della presente esercitazione è la definizione dell'area da cui provengono i problemi di GitHub in ingresso, per etichettarli correttamente ai fini dell'assegnazione della priorità e della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2a491-140">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="2a491-141">È possibile suddividere il problema nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-141">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="2a491-142">testo del titolo del problema</span><span class="sxs-lookup"><span data-stu-id="2a491-142">the issue title text</span></span>
* <span data-ttu-id="2a491-143">testo della descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="2a491-143">the issue description text</span></span>
* <span data-ttu-id="2a491-144">valore di area per i dati di training del modello</span><span class="sxs-lookup"><span data-stu-id="2a491-144">an area value for the model training data</span></span>
* <span data-ttu-id="2a491-145">valore di area stimato che è possibile valutare e quindi usare a livello operativo</span><span class="sxs-lookup"><span data-stu-id="2a491-145">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="2a491-146">È quindi necessario **determinare** l'area, che facilita la selezione dell'attività di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="2a491-146">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="2a491-147">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="2a491-147">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="2a491-148">Per questo problema, sono noti i fatti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-148">With this problem, you know the following facts:</span></span>

<span data-ttu-id="2a491-149">Dati di training:</span><span class="sxs-lookup"><span data-stu-id="2a491-149">Training data:</span></span>

<span data-ttu-id="2a491-150">I problemi di GitHub possono essere etichettati in aree diverse (**Area**), come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-150">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="2a491-151">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="2a491-151">area-System.Numerics</span></span>
* <span data-ttu-id="2a491-152">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="2a491-152">area-System.Xml</span></span>
* <span data-ttu-id="2a491-153">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="2a491-153">area-Infrastructure</span></span>
* <span data-ttu-id="2a491-154">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="2a491-154">area-System.Linq</span></span>
* <span data-ttu-id="2a491-155">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="2a491-155">area-System.IO</span></span>

<span data-ttu-id="2a491-156">È possibile eseguire la stima del valore **Area** di un nuovo problema in GitHub, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-156">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="2a491-157">Contract.Assert rispetto a Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="2a491-157">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="2a491-158">Rendere i campi di sola lettura in System.Xml</span><span class="sxs-lookup"><span data-stu-id="2a491-158">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="2a491-159">L'algoritmo di Machine Learning di classificazione è il più adatto per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="2a491-159">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="2a491-160">Informazioni sull'algoritmo di Machine Learning di classificazione</span><span class="sxs-lookup"><span data-stu-id="2a491-160">About the classification learning algorithm</span></span>

<span data-ttu-id="2a491-161">La classificazione è un algoritmo di Machine Learning che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-161">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="2a491-162">È ad esempio possibile usare la classificazione per:</span><span class="sxs-lookup"><span data-stu-id="2a491-162">For example, you can use classification to:</span></span>

* <span data-ttu-id="2a491-163">Identificare il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="2a491-163">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="2a491-164">Classificare messaggi di posta elettronica come posta indesiderata o legittima.</span><span class="sxs-lookup"><span data-stu-id="2a491-164">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="2a491-165">Determinare se le analisi di laboratorio di un paziente indicano la presenza di cellule tumorali.</span><span class="sxs-lookup"><span data-stu-id="2a491-165">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="2a491-166">Suddividere in categorie i clienti in base alla relativa propensione a rispondere a una campagna di vendita.</span><span class="sxs-lookup"><span data-stu-id="2a491-166">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="2a491-167">I casi d'uso dell'algoritmo di Machine Learning di classificazione rientrano in genere in uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-167">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="2a491-168">Binarie: A o B.</span><span class="sxs-lookup"><span data-stu-id="2a491-168">Binary: either A or B.</span></span>
* <span data-ttu-id="2a491-169">Multiclasse: più categorie che possono essere stimate tramite un singolo modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-169">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="2a491-170">Per questo tipo di problema, usare un algoritmo di Machine Learning di classificazione multiclasse, poiché la stima della categoria di problemi può essere una tra più categorie (multiclasse) anziché solo due categorie (binarie).</span><span class="sxs-lookup"><span data-stu-id="2a491-170">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="2a491-171">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="2a491-171">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="2a491-172">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="2a491-172">Create a project</span></span>

1. <span data-ttu-id="2a491-173">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2a491-173">Open Visual Studio 2017.</span></span> <span data-ttu-id="2a491-174">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="2a491-174">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="2a491-175">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="2a491-175">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="2a491-176">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="2a491-176">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="2a491-177">Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a491-177">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="2a491-178">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:</span><span class="sxs-lookup"><span data-stu-id="2a491-178">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="2a491-179">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="2a491-179">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="2a491-180">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="2a491-180">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="2a491-181">Creare una directory denominata *Models* nel progetto per salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="2a491-181">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="2a491-182">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="2a491-182">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="2a491-183">Digitare "Models" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="2a491-183">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="2a491-184">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="2a491-184">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="2a491-185">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2a491-185">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2a491-186">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="2a491-186">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="2a491-187">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="2a491-187">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="2a491-188">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="2a491-188">Prepare your data</span></span>

1. <span data-ttu-id="2a491-189">Scaricare i set di dati [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) e salvarli nella cartella *Data* creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2a491-189">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="2a491-190">Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-190">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="2a491-191">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2a491-191">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="2a491-192">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="2a491-192">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="2a491-193">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="2a491-193">Create classes and define paths</span></span>

<span data-ttu-id="2a491-194">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="2a491-194">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="2a491-195">Creare tre campi globali per i percorsi dei file scaricati di recente e variabili globali per `MLContext`,`DataView`, `PredictionEngine` e `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="2a491-195">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="2a491-196">`_trainDataPath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-196">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="2a491-197">`_testDataPath` contiene il percorso del set di dati usato per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-197">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="2a491-198">`_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="2a491-198">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="2a491-199">`_mlContext` è l'elemento <xref:Microsoft.ML.MLContext> che specifica il contesto di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2a491-199">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="2a491-200">`_trainingDataView` è l'elemento <xref:Microsoft.ML.Data.IDataView> usato per elaborare il set di dati di training.</span><span class="sxs-lookup"><span data-stu-id="2a491-200">`_trainingDataView` is the <xref:Microsoft.ML.Data.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="2a491-201">`_predEngine` è l'elemento <xref:Microsoft.ML.PredictionEngine%602> usato per le stime singole.</span><span class="sxs-lookup"><span data-stu-id="2a491-201">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="2a491-202">`_reader` è l'istanza della classe <xref:Microsoft.ML.Data.TextLoader> usata per caricare e trasformare i set di dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-202">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="2a491-203">Aggiungere il codice seguente nella riga subito sopra il metodo `Main` per specificare questi percorsi e le altre variabili:</span><span class="sxs-lookup"><span data-stu-id="2a491-203">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="2a491-204">Creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="2a491-204">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="2a491-205">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="2a491-205">Add a new class to your project:</span></span>

1. <span data-ttu-id="2a491-206">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2a491-206">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="2a491-207">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** impostando *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="2a491-207">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="2a491-208">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2a491-208">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2a491-209">Il file *GitHubIssueData.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="2a491-209">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="2a491-210">Aggiungere l'istruzione `using` seguente all'inizio del file *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2a491-210">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="2a491-211">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `GitHubIssue` e `IssuePrediction`, al file *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2a491-211">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="2a491-212">`GitHubIssue` è la classe del set di dati input e ha i seguenti campi <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="2a491-212">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="2a491-213">`ID` contiene un valore per l'ID del problema GitHub</span><span class="sxs-lookup"><span data-stu-id="2a491-213">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="2a491-214">`Area` contiene un valore per l'etichetta `Area`</span><span class="sxs-lookup"><span data-stu-id="2a491-214">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="2a491-215">`Title` contiene il titolo del problema GitHub</span><span class="sxs-lookup"><span data-stu-id="2a491-215">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="2a491-216">`Description` contiene la descrizione del problema GitHub</span><span class="sxs-lookup"><span data-stu-id="2a491-216">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="2a491-217">`IssuePrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-217">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="2a491-218">Dispone di un `string` singolo (`Area`) e di un attributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="2a491-218">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="2a491-219">`Label` viene usato per creare il modello ed eseguirne il training, nonché con un secondo set di dati per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-219">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="2a491-220">`PredictedLabel` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="2a491-220">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="2a491-221">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-221">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="2a491-222">Quando si crea un modello con ML.NET, si inizia creando un <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="2a491-222">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="2a491-223">A livello concettuale `MLContext` è paragonabile all'uso di `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2a491-223">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="2a491-224">L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="2a491-224">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="2a491-225">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="2a491-225">Initialize variables in Main</span></span>

<span data-ttu-id="2a491-226">Inizializzare la variabile globale `_mlContext` con una nuova istanza di `MLContext` con un valore di inizializzazione casuale (`seed: 0`) per risultati ripetibili/deterministici in più training.</span><span class="sxs-lookup"><span data-stu-id="2a491-226">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="2a491-227">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="2a491-227">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="2a491-228">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="2a491-228">Load the data</span></span>

<span data-ttu-id="2a491-229">Quindi inizializzare la variabile globale `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> e caricare i dati con il parametro `_trainDataPath`.</span><span class="sxs-lookup"><span data-stu-id="2a491-229">Next, initialize the `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="2a491-230">Come input e output di [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), `DataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="2a491-230">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="2a491-231">In ML.NET i dati sono simili a una `SQL view`.</span><span class="sxs-lookup"><span data-stu-id="2a491-231">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="2a491-232">Vengono valutati in modalità differita, sono schematizzati ed eterogenei.</span><span class="sxs-lookup"><span data-stu-id="2a491-232">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="2a491-233">L'oggetto è la prima parte della pipeline e carica i dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-233">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="2a491-234">Per questa esercitazione carica un set di dati con titoli e descrizioni di problemi e con l'etichetta GitHub dell'area corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2a491-234">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="2a491-235">L'elemento `DataView` viene usato per creare il modello ed eseguirne il training.</span><span class="sxs-lookup"><span data-stu-id="2a491-235">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="2a491-236">Poiché il tipo di modello di dati `GitHubIssue` creato in precedenza corrisponde allo schema del set di dati, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati in un'unica riga di codice.</span><span class="sxs-lookup"><span data-stu-id="2a491-236">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="2a491-237">La prima parte della riga (`CreateTextReader<GitHubIssue>(hasHeader: true)`) crea un <xref:Microsoft.ML.Data.TextLoader> tramite inferenza dello schema del set di dati dal tipo modello di dati `GitHubIssue` e usando l'intestazione del set di dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-237">The first part of the line (`CreateTextReader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferring the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="2a491-238">Lo schema di dati è stato definito in precedenza quando è stata creata la classe `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="2a491-238">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="2a491-239">Per lo schema:</span><span class="sxs-lookup"><span data-stu-id="2a491-239">For your schema:</span></span>

* <span data-ttu-id="2a491-240">La prima colonna `ID` (ID problema di GitHub)</span><span class="sxs-lookup"><span data-stu-id="2a491-240">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="2a491-241">La seconda colonna `Area` (stima per il training)</span><span class="sxs-lookup"><span data-stu-id="2a491-241">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="2a491-242">La terza colonna `Title` (titolo del problema GitHub) è la prima [funzionalità](../resources/glossary.md##feature) usata per la stima di `Area`</span><span class="sxs-lookup"><span data-stu-id="2a491-242">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="2a491-243">La quarta colonna `Description` è la seconda funzionalità usata per la stima di `Area`</span><span class="sxs-lookup"><span data-stu-id="2a491-243">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="2a491-244">La seconda parte della riga (`.Read(_trainDataPath)`) usa il metodo <xref:Microsoft.ML.Data.TextLoader.Read%2A> per caricare il file di testo di training usando `_trainDataPath` nella variabile globale `IDataView` (`_trainingDataView`).</span><span class="sxs-lookup"><span data-stu-id="2a491-244">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="2a491-245">Per inizializzare e caricare la variabile globale `_trainingDataView` in modo da riusarla per la pipeline, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="2a491-245">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="2a491-246">Aggiungere il codice seguente al metodo `Main` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="2a491-246">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="2a491-247">Il metodo `ProcessData` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-247">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="2a491-248">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-248">Extracts and transforms the data.</span></span>
* <span data-ttu-id="2a491-249">Restituisce la pipeline di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2a491-249">Returns the processing pipeline.</span></span>

<span data-ttu-id="2a491-250">Creare il metodo `ProcessData` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-250">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="2a491-251">Estrarre le funzionalità e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="2a491-251">Extract Features and transform the data</span></span>

<span data-ttu-id="2a491-252">La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="2a491-252">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="2a491-253">I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="2a491-253">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="2a491-254">L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.</span><span class="sxs-lookup"><span data-stu-id="2a491-254">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="2a491-255">Le pipeline di trasformazione di ML.NET compongono un `transforms`set personalizzato che viene applicato ai dati prima di eseguire il training o i test.</span><span class="sxs-lookup"><span data-stu-id="2a491-255">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="2a491-256">Lo scopo principale delle trasformazioni è l'[estrazione delle caratteristiche](../resources/glossary.md#feature-engineering) dai dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-256">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="2a491-257">Gli algoritmi di apprendimento automatico sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) in modo da trasformare successivamente i dati testuali in un formato riconoscibile da tali algoritmi.</span><span class="sxs-lookup"><span data-stu-id="2a491-257">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="2a491-258">Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="2a491-258">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="2a491-259">Nei passaggi successivi si fa riferimento alle colonne in base ai nomi definiti nella classe `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="2a491-259">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="2a491-260">Quando vengono eseguiti il training e la valutazione del modello, i valori nella colonna **Label** vengono considerati per impostazione predefinita come valori corretti da stimare.</span><span class="sxs-lookup"><span data-stu-id="2a491-260">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="2a491-261">Dato che si vuole stimare l'etichetta GitHub Area per un `GitHubIssue`, copiare la colonna `Area` nella colonna **Label**.</span><span class="sxs-lookup"><span data-stu-id="2a491-261">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="2a491-262">A tale scopo usare `MLContext.Transforms.Conversion.MapValueToKey`, che è un wrapper per la classe di trasformazione <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a491-262">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="2a491-263">`MapValueToKey` restituisce un oggetto <xref:Microsoft.ML.Data.EstimatorChain%601> che sarà effettivamente una pipeline.</span><span class="sxs-lookup"><span data-stu-id="2a491-263">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="2a491-264">Assegnare un nome a questa `pipeline` poiché successivamente si aggiungerà l'algoritmo di training all'oggetto `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="2a491-264">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="2a491-265">Aggiungere la riga di codice successiva:</span><span class="sxs-lookup"><span data-stu-id="2a491-265">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="2a491-266">L'estrazione delle funzionalità assegna valori chiave numerici diversi ai diversi valori in ogni colonna ed è usata dall'algoritmo di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="2a491-266">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="2a491-267">Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` che trasforma le colonne di testo (`Title` e `Description`) in un vettore numerico per ogni `TitleFeaturized` e `DescriptionFeaturized` di cui è stata eseguita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a491-267">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="2a491-268">Aggiungere l'estrazione delle funzionalità per entrambe le colonne alla pipeline con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-268">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

<span data-ttu-id="2a491-269">L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione `Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="2a491-269">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="2a491-270">Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**.</span><span class="sxs-lookup"><span data-stu-id="2a491-270">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="2a491-271">Aggiungere questa trasformazione alla pipeline con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-271">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="2a491-272">Aggiungere quindi <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> per memorizzare nella cache la vista dati e ottenere prestazioni migliori quando si esegue più volte l'iterazione dei dati usando la cache, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-272">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

<span data-ttu-id="2a491-273">Applicare return alla pipeline alla fine del metodo `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="2a491-273">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="2a491-274">Questo passaggio gestisce la pre-elaborazione/estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a491-274">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="2a491-275">Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-275">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="2a491-276">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2a491-276">Build and train the model</span></span>

<span data-ttu-id="2a491-277">Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="2a491-277">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="2a491-278">Il metodo `BuildAndTrainModel` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-278">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="2a491-279">Crea la classe di algoritmo di training.</span><span class="sxs-lookup"><span data-stu-id="2a491-279">Creates the training algorithm class.</span></span>
* <span data-ttu-id="2a491-280">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-280">Trains the model.</span></span>
* <span data-ttu-id="2a491-281">Esegue la stima dell'area sulla base dei dati di training.</span><span class="sxs-lookup"><span data-stu-id="2a491-281">Predicts area based on training data.</span></span>
* <span data-ttu-id="2a491-282">Salva il modello in un file `.zip`.</span><span class="sxs-lookup"><span data-stu-id="2a491-282">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="2a491-283">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="2a491-283">Returns the model.</span></span>

<span data-ttu-id="2a491-284">Creare il metodo `BuildAndTrainModel` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-284">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<KeyToValueMappingTransformer> BuildAndTrainModel(IDataView trainingDataView, EstimatorChain<ITransformer> pipeline)
{

}
```

<span data-ttu-id="2a491-285">Si noti che nel metodo BuildAndTrainModel vengono passati due parametri, un `IDataView` per il set di dati di training (`trainingDataView`) e un <xref:Microsoft.ML.Data.EstimatorChain%601> per la pipeline di elaborazione creata in ProcessData (`pipeline`).</span><span class="sxs-lookup"><span data-stu-id="2a491-285">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="2a491-286">Aggiungere il codice seguente come prima riga del metodo `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="2a491-286">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="2a491-287">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="2a491-287">Choose a learning algorithm</span></span>

<span data-ttu-id="2a491-288">Per aggiungere l'algoritmo di Machine Learning, usare l'oggetto <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>.</span><span class="sxs-lookup"><span data-stu-id="2a491-288">To add the learning algorithm, use the <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="2a491-289">L'oggetto `SdcaMultiClassTrainer` viene aggiunto a `pipeline` e accetta gli elementi `Title` e `Description` (`Features`) con estrazione di funzionalità e i parametri di input `Label` per l'apprendimento dai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="2a491-289">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="2a491-290">Aggiungere al metodo `BuildAndTrainModel` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-290">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[SdcaMultiClassTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SdcaMultiClassTrainer)]

<span data-ttu-id="2a491-291">Dopo aver creato l'algoritmo di Machine Learning, aggiungerlo a `pipeline`.</span><span class="sxs-lookup"><span data-stu-id="2a491-291">Now that you've created a learning algorithm, append it to the `pipeline`.</span></span> <span data-ttu-id="2a491-292">È anche necessario eseguire il mapping dell'etichetta al valore per restituirlo allo stato leggibile originale.</span><span class="sxs-lookup"><span data-stu-id="2a491-292">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="2a491-293">Eseguire entrambe le operazioni con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-293">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="2a491-294">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2a491-294">Train the model</span></span>

<span data-ttu-id="2a491-295">Il training del modello, <xref:Microsoft.ML.Data.TransformerChain%601>, viene eseguito in base al set di dati caricato e trasformato.</span><span class="sxs-lookup"><span data-stu-id="2a491-295">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="2a491-296">Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati.</span><span class="sxs-lookup"><span data-stu-id="2a491-296">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="2a491-297">Questo metodo restituisce un modello da usare per le stime.</span><span class="sxs-lookup"><span data-stu-id="2a491-297">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="2a491-298">`trainingPipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata.</span><span class="sxs-lookup"><span data-stu-id="2a491-298">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="2a491-299">L'esperimento non viene eseguito finché non viene eseguito il metodo `.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="2a491-299">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="2a491-300">Aggiungere al metodo `BuildAndTrainModel` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-300">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="2a491-301">Mentre `model` è un `transformer` che opera su numerose righe di dati, la necessità di stime su singoli esempi è uno scenario di produzione comune.</span><span class="sxs-lookup"><span data-stu-id="2a491-301">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="2a491-302"><xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="2a491-302">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="2a491-303">A questo punto si aggiunge il codice seguente per creare `PredictionEngine` come riga successiva nel metodo `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="2a491-303">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

<span data-ttu-id="2a491-304">Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="2a491-304">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="2a491-305">È possibile usare quanto sopra per eseguire la stima dell'etichetta `Area` di una singola istanza dei dati del problema.</span><span class="sxs-lookup"><span data-stu-id="2a491-305">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="2a491-306">Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-306">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="2a491-307">I dati di input sono una stringa e il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a491-307">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="2a491-308">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="2a491-308">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="2a491-309">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="2a491-309">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction"></a><span data-ttu-id="2a491-310">Uso del modello: stima</span><span class="sxs-lookup"><span data-stu-id="2a491-310">Using the model: prediction</span></span>

<span data-ttu-id="2a491-311">Visualizzare `GitHubIssue` e la stima dell'etichetta `Area` corrispondente per condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="2a491-311">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="2a491-312">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-312">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="2a491-313">Restituire il modello di cui è stato eseguito il training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="2a491-313">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="2a491-314">Restituire il modello alla fine del metodo `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="2a491-314">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="2a491-315">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="2a491-315">Evaluate the model</span></span>

<span data-ttu-id="2a491-316">Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida.</span><span class="sxs-lookup"><span data-stu-id="2a491-316">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="2a491-317">Nel metodo `Evaluate` viene passato il modello creato in `BuildAndTrainModel` per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="2a491-317">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="2a491-318">Creare il metodo `Evaluate` subito dopo `BuildAndTrainModel`, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-318">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="2a491-319">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-319">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="2a491-320">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="2a491-320">Loads the test dataset.</span></span>
* <span data-ttu-id="2a491-321">Crea l'analizzatore multiclasse.</span><span class="sxs-lookup"><span data-stu-id="2a491-321">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="2a491-322">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="2a491-322">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="2a491-323">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="2a491-323">Displays the metrics.</span></span>

<span data-ttu-id="2a491-324">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `BuildAndTrainModel`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-324">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="2a491-325">Come in precedenza con il set di dati di training, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati di test in una sola riga di codice.</span><span class="sxs-lookup"><span data-stu-id="2a491-325">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="2a491-326">È possibile valutare il modello usando questo set di dati come controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="2a491-326">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="2a491-327">Aggiungere al metodo `Evaluate` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-327">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="2a491-328">`MulticlassClassificationContext.Evaluate` è un wrapper del metodo <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> che calcola le metriche di qualità per il modello usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="2a491-328">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="2a491-329">Restituisce un oggetto <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> che contiene le metriche complessive calcolate dagli analizzatori della classificazione multiclasse.</span><span class="sxs-lookup"><span data-stu-id="2a491-329">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="2a491-330">Per visualizzare la metrica per determinare la qualità del modello, è prima necessario ottenerla.</span><span class="sxs-lookup"><span data-stu-id="2a491-330">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="2a491-331">Osservare l'uso del metodo `Transform` della variabile globale di apprendimento automatico `_trainedModel` (un oggetto Transformer) per l'input di funzionalità e la generazione di stime.</span><span class="sxs-lookup"><span data-stu-id="2a491-331">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="2a491-332">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="2a491-332">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="2a491-333">Le metriche seguenti vengono valutate per la classificazione multiclasse:</span><span class="sxs-lookup"><span data-stu-id="2a491-333">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="2a491-334">MicroAccuracy (Accuratezza micro): ogni coppia campione-classe contribuisce nello stesso modo alla metrica di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="2a491-334">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="2a491-335">Il valore desiderato per MicroAccuracy è il valore più prossimo a 1.</span><span class="sxs-lookup"><span data-stu-id="2a491-335">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="2a491-336">MacroAccuracy (Accuratezza macro): ogni classe contribuisce nello stesso modo alla metrica di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="2a491-336">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="2a491-337">Alle classi di minoranza viene assegnato un peso uguale a quello delle classi più grandi.</span><span class="sxs-lookup"><span data-stu-id="2a491-337">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="2a491-338">Il valore desiderato per MacroAccuracy è il valore più prossimo a 1.</span><span class="sxs-lookup"><span data-stu-id="2a491-338">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="2a491-339">LogLoss (Perdita di log): vedere [Perdita di log](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="2a491-339">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="2a491-340">Il valore desiderato per LogLoss è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="2a491-340">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="2a491-341">LogLossReduction (Riduzione della perdita di log): è compreso nell'intervallo [-inf, 100], dove 100 corrisponde a stime perfette e 0 indica stime medie.</span><span class="sxs-lookup"><span data-stu-id="2a491-341">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="2a491-342">Il valore desiderato per LogLossReduction è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="2a491-342">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="2a491-343">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="2a491-343">Displaying the metrics for model validation</span></span>

<span data-ttu-id="2a491-344">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="2a491-344">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="2a491-345">Salvare il modello di cui è stato eseguito il training e valutato</span><span class="sxs-lookup"><span data-stu-id="2a491-345">Save the trained and evaluated model</span></span>

<span data-ttu-id="2a491-346">A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain%601> che può essere integrato nelle applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="2a491-346">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="2a491-347">Per salvare il modello sottoposto a training in un file con estensione zip, aggiungere il codice seguente per chiamare il metodo `SaveModelAsFile` come riga successiva in `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="2a491-347">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="2a491-348">Salvare il modello come file con estensione zip</span><span class="sxs-lookup"><span data-stu-id="2a491-348">Save the model as a .zip file</span></span>

<span data-ttu-id="2a491-349">Creare il metodo `SaveModelAsFile` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-349">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="2a491-350">Il metodo `SaveModelAsFile` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-350">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="2a491-351">Salva il modello come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="2a491-351">Saves the model as a .zip file.</span></span>

<span data-ttu-id="2a491-352">A questo punto, creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2a491-352">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="2a491-353">L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="2a491-353">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="2a491-354">Per salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="2a491-354">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="2a491-355">Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="2a491-355">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="2a491-356">È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-356">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="2a491-357">Stimare il risultato dei dati di test con il modello salvato</span><span class="sxs-lookup"><span data-stu-id="2a491-357">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="2a491-358">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-358">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="2a491-359">Creare il metodo `PredictIssue`, subito dopo il metodo `Evaluate` e subito prima del metodo `SaveModelAsFile`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-359">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="2a491-360">Il metodo `PredictIssue` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a491-360">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="2a491-361">Crea un singolo problema con dati di test.</span><span class="sxs-lookup"><span data-stu-id="2a491-361">Creates a single issue of test data.</span></span>
* <span data-ttu-id="2a491-362">Esegue la stima dell'Area in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="2a491-362">Predicts Area based on test data.</span></span>
* <span data-ttu-id="2a491-363">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="2a491-363">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="2a491-364">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="2a491-364">Displays the predicted results.</span></span>

<span data-ttu-id="2a491-365">In primo luogo caricare il modello salvato in precedenza con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-365">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="2a491-366">Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="2a491-366">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="2a491-367">Ora che è presente un modello, è possibile usarlo per stimare l'etichetta GitHub Area di una singola istanza dei dati del problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="2a491-367">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="2a491-368">Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati.</span><span class="sxs-lookup"><span data-stu-id="2a491-368">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="2a491-369">I dati di input sono una stringa e il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a491-369">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="2a491-370">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="2a491-370">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="2a491-371">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="2a491-371">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="2a491-372">Aggiungere il codice seguente al metodo `PredictIssue` per le stime:</span><span class="sxs-lookup"><span data-stu-id="2a491-372">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="2a491-373">Uso del modello caricato per la stima</span><span class="sxs-lookup"><span data-stu-id="2a491-373">Using the loaded model for prediction</span></span>

<span data-ttu-id="2a491-374">Visualizzare `Area` per classificare il problema e agire su di esso di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="2a491-374">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="2a491-375">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="2a491-375">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="2a491-376">Risultati</span><span class="sxs-lookup"><span data-stu-id="2a491-376">Results</span></span>

<span data-ttu-id="2a491-377">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2a491-377">Your results should be similar to the following.</span></span> <span data-ttu-id="2a491-378">Durante l'elaborazione della pipeline, vengono visualizzati messaggi.</span><span class="sxs-lookup"><span data-stu-id="2a491-378">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="2a491-379">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2a491-379">You may see warnings, or processing messages.</span></span> <span data-ttu-id="2a491-380">Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="2a491-380">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="2a491-381">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="2a491-381">Congratulations!</span></span> <span data-ttu-id="2a491-382">È stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima di un'etichetta Area per un problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="2a491-382">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="2a491-383">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="2a491-383">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2a491-384">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2a491-384">Next steps</span></span>

<span data-ttu-id="2a491-385">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="2a491-385">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2a491-386">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="2a491-386">Understand the problem</span></span>
> * <span data-ttu-id="2a491-387">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="2a491-387">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="2a491-388">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="2a491-388">Prepare your data</span></span>
> * <span data-ttu-id="2a491-389">Estrarre le funzionalità e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="2a491-389">Extract Features and transform the data</span></span>
> * <span data-ttu-id="2a491-390">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2a491-390">Train the model</span></span>
> * <span data-ttu-id="2a491-391">Valutare il modello con un set di dati diverso</span><span class="sxs-lookup"><span data-stu-id="2a491-391">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="2a491-392">Eseguire una stima relativa a una singola istanza del risultato dei dati di test con il modello di cui è stato eseguito il training</span><span class="sxs-lookup"><span data-stu-id="2a491-392">Predict a single instance of test data outcome with the trained model</span></span>
> * <span data-ttu-id="2a491-393">Eseguire una stima relativa a una singola istanza dei dati di test con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="2a491-393">Predict a single instance of test data with a loaded model</span></span>

<span data-ttu-id="2a491-394">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="2a491-394">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2a491-395">Previsione tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="2a491-395">Taxi Fare Predictor</span></span>](taxi-fare.md)
