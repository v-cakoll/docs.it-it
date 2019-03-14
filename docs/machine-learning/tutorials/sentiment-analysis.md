---
title: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment
description: Informazioni su come usare ML.NET in uno scenario di classificazione binaria per comprendere come usare la stima del sentiment al fine di eseguire l'azione appropriata.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: d7e46b489506f4adad843ba5315afde4c7689b4e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723322"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="a874b-103">Esercitazione: Usare ML.NET in uno scenario di classificazione binaria per l'analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="a874b-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

<span data-ttu-id="a874b-104">Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore del sentiment per la stima del sentiment positivo o negativo tramite un'applicazione console .NET Core con C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a874b-104">This sample tutorial illustrates using ML.NET to create a sentiment classifier to predict either positive or negative sentiment via a .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="a874b-105">Nel mondo del machine learning, questo tipo di stima è noto come nella classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="a874b-105">In the world of machine learning, this type of prediction is known as binary classification.</span></span>

> [!NOTE]
> <span data-ttu-id="a874b-106">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="a874b-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="a874b-107">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a874b-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="a874b-108">Questa esercitazione e l'esempio correlato usano attualmente **ML.NET versione 0.11**.</span><span class="sxs-lookup"><span data-stu-id="a874b-108">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="a874b-109">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="a874b-109">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="a874b-110">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="a874b-110">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="a874b-111">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="a874b-111">Understand the problem</span></span>
> * <span data-ttu-id="a874b-112">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="a874b-112">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="a874b-113">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="a874b-113">Prepare your data</span></span>
> * <span data-ttu-id="a874b-114">Trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="a874b-114">Transform the data</span></span>
> * <span data-ttu-id="a874b-115">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="a874b-115">Train the model</span></span>
> * <span data-ttu-id="a874b-116">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="a874b-116">Evaluate the model</span></span>
> * <span data-ttu-id="a874b-117">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="a874b-117">Predict with the trained model</span></span>
> * <span data-ttu-id="a874b-118">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="a874b-118">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="a874b-119">Panoramica dell'esempio di analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="a874b-119">Sentiment analysis sample overview</span></span>

<span data-ttu-id="a874b-120">L'esempio è un'app console che usa ML.NET per eseguire il training di un modello che classifica e stima il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a874b-120">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="a874b-121">Il set di dati del sentiment Yelp è prodotto dalla University of California, Irvine (UCI) ed è suddiviso in set di dati di training e set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="a874b-121">The Yelp sentiment dataset is from University of California, Irvine (UCI), which is split into a train dataset and a test dataset.</span></span> <span data-ttu-id="a874b-122">L'esempio consente di valutare il modello con il set di dati di test per l'analisi della qualità.</span><span class="sxs-lookup"><span data-stu-id="a874b-122">The sample evaluates the model with the test dataset for quality analysis.</span></span> 

<span data-ttu-id="a874b-123">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="a874b-123">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a874b-124">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a874b-124">Prerequisites</span></span>

* <span data-ttu-id="a874b-125">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="a874b-125">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="a874b-126">File ZIP del set di dati Sentiment Labeled Sentences di UCI</span><span class="sxs-lookup"><span data-stu-id="a874b-126">The UCI Sentiment Labeled Sentences dataset zip file</span></span>](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a><span data-ttu-id="a874b-127">Flusso di lavoro di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="a874b-127">Machine learning workflow</span></span>

<span data-ttu-id="a874b-128">Questa esercitazione segue un flusso di lavoro di apprendimento automatico che consente l'esecuzione del processo in modo ordinato.</span><span class="sxs-lookup"><span data-stu-id="a874b-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="a874b-129">Le fasi del flusso di lavoro sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="a874b-130">**Informazioni sul problema**</span><span class="sxs-lookup"><span data-stu-id="a874b-130">**Understand the problem**</span></span>
2. <span data-ttu-id="a874b-131">**Preparare i dati**</span><span class="sxs-lookup"><span data-stu-id="a874b-131">**Prepare your data**</span></span>
   * <span data-ttu-id="a874b-132">**Caricare i dati**</span><span class="sxs-lookup"><span data-stu-id="a874b-132">**Load the data**</span></span>
   * <span data-ttu-id="a874b-133">**Estrarre le caratteristiche (trasformare i dati)**</span><span class="sxs-lookup"><span data-stu-id="a874b-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="a874b-134">**Compilare ed eseguire il training**</span><span class="sxs-lookup"><span data-stu-id="a874b-134">**Build and train**</span></span> 
   * <span data-ttu-id="a874b-135">**Eseguire il training del modello**</span><span class="sxs-lookup"><span data-stu-id="a874b-135">**Train the model**</span></span>
   * <span data-ttu-id="a874b-136">**Valutazione del modello**</span><span class="sxs-lookup"><span data-stu-id="a874b-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="a874b-137">**Distribuire il modello**</span><span class="sxs-lookup"><span data-stu-id="a874b-137">**Deploy Model**</span></span>
   * <span data-ttu-id="a874b-138">**Usare il modello per le stime**</span><span class="sxs-lookup"><span data-stu-id="a874b-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="a874b-139">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="a874b-139">Understand the problem</span></span>

<span data-ttu-id="a874b-140">È innanzitutto necessario comprendere il problema. A tale scopo, è possibile suddividerlo in diverse parti in grado di supportare la creazione e il training del modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="a874b-141">La suddivisione del problema consente di stimare e valutare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a874b-141">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="a874b-142">Il problema per questa esercitazione consiste nel comprendere il sentiment dei commenti in un sito Web per eseguire l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="a874b-142">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="a874b-143">È possibile suddividere il problema nel testo del sentiment e nel valore del sentiment per i dati con cui si vuole eseguire il training del modello e un valore del sentiment stimato che è possibile valutare e quindi usare a livello operativo.</span><span class="sxs-lookup"><span data-stu-id="a874b-143">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="a874b-144">Sarà quindi necessario **determinare** il sentiment, che consente di selezionare l'attività di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="a874b-144">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="a874b-145">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="a874b-145">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="a874b-146">Per questo problema, sono noti i fatti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-146">With this problem, you know the following facts:</span></span>

<span data-ttu-id="a874b-147">Dati di training: i commenti nel sito Web possono essere positivi (1) o negativi (0) (**sentiment**).</span><span class="sxs-lookup"><span data-stu-id="a874b-147">Training data: website comments can be positive (1) or negative (0) (**sentiment**).</span></span>

<span data-ttu-id="a874b-148">Stimare il **sentiment** di un nuovo commento nel sito Web (positivo o negativo), come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-148">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="a874b-149">Mi piace il personale.</span><span class="sxs-lookup"><span data-stu-id="a874b-149">I love the wait staff here.</span></span> <span data-ttu-id="a874b-150">Sono veloci.</span><span class="sxs-lookup"><span data-stu-id="a874b-150">They rock.</span></span>
* <span data-ttu-id="a874b-151">Questo posto offre i primi peggiori.</span><span class="sxs-lookup"><span data-stu-id="a874b-151">This place has the worst soup.</span></span>

<span data-ttu-id="a874b-152">L'algoritmo di Machine Learning di classificazione è il più adatto per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="a874b-152">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-algorithm"></a><span data-ttu-id="a874b-153">Informazioni sull'algoritmo di classificazione</span><span class="sxs-lookup"><span data-stu-id="a874b-153">About the classification algorithm</span></span>

<span data-ttu-id="a874b-154">La classificazione è un algoritmo di Machine Learning che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-154">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="a874b-155">È ad esempio possibile usare la classificazione per:</span><span class="sxs-lookup"><span data-stu-id="a874b-155">For example, you can use classification to:</span></span>

* <span data-ttu-id="a874b-156">Identificare il sentiment come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a874b-156">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="a874b-157">Classificare messaggi di posta elettronica come posta indesiderata o legittima.</span><span class="sxs-lookup"><span data-stu-id="a874b-157">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="a874b-158">Determinare se le analisi di laboratorio di un paziente indicano la presenza di cellule tumorali.</span><span class="sxs-lookup"><span data-stu-id="a874b-158">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="a874b-159">Suddividere in categorie i clienti in base alla relativa propensione a rispondere a una campagna di vendita.</span><span class="sxs-lookup"><span data-stu-id="a874b-159">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="a874b-160">Gli algoritmi di classificazione sono spesso di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-160">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="a874b-161">Binarie: A o B.</span><span class="sxs-lookup"><span data-stu-id="a874b-161">Binary: either A or B.</span></span>
* <span data-ttu-id="a874b-162">Multiclasse: più categorie che possono essere stimate tramite un singolo modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-162">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="a874b-163">Dato che i commenti nel sito Web devono essere classificati come positivi o negativi, si usa l'algoritmo di classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="a874b-163">Because the website comments need to be classified as either positive or negative, you use the Binary Classification algorithm.</span></span> 

## <a name="create-a-console-application"></a><span data-ttu-id="a874b-164">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="a874b-164">Create a console application</span></span>

1. <span data-ttu-id="a874b-165">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a874b-165">Open Visual Studio 2017.</span></span> <span data-ttu-id="a874b-166">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="a874b-166">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="a874b-167">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="a874b-167">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="a874b-168">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="a874b-168">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="a874b-169">Nella casella di testo **Nome** digitare "SentimentAnalysis" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="a874b-169">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="a874b-170">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:</span><span class="sxs-lookup"><span data-stu-id="a874b-170">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="a874b-171">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="a874b-171">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="a874b-172">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a874b-172">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="a874b-173">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="a874b-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a874b-174">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a874b-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a874b-175">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a874b-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a874b-176">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="a874b-176">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="a874b-177">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="a874b-177">Prepare your data</span></span>

1. <span data-ttu-id="a874b-178">Scaricare il [file ZIP del set di dati Sentiment Labeled Sentences UCI (vedere le citazioni nella nota seguente)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) e decomprimere il file.</span><span class="sxs-lookup"><span data-stu-id="a874b-178">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="a874b-179">Copiare il file `yelp_labelled.txt` nella directory *Data* creata.</span><span class="sxs-lookup"><span data-stu-id="a874b-179">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

> [!NOTE]
> <span data-ttu-id="a874b-180">I set di dati usati in questa esercitazione provengono da 'From Group to Individual Labels using Deep Features', Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="a874b-180">The datasets this tutorial uses are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="a874b-181">al,.</span><span class="sxs-lookup"><span data-stu-id="a874b-181">al,.</span></span> <span data-ttu-id="a874b-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. e Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="a874b-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="a874b-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="a874b-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="a874b-184">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="a874b-184">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

3. <span data-ttu-id="a874b-185">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file `yelp_labeled.txt` e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a874b-185">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="a874b-186">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="a874b-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="a874b-187">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="a874b-187">Create classes and define paths</span></span>

<span data-ttu-id="a874b-188">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="a874b-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="a874b-189">È necessario creare due campi globali per contenere il percorso del file del set di dati scaricato di recente e il percorso del file modello salvato:</span><span class="sxs-lookup"><span data-stu-id="a874b-189">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="a874b-190">`_dataPath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-190">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="a874b-191">`_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="a874b-191">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="a874b-192">Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:</span><span class="sxs-lookup"><span data-stu-id="a874b-192">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="a874b-193">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="a874b-193">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="a874b-194">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="a874b-194">Add a new class to your project:</span></span>

1. <span data-ttu-id="a874b-195">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a874b-195">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="a874b-196">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="a874b-196">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="a874b-197">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a874b-197">Then, select the **Add** button.</span></span>

    <span data-ttu-id="a874b-198">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="a874b-198">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a874b-199">Aggiungere l'istruzione `using` seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="a874b-199">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="a874b-200">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `SentimentData` e `SentimentPrediction`, al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="a874b-200">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="a874b-201">La classe del set di dati di input, `SentimentData`, include un valore `string` per il commento (`SentimentText`) e un valore `bool` (`Sentiment`) che include un valore per il sentiment positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a874b-201">The input dataset class, `SentimentData`, has a `string` for the comment (`SentimentText`) and a `bool` (`Sentiment`) that has a value for sentiment of either positive or negative.</span></span> <span data-ttu-id="a874b-202">A entrambi i campi sono associati attributi <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29>.</span><span class="sxs-lookup"><span data-stu-id="a874b-202">Both fields have <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> attributes attached to them.</span></span> <span data-ttu-id="a874b-203">Questo attributo descrive l'ordine di ogni campo nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-203">This attribute describes the order of each field in the data file.</span></span>  <span data-ttu-id="a874b-204">Inoltre, la proprietà `Sentiment` include un elemento <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> per designarlo come il campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="a874b-204">In addition, the `Sentiment` property has a <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> to designate it as the `Label` field.</span></span> <span data-ttu-id="a874b-205">`SentimentPrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-205">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="a874b-206">Dispone di un singolo valore booleano (`Sentiment`) e un attributo `ColumnName` `PredictedLabel`.</span><span class="sxs-lookup"><span data-stu-id="a874b-206">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="a874b-207">`Label` viene usato per creare il modello ed eseguirne il training, nonché con il set di dati suddiviso per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-207">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="a874b-208">`PredictedLabel` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="a874b-208">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="a874b-209">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-209">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="a874b-210">Quando si crea un modello con ML.NET, si inizia creando un'istanza di <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="a874b-210">When building a model with ML.NET you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="a874b-211">A livello concettuale `MLContext` è paragonabile all'uso di `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="a874b-211">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="a874b-212">L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a874b-212">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="a874b-213">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="a874b-213">Initialize variables in Main</span></span>

<span data-ttu-id="a874b-214">Creare una variabile denominata `mlContext` e inizializzarla con una nuova istanza di `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="a874b-214">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="a874b-215">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="a874b-215">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

<span data-ttu-id="a874b-216">Aggiungere il codice seguente al metodo `Main` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="a874b-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallLoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

<span data-ttu-id="a874b-217">Il metodo `LoadData` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-217">The `LoadData` method executes the following tasks:</span></span>

* <span data-ttu-id="a874b-218">Carica i dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-218">Loads the data.</span></span>
* <span data-ttu-id="a874b-219">Suddivide il set di dati caricati in set di dati di training e di test.</span><span class="sxs-lookup"><span data-stu-id="a874b-219">Splits the loaded dataset into train and test datasets.</span></span>
* <span data-ttu-id="a874b-220">Restituisce i set di dati di training e di test divisi.</span><span class="sxs-lookup"><span data-stu-id="a874b-220">Returns the split train and test datasets.</span></span>

<span data-ttu-id="a874b-221">Creare il metodo `LoadData` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-221">Create the `LoadData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static (IDataView trainSet, IDataView testSet) LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a><span data-ttu-id="a874b-222">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="a874b-222">Load the data</span></span>

<span data-ttu-id="a874b-223">Poiché il tipo di modello di dati `SentimentData` creato in precedenza corrisponde allo schema del set di dati, è possibile combinare l'inizializzazione, il mapping e il caricamento del set di dati in un'unica riga di codice usando il wrapper `MLContext.Data.ReadFromTextFile` per <xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="a874b-223">Since your previously created `SentimentData` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code using the `MLContext.Data.ReadFromTextFile` wrapper for <xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29>.</span></span> <span data-ttu-id="a874b-224">Verrà restituita un'istanza di <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="a874b-224">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> 

 <span data-ttu-id="a874b-225">Come input e output di `Transforms`, una `DataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="a874b-225">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="a874b-226">In ML.NET i dati sono simili a una visualizzazione SQL.</span><span class="sxs-lookup"><span data-stu-id="a874b-226">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="a874b-227">Vengono valutati in modalità differita, sono schematizzati ed eterogenei.</span><span class="sxs-lookup"><span data-stu-id="a874b-227">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="a874b-228">L'oggetto è la prima parte della pipeline e carica i dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-228">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="a874b-229">Per questa esercitazione, carica un set di dati con commenti e il sentiment positivo o negativo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a874b-229">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="a874b-230">Queste informazioni vengono usate per creare il modello ed eseguirne il training.</span><span class="sxs-lookup"><span data-stu-id="a874b-230">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="a874b-231">Aggiungere il codice seguente come prima riga del metodo `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="a874b-231">Add the following code as the first line of the `LoadData` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="a874b-232">Dividere il set di dati per il training e il test del modello</span><span class="sxs-lookup"><span data-stu-id="a874b-232">Split the dataset for model training and testing</span></span>

<span data-ttu-id="a874b-233">Successivamente, è necessario sia un set di dati di training per il training del modello che un set di dati di test per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-233">Next, you need both a training dataset to train the model and a test dataset to evaluate the model.</span></span> <span data-ttu-id="a874b-234">Usare `MLContext.BinaryClassification.TrainTestSplit` che esegue il wrapping di <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> per dividere il set di dati caricato in set di dati di training e di test e restituirli all'interno di un <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span><span class="sxs-lookup"><span data-stu-id="a874b-234">Use the `MLContext.BinaryClassification.TrainTestSplit` which wraps <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> to split the loaded dataset into train and test datasets and return them inside of a <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span></span> <span data-ttu-id="a874b-235">È possibile specificare la frazione di dati per il set di test con il parametro `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="a874b-235">You can specify the fraction of data for the test set with the `testFraction`parameter.</span></span> <span data-ttu-id="a874b-236">Il valore predefinito è 10%, ma in questo caso si usa il 20% per usare più dati per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="a874b-236">The default is 10% but you use 20% in this case to use more data for the evaluation.</span></span>  

<span data-ttu-id="a874b-237">Per dividere i dati caricati nei set di dati necessari, aggiungere il codice seguente come riga successiva nel metodo `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="a874b-237">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData` method:</span></span>

[!code-csharp[SplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

<span data-ttu-id="a874b-238">Restituire `splitDataView` alla fine del metodo `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="a874b-238">Return the `splitDataView` at the end of the `LoadData` method:</span></span>

[!code-csharp[ReturnSplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="a874b-239">Compilare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="a874b-239">Build and train the model</span></span>

<span data-ttu-id="a874b-240">Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="a874b-240">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="a874b-241">Il metodo `BuildAndTrainModel` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-241">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="a874b-242">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-242">Extracts and transforms the data.</span></span>
* <span data-ttu-id="a874b-243">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-243">Trains the model.</span></span>
* <span data-ttu-id="a874b-244">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="a874b-244">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="a874b-245">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-245">Returns the model.</span></span>

<span data-ttu-id="a874b-246">Creare il metodo `Train` subito dopo il metodo `Main`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-246">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

<span data-ttu-id="a874b-247">Si noti che vengono passati due parametri al metodo Train: `MLContext` per il contesto (`mlContext`) e `IDataView` per il set di dati di training (`splitTrainSet`).</span><span class="sxs-lookup"><span data-stu-id="a874b-247">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and an `IDataView`for the training dataset (`splitTrainSet`).</span></span> 

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="a874b-248">Estrarre e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="a874b-248">Extract and transform the data</span></span>

<span data-ttu-id="a874b-249">La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="a874b-249">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="a874b-250">I dati non elaborati spesso sono non pertinenti e poco affidabili e possono presentare valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="a874b-250">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="a874b-251">L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.</span><span class="sxs-lookup"><span data-stu-id="a874b-251">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="a874b-252">Le pipeline di trasformazione di ML.NET compongono un set personalizzato di trasformazioni che vengono applicate ai dati prima di eseguire il training o i test.</span><span class="sxs-lookup"><span data-stu-id="a874b-252">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="a874b-253">Lo scopo principale delle trasformazioni è l'[estrazione delle caratteristiche](../resources/glossary.md#feature-engineering) dai dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-253">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="a874b-254">Gli algoritmi di apprendimento automatico sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) in modo da trasformare successivamente i dati testuali in un formato riconoscibile da tali algoritmi.</span><span class="sxs-lookup"><span data-stu-id="a874b-254">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="a874b-255">Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="a874b-255">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="a874b-256">Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` che estrae le caratteristiche della colonna di testo (`SentimentText`) e le trasforma in un vettore numerico denominato `Features` che viene usato dall'algoritmo di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="a874b-256">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="a874b-257">Questa è una chiamata di wrapper che restituisce un oggetto <xref:Microsoft.ML.Data.EstimatorChain%601> che sarà effettivamente una pipeline.</span><span class="sxs-lookup"><span data-stu-id="a874b-257">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="a874b-258">Assegnare un nome a questa `pipeline` poiché successivamente si aggiungerà l'algoritmo di training all'oggetto `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="a874b-258">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="a874b-259">Aggiungere il codice seguente come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="a874b-259">Add this as the next line of code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> <span data-ttu-id="a874b-260">In ML.NET versione 0.10 è stato modificato l'ordine dei parametri Transforms.</span><span class="sxs-lookup"><span data-stu-id="a874b-260">ML.NET Version 0.10 changed the order of the Transform parameters.</span></span> <span data-ttu-id="a874b-261">Non verranno segnalati errori fino a quando non si esegue l'applicazione e si compila il modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-261">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="a874b-262">Usare i nomi dei parametri per Transforms come illustrato nel frammento di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="a874b-262">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="a874b-263">Questo è il passaggio di pre-elaborazione/estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a874b-263">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="a874b-264">Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-264">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="a874b-265">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="a874b-265">Choose a learning algorithm</span></span>

<span data-ttu-id="a874b-266">Per aggiungere l'algoritmo di training, chiamare il metodo wrapper `mlContext.BinaryClassification.Trainers.FastTree` che restituisce un oggetto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>,</span><span class="sxs-lookup"><span data-stu-id="a874b-266">To add the trainer, call the `mlContext.BinaryClassification.Trainers.FastTree` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="a874b-267">un algoritmo di apprendimento basato su un albero delle decisioni che si userà in questa pipeline.</span><span class="sxs-lookup"><span data-stu-id="a874b-267">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="a874b-268">L'oggetto `FastTreeBinaryClassificationTrainer` viene aggiunto alla `pipeline` e accetta l'oggetto `SentimentText` (`Features`) da cui sono state estratte le caratteristiche e i parametri di input `Label` per l'apprendimento in base ai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="a874b-268">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="a874b-269">Aggiungere al metodo `BuildAndTrainModel` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-269">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="a874b-270">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="a874b-270">Train the model</span></span>

<span data-ttu-id="a874b-271">Il training del modello, <xref:Microsoft.ML.Data.TransformerChain%601>, viene eseguito in base al set di dati caricato e trasformato.</span><span class="sxs-lookup"><span data-stu-id="a874b-271">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="a874b-272">Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati.</span><span class="sxs-lookup"><span data-stu-id="a874b-272">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> method while providing the already loaded training data.</span></span> <span data-ttu-id="a874b-273">Viene così restituito un modello da usare per le stime.</span><span class="sxs-lookup"><span data-stu-id="a874b-273">This returns a model to use for predictions.</span></span> <span data-ttu-id="a874b-274">`pipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata.</span><span class="sxs-lookup"><span data-stu-id="a874b-274">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="a874b-275">L'esperimento non viene eseguito finché non viene eseguito il metodo `.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="a874b-275">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="a874b-276">Aggiungere al metodo `BuildAndTrainModel` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-276">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="a874b-277">Salvare e restituire il modello sottoposto a training da usare per la valutazione</span><span class="sxs-lookup"><span data-stu-id="a874b-277">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="a874b-278">A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain%601> che può essere integrato nelle applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="a874b-278">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="a874b-279">Restituire il modello alla fine del metodo `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="a874b-279">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="a874b-280">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="a874b-280">Evaluate the model</span></span>

<span data-ttu-id="a874b-281">Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida.</span><span class="sxs-lookup"><span data-stu-id="a874b-281">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="a874b-282">Nel metodo `Evaluate` viene passato il modello creato in `BuildAndTrainModel` per la valutazione.</span><span class="sxs-lookup"><span data-stu-id="a874b-282">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="a874b-283">Creare il metodo `Evaluate` subito dopo `BuildAndTrainModel`, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-283">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

<span data-ttu-id="a874b-284">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-284">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="a874b-285">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="a874b-285">Loads the test dataset.</span></span>
* <span data-ttu-id="a874b-286">Crea l'analizzatore binaryclassification.</span><span class="sxs-lookup"><span data-stu-id="a874b-286">Creates the binaryclassification evaluator.</span></span>
* <span data-ttu-id="a874b-287">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="a874b-287">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="a874b-288">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="a874b-288">Displays the metrics.</span></span>

<span data-ttu-id="a874b-289">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-289">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

<span data-ttu-id="a874b-290">Si useranno quindi il parametro `model` di machine learning automatico (un oggetto Transformer) e il parametro `splitTestSet` per l'input di caratteristiche e la generazione di stime.</span><span class="sxs-lookup"><span data-stu-id="a874b-290">Next, you'll use the machine learning `model` parameter (a transformer) and the `splitTestSet` parameter to input the features and return predictions.</span></span> <span data-ttu-id="a874b-291">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="a874b-291">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

<span data-ttu-id="a874b-292">Il metodo `mlContext.BinaryClassification.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="a874b-292">The `mlContext.BinaryClassification.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="a874b-293">Restituisce un oggetto <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> che contiene le metriche complessive calcolate dagli analizzatori della classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="a874b-293">It returns a <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> object that contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="a874b-294">Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche.</span><span class="sxs-lookup"><span data-stu-id="a874b-294">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="a874b-295">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="a874b-295">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="a874b-296">Visualizzazione delle metriche per la convalida del modello</span><span class="sxs-lookup"><span data-stu-id="a874b-296">Displaying the metrics for model validation</span></span>

<span data-ttu-id="a874b-297">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="a874b-297">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

<span data-ttu-id="a874b-298">Per salvare il modello in un file con estensione zip prima della restituzione, aggiungere il codice seguente per chiamare il metodo `SaveModelAsFile` come riga successiva in `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="a874b-298">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="a874b-299">Salvare il modello come file con estensione zip</span><span class="sxs-lookup"><span data-stu-id="a874b-299">Save the model as a.zip file</span></span>

<span data-ttu-id="a874b-300">Creare il metodo `SaveModelAsFile` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-300">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="a874b-301">Il metodo `SaveModelAsFile` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-301">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="a874b-302">Salva il modello come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="a874b-302">Saves the model as a .zip file.</span></span>

<span data-ttu-id="a874b-303">A questo punto, creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a874b-303">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="a874b-304">L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="a874b-304">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="a874b-305">Per salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="a874b-305">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="a874b-306">Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="a874b-306">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="a874b-307">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="a874b-307">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="a874b-308">È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-308">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="a874b-309">Stimare il risultato dei dati di test con il modello salvato</span><span class="sxs-lookup"><span data-stu-id="a874b-309">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="a874b-310">Creare il metodo `UseModelWithSingleItem` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-310">Create the `UseModelWithSingleItem` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="a874b-311">Il metodo `UseModelWithSingleItem` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-311">The `UseModelWithSingleItem` method executes the following tasks:</span></span>

* <span data-ttu-id="a874b-312">Crea un singolo commento di dati di test.</span><span class="sxs-lookup"><span data-stu-id="a874b-312">Creates a single comment of test data.</span></span>
* <span data-ttu-id="a874b-313">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="a874b-313">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="a874b-314">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="a874b-314">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="a874b-315">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="a874b-315">Displays the predicted results.</span></span>

<span data-ttu-id="a874b-316">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-316">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallUseModelWithSingleItem](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

<span data-ttu-id="a874b-317">`model` è un oggetto `transformer` che opera su molte righe di dati, ma in un ambiente produzione è spesso necessario eseguire stime su singoli esempi.</span><span class="sxs-lookup"><span data-stu-id="a874b-317">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="a874b-318"><xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="a874b-318">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="a874b-319">A questo punto si aggiunge il codice seguente per creare l'istanza di `PredictionEngine` come prima riga nel metodo `Predict`:</span><span class="sxs-lookup"><span data-stu-id="a874b-319">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
<span data-ttu-id="a874b-320">Aggiungere un commento per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="a874b-320">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 <span data-ttu-id="a874b-321">È possibile usare questo commento per eseguire una stima del sentiment positivo o negativo di una singola istanza dei dati relativi ai commenti.</span><span class="sxs-lookup"><span data-stu-id="a874b-321">You can use that to predict the positive or negative sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="a874b-322">Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-322">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="a874b-323">Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a874b-323">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="a874b-324">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="a874b-324">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="a874b-325">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a874b-325">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a><span data-ttu-id="a874b-326">Usare il modello: stima</span><span class="sxs-lookup"><span data-stu-id="a874b-326">Use the model: prediction</span></span>

<span data-ttu-id="a874b-327">Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a874b-327">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="a874b-328">Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi.</span><span class="sxs-lookup"><span data-stu-id="a874b-328">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="a874b-329">Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-329">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="a874b-330">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="a874b-330">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="a874b-331">Creare il metodo `UseLoadedModelWithBatchItems` subito prima del metodo `SaveModelAsFile`, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-331">Create the `UseLoadedModelWithBatchItems` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

<span data-ttu-id="a874b-332">Il metodo `UseLoadedModelWithBatchItems` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a874b-332">The `UseLoadedModelWithBatchItems` method executes the following tasks:</span></span>

* <span data-ttu-id="a874b-333">Crea i dati di test in batch.</span><span class="sxs-lookup"><span data-stu-id="a874b-333">Creates batch test data.</span></span>
* <span data-ttu-id="a874b-334">Esegue la stima del sentiment in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="a874b-334">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="a874b-335">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="a874b-335">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="a874b-336">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="a874b-336">Displays the predicted results.</span></span>

<span data-ttu-id="a874b-337">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `UseModelWithSingleItem`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-337">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

<span data-ttu-id="a874b-338">Aggiungere alcuni commenti per testare le stime del modello sottoposto a training nel metodo `UseLoadedModelWithBatchItems`:</span><span class="sxs-lookup"><span data-stu-id="a874b-338">Add some comments to test the trained model's predictions in the `UseLoadedModelWithBatchItems` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

<span data-ttu-id="a874b-339">Caricare il modello</span><span class="sxs-lookup"><span data-stu-id="a874b-339">Load the model</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

<span data-ttu-id="a874b-340">Dopo aver creato un modello, è possibile usarlo per stimare il sentiment positivo o negativo dei dati relativi ai commenti usando il metodo <xref:Microsoft.ML.ITransformer.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="a874b-340">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="a874b-341">Per ottenere una stima, usare `Predict` sui nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="a874b-341">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="a874b-342">Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a874b-342">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="a874b-343">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="a874b-343">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="a874b-344">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a874b-344">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="a874b-345">Aggiungere il codice seguente al metodo `UseLoadedModelWithBatchItems` per le stime:</span><span class="sxs-lookup"><span data-stu-id="a874b-345">Add the following code to the `UseLoadedModelWithBatchItems` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a><span data-ttu-id="a874b-346">Usare il modello caricato per la stima</span><span class="sxs-lookup"><span data-stu-id="a874b-346">Use the loaded model for prediction</span></span>

<span data-ttu-id="a874b-347">Visualizzare `SentimentText` e la stima del sentiment corrispondente allo scopo di condividere i risultati e agire su di essi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a874b-347">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="a874b-348">Questa operazione viene denominata operazionalizzazione, ovvero l'uso dei dati restituiti come parte dei criteri operativi.</span><span class="sxs-lookup"><span data-stu-id="a874b-348">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="a874b-349">Creare un'intestazione per i risultati con il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-349">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="a874b-350">Prima di visualizzare i risultati stimati, combinare il sentiment e la stima per visualizzare il commento originale con il sentiment stimato.</span><span class="sxs-lookup"><span data-stu-id="a874b-350">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="a874b-351">Il codice seguente usa il metodo <xref:System.Linq.Enumerable.Zip%2A> per eseguire tale operazione. Aggiungere pertanto il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a874b-351">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="a874b-352">Ora che `SentimentText` e `Sentiment` sono stati combinati in una classe, è possibile visualizzare i risultati usando il metodo <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="a874b-352">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

<span data-ttu-id="a874b-353">Poiché i nomi degli elementi di tupla dedotti sono una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a874b-353">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="a874b-354">A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a874b-354">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="a874b-355">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="a874b-355">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="a874b-356">Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="a874b-356">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="a874b-357">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="a874b-357">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="a874b-358">Risultati</span><span class="sxs-lookup"><span data-stu-id="a874b-358">Results</span></span>

<span data-ttu-id="a874b-359">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a874b-359">Your results should be similar to the following.</span></span> <span data-ttu-id="a874b-360">Durante l'elaborazione della pipeline, vengono visualizzati messaggi.</span><span class="sxs-lookup"><span data-stu-id="a874b-360">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="a874b-361">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="a874b-361">You may see warnings, or processing messages.</span></span> <span data-ttu-id="a874b-362">Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="a874b-362">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="a874b-363">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a874b-363">Congratulations!</span></span> <span data-ttu-id="a874b-364">A questo punto, è stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima del sentiment dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a874b-364">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> 

<span data-ttu-id="a874b-365">La creazione di modelli efficaci è un processo iterativo.</span><span class="sxs-lookup"><span data-stu-id="a874b-365">Building successful models is an iterative process.</span></span> <span data-ttu-id="a874b-366">Questo modello ha inizialmente una qualità inferiore, perché l'esercitazione usa set di dati di dimensioni contenute per consentire il training rapido del modello.</span><span class="sxs-lookup"><span data-stu-id="a874b-366">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="a874b-367">Se non si è soddisfatti della qualità del modello, è possibile provare a migliorarla fornendo set di dati di training più grandi o scegliendo algoritmi di training diversi con iperparametri diversi per ogni algoritmo.</span><span class="sxs-lookup"><span data-stu-id="a874b-367">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span>

<span data-ttu-id="a874b-368">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="a874b-368">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a874b-369">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a874b-369">Next steps</span></span>

<span data-ttu-id="a874b-370">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="a874b-370">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="a874b-371">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="a874b-371">Understand the problem</span></span>
> * <span data-ttu-id="a874b-372">Selezionare l'algoritmo di Machine Learning appropriato</span><span class="sxs-lookup"><span data-stu-id="a874b-372">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="a874b-373">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="a874b-373">Prepare your data</span></span>
> * <span data-ttu-id="a874b-374">Trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="a874b-374">Transform the data</span></span>
> * <span data-ttu-id="a874b-375">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="a874b-375">Train the model</span></span>
> * <span data-ttu-id="a874b-376">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="a874b-376">Evaluate the model</span></span>
> * <span data-ttu-id="a874b-377">Eseguire stime con il modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="a874b-377">Predict with the trained model</span></span>
> * <span data-ttu-id="a874b-378">Eseguire distribuzione e stime con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="a874b-378">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="a874b-379">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a874b-379">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a874b-380">Classificazione del problema</span><span class="sxs-lookup"><span data-stu-id="a874b-380">Issue Classification</span></span>](github-issue-classification.md)
