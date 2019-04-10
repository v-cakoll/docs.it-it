---
title: Usare ML.NET in uno scenario di classificazione multiclasse dei problemi in GitHub
description: Informazioni su come usare ML.NET in uno scenario di classificazione multiclasse per assegnare i problemi di GitHub a un'area specifica.
ms.date: 03/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: fc21a37fe585ed4b9880ec86ee26815e0668108c
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920987"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="6ad15-103">Esercitazione: Usare ML.NET in uno scenario di classificazione multiclasse per classificare i problemi di GitHub</span><span class="sxs-lookup"><span data-stu-id="6ad15-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="6ad15-104">Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore di problemi di GitHub tramite un'applicazione console .NET Core con C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="6ad15-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="6ad15-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="6ad15-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="6ad15-106">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="6ad15-106">Understand the problem</span></span>
> * <span data-ttu-id="6ad15-107">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="6ad15-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="6ad15-108">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-108">Prepare your data</span></span>
> * <span data-ttu-id="6ad15-109">Trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-109">Transform the data</span></span>
> * <span data-ttu-id="6ad15-110">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-110">Train the model</span></span>
> * <span data-ttu-id="6ad15-111">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-111">Evaluate the model</span></span>
> * <span data-ttu-id="6ad15-112">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="6ad15-112">Predict with the trained model</span></span>
> * <span data-ttu-id="6ad15-113">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="6ad15-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="6ad15-114">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="6ad15-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="6ad15-115">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="6ad15-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="6ad15-116">Questa esercitazione e l'esempio correlato usano attualmente **ML.NET versione 0.11**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-116">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="6ad15-117">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="6ad15-117">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="6ad15-118">Panoramica di esempio di problema GitHub</span><span class="sxs-lookup"><span data-stu-id="6ad15-118">GitHub issue sample overview</span></span>

<span data-ttu-id="6ad15-119">L'esempio è un'app console che usa ML.NET per il training di un modello che classifica e stima l'etichetta Area associata a un problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="6ad15-119">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="6ad15-120">Valuta inoltre il modello con un secondo set di dati per l'analisi della qualità.</span><span class="sxs-lookup"><span data-stu-id="6ad15-120">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="6ad15-121">I set di dati del problema derivano dal repository GitHub dotnet/corefx.</span><span class="sxs-lookup"><span data-stu-id="6ad15-121">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="6ad15-122">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="6ad15-122">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ad15-123">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6ad15-123">Prerequisites</span></span>

* <span data-ttu-id="6ad15-124">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="6ad15-124">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="6ad15-125">Il [file separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="6ad15-125">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="6ad15-126">Il [file di test separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="6ad15-126">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="6ad15-127">Flusso di lavoro di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="6ad15-127">Machine learning workflow</span></span>

<span data-ttu-id="6ad15-128">Questa esercitazione segue un flusso di lavoro di apprendimento automatico che consente l'esecuzione del processo in modo ordinato.</span><span class="sxs-lookup"><span data-stu-id="6ad15-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="6ad15-129">Le fasi del flusso di lavoro sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-129">The workflow phases are as follows:</span></span>

1. **<span data-ttu-id="6ad15-130">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="6ad15-130">Understand the problem</span></span>**
2. **<span data-ttu-id="6ad15-131">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-131">Prepare your data</span></span>**
   * **<span data-ttu-id="6ad15-132">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-132">Load the data</span></span>**
   * **<span data-ttu-id="6ad15-133">Estrarre le caratteristiche (trasformare i dati)</span><span class="sxs-lookup"><span data-stu-id="6ad15-133">Extract features (Transform your data)</span></span>**
3. **<span data-ttu-id="6ad15-134">Creare il modello ed eseguirne il training</span><span class="sxs-lookup"><span data-stu-id="6ad15-134">Build and train</span></span>** 
   * **<span data-ttu-id="6ad15-135">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-135">Train the model</span></span>**
   * **<span data-ttu-id="6ad15-136">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-136">Evaluate the model</span></span>**
4. **<span data-ttu-id="6ad15-137">Distribuire il modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-137">Deploy Model</span></span>**
   * **<span data-ttu-id="6ad15-138">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="6ad15-138">Use the Model to predict</span></span>**

### <a name="understand-the-problem"></a><span data-ttu-id="6ad15-139">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="6ad15-139">Understand the problem</span></span>

<span data-ttu-id="6ad15-140">È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="6ad15-141">La suddivisione del problema consente di stimare e valutare i risultati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-141">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="6ad15-142">L'oggetto della presente esercitazione è la definizione dell'area da cui provengono i problemi di GitHub in ingresso, per etichettarli correttamente ai fini dell'assegnazione della priorità e della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6ad15-142">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="6ad15-143">È possibile suddividere il problema nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-143">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="6ad15-144">testo del titolo del problema</span><span class="sxs-lookup"><span data-stu-id="6ad15-144">the issue title text</span></span>
* <span data-ttu-id="6ad15-145">testo della descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="6ad15-145">the issue description text</span></span>
* <span data-ttu-id="6ad15-146">valore di area per i dati di training del modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-146">an area value for the model training data</span></span>
* <span data-ttu-id="6ad15-147">valore di area stimato che è possibile valutare e quindi usare a livello operativo</span><span class="sxs-lookup"><span data-stu-id="6ad15-147">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="6ad15-148">È quindi necessario **determinare** l'area, che facilita la selezione dell'attività di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="6ad15-148">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="6ad15-149">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="6ad15-149">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="6ad15-150">Per questo problema, sono noti i fatti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-150">With this problem, you know the following facts:</span></span>

<span data-ttu-id="6ad15-151">Dati di training:</span><span class="sxs-lookup"><span data-stu-id="6ad15-151">Training data:</span></span>

<span data-ttu-id="6ad15-152">I problemi di GitHub possono essere etichettati in aree diverse (**Area**), come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-152">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="6ad15-153">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="6ad15-153">area-System.Numerics</span></span>
* <span data-ttu-id="6ad15-154">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="6ad15-154">area-System.Xml</span></span>
* <span data-ttu-id="6ad15-155">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="6ad15-155">area-Infrastructure</span></span>
* <span data-ttu-id="6ad15-156">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="6ad15-156">area-System.Linq</span></span>
* <span data-ttu-id="6ad15-157">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="6ad15-157">area-System.IO</span></span>

<span data-ttu-id="6ad15-158">È possibile eseguire la stima del valore **Area** di un nuovo problema in GitHub, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-158">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="6ad15-159">Contract.Assert rispetto a Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="6ad15-159">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="6ad15-160">Rendere i campi di sola lettura in System.Xml</span><span class="sxs-lookup"><span data-stu-id="6ad15-160">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="6ad15-161">L'algoritmo di Machine Learning di classificazione è il più adatto per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="6ad15-161">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="6ad15-162">Informazioni sull'algoritmo di Machine Learning di classificazione</span><span class="sxs-lookup"><span data-stu-id="6ad15-162">About the classification learning algorithm</span></span>

<span data-ttu-id="6ad15-163">La classificazione è un algoritmo di Machine Learning che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-163">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="6ad15-164">È ad esempio possibile usare la classificazione per:</span><span class="sxs-lookup"><span data-stu-id="6ad15-164">For example, you can use classification to:</span></span>

* <span data-ttu-id="6ad15-165">Identificare il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="6ad15-165">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="6ad15-166">Classificare messaggi di posta elettronica come posta indesiderata o legittima.</span><span class="sxs-lookup"><span data-stu-id="6ad15-166">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="6ad15-167">Determinare se le analisi di laboratorio di un paziente indicano la presenza di cellule tumorali.</span><span class="sxs-lookup"><span data-stu-id="6ad15-167">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="6ad15-168">Suddividere in categorie i clienti in base alla relativa propensione a rispondere a una campagna di vendita.</span><span class="sxs-lookup"><span data-stu-id="6ad15-168">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="6ad15-169">I casi d'uso dell'algoritmo di Machine Learning di classificazione rientrano in genere in uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-169">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="6ad15-170">Binarie: A o B.</span><span class="sxs-lookup"><span data-stu-id="6ad15-170">Binary: either A or B.</span></span>
* <span data-ttu-id="6ad15-171">Multiclasse: più categorie che possono essere stimate tramite un singolo modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-171">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="6ad15-172">Per questo tipo di problema, usare un algoritmo di Machine Learning di classificazione multiclasse, poiché la stima della categoria di problemi può essere una tra più categorie (multiclasse) anziché solo due categorie (binarie).</span><span class="sxs-lookup"><span data-stu-id="6ad15-172">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="6ad15-173">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="6ad15-173">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="6ad15-174">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="6ad15-174">Create a project</span></span>

1. <span data-ttu-id="6ad15-175">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="6ad15-175">Open Visual Studio 2017.</span></span> <span data-ttu-id="6ad15-176">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="6ad15-176">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="6ad15-177">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-177">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="6ad15-178">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-178">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="6ad15-179">Nella casella di testo **Nome** digitare "GitHubIssueClassification" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-179">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="6ad15-180">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:</span><span class="sxs-lookup"><span data-stu-id="6ad15-180">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="6ad15-181">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-181">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="6ad15-182">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="6ad15-182">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="6ad15-183">Creare una directory denominata *Models* nel progetto per salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="6ad15-183">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="6ad15-184">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-184">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="6ad15-185">Digitare "Models" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="6ad15-185">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="6ad15-186">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="6ad15-186">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="6ad15-187">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-187">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="6ad15-188">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-188">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="6ad15-189">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-189">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="6ad15-190">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-190">Prepare your data</span></span>

1. <span data-ttu-id="6ad15-191">Scaricare i set di dati [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) e salvarli nella cartella *Data* creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6ad15-191">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="6ad15-192">Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-192">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="6ad15-193">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-193">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="6ad15-194">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-194">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="6ad15-195">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="6ad15-195">Create classes and define paths</span></span>

<span data-ttu-id="6ad15-196">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="6ad15-196">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="6ad15-197">Creare tre campi globali per i percorsi dei file scaricati di recente e variabili globali per `MLContext`,`DataView`, `PredictionEngine` e `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-197">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* `_trainDataPath` <span data-ttu-id="6ad15-198">contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-198">has the path to the dataset used to train the model.</span></span>
* `_testDataPath` <span data-ttu-id="6ad15-199">contiene il percorso del set di dati usato per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-199">has the path to the dataset used to evaluate the model.</span></span>
* `_modelPath` <span data-ttu-id="6ad15-200">contiene il percorso in cui è salvato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="6ad15-200">has the path where the trained model is saved.</span></span>
* `_mlContext` <span data-ttu-id="6ad15-201">è l'elemento <xref:Microsoft.ML.MLContext> che specifica il contesto di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="6ad15-201">is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* `_trainingDataView` <span data-ttu-id="6ad15-202">è l'elemento <xref:Microsoft.Data.DataView.IDataView> usato per elaborare il set di dati di training.</span><span class="sxs-lookup"><span data-stu-id="6ad15-202">is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* `_predEngine` <span data-ttu-id="6ad15-203">è l'elemento <xref:Microsoft.ML.PredictionEngine%602> usato per le stime singole.</span><span class="sxs-lookup"><span data-stu-id="6ad15-203">is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* `_reader` <span data-ttu-id="6ad15-204">è l'istanza della classe <xref:Microsoft.ML.Data.TextLoader> usata per caricare e trasformare i set di dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-204">is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="6ad15-205">Aggiungere il codice seguente nella riga subito sopra il metodo `Main` per specificare questi percorsi e le altre variabili:</span><span class="sxs-lookup"><span data-stu-id="6ad15-205">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="6ad15-206">Creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="6ad15-206">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="6ad15-207">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="6ad15-207">Add a new class to your project:</span></span>

1. <span data-ttu-id="6ad15-208">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-208">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="6ad15-209">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** impostando *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="6ad15-209">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="6ad15-210">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-210">Then, select the **Add** button.</span></span>

    <span data-ttu-id="6ad15-211">Il file *GitHubIssueData.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="6ad15-211">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="6ad15-212">Aggiungere l'istruzione `using` seguente all'inizio del file *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="6ad15-212">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="6ad15-213">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `GitHubIssue` e `IssuePrediction`, al file *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="6ad15-213">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

`GitHubIssue` <span data-ttu-id="6ad15-214">è la classe del set di dati di input e ha i campi <xref:System.String> seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-214">is the input dataset class and has the following <xref:System.String> fields:</span></span>

* `ID` <span data-ttu-id="6ad15-215">contiene un valore per l'ID del problema GitHub</span><span class="sxs-lookup"><span data-stu-id="6ad15-215">contains a value for the GitHub issue ID</span></span>
* `Area` <span data-ttu-id="6ad15-216">contiene un valore per l'etichetta `Area`</span><span class="sxs-lookup"><span data-stu-id="6ad15-216">contains a value for the `Area` label</span></span>
* `Title` <span data-ttu-id="6ad15-217">contiene il titolo del problema GitHub</span><span class="sxs-lookup"><span data-stu-id="6ad15-217">contains the GitHub issue title</span></span>
* `Description` <span data-ttu-id="6ad15-218">contiene la descrizione del problema GitHub</span><span class="sxs-lookup"><span data-stu-id="6ad15-218">contains the GitHub issue description</span></span>

`IssuePrediction` <span data-ttu-id="6ad15-219">è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-219">is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="6ad15-220">Dispone di un `string` singolo (`Area`) e di un attributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-220">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="6ad15-221">`Label` viene usato per creare il modello ed eseguirne il training, nonché con un secondo set di dati per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-221">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="6ad15-222">`PredictedLabel` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="6ad15-222">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="6ad15-223">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-223">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="6ad15-224">Quando si crea un modello con ML.NET, si inizia creando un <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="6ad15-224">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> `MLContext` <span data-ttu-id="6ad15-225">è paragonabile a livello concettuale all'uso di `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6ad15-225">is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="6ad15-226">L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6ad15-226">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="6ad15-227">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="6ad15-227">Initialize variables in Main</span></span>

<span data-ttu-id="6ad15-228">Inizializzare la variabile globale `_mlContext` con una nuova istanza di `MLContext` con un valore di inizializzazione casuale (`seed: 0`) per risultati ripetibili/deterministici in più training.</span><span class="sxs-lookup"><span data-stu-id="6ad15-228">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="6ad15-229">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-229">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="6ad15-230">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-230">Load the data</span></span>

<span data-ttu-id="6ad15-231">Quindi inizializzare la variabile globale `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> e caricare i dati con il parametro `_trainDataPath`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-231">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="6ad15-232">Come input e output di [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), `DataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-232">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="6ad15-233">In ML.NET i dati sono simili a una `SQL view`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-233">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="6ad15-234">Vengono valutati in modalità differita, sono schematizzati ed eterogenei.</span><span class="sxs-lookup"><span data-stu-id="6ad15-234">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="6ad15-235">L'oggetto è la prima parte della pipeline e carica i dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-235">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="6ad15-236">Per questa esercitazione carica un set di dati con titoli e descrizioni di problemi e con l'etichetta GitHub dell'area corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6ad15-236">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="6ad15-237">L'elemento `DataView` viene usato per creare il modello ed eseguirne il training.</span><span class="sxs-lookup"><span data-stu-id="6ad15-237">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="6ad15-238">Poiché il tipo di modello di dati `GitHubIssue` creato in precedenza corrisponde allo schema del set di dati, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati in un'unica riga di codice.</span><span class="sxs-lookup"><span data-stu-id="6ad15-238">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="6ad15-239">Caricare i dati usando il wrapper `MLContext.Data.LoadFromTextFile` per il [metodo LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span><span class="sxs-lookup"><span data-stu-id="6ad15-239">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="6ad15-240">Restituisce un'interfaccia <xref:Microsoft.Data.DataView.IDataView> che deduce lo schema del set di dati dal tipo di modello di dati `GitHubIssue` e usa l'intestazione del set di dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-240">It returns a <xref:Microsoft.Data.DataView.IDataView> which infers the dataset schema from the `GitHubIssue` data model type and uses the dataset header.</span></span> 

<span data-ttu-id="6ad15-241">Lo schema di dati è stato definito in precedenza quando è stata creata la classe `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-241">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="6ad15-242">Per lo schema:</span><span class="sxs-lookup"><span data-stu-id="6ad15-242">For your schema:</span></span>

* <span data-ttu-id="6ad15-243">La prima colonna `ID` (ID problema di GitHub)</span><span class="sxs-lookup"><span data-stu-id="6ad15-243">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="6ad15-244">La seconda colonna `Area` (stima per il training)</span><span class="sxs-lookup"><span data-stu-id="6ad15-244">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="6ad15-245">La terza colonna `Title` (titolo del problema GitHub) è la prima [caratteristica](../resources/glossary.md##feature) usata per la stima di</span><span class="sxs-lookup"><span data-stu-id="6ad15-245">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the</span></span> `Area`
* <span data-ttu-id="6ad15-246">La quarta colonna `Description` è la seconda caratteristica usata per la stima di</span><span class="sxs-lookup"><span data-stu-id="6ad15-246">the fourth column  `Description` is the second feature used for predicting the</span></span> `Area`

<span data-ttu-id="6ad15-247">Per inizializzare e caricare la variabile globale `_trainingDataView` in modo da riusarla per la pipeline, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-247">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

<span data-ttu-id="6ad15-248">Aggiungere il codice seguente al metodo `Main` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="6ad15-248">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="6ad15-249">Il metodo `ProcessData` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-249">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="6ad15-250">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-250">Extracts and transforms the data.</span></span>
* <span data-ttu-id="6ad15-251">Restituisce la pipeline di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="6ad15-251">Returns the processing pipeline.</span></span>

<span data-ttu-id="6ad15-252">Creare il metodo `ProcessData` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-252">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="6ad15-253">Estrarre le funzionalità e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-253">Extract Features and transform the data</span></span>

<span data-ttu-id="6ad15-254">La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="6ad15-254">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="6ad15-255">I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="6ad15-255">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="6ad15-256">L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.</span><span class="sxs-lookup"><span data-stu-id="6ad15-256">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="6ad15-257">Le pipeline di trasformazione di ML.NET compongono un `transforms`set personalizzato che viene applicato ai dati prima di eseguire il training o i test.</span><span class="sxs-lookup"><span data-stu-id="6ad15-257">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="6ad15-258">Lo scopo principale delle trasformazioni è l'[estrazione delle caratteristiche](../resources/glossary.md#feature-engineering) dai dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-258">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="6ad15-259">Gli algoritmi di apprendimento automatico sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) in modo da trasformare successivamente i dati testuali in un formato riconoscibile da tali algoritmi.</span><span class="sxs-lookup"><span data-stu-id="6ad15-259">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="6ad15-260">Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="6ad15-260">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="6ad15-261">Nei passaggi successivi si fa riferimento alle colonne in base ai nomi definiti nella classe `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-261">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="6ad15-262">Quando vengono eseguiti il training e la valutazione del modello, i valori nella colonna **Label** vengono considerati per impostazione predefinita come valori corretti da stimare.</span><span class="sxs-lookup"><span data-stu-id="6ad15-262">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="6ad15-263">Dato che si vuole stimare l'etichetta GitHub Area per un `GitHubIssue`, copiare la colonna `Area` nella colonna **Label**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-263">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="6ad15-264">A tale scopo usare `MLContext.Transforms.Conversion.MapValueToKey`, che è un wrapper per la classe di trasformazione <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ad15-264">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="6ad15-265">`MapValueToKey` restituisce un oggetto <xref:Microsoft.ML.Data.EstimatorChain%601> che sarà effettivamente una pipeline.</span><span class="sxs-lookup"><span data-stu-id="6ad15-265">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="6ad15-266">Assegnare un nome a questa `pipeline` poiché successivamente si aggiungerà l'algoritmo di training all'oggetto `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-266">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="6ad15-267">Aggiungere la riga di codice successiva:</span><span class="sxs-lookup"><span data-stu-id="6ad15-267">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="6ad15-268">L'estrazione delle funzionalità assegna valori chiave numerici diversi ai diversi valori in ogni colonna ed è usata dall'algoritmo di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="6ad15-268">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="6ad15-269">Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` che trasforma le colonne di testo (`Title` e `Description`) in un vettore numerico per ogni `TitleFeaturized` e `DescriptionFeaturized` di cui è stata eseguita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6ad15-269">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="6ad15-270">Aggiungere l'estrazione delle funzionalità per entrambe le colonne alla pipeline con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-270">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="6ad15-271">In ML.NET versione 0.10 è stato modificato l'ordine dei parametri Transforms.</span><span class="sxs-lookup"><span data-stu-id="6ad15-271">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="6ad15-272">Non si verificherà nessun errore fino a quando non si compila.</span><span class="sxs-lookup"><span data-stu-id="6ad15-272">This will not error out until you build.</span></span> <span data-ttu-id="6ad15-273">Usare i nomi dei parametri per Transforms come illustrato nel frammento di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="6ad15-273">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="6ad15-274">L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione `Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-274">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="6ad15-275">Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**.</span><span class="sxs-lookup"><span data-stu-id="6ad15-275">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="6ad15-276">Aggiungere questa trasformazione alla pipeline con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-276">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="6ad15-277">Aggiungere quindi <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> per memorizzare nella cache la vista dati e ottenere prestazioni migliori quando si esegue più volte l'iterazione dei dati usando la cache, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-277">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="6ad15-278">Usare AppendCacheCheckpoint per i set di dati di piccole e medie dimensioni per ridurre i tempi di training.</span><span class="sxs-lookup"><span data-stu-id="6ad15-278">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="6ad15-279">NON usarlo (rimuovere. AppendCacheCheckpoint()) durante la gestione di set di dati molto grandi.</span><span class="sxs-lookup"><span data-stu-id="6ad15-279">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="6ad15-280">Applicare return alla pipeline alla fine del metodo `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-280">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="6ad15-281">Questo passaggio gestisce la pre-elaborazione/estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6ad15-281">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="6ad15-282">Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-282">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="6ad15-283">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-283">Build and train the model</span></span>

<span data-ttu-id="6ad15-284">Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-284">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="6ad15-285">Il metodo `BuildAndTrainModel` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-285">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="6ad15-286">Crea la classe di algoritmo di training.</span><span class="sxs-lookup"><span data-stu-id="6ad15-286">Creates the training algorithm class.</span></span>
* <span data-ttu-id="6ad15-287">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-287">Trains the model.</span></span>
* <span data-ttu-id="6ad15-288">Esegue la stima dell'area sulla base dei dati di training.</span><span class="sxs-lookup"><span data-stu-id="6ad15-288">Predicts area based on training data.</span></span>
* <span data-ttu-id="6ad15-289">Salva il modello in un file `.zip`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-289">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="6ad15-290">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="6ad15-290">Returns the model.</span></span>

<span data-ttu-id="6ad15-291">Creare il metodo `BuildAndTrainModel` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-291">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

<span data-ttu-id="6ad15-292">Si noti che nel metodo BuildAndTrainModel vengono passati due parametri, un `IDataView` per il set di dati di training (`trainingDataView`) e un <xref:Microsoft.ML.Data.EstimatorChain%601> per la pipeline di elaborazione creata in ProcessData (`pipeline`).</span><span class="sxs-lookup"><span data-stu-id="6ad15-292">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="6ad15-293">Aggiungere il codice seguente come prima riga del metodo `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-293">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="6ad15-294">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="6ad15-294">Choose a learning algorithm</span></span>

<span data-ttu-id="6ad15-295">Per aggiungere l'algoritmo di apprendimento chiamare il metodo wrapper `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent`, che restituisce un oggetto <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>.</span><span class="sxs-lookup"><span data-stu-id="6ad15-295">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="6ad15-296">L'oggetto `SdcaMultiClassTrainer` viene aggiunto a `pipeline` e accetta gli elementi `Title` e `Description` (`Features`) con estrazione di funzionalità e i parametri di input `Label` per l'apprendimento dai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="6ad15-296">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="6ad15-297">È anche necessario eseguire il mapping dell'etichetta al valore per restituirlo allo stato leggibile originale.</span><span class="sxs-lookup"><span data-stu-id="6ad15-297">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="6ad15-298">Eseguire entrambe le operazioni con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-298">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="6ad15-299">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-299">Train the model</span></span>

<span data-ttu-id="6ad15-300">Il training del modello, <xref:Microsoft.ML.Data.TransformerChain%601>, viene eseguito in base al set di dati caricato e trasformato.</span><span class="sxs-lookup"><span data-stu-id="6ad15-300">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="6ad15-301">Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-301">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="6ad15-302">Questo metodo restituisce un modello da usare per le stime.</span><span class="sxs-lookup"><span data-stu-id="6ad15-302">This  method returns a model to use for predictions.</span></span> `trainingPipeline.Fit()` <span data-ttu-id="6ad15-303">esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata.</span><span class="sxs-lookup"><span data-stu-id="6ad15-303">trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="6ad15-304">L'esperimento non viene eseguito finché non viene eseguito il metodo `.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-304">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="6ad15-305">Aggiungere al metodo `BuildAndTrainModel` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-305">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="6ad15-306">Mentre `model` è un `transformer` che opera su numerose righe di dati, la necessità di stime su singoli esempi è uno scenario di produzione comune.</span><span class="sxs-lookup"><span data-stu-id="6ad15-306">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="6ad15-307"><xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="6ad15-308">A questo punto si aggiunge il codice seguente per creare `PredictionEngine` come riga successiva nel metodo `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-308">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="6ad15-309">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="6ad15-309">Predict with the trained model</span></span>

<span data-ttu-id="6ad15-310">Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-310">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="6ad15-311">È possibile usare quanto sopra per eseguire la stima dell'etichetta `Area` di una singola istanza dei dati del problema.</span><span class="sxs-lookup"><span data-stu-id="6ad15-311">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="6ad15-312">Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-312">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="6ad15-313">I dati di input sono una stringa e il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6ad15-313">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="6ad15-314">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="6ad15-314">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="6ad15-315">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="6ad15-315">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="6ad15-316">Uso del modello: risultati della stima</span><span class="sxs-lookup"><span data-stu-id="6ad15-316">Using the model: prediction results</span></span>

<span data-ttu-id="6ad15-317">Visualizzare `GitHubIssue` e la stima dell'etichetta `Area` corrispondente per condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="6ad15-317">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="6ad15-318">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="6ad15-319">Restituire il modello di cui è stato eseguito il training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="6ad15-319">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="6ad15-320">Restituire il modello alla fine del metodo `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-320">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="6ad15-321">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-321">Evaluate the model</span></span>

<span data-ttu-id="6ad15-322">Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida.</span><span class="sxs-lookup"><span data-stu-id="6ad15-322">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="6ad15-323">Nel metodo `Evaluate` viene passato il modello creato in `BuildAndTrainModel` per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="6ad15-323">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="6ad15-324">Creare il metodo `Evaluate` subito dopo `BuildAndTrainModel`, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-324">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="6ad15-325">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-325">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="6ad15-326">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="6ad15-326">Loads the test dataset.</span></span>
* <span data-ttu-id="6ad15-327">Crea l'analizzatore multiclasse.</span><span class="sxs-lookup"><span data-stu-id="6ad15-327">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="6ad15-328">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="6ad15-328">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="6ad15-329">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="6ad15-329">Displays the metrics.</span></span>

<span data-ttu-id="6ad15-330">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `BuildAndTrainModel`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-330">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="6ad15-331">Come in precedenza con il set di dati di training, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati di test in una sola riga di codice.</span><span class="sxs-lookup"><span data-stu-id="6ad15-331">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="6ad15-332">È possibile valutare il modello usando questo set di dati come controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="6ad15-332">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="6ad15-333">Aggiungere al metodo `Evaluate` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-333">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="6ad15-334">`MulticlassClassificationContext.Evaluate` è un wrapper del metodo <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> che calcola le metriche di qualità per il modello usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="6ad15-334">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="6ad15-335">Restituisce un oggetto <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> che contiene le metriche complessive calcolate dagli analizzatori della classificazione multiclasse.</span><span class="sxs-lookup"><span data-stu-id="6ad15-335">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="6ad15-336">Per visualizzare la metrica per determinare la qualità del modello, è prima necessario ottenerla.</span><span class="sxs-lookup"><span data-stu-id="6ad15-336">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="6ad15-337">Osservare l'uso del metodo `Transform` della variabile globale di apprendimento automatico `_trainedModel` (un oggetto Transformer) per l'input di funzionalità e la generazione di stime.</span><span class="sxs-lookup"><span data-stu-id="6ad15-337">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="6ad15-338">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="6ad15-338">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="6ad15-339">Le metriche seguenti vengono valutate per la classificazione multiclasse:</span><span class="sxs-lookup"><span data-stu-id="6ad15-339">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="6ad15-340">MicroAccuracy (Accuratezza micro): ogni coppia campione-classe contribuisce nello stesso modo alla metrica di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="6ad15-340">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="6ad15-341">Il valore desiderato per MicroAccuracy è il valore più prossimo a 1.</span><span class="sxs-lookup"><span data-stu-id="6ad15-341">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="6ad15-342">MacroAccuracy (Accuratezza macro): ogni classe contribuisce nello stesso modo alla metrica di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="6ad15-342">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="6ad15-343">Alle classi di minoranza viene assegnato un peso uguale a quello delle classi più grandi.</span><span class="sxs-lookup"><span data-stu-id="6ad15-343">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="6ad15-344">Il valore desiderato per MacroAccuracy è il valore più prossimo a 1.</span><span class="sxs-lookup"><span data-stu-id="6ad15-344">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="6ad15-345">LogLoss (Perdita di log): vedere [Perdita di log](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="6ad15-345">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="6ad15-346">Il valore desiderato per LogLoss è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="6ad15-346">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="6ad15-347">LogLossReduction (Riduzione della perdita di log): è compreso nell'intervallo [-inf, 100], dove 100 corrisponde a stime perfette e 0 indica stime medie.</span><span class="sxs-lookup"><span data-stu-id="6ad15-347">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="6ad15-348">Il valore desiderato per LogLossReduction è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="6ad15-348">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="6ad15-349">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-349">Displaying the metrics for model validation</span></span>

<span data-ttu-id="6ad15-350">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="6ad15-350">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="6ad15-351">Salvare il modello di cui è stato eseguito il training e valutato</span><span class="sxs-lookup"><span data-stu-id="6ad15-351">Save the trained and evaluated model</span></span>

<span data-ttu-id="6ad15-352">A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain%601> che può essere integrato nelle applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="6ad15-352">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="6ad15-353">Per salvare il modello sottoposto a training in un file con estensione zip, aggiungere il codice seguente per chiamare il metodo `SaveModelAsFile` come riga successiva in `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-353">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="6ad15-354">Salvare il modello come file con estensione zip</span><span class="sxs-lookup"><span data-stu-id="6ad15-354">Save the model as a .zip file</span></span>

<span data-ttu-id="6ad15-355">Creare il metodo `SaveModelAsFile` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-355">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="6ad15-356">Il metodo `SaveModelAsFile` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-356">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="6ad15-357">Salva il modello come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="6ad15-357">Saves the model as a .zip file.</span></span>

<span data-ttu-id="6ad15-358">A questo punto, creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6ad15-358">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="6ad15-359">L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="6ad15-359">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="6ad15-360">Per salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="6ad15-360">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="6ad15-361">Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="6ad15-361">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="6ad15-362">È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-362">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="6ad15-363">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="6ad15-363">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="6ad15-364">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-364">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="6ad15-365">Creare il metodo `PredictIssue`, subito dopo il metodo `Evaluate` e subito prima del metodo `SaveModelAsFile`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-365">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="6ad15-366">Il metodo `PredictIssue` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad15-366">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="6ad15-367">Crea un singolo problema con dati di test.</span><span class="sxs-lookup"><span data-stu-id="6ad15-367">Creates a single issue of test data.</span></span>
* <span data-ttu-id="6ad15-368">Esegue la stima dell'Area in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="6ad15-368">Predicts Area based on test data.</span></span>
* <span data-ttu-id="6ad15-369">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="6ad15-369">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="6ad15-370">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-370">Displays the predicted results.</span></span>

<span data-ttu-id="6ad15-371">In primo luogo caricare il modello salvato in precedenza con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-371">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="6ad15-372">Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="6ad15-372">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="6ad15-373">Ora che è presente un modello, è possibile usarlo per stimare l'etichetta GitHub Area di una singola istanza dei dati del problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="6ad15-373">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="6ad15-374">Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati.</span><span class="sxs-lookup"><span data-stu-id="6ad15-374">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="6ad15-375">I dati di input sono una stringa e il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6ad15-375">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="6ad15-376">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="6ad15-376">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="6ad15-377">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="6ad15-377">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="6ad15-378">Aggiungere il codice seguente al metodo `PredictIssue` per le stime:</span><span class="sxs-lookup"><span data-stu-id="6ad15-378">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="6ad15-379">Uso del modello caricato per la stima</span><span class="sxs-lookup"><span data-stu-id="6ad15-379">Using the loaded model for prediction</span></span>

<span data-ttu-id="6ad15-380">Visualizzare `Area` per classificare il problema e agire su di esso di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="6ad15-380">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="6ad15-381">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad15-381">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="6ad15-382">Risultati</span><span class="sxs-lookup"><span data-stu-id="6ad15-382">Results</span></span>

<span data-ttu-id="6ad15-383">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6ad15-383">Your results should be similar to the following.</span></span> <span data-ttu-id="6ad15-384">Durante l'elaborazione della pipeline, vengono visualizzati messaggi.</span><span class="sxs-lookup"><span data-stu-id="6ad15-384">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="6ad15-385">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="6ad15-385">You may see warnings, or processing messages.</span></span> <span data-ttu-id="6ad15-386">Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="6ad15-386">These messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="6ad15-387">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="6ad15-387">Congratulations!</span></span> <span data-ttu-id="6ad15-388">È stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima di un'etichetta Area per un problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="6ad15-388">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="6ad15-389">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="6ad15-389">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ad15-390">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6ad15-390">Next steps</span></span>

<span data-ttu-id="6ad15-391">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="6ad15-391">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="6ad15-392">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="6ad15-392">Understand the problem</span></span>
> * <span data-ttu-id="6ad15-393">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="6ad15-393">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="6ad15-394">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-394">Prepare your data</span></span>
> * <span data-ttu-id="6ad15-395">Trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="6ad15-395">Transform the data</span></span>
> * <span data-ttu-id="6ad15-396">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-396">Train the model</span></span>
> * <span data-ttu-id="6ad15-397">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="6ad15-397">Evaluate the model</span></span>
> * <span data-ttu-id="6ad15-398">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="6ad15-398">Predict with the trained model</span></span>
> * <span data-ttu-id="6ad15-399">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="6ad15-399">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="6ad15-400">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6ad15-400">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="6ad15-401">Previsione tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="6ad15-401">Taxi Fare Predictor</span></span>](taxi-fare.md)
