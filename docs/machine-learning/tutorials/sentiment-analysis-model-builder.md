---
title: 'Esercitazione: Analizzare il sentiment - classificazione binariaTutorial: Analyze sentiment - binary classification'
description: Questa esercitazione illustra come creare un'applicazione Razor Pages che classifica il sentiment dai commenti del sito Web ed esegue l'azione appropriata. Il classificatore di valutazione binario usa Model Builder in Visual Studio.The binary sentiment classifier uses Model Builder in Visual Studio.
ms.date: 11/21/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: 3419afb36d73599b8fdb0417a8c0cc4057f60089
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187640"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="0aa8a-104">Esercitazione: Analizzare il sentiment dei commenti del sito Web in un'applicazione Web utilizzando ML.NET Model Builder</span><span class="sxs-lookup"><span data-stu-id="0aa8a-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="0aa8a-105">Scopri come analizzare il sentiment dei commenti in tempo reale all'interno di un'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-105">Learn how to analyze sentiment from comments in real-time inside a web application.</span></span>

<span data-ttu-id="0aa8a-106">Questa esercitazione illustra come creare un'applicazione di ASP.NET Core Razor Pages che classifica il sentiment dei commenti del sito Web in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real-time.</span></span>

<span data-ttu-id="0aa8a-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="0aa8a-108">Creare un'applicazione ASP.NET Core Razor PagesCreate an ASP.NET Core Razor Pages application</span><span class="sxs-lookup"><span data-stu-id="0aa8a-108">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="0aa8a-109">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="0aa8a-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="0aa8a-110">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="0aa8a-110">Choose a scenario</span></span>
> - <span data-ttu-id="0aa8a-111">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="0aa8a-111">Load the data</span></span>
> - <span data-ttu-id="0aa8a-112">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="0aa8a-112">Train the model</span></span>
> - <span data-ttu-id="0aa8a-113">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="0aa8a-113">Evaluate the model</span></span>
> - <span data-ttu-id="0aa8a-114">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="0aa8a-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="0aa8a-115">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="0aa8a-116">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/machinelearning-samples.You](https://github.com/dotnet/machinelearning-samples) can find the source code for this tutorial at the dotnet/machinelearning-samples repository.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="0aa8a-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0aa8a-117">Pre-requisites</span></span>

<span data-ttu-id="0aa8a-118">Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="0aa8a-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="0aa8a-119">Creare un'applicazione Razor PagesCreate a Razor Pages application</span><span class="sxs-lookup"><span data-stu-id="0aa8a-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="0aa8a-120">Creare **un'applicazione ASP.NET pagine razor di base**.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="0aa8a-121">Aprire Visual Studio e selezionare **File > nuovo > progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span>
    1. <span data-ttu-id="0aa8a-122">Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span>
    1. <span data-ttu-id="0aa8a-123">Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-123">Then select the **ASP.NET Core Web Application** project template.</span></span>
    1. <span data-ttu-id="0aa8a-124">Nella casella di testo **Nome** digitare "SentimentRazor".</span><span class="sxs-lookup"><span data-stu-id="0aa8a-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="0aa8a-125">Assicurarsi che **l'opzione Inserisci soluzione e progetto nella stessa directory** sia **deselezionata** (VS 2019) o **l'opzione Crea directory per soluzione** sia **selezionata** (VS 2017).</span><span class="sxs-lookup"><span data-stu-id="0aa8a-125">Make sure **Place solution and project in the same directory** is **unchecked** (VS 2019), or **Create directory for solution** is **checked** (VS 2017).</span></span>
    1. <span data-ttu-id="0aa8a-126">Selezionare il pulsante **OK.**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-126">Select the **OK** button.</span></span>
    1. <span data-ttu-id="0aa8a-127">Scegliere **Applicazione Web** nella finestra che visualizza i diversi tipi di ASP.NET progetti principali, quindi fare clic sul pulsante **OK.**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-127">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="0aa8a-128">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="0aa8a-128">Prepare and understand the data</span></span>

<span data-ttu-id="0aa8a-129">Scarica [Wikipedia disintossicazione set di dati](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="0aa8a-129">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="0aa8a-130">Quando si apre la pagina Web, fare clic con il pulsante destro del mouse sulla pagina, selezionare **Salva con** nome e salvare il file in un punto qualsiasi del computer.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-130">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span>

<span data-ttu-id="0aa8a-131">Ogni riga del set di dati *wikipedia-detox-250-line-data.tsv* rappresenta una revisione diversa lasciata da un utente su Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-131">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="0aa8a-132">La prima colonna rappresenta il sentiment del testo (0 è non tossico, 1 è tossico) e la seconda colonna rappresenta il commento lasciato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-132">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="0aa8a-133">Le colonne sono separate da tabulazioni.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-133">The columns are separated by tabs.</span></span> <span data-ttu-id="0aa8a-134">I dati sono simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-134">The data looks like the following:</span></span>

| <span data-ttu-id="0aa8a-135">Valutazione</span><span class="sxs-lookup"><span data-stu-id="0aa8a-135">Sentiment</span></span> | <span data-ttu-id="0aa8a-136">SentimentText</span><span class="sxs-lookup"><span data-stu-id="0aa8a-136">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="0aa8a-137">1</span><span class="sxs-lookup"><span data-stu-id="0aa8a-137">1</span></span> | <span data-ttu-id="0aa8a-138">Amico, sei un caricamento maleducato che l'immagine di Carl indietro, altrimenti.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-138">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="0aa8a-139">1</span><span class="sxs-lookup"><span data-stu-id="0aa8a-139">1</span></span> | <span data-ttu-id="0aa8a-140">" OK!</span><span class="sxs-lookup"><span data-stu-id="0aa8a-140">== OK!</span></span> <span data-ttu-id="0aa8a-141">IM GOING TO VANDALIzeI WILD ONES WIKI THEN!!!</span><span class="sxs-lookup"><span data-stu-id="0aa8a-141">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="0aa8a-142">0</span><span class="sxs-lookup"><span data-stu-id="0aa8a-142">0</span></span> | <span data-ttu-id="0aa8a-143">Spero che questo aiuti.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-143">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="0aa8a-144">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="0aa8a-144">Choose a scenario</span></span>

![Creazione guidata Generatore di modelli in Visual StudioModel Builder wizard in Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="0aa8a-146">Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-146">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span>

1. <span data-ttu-id="0aa8a-147">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *SentimentRazor* e scegliere **Aggiungi** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-147">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="0aa8a-148">Per questo esempio, lo scenario è l'analisi del sentiment.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-148">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="0aa8a-149">Nel passaggio *dello scenario* dello strumento Generatore di modelli, selezionare lo scenario Analisi **del sentiment.**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-149">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="0aa8a-150">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="0aa8a-150">Load the data</span></span>

<span data-ttu-id="0aa8a-151">Model Builder accetta dati da due origini, un database `csv` `tsv` di SQL Server o un file locale in o formato.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-151">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="0aa8a-152">Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare **File** dall'elenco a discesa delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-152">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="0aa8a-153">Selezionare il pulsante accanto alla casella di testo **Selezionare un file** e utilizzare Esplora file per sfogliare e selezionare il file *wikipedia-detox-250-line-data.tsv.*</span><span class="sxs-lookup"><span data-stu-id="0aa8a-153">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="0aa8a-154">Scegli **Valutazione** nell'elenco a discesa **Colonna da prevedere (etichetta).**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-154">Choose **Sentiment** in the **Column to Predict (Label)** dropdown.</span></span>
1. <span data-ttu-id="0aa8a-155">Lasciare i valori predefiniti per l'elenco a discesa **Colonne di input (funzionalità).**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-155">Leave the default values for the **Input Columns (Features)** dropdown.</span></span>
1. <span data-ttu-id="0aa8a-156">Selezionare il collegamento **Train** per passare al passaggio successivo nello strumento Generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-156">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="0aa8a-157">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="0aa8a-157">Train the model</span></span>

<span data-ttu-id="0aa8a-158">L'attività di apprendimento automatico usata per eseguire il training del modello di analisi del sentiment in questa esercitazione è la classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-158">The machine learning task used to train the sentiment analysis model in this tutorial is binary classification.</span></span> <span data-ttu-id="0aa8a-159">Durante il processo di training del modello, Model Builder esegue il training di modelli separati usando algoritmi e impostazioni di classificazione binaria diversi per trovare il modello con le prestazioni migliori per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-159">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="0aa8a-160">Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-160">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="0aa8a-161">Model Builder seleziona automaticamente un valore predefinito per **Time to train (seconds)** in base alle dimensioni dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-161">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="0aa8a-162">Anche se Model Builder imposta il valore di **Time to train (secondi)** su 10 secondi, aumentarlo a 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-162">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="0aa8a-163">Il training per un periodo di tempo più lungo consente a Model Builder di esplorare un numero maggiore di algoritmi e una combinazione di parametri alla ricerca del modello migliore.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-163">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="0aa8a-164">Selezionare **Start Training** (Avvia training).</span><span class="sxs-lookup"><span data-stu-id="0aa8a-164">Select **Start Training**.</span></span>

    <span data-ttu-id="0aa8a-165">Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-165">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="0aa8a-166">Stato visualizza lo stato di completamento del processo di training.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-166">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="0aa8a-167">Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-167">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="0aa8a-168">Precisione maggiore indica il modello stimato più correttamente con i dati di test.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-168">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="0aa8a-169">Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-169">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="0aa8a-170">Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-170">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="0aa8a-171">Una volta completato l'allenamento, selezionare il collegamento **di valutazione** per passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-171">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="0aa8a-172">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="0aa8a-172">Evaluate the model</span></span>

<span data-ttu-id="0aa8a-173">Il risultato del passaggio relativo al training è rappresentato dal modello con le prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-173">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="0aa8a-174">Nel passaggio di valutazione dello strumento Generatore di modelli, la sezione di output conterrà l'algoritmo utilizzato dal modello con le migliori prestazioni nella voce **Best Model** insieme alle metriche in Best **Model Accuracy**.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-174">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the **Best Model** entry along with metrics in **Best Model Accuracy**.</span></span> <span data-ttu-id="0aa8a-175">Viene visualizzata anche una tabella di riepilogo con i cinque modelli migliori e le metriche relative.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-175">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="0aa8a-176">Se non si è soddisfatti della precisione delle metriche,un modo semplice per migliorarla consiste nell'aumentare la durata del training del modello o nell'usare più dati.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-176">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="0aa8a-177">In caso contrario, selezionare il collegamento al **codice** per passare al passaggio finale nello strumento Generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-177">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="0aa8a-178">Aggiungere il codice per eseguire stime</span><span class="sxs-lookup"><span data-stu-id="0aa8a-178">Add the code to make predictions</span></span>

<span data-ttu-id="0aa8a-179">Il risultato del processo di training sarà la creazione di due progetti.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-179">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="0aa8a-180">Fare riferimento al modello sottoposto a trainingReference the trained model</span><span class="sxs-lookup"><span data-stu-id="0aa8a-180">Reference the trained model</span></span>

1. <span data-ttu-id="0aa8a-181">Nel passaggio di *codice* dello strumento Generatore di modelli selezionare **Aggiungi progetti** per aggiungere i progetti generati automaticamente alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-181">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="0aa8a-182">I progetti seguenti dovrebbero essere visualizzati in **Esplora soluzioni:**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-182">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="0aa8a-183">*SentimentRazorML.ConsoleApp:* applicazione console .NET Core che contiene il codice di training e stima del modello.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-183">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="0aa8a-184">*SentimentRazorML.Model:* libreria di classi .NET Standard contenente i modelli di dati che definiscono lo schema dei dati del modello di input e di output, nonché la versione salvata del modello con le prestazioni migliori durante il training.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-184">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the saved version of the best performing model during training.</span></span>

    <span data-ttu-id="0aa8a-185">Per questa esercitazione viene usato solo il progetto *SentimentRazorML.Model* perché le stime verranno eseguite nell'applicazione Web *SentimentRazor* anziché nella console.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-185">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="0aa8a-186">Anche se *sentimentRazorML.ConsoleApp* non verrà usata per il punteggio, può essere usata per eseguire nuovamente il training del modello usando nuovi dati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-186">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="0aa8a-187">La riqualificazione non rientra nell'ambito di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-187">Retraining is outside the scope of this tutorial though.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="0aa8a-188">Configurare il pool PredictionEngine</span><span class="sxs-lookup"><span data-stu-id="0aa8a-188">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="0aa8a-189">Per eseguire una singola stima, [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)è necessario creare un file .</span><span class="sxs-lookup"><span data-stu-id="0aa8a-189">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="0aa8a-190">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-190">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="0aa8a-191">Inoltre, è necessario creare un'istanza di esso ovunque sia necessario all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-191">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="0aa8a-192">Man mano che l'applicazione cresce, questo processo può diventare ingestibile.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-192">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="0aa8a-193">Per migliorare le prestazioni e la thread safety, `PredictionEnginePool` usare una [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) combinazione [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) di inserimento delle dipendenze e il servizio, che crea un oggetto da utilizzare in tutta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-193">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

1. <span data-ttu-id="0aa8a-194">Installare il *pacchetto NuGet Microsoft.Extensions.ML:*</span><span class="sxs-lookup"><span data-stu-id="0aa8a-194">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="0aa8a-195">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto e **scegliere Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-195">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="0aa8a-196">Scegliere "nuget.org" come origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-196">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="0aa8a-197">Selezionare la scheda **Sfoglia** e cercare **Microsoft.Extensions.ML**.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-197">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span>
    1. <span data-ttu-id="0aa8a-198">Selezionare il pacchetto nell'elenco e selezionare il pulsante **Installa.**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-198">Select the package in the list, and select the **Install** button.</span></span>
    1. <span data-ttu-id="0aa8a-199">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche**</span><span class="sxs-lookup"><span data-stu-id="0aa8a-199">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="0aa8a-200">Selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione licenza** se si è soddisfatti delle condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-200">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="0aa8a-201">Aprire il file *Startup.cs* nel progetto *SentimentRazor.*</span><span class="sxs-lookup"><span data-stu-id="0aa8a-201">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="0aa8a-202">Aggiungere le istruzioni using seguenti per fare riferimento al Microsoft.Extensions.ML pacchetto NuGet e al progetto *SentimentRazorML.Model:Add* the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and SentimentRazorML.Model project:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-202">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. <span data-ttu-id="0aa8a-203">Creare una variabile globale per archiviare il percorso del file di modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-203">Create a global variable to store the location of the trained model file.</span></span>

    ```csharp
    private readonly string _modelPath;
    ```

1. <span data-ttu-id="0aa8a-204">Il file di modello viene archiviato nella directory di compilazione insieme ai file di assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-204">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="0aa8a-205">Per semplificare l'accesso, creare `GetAbsolutePath` un `Configure` metodo helper chiamato dopo il metodoTo make it easier to access, create a helper method called after the method</span><span class="sxs-lookup"><span data-stu-id="0aa8a-205">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }
    ```

1. <span data-ttu-id="0aa8a-206">Utilizzare `GetAbsolutePath` il metodo `Startup` nel costruttore `_modelPath`della classe per impostare l'oggetto .</span><span class="sxs-lookup"><span data-stu-id="0aa8a-206">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. <span data-ttu-id="0aa8a-207">Configurare `PredictionEnginePool` l'oggetto `ConfigureServices` per l'applicazione nel metodo:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-207">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="0aa8a-208">Creare un gestore di analisi del sentimentCreate sentiment analysis handler</span><span class="sxs-lookup"><span data-stu-id="0aa8a-208">Create sentiment analysis handler</span></span>

<span data-ttu-id="0aa8a-209">Le previsioni verranno effettuate all'interno della pagina principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-209">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="0aa8a-210">Pertanto, è necessario aggiungere un `PredictionEnginePool` metodo che accetta l'input dell'utente e che utilizza per restituire una stima.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-210">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="0aa8a-211">Aprire il file *Index.cshtml.cs* che si trova nella directory *Pages* e aggiungere le seguenti istruzioni using:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-211">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    <span data-ttu-id="0aa8a-212">Per utilizzare il `PredictionEnginePool` configurato `Startup` nella classe, è necessario inserirlo nel costruttore del modello in cui si desidera utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-212">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span>

1. <span data-ttu-id="0aa8a-213">Aggiungere una variabile `PredictionEnginePool` per `IndexModel` fare riferimento all'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-213">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. <span data-ttu-id="0aa8a-214">Creare un costruttore nella `IndexModel` `PredictionEnginePool` classe e inserirlo il servizio.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-214">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }
    ```

1. <span data-ttu-id="0aa8a-215">Creare un gestore `PredictionEnginePool` di metodo che utilizza l'oggetto per eseguire stime dall'input dell'utente ricevuto dalla pagina Web.Create a method handler that uses the to make predictions from user input received from the web page.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-215">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="0aa8a-216">Sotto `OnGet` il metodo, creare un nuovo metodo chiamato`OnGetAnalyzeSentiment`</span><span class="sxs-lookup"><span data-stu-id="0aa8a-216">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="0aa8a-217">All'interno del `OnGetAnalyzeSentiment` metodo, restituire il sentiment *neutro* se l'input dell'utente è vuoto o null.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-217">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. <span data-ttu-id="0aa8a-218">Dato un input valido, creare `ModelInput`una nuova istanza di .</span><span class="sxs-lookup"><span data-stu-id="0aa8a-218">Given a valid input, create a new instance of `ModelInput`.</span></span>

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. <span data-ttu-id="0aa8a-219">Utilizzare `PredictionEnginePool` il per prevedere il sentiment.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-219">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. <span data-ttu-id="0aa8a-220">Convertire il `bool` valore stimato in tossico o non tossico con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-220">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. <span data-ttu-id="0aa8a-221">Infine, riporta il sentiment alla pagina web.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-221">Finally, return the sentiment back to the web page.</span></span>

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a><span data-ttu-id="0aa8a-222">Configurare la pagina Web</span><span class="sxs-lookup"><span data-stu-id="0aa8a-222">Configure the web page</span></span>

<span data-ttu-id="0aa8a-223">I risultati restituiti `OnGetAnalyzeSentiment` da `Index` verranno visualizzati dinamicamente nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-223">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="0aa8a-224">Aprire il file *Index.cshtml* nella directory *Pages* e sostituirne il contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-224">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span>

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="0aa8a-225">Successivamente, aggiungere il codice di stile css alla fine della pagina *site.css* nella directory *wwwroot:css:*</span><span class="sxs-lookup"><span data-stu-id="0aa8a-225">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="0aa8a-226">Successivamente, aggiungere il codice per inviare gli `OnGetAnalyzeSentiment` input dalla pagina Web al gestore.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-226">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="0aa8a-227">Nel file *site.js* che si trova nella directory *wwwroot.js,* creare una funzione `getSentiment` chiamata `OnGetAnalyzeSentiment` per effettuare una richiesta HTTP GET con l'input dell'utente al gestore.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-227">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="0aa8a-228">Sotto di esso, `updateMarker` aggiungere un'altra funzione chiamata per aggiornare dinamicamente la posizione del marcatore nella pagina web come sentiment è previsto.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-228">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="0aa8a-229">Creare una funzione `updateSentiment` del gestore eventi chiamata per ottenere `OnGetAnalyzeSentiment` l'input dall'utente, inviarlo alla funzione utilizzando la `getSentiment` funzione e aggiornare il marcatore con la `updateMarker` funzione.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-229">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="0aa8a-230">Infine, registrare il gestore `textarea` eventi e `id=Message` associarlo all'elemento con l'attributo .</span><span class="sxs-lookup"><span data-stu-id="0aa8a-230">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="0aa8a-231">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="0aa8a-231">Run the application</span></span>

<span data-ttu-id="0aa8a-232">Ora che l'applicazione è configurata, eseguire l'applicazione che dovrebbe essere avviata nel browser.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-232">Now that your application is set up, run the application which should launch in your browser.</span></span>

<span data-ttu-id="0aa8a-233">Quando l'applicazione viene avviata, immettere *Model Builder è cool!*</span><span class="sxs-lookup"><span data-stu-id="0aa8a-233">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="0aa8a-234">nell'area di testo.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-234">into the text area.</span></span> <span data-ttu-id="0aa8a-235">Il sentiment previsto visualizzato deve essere *Non tossico*.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-235">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![Finestra in esecuzione con la finestra di valutazione prevista](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="0aa8a-237">Se è necessario fare riferimento ai progetti generati da Model Builder in `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` un secondo momento all'interno di un'altra soluzione, è possibile trovarli all'interno della directory.</span><span class="sxs-lookup"><span data-stu-id="0aa8a-237">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0aa8a-238">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0aa8a-238">Next steps</span></span>

<span data-ttu-id="0aa8a-239">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-239">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="0aa8a-240">Creare un'applicazione ASP.NET Core Razor PagesCreate an ASP.NET Core Razor Pages application</span><span class="sxs-lookup"><span data-stu-id="0aa8a-240">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="0aa8a-241">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="0aa8a-241">Prepare and understand the data</span></span>
> - <span data-ttu-id="0aa8a-242">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="0aa8a-242">Choose a scenario</span></span>
> - <span data-ttu-id="0aa8a-243">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="0aa8a-243">Load the data</span></span>
> - <span data-ttu-id="0aa8a-244">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="0aa8a-244">Train the model</span></span>
> - <span data-ttu-id="0aa8a-245">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="0aa8a-245">Evaluate the model</span></span>
> - <span data-ttu-id="0aa8a-246">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="0aa8a-246">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0aa8a-247">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0aa8a-247">Additional Resources</span></span>

<span data-ttu-id="0aa8a-248">Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="0aa8a-248">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="0aa8a-249">Scenari del generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="0aa8a-249">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="0aa8a-250">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="0aa8a-250">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="0aa8a-251">Metriche del modello di classificazione binariaBinary Classification Model Metrics</span><span class="sxs-lookup"><span data-stu-id="0aa8a-251">Binary Classification Model Metrics</span></span>](../resources/metrics.md#evaluation-metrics-for-binary-classification)
