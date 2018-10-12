---
title: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment
description: Informazioni su come usare ML.NET in uno scenario di classificazione binaria per comprendere come usare la stima del sentiment al fine di eseguire l'azione appropriata.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7d2935fafe9dbad28205c8a896d97d80474a686f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2018
ms.locfileid: "47436141"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="4d86e-103">Esercitazione: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="4d86e-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="4d86e-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="4d86e-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="4d86e-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="4d86e-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="4d86e-106">Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore del sentiment tramite un'applicazione console .NET Core con C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="4d86e-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="4d86e-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="4d86e-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4d86e-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="4d86e-108">Understand the problem</span></span>
> * <span data-ttu-id="4d86e-109">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="4d86e-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="4d86e-110">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="4d86e-110">Prepare your data</span></span>
> * <span data-ttu-id="4d86e-111">Creare la pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="4d86e-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="4d86e-112">Caricare un classificatore</span><span class="sxs-lookup"><span data-stu-id="4d86e-112">Load a classifier</span></span>
> * <span data-ttu-id="4d86e-113">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-113">Train the model</span></span>
> * <span data-ttu-id="4d86e-114">Valutare il modello con un set di dati diverso</span><span class="sxs-lookup"><span data-stu-id="4d86e-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="4d86e-115">Stimare i risultati dei dati di test con il modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-115">Predict the test data outcomes with the model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="4d86e-116">Panoramica dell'esempio di analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="4d86e-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="4d86e-117">L'esempio è un'app console che usa ML.NET per eseguire il training di un modello che classifica e stima il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4d86e-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="4d86e-118">Valuta inoltre il modello con un secondo set di dati per l'analisi della qualità.</span><span class="sxs-lookup"><span data-stu-id="4d86e-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="4d86e-119">I set di dati per il sentiment provengono dal progetto WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="4d86e-119">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d86e-120">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4d86e-120">Prerequisites</span></span>

* <span data-ttu-id="4d86e-121">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="4d86e-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="4d86e-122">[File con valori delimitati da tabulazioni Wikipedia detox line data (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="4d86e-122">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="4d86e-123">[File con valori delimitati da tabulazioni Wikipedia detox line test (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="4d86e-123">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="4d86e-124">Flusso di lavoro di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="4d86e-124">Machine learning workflow</span></span>

<span data-ttu-id="4d86e-125">Questa esercitazione segue un flusso di lavoro di apprendimento automatico che consente l'esecuzione del processo in modo ordinato.</span><span class="sxs-lookup"><span data-stu-id="4d86e-125">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="4d86e-126">Le fasi del flusso di lavoro sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d86e-126">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="4d86e-127">**Informazioni sul problema**</span><span class="sxs-lookup"><span data-stu-id="4d86e-127">**Understand the problem**</span></span>
2. <span data-ttu-id="4d86e-128">**Inserimento dei dati**</span><span class="sxs-lookup"><span data-stu-id="4d86e-128">**Ingest the data**</span></span>
3. <span data-ttu-id="4d86e-129">**Pre-elaborazione dei dati e progettazione delle funzionalità**</span><span class="sxs-lookup"><span data-stu-id="4d86e-129">**Data preprocess and feature engineering**</span></span>
4. <span data-ttu-id="4d86e-130">**Training e stima del modello**</span><span class="sxs-lookup"><span data-stu-id="4d86e-130">**Train and predict the model**</span></span>
5. <span data-ttu-id="4d86e-131">**Valutazione del modello**</span><span class="sxs-lookup"><span data-stu-id="4d86e-131">**Evaluate the model**</span></span>
6. <span data-ttu-id="4d86e-132">**Operazionalizzazione del modello**</span><span class="sxs-lookup"><span data-stu-id="4d86e-132">**Model operationalization**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="4d86e-133">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="4d86e-133">Understand the problem</span></span>

<span data-ttu-id="4d86e-134">È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-134">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="4d86e-135">La suddivisione del problema consente di stimare e valutare i risultati.</span><span class="sxs-lookup"><span data-stu-id="4d86e-135">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="4d86e-136">Il problema per questa esercitazione consiste nel comprendere il sentiment dei commenti in un sito Web per eseguire l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="4d86e-136">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="4d86e-137">È possibile suddividere il problema nel testo del sentiment e nel valore del sentiment per i dati con cui si vuole eseguire il training del modello e un valore del sentiment stimato che è possibile valutare e quindi usare a livello operativo.</span><span class="sxs-lookup"><span data-stu-id="4d86e-137">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="4d86e-138">Sarà quindi necessario **determinare** il sentiment, che consente di selezionare l'attività di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="4d86e-138">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="4d86e-139">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="4d86e-139">Select the appropriate machine learning task</span></span>

<span data-ttu-id="4d86e-140">Per questo problema, sono noti i fatti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d86e-140">With this problem, you know the following facts:</span></span>

<span data-ttu-id="4d86e-141">Dati di training: i commenti nel sito Web possono essere positivi o negativi (**sentiment**).</span><span class="sxs-lookup"><span data-stu-id="4d86e-141">Training data: website comments can be positive or negative (**sentiment**).</span></span>
<span data-ttu-id="4d86e-142">Stimare il **sentiment** di un nuovo commento nel sito Web (positivo o negativo), come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d86e-142">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="4d86e-143">Per favore evita di aggiungere cose insensate a Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="4d86e-143">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="4d86e-144">È il migliore, e l'articolo dovrebbe indicarlo.</span><span class="sxs-lookup"><span data-stu-id="4d86e-144">He is the best, and the article should say that.</span></span>

<span data-ttu-id="4d86e-145">L'attività di apprendimento automatico tramite classificazione è la più adatta per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="4d86e-145">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="4d86e-146">Informazioni sull'attività di classificazione</span><span class="sxs-lookup"><span data-stu-id="4d86e-146">About the classification task</span></span>

<span data-ttu-id="4d86e-147">La classificazione è un'attività di apprendimento automatico che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="4d86e-147">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="4d86e-148">È ad esempio possibile usare la classificazione per:</span><span class="sxs-lookup"><span data-stu-id="4d86e-148">For example, you can use classification to:</span></span>

* <span data-ttu-id="4d86e-149">Identificare il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4d86e-149">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="4d86e-150">Classificare messaggi di posta elettronica come posta indesiderata o legittima.</span><span class="sxs-lookup"><span data-stu-id="4d86e-150">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="4d86e-151">Determinare se le analisi di laboratorio di un paziente indicano la presenza di cellule tumorali.</span><span class="sxs-lookup"><span data-stu-id="4d86e-151">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="4d86e-152">Suddividere in categorie i clienti in base alla relativa propensione a rispondere a una campagna di vendita.</span><span class="sxs-lookup"><span data-stu-id="4d86e-152">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="4d86e-153">Le attività di classificazione sono spesso di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d86e-153">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="4d86e-154">Binarie: A o B.</span><span class="sxs-lookup"><span data-stu-id="4d86e-154">Binary: either A or B.</span></span>
* <span data-ttu-id="4d86e-155">Multiclasse: più categorie che possono essere stimate tramite un singolo modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-155">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="4d86e-156">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="4d86e-156">Create a console application</span></span>

1. <span data-ttu-id="4d86e-157">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="4d86e-157">Open Visual Studio 2017.</span></span> <span data-ttu-id="4d86e-158">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="4d86e-158">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="4d86e-159">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-159">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="4d86e-160">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-160">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="4d86e-161">Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-161">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="4d86e-162">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:</span><span class="sxs-lookup"><span data-stu-id="4d86e-162">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="4d86e-163">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-163">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="4d86e-164">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4d86e-164">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="4d86e-165">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="4d86e-165">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="4d86e-166">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-166">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="4d86e-167">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-167">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="4d86e-168">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="4d86e-168">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="4d86e-169">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="4d86e-169">Prepare your data</span></span>

1. <span data-ttu-id="4d86e-170">Scaricare i set di dati [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) e [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) e salvarli nella cartella *Data* creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4d86e-170">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="4d86e-171">Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-171">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="4d86e-172">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-172">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="4d86e-173">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-173">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="4d86e-174">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="4d86e-174">Create classes and define paths</span></span>

<span data-ttu-id="4d86e-175">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="4d86e-175">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="4d86e-176">È necessario creare tre campi globali per contenere i percorsi dei file scaricati di recente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-176">You need to create three global fields to hold the paths to the recently downloaded files:</span></span>

* <span data-ttu-id="4d86e-177">`_dataPath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-177">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="4d86e-178">`_testDataPath` contiene il percorso del set di dati usato per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-178">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="4d86e-179">`_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="4d86e-179">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="4d86e-180">Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:</span><span class="sxs-lookup"><span data-stu-id="4d86e-180">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

<span data-ttu-id="4d86e-181">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="4d86e-181">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="4d86e-182">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="4d86e-182">Add a new class to your project:</span></span>

1. <span data-ttu-id="4d86e-183">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-183">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="4d86e-184">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="4d86e-184">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="4d86e-185">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-185">Then, select the **Add** button.</span></span>

    <span data-ttu-id="4d86e-186">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="4d86e-186">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="4d86e-187">Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="4d86e-187">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="4d86e-188">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="4d86e-188">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="4d86e-189">`SentimentData` è la classe dataset di input e dispone di un valore `float` (`Sentiment`) per il sentiment positivo o negativo e una stringa per il commento (`SentimentText`).</span><span class="sxs-lookup"><span data-stu-id="4d86e-189">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="4d86e-190">A entrambi i campi sono associati attributi `Column`.</span><span class="sxs-lookup"><span data-stu-id="4d86e-190">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="4d86e-191">Questo attributo descrive l'ordine di ogni campo nel file di dati e indica qual è il campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="4d86e-191">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="4d86e-192">`SentimentPrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-192">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="4d86e-193">Dispone di un singolo valore booleano (`Sentiment`) e un attributo `ColumnName` `PredictedLabel`.</span><span class="sxs-lookup"><span data-stu-id="4d86e-193">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="4d86e-194">`Label` viene usato per creare il modello ed eseguirne il training, nonché con un secondo set di dati per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-194">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="4d86e-195">`PredictedLabel` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="4d86e-195">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="4d86e-196">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-196">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="4d86e-197">Nel file *Program.cs* modificare la firma del metodo `Main` sostituendo `void` con `async Task`, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-197">In the *Program.cs* file, change the `Main` method signature by replacing `void` with `async Task`, as in the following example:</span></span>

```csharp
static async Task Main(string[] args) 
{

}
```

<span data-ttu-id="4d86e-198">Si aggiunge `async` a `Main` con un tipo restituito <xref:System.Threading.Tasks.Task> perché il modello verrà salvato in un file ZIP in un secondo momento e il programma deve attendere fino al completamento di tale attività esterna.</span><span class="sxs-lookup"><span data-stu-id="4d86e-198">You add `async` to `Main` with a <xref:System.Threading.Tasks.Task> return type because you're saving the model to a zip file later, and the program needs to wait until that external task completes.</span></span>

> [!NOTE]
> <span data-ttu-id="4d86e-199">Un metodo *async main* consente di usare `await` nel proprio metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="4d86e-199">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="4d86e-200">Per altre informazioni, vedere l'argomento relativo ad [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) nella Guida per programmatori C#.</span><span class="sxs-lookup"><span data-stu-id="4d86e-200">For more information, see the [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) topic in the C# programming guide.</span></span>

<span data-ttu-id="4d86e-201">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="4d86e-201">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

<span data-ttu-id="4d86e-202">Il metodo `Train` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d86e-202">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="4d86e-203">Carica o inserisce i dati.</span><span class="sxs-lookup"><span data-stu-id="4d86e-203">Loads or ingests the data.</span></span>
* <span data-ttu-id="4d86e-204">Esegue la pre-elaborazione dei dati ed estrae le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4d86e-204">Preprocesses and featurizes the data.</span></span>
* <span data-ttu-id="4d86e-205">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-205">Trains the model.</span></span>
* <span data-ttu-id="4d86e-206">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="4d86e-206">Predicts sentiment based on test data.</span></span>

<span data-ttu-id="4d86e-207">Creare il metodo `Train` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-207">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a><span data-ttu-id="4d86e-208">Inserimento dei dati</span><span class="sxs-lookup"><span data-stu-id="4d86e-208">Ingest the data</span></span>

<span data-ttu-id="4d86e-209">Inizializzare una nuova istanza di <xref:Microsoft.ML.LearningPipeline> che includerà il caricamento dei dati, l'elaborazione dei dati/l'estrazione delle funzionalità e il modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-209">Initialize a new instance of <xref:Microsoft.ML.LearningPipeline> that will include the data loading, data processing/featurization, and model.</span></span> <span data-ttu-id="4d86e-210">Aggiungere il codice seguente come prima riga del metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="4d86e-210">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

<span data-ttu-id="4d86e-211">L'oggetto <xref:Microsoft.ML.Data.TextLoader> è la prima parte della pipeline e carica i dati dei file di training.</span><span class="sxs-lookup"><span data-stu-id="4d86e-211">The <xref:Microsoft.ML.Data.TextLoader> object is the first part of the pipeline, and loads the training file data.</span></span>

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a><span data-ttu-id="4d86e-212">Pre-elaborazione dei dati e progettazione delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="4d86e-212">Data preprocess and feature engineering</span></span>

<span data-ttu-id="4d86e-213">La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="4d86e-213">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="4d86e-214">I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="4d86e-214">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="4d86e-215">L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.</span><span class="sxs-lookup"><span data-stu-id="4d86e-215">Using data without these modeling tasks can produce misleading results.</span></span> <span data-ttu-id="4d86e-216">Le pipeline di trasformazione di ML.NET consentono di comporre un set personalizzato di trasformazioni che vengono applicate ai dati prima di eseguire il training o i test.</span><span class="sxs-lookup"><span data-stu-id="4d86e-216">ML.NET's transform pipelines allow you to compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="4d86e-217">Lo scopo principale delle trasformazioni è l'estrazione delle funzionalità dai dati.</span><span class="sxs-lookup"><span data-stu-id="4d86e-217">The transforms' primary purpose is for data featurization.</span></span> <span data-ttu-id="4d86e-218">Il vantaggio di una pipeline di trasformazione è che dopo la definizione della pipeline di trasformazione, è possibile salvare la pipeline per applicarla ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="4d86e-218">A transform pipeline's advantage is that after transform pipeline definition, save the pipeline to apply it to test data.</span></span>

<span data-ttu-id="4d86e-219">Applicare un <xref:Microsoft.ML.Transforms.TextFeaturizer> per convertire la colonna `SentimentText` in un [vettore numerico](../resources/glossary.md#numerical-feature-vector) denominato `Features` usato dall'algoritmo di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="4d86e-219">Apply a <xref:Microsoft.ML.Transforms.TextFeaturizer> to convert the `SentimentText` column into a [numeric vector](../resources/glossary.md#numerical-feature-vector) called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="4d86e-220">Questo è il passaggio di pre-elaborazione/estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4d86e-220">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="4d86e-221">Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-221">Using additional components available in ML.NET can enable better results with your model.</span></span> <span data-ttu-id="4d86e-222">Aggiungere `TextFeaturizer` alla pipeline con la seguente riga di codice:</span><span class="sxs-lookup"><span data-stu-id="4d86e-222">Add `TextFeaturizer` to the pipeline as the next line of code:</span></span>

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="4d86e-223">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="4d86e-223">Choose a learning algorithm</span></span>

<span data-ttu-id="4d86e-224">L'oggetto <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> è un algoritmo di apprendimento dell'albero delle decisioni da usare in questa pipeline.</span><span class="sxs-lookup"><span data-stu-id="4d86e-224">The <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> object is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="4d86e-225">Come nel passaggio di estrazione delle funzionalità, l'uso dei diversi algoritmi di apprendimento disponibili in ML.NET e la modifica dei relativi parametri determinano risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="4d86e-225">Similar to the featurization step, trying out different learners available in ML.NET and changing their parameters leads to different results.</span></span> <span data-ttu-id="4d86e-226">A scopo di ottimizzazione, è possibile impostare [iperparametri](../resources/glossary.md#hyperparameter) come <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> e <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span><span class="sxs-lookup"><span data-stu-id="4d86e-226">For tuning, you can set [hyperparameters](../resources/glossary.md#hyperparameter) like <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves>, and <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span></span> <span data-ttu-id="4d86e-227">Questi iperparametri vengono impostati prima che qualsiasi elemento possa influire sul modello e sono specifici del modello.</span><span class="sxs-lookup"><span data-stu-id="4d86e-227">These hyperparameters are set before anything affects the model and are model-specific.</span></span> <span data-ttu-id="4d86e-228">Vengono usati per ottimizzare le prestazioni dell'albero delle decisioni, pertanto valori più grandi possono influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4d86e-228">They're used to tune the decision tree for performance, so larger values can negatively impact performance.</span></span>

<span data-ttu-id="4d86e-229">Aggiungere al metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-229">Add the following code to the `Train` method:</span></span>

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a><span data-ttu-id="4d86e-230">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-230">Train the model</span></span>

<span data-ttu-id="4d86e-231">Il training del modello, <xref:Microsoft.ML.PredictionModel%602>, viene eseguito in base al set di dati caricato e trasformato.</span><span class="sxs-lookup"><span data-stu-id="4d86e-231">You train the model, <xref:Microsoft.ML.PredictionModel%602>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="4d86e-232">`pipeline.Train<SentimentData, SentimentPrediction>()` esegue il training della pipeline (carica i dati ed esegue il training dell'algoritmo di estrazione delle funzionalità e dell'algoritmo di apprendimento).</span><span class="sxs-lookup"><span data-stu-id="4d86e-232">`pipeline.Train<SentimentData, SentimentPrediction>()` trains the pipeline (loads the data, trains the featurizer and learner).</span></span> <span data-ttu-id="4d86e-233">L'esperimento non viene eseguito finché questa operazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="4d86e-233">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="4d86e-234">Aggiungere al metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-234">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="4d86e-235">Salvare e restituire il modello sottoposto a training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="4d86e-235">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="4d86e-236">A questo punto, è disponibile un modello che può essere integrato in tutte le applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="4d86e-236">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="4d86e-237">Per salvare il modello in un file ZIP prima della restituzione, aggiungere il codice seguente alla riga successiva in `Train`:</span><span class="sxs-lookup"><span data-stu-id="4d86e-237">To save your model to a .zip file before returning, add the following code to the next line in `Train`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

<span data-ttu-id="4d86e-238">Restituire il modello alla fine del metodo `Train`.</span><span class="sxs-lookup"><span data-stu-id="4d86e-238">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="4d86e-239">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-239">Evaluate the model</span></span>

<span data-ttu-id="4d86e-240">Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida.</span><span class="sxs-lookup"><span data-stu-id="4d86e-240">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="4d86e-241">Nel metodo `Evaluate` viene passato il modello creato in `Train` per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="4d86e-241">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="4d86e-242">Creare il metodo `Evaluate` subito dopo `Train`, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-242">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="4d86e-243">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d86e-243">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="4d86e-244">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="4d86e-244">Loads the test dataset.</span></span>
* <span data-ttu-id="4d86e-245">Crea l'analizzatore binario.</span><span class="sxs-lookup"><span data-stu-id="4d86e-245">Creates the binary evaluator.</span></span>
* <span data-ttu-id="4d86e-246">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="4d86e-246">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="4d86e-247">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="4d86e-247">Displays the metrics.</span></span>

<span data-ttu-id="4d86e-248">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-248">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

<span data-ttu-id="4d86e-249">La classe <xref:Microsoft.ML.Data.TextLoader> carica il nuovo set di dati di test con lo stesso schema.</span><span class="sxs-lookup"><span data-stu-id="4d86e-249">The <xref:Microsoft.ML.Data.TextLoader> class loads the new test dataset with the same schema.</span></span> <span data-ttu-id="4d86e-250">È possibile valutare il modello usando questo set di dati come controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="4d86e-250">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="4d86e-251">Aggiungere al metodo `Evaluate` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-251">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

<span data-ttu-id="4d86e-252">L'oggetto <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> calcola le metriche di qualità per `PredictionModel` usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="4d86e-252">The <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> object computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="4d86e-253">Per visualizzare queste metriche, aggiungere l'analizzatore come riga successiva nel metodo `Evaluate`, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-253">To see those metrics, add the evaluator as the next line in the `Evaluate` method, with the following code:</span></span>

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<span data-ttu-id="4d86e-254"><xref:Microsoft.ML.Models.BinaryClassificationMetrics> contiene le metriche complessive calcolate dagli analizzatori di classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="4d86e-254">The <xref:Microsoft.ML.Models.BinaryClassificationMetrics> contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="4d86e-255">Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche.</span><span class="sxs-lookup"><span data-stu-id="4d86e-255">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="4d86e-256">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-256">Add the following code:</span></span>

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="4d86e-257">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-257">Displaying the metrics for model validation</span></span>

<span data-ttu-id="4d86e-258">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="4d86e-258">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a><span data-ttu-id="4d86e-259">Stimare i risultati dei dati di test con il modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-259">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="4d86e-260">Creare il metodo `Predict` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-260">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="4d86e-261">Il metodo `Predict` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d86e-261">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="4d86e-262">Crea i dati di test.</span><span class="sxs-lookup"><span data-stu-id="4d86e-262">Creates test data.</span></span>
* <span data-ttu-id="4d86e-263">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="4d86e-263">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="4d86e-264">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="4d86e-264">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="4d86e-265">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="4d86e-265">Displays the predicted results.</span></span>

<span data-ttu-id="4d86e-266">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-266">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

<span data-ttu-id="4d86e-267">Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `Predict`:</span><span class="sxs-lookup"><span data-stu-id="4d86e-267">Add some comments to test the trained model's predictions in the `Predict` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

<span data-ttu-id="4d86e-268">Dopo aver creato un modello, è possibile usarlo per stimare il sentiment positivo o negativo dei dati relativi ai commenti mediante il metodo <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4d86e-268">Now that you have a model, you can use that to predict the positive or negative sentiment of the comment data using the <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4d86e-269">Per ottenere una stima, usare `Predict` sui nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="4d86e-269">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="4d86e-270">Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4d86e-270">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="4d86e-271">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="4d86e-271">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="4d86e-272">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="4d86e-272">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="4d86e-273">Operazionalizzazione del modello: stima</span><span class="sxs-lookup"><span data-stu-id="4d86e-273">Model operationalization: prediction</span></span>

<span data-ttu-id="4d86e-274">Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="4d86e-274">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="4d86e-275">Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi.</span><span class="sxs-lookup"><span data-stu-id="4d86e-275">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="4d86e-276">Creare un'intestazione per i risultati con il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-276">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

<span data-ttu-id="4d86e-277">Prima di visualizzare i risultati stimati, combinare il sentiment e la stima per visualizzare il commento originale con il sentiment stimato.</span><span class="sxs-lookup"><span data-stu-id="4d86e-277">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="4d86e-278">Il codice seguente usa il metodo <xref:System.Linq.Enumerable.Zip%2A> per eseguire tale operazione. Aggiungere pertanto il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d86e-278">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="4d86e-279">Ora che `SentimentText` e `Sentiment` sono stati combinati in una classe, è possibile visualizzare i risultati usando il metodo <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="4d86e-279">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

<span data-ttu-id="4d86e-280">Poiché i nomi degli elementi di tupla dedotti sono una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="4d86e-280">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="4d86e-281">A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-281">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="4d86e-282">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="4d86e-282">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="4d86e-283">Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="4d86e-283">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="4d86e-284">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="4d86e-284">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="4d86e-285">Risultati</span><span class="sxs-lookup"><span data-stu-id="4d86e-285">Results</span></span>

<span data-ttu-id="4d86e-286">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4d86e-286">Your results should be similar to the following.</span></span> <span data-ttu-id="4d86e-287">Durante l'elaborazione della pipeline, vengono visualizzati messaggi.</span><span class="sxs-lookup"><span data-stu-id="4d86e-287">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="4d86e-288">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="4d86e-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="4d86e-289">Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="4d86e-289">These have been removed from the following results for clarity.</span></span>

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

<span data-ttu-id="4d86e-290">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="4d86e-290">Congratulations!</span></span> <span data-ttu-id="4d86e-291">A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="4d86e-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="4d86e-292">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="4d86e-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d86e-293">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4d86e-293">Next steps</span></span>

<span data-ttu-id="4d86e-294">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="4d86e-294">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4d86e-295">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="4d86e-295">Understand the problem</span></span>
> * <span data-ttu-id="4d86e-296">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="4d86e-296">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="4d86e-297">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="4d86e-297">Prepare your data</span></span>
> * <span data-ttu-id="4d86e-298">Creare la pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="4d86e-298">Create the learning pipeline</span></span>
> * <span data-ttu-id="4d86e-299">Caricare un classificatore</span><span class="sxs-lookup"><span data-stu-id="4d86e-299">Load a classifier</span></span>
> * <span data-ttu-id="4d86e-300">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-300">Train the model</span></span>
> * <span data-ttu-id="4d86e-301">Valutare il modello con un set di dati diverso</span><span class="sxs-lookup"><span data-stu-id="4d86e-301">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="4d86e-302">Stimare i risultati dei dati di test con il modello</span><span class="sxs-lookup"><span data-stu-id="4d86e-302">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="4d86e-303">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="4d86e-303">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="4d86e-304">Previsione tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="4d86e-304">Taxi Fare Predictor</span></span>](taxi-fare.md)
