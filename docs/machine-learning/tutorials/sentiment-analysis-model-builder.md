---
title: 'Esercitazione: Analizzare i sentimenti-classificazione binaria'
description: Questa esercitazione illustra come creare un'applicazione Razor Pages che classifica i sentimenti dai commenti del sito Web ed esegue l'azione appropriata. Il classificatore dei sentimenti binari usa il generatore di modelli in Visual Studio.
ms.date: 09/13/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 375440d98fd728cc89c1ac620614067edbd3adf8
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216874"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="0fa9f-104">Esercitazione: Analizzare i sentimenti dei commenti del sito Web in un'applicazione Web usando il generatore di modelli ML.NET</span><span class="sxs-lookup"><span data-stu-id="0fa9f-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="0fa9f-105">Informazioni su come analizzare i sentimenti dai commenti in tempo reale all'interno di un'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-105">Learn how to analyze sentiment from comments in real-time inside a web application.</span></span>

<span data-ttu-id="0fa9f-106">Questa esercitazione illustra come creare un ASP.NET Core Razor Pages applicazione che classifica i sentimenti dai commenti del sito Web in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real-time.</span></span>

<span data-ttu-id="0fa9f-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="0fa9f-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="0fa9f-108">Creare un'applicazione Razor Pages ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0fa9f-108">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="0fa9f-109">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="0fa9f-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="0fa9f-110">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="0fa9f-110">Choose a scenario</span></span>
> - <span data-ttu-id="0fa9f-111">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="0fa9f-111">Load the data</span></span>
> - <span data-ttu-id="0fa9f-112">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="0fa9f-112">Train the model</span></span>
> - <span data-ttu-id="0fa9f-113">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="0fa9f-113">Evaluate the model</span></span>
> - <span data-ttu-id="0fa9f-114">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="0fa9f-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="0fa9f-115">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="0fa9f-116">Il codice sorgente per questa esercitazione è reperibile nel repository [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples) .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="0fa9f-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0fa9f-117">Pre-requisites</span></span>

<span data-ttu-id="0fa9f-118">Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="0fa9f-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="0fa9f-119">Creare un'applicazione Razor Pages</span><span class="sxs-lookup"><span data-stu-id="0fa9f-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="0fa9f-120">Creare un' **applicazione ASP.NET Core Razor Pages**.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="0fa9f-121">Aprire Visual Studio e selezionare **File > nuovo progetto >** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span>
    1. <span data-ttu-id="0fa9f-122">Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span>
    1. <span data-ttu-id="0fa9f-123">Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-123">Then select the **ASP.NET Core Web Application** project template.</span></span>
    1. <span data-ttu-id="0fa9f-124">Nella casella di testo **nome** Digitare "SentimentRazor".</span><span class="sxs-lookup"><span data-stu-id="0fa9f-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="0fa9f-125">Per impostazione predefinita, è necessario selezionare la casella di controllo **Crea una directory per soluzione** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-125">The **Create a directory for solution** checkbox should be checked by default.</span></span> <span data-ttu-id="0fa9f-126">In caso contrario, controllarlo.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-126">If that's not the case, check it.</span></span>
    1. <span data-ttu-id="0fa9f-127">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-127">Select the **OK** button.</span></span>
    1. <span data-ttu-id="0fa9f-128">Scegliere **applicazione Web** nella finestra che consente di visualizzare i diversi tipi di progetti di ASP.NET Core, quindi selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-128">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="0fa9f-129">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="0fa9f-129">Prepare and understand the data</span></span>

<span data-ttu-id="0fa9f-130">Scaricare il [set di dati di Wikipedia Detox](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="0fa9f-130">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="0fa9f-131">Quando si apre la pagina Web, fare clic con il pulsante destro del mouse sulla pagina, scegliere **Salva con nome** e salvare il file in un punto qualsiasi del computer.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-131">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span>

<span data-ttu-id="0fa9f-132">Ogni riga nel set di dati *Wikipedia-Detox-250-line-data. TSV* rappresenta una revisione diversa lasciata da un utente in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-132">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="0fa9f-133">La prima colonna rappresenta il sentimento del testo (0 è non tossico, 1 è tossico) e la seconda colonna rappresenta il commento lasciato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-133">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="0fa9f-134">Le colonne sono separate da tabulazioni.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-134">The columns are separated by tabs.</span></span> <span data-ttu-id="0fa9f-135">I dati hanno un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0fa9f-135">The data looks like the following:</span></span>

| <span data-ttu-id="0fa9f-136">Valutazione</span><span class="sxs-lookup"><span data-stu-id="0fa9f-136">Sentiment</span></span> | <span data-ttu-id="0fa9f-137">SentimentText</span><span class="sxs-lookup"><span data-stu-id="0fa9f-137">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="0fa9f-138">1</span><span class="sxs-lookup"><span data-stu-id="0fa9f-138">1</span></span> | <span data-ttu-id="0fa9f-139">= = RUDE = = Dude, l'utente non è in grado di caricare nuovamente l'immagine di Carl, altrimenti.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="0fa9f-140">1</span><span class="sxs-lookup"><span data-stu-id="0fa9f-140">1</span></span> | <span data-ttu-id="0fa9f-141">= = OK!</span><span class="sxs-lookup"><span data-stu-id="0fa9f-141">== OK!</span></span> <span data-ttu-id="0fa9f-142">= = IM PASSERÀ A VANDALIZZARE WILD A UN WIKI, QUINDI!!!</span><span class="sxs-lookup"><span data-stu-id="0fa9f-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="0fa9f-143">0</span><span class="sxs-lookup"><span data-stu-id="0fa9f-143">0</span></span> | <span data-ttu-id="0fa9f-144">Spero che questo possa essere utile.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-144">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="0fa9f-145">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="0fa9f-145">Choose a scenario</span></span>

![](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="0fa9f-146">Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-146">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span>

1. <span data-ttu-id="0fa9f-147">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *SentimentRazor* e scegliere **Aggiungi** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-147">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="0fa9f-148">Per questo esempio, lo scenario è analisi dei sentimenti.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-148">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="0fa9f-149">Nel passaggio dello *scenario* dello strumento generatore di modelli selezionare lo scenario **analisi del sentiment** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-149">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="0fa9f-150">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="0fa9f-150">Load the data</span></span>

<span data-ttu-id="0fa9f-151">Il generatore di modelli accetta dati da due origini, un database SQL Server o un file `csv` locale `tsv` in formato o.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-151">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="0fa9f-152">Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare **File** dall'elenco a discesa delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-152">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="0fa9f-153">Selezionare il pulsante accanto alla casella di testo **selezionare un file** e usare Esplora file per cercare e selezionare il file *Wikipedia-Detox-250-line-data. TSV* .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-153">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="0fa9f-154">Scegliere **la valutazione dell'elenco** **a discesa stima nell'etichetta o nella colonna**</span><span class="sxs-lookup"><span data-stu-id="0fa9f-154">Choose **Sentiment** in the **Label or Column to Predict** dropdown</span></span>
1. <span data-ttu-id="0fa9f-155">Selezionare il collegamento **Train (Train** ) per passare al passaggio successivo nello strumento generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-155">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="0fa9f-156">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="0fa9f-156">Train the model</span></span>

<span data-ttu-id="0fa9f-157">L'attività di Machine Learning utilizzata per eseguire il training del modello di stima dei prezzi in questa esercitazione è la classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-157">The machine learning task used to train the price prediction model in this tutorial is binary classification.</span></span> <span data-ttu-id="0fa9f-158">Durante il processo di training del modello, generatore di modelli esegue il training di modelli distinti usando algoritmi di classificazione binari e impostazioni differenti per trovare il modello di prestazioni migliori per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-158">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="0fa9f-159">Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-159">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="0fa9f-160">Generatore di modelli seleziona automaticamente un valore predefinito per il **tempo di training (secondi)** in base alle dimensioni dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-160">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="0fa9f-161">Sebbene generatore di modelli imposti il valore di **tempo per il training (secondi)** su 10 secondi, aumentarlo a 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-161">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="0fa9f-162">Il training per un periodo di tempo più lungo consente a Generatore di modelli di esplorare un numero maggiore di algoritmi e una combinazione di parametri nella ricerca del modello migliore.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-162">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="0fa9f-163">Selezionare **Start Training** (Avvia training).</span><span class="sxs-lookup"><span data-stu-id="0fa9f-163">Select **Start Training**.</span></span>

    <span data-ttu-id="0fa9f-164">Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-164">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="0fa9f-165">Stato visualizza lo stato di completamento del processo di training.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-165">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="0fa9f-166">Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-166">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="0fa9f-167">Precisione maggiore indica il modello stimato più correttamente con i dati di test.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-167">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="0fa9f-168">Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-168">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="0fa9f-169">Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-169">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="0fa9f-170">Al termine del training, selezionare il collegamento **Evaluate (valuta** ) per passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-170">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="0fa9f-171">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="0fa9f-171">Evaluate the model</span></span>

<span data-ttu-id="0fa9f-172">Il risultato del passaggio relativo al training è rappresentato dal modello con le prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-172">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="0fa9f-173">Nel passaggio di valutazione dello strumento generatore di modelli la sezione di output conterrà l'algoritmo usato dal modello con le prestazioni migliori nella voce **Best model** (Modello migliore), insieme con le metriche in **Best Model Quality (RSquared)** (Qualità modello migliore).</span><span class="sxs-lookup"><span data-stu-id="0fa9f-173">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the **Best Model** entry along with metrics in **Best Model Quality (RSquared)**.</span></span> <span data-ttu-id="0fa9f-174">Viene visualizzata anche una tabella di riepilogo con i cinque modelli migliori e le metriche relative.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-174">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="0fa9f-175">Se non si è soddisfatti della precisione delle metriche,un modo semplice per migliorarla consiste nell'aumentare la durata del training del modello o nell'usare più dati.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-175">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="0fa9f-176">In caso contrario, selezionare il collegamento al **codice** per passare al passaggio finale nello strumento generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-176">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="0fa9f-177">Aggiungere il codice per eseguire stime</span><span class="sxs-lookup"><span data-stu-id="0fa9f-177">Add the code to make predictions</span></span>

<span data-ttu-id="0fa9f-178">Il risultato del processo di training sarà la creazione di due progetti.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-178">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="0fa9f-179">Riferimento al modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="0fa9f-179">Reference the trained model</span></span>

1. <span data-ttu-id="0fa9f-180">Nel passaggio del *codice* dello strumento generatore di modelli selezionare **Aggiungi progetti** per aggiungere i progetti generati automaticamente alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-180">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="0fa9f-181">I progetti seguenti dovrebbero essere visualizzati nella **Esplora soluzioni**:</span><span class="sxs-lookup"><span data-stu-id="0fa9f-181">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="0fa9f-182">*SentimentRazorML. ConsoleApp*: Applicazione console .NET Core che contiene il codice di training e di stima del modello.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-182">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="0fa9f-183">*SentimentRazorML. Model*: una libreria di classi .NET Standard che contiene i modelli di dati che definiscono lo schema di input e output dei dati del modello, nonché la versione persistente del modello che ha avuto le prestazioni migliori durante il training.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-183">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

    <span data-ttu-id="0fa9f-184">Per questa esercitazione viene usato solo il progetto *SentimentRazorML. Model* , perché le stime verranno effettuate nell'applicazione Web *SentimentRazor* anziché nella console.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-184">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="0fa9f-185">Sebbene *SentimentRazorML. ConsoleApp* non venga usato per l'assegnazione dei punteggi, può essere usato per ripetere il training del modello usando nuovi dati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-185">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="0fa9f-186">Tuttavia, la ripetizione del training esula dall'ambito di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-186">Retraining is outside the scope of this tutorial though.</span></span>

1. <span data-ttu-id="0fa9f-187">Per usare il modello sottoposto a training all'interno dell'applicazione Razor Pages, aggiungere un riferimento al progetto *SentimentRazorML. Model* .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-187">To use the trained model inside your Razor Pages application, add a reference to the *SentimentRazorML.Model* project.</span></span>

    1. <span data-ttu-id="0fa9f-188">Fare clic con il pulsante destro del mouse su progetto **SentimentRazor** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-188">Right-click **SentimentRazor** project.</span></span>
    1. <span data-ttu-id="0fa9f-189">Selezionare **Aggiungi riferimento >** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-189">Select **Add > Reference**.</span></span>
    1. <span data-ttu-id="0fa9f-190">Selezionare il nodo **progetti > soluzione** e nell'elenco selezionare il progetto **SentimentRazorML. Model** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-190">Choose the **Projects > Solution** node and from the list, check the **SentimentRazorML.Model** project.</span></span>
    1. <span data-ttu-id="0fa9f-191">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-191">Select **OK**.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="0fa9f-192">Configurare il pool di PredictionEngine</span><span class="sxs-lookup"><span data-stu-id="0fa9f-192">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="0fa9f-193">Per effettuare una singola previsione, usare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="0fa9f-193">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="0fa9f-194">Per poter usare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) nell'applicazione, è necessario crearlo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-194">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application, you must create it when it's needed.</span></span> <span data-ttu-id="0fa9f-195">In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-195">In that case, a best practice to consider is dependency injection.</span></span>

> [!WARNING]
> <span data-ttu-id="0fa9f-196">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-196">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="0fa9f-197">Per migliorare le prestazioni e le capacità di thread safety, usare il servizio `PredictionEnginePool` che crea una classe [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti `PredictionEngine` per l'uso da parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-197">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="0fa9f-198">Leggere il post di blog seguente per altre informazioni su come [creare e usare pool di oggetti `PredictionEngine` in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="0fa9f-198">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>

1. <span data-ttu-id="0fa9f-199">Installare il pacchetto NuGet *Microsoft.Extensions.ml* :</span><span class="sxs-lookup"><span data-stu-id="0fa9f-199">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="0fa9f-200">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-200">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="0fa9f-201">Scegliere "nuget.org" come origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-201">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="0fa9f-202">Selezionare la scheda **Sfoglia** e cercare **Microsoft.Extensions.ml**.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-202">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span>
    1. <span data-ttu-id="0fa9f-203">Selezionare il pacchetto nell'elenco e fare clic sul pulsante **Installa** .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-203">Select the package in the list, and select the **Install** button.</span></span>
    1. <span data-ttu-id="0fa9f-204">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche**</span><span class="sxs-lookup"><span data-stu-id="0fa9f-204">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="0fa9f-205">Selezionare il pulsante **Accetto** nella finestra di dialogo **accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-205">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="0fa9f-206">Aprire il file *Startup.cs* nel progetto *SentimentRazor* .</span><span class="sxs-lookup"><span data-stu-id="0fa9f-206">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="0fa9f-207">Aggiungere le istruzioni using seguenti per fare riferimento al pacchetto NuGet *Microsoft.Extensions.ml* e al progetto *SentimentRazorML. Model* :</span><span class="sxs-lookup"><span data-stu-id="0fa9f-207">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L12-L14)]

1. <span data-ttu-id="0fa9f-208">Creare una variabile globale per archiviare il percorso del file di modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-208">Create a global variable to store the location of the trained model file.</span></span>

    [!code-csharp [ModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L20)]

1. <span data-ttu-id="0fa9f-209">Il file del modello viene archiviato nella directory di compilazione insieme ai file di assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-209">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="0fa9f-210">Per semplificare l'accesso, creare un metodo helper chiamato `GetAbsolutePath` dopo il `Configure` metodo.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-210">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    [!code-csharp [GetAbsolutePathMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L66-L73)]

1. <span data-ttu-id="0fa9f-211">Usare il `GetAbsolutePath` metodo `Startup` nel costruttore della `_modelPath`classe per impostare.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-211">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    [!code-csharp [InitModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L25)]

1. <span data-ttu-id="0fa9f-212">Configurare per l'applicazione `ConfigureServices` nel metodo: `PredictionEnginePool`</span><span class="sxs-lookup"><span data-stu-id="0fa9f-212">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    [!code-csharp [InitPredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L42)]

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="0fa9f-213">Crea gestore analisi dei sentimenti</span><span class="sxs-lookup"><span data-stu-id="0fa9f-213">Create sentiment analysis handler</span></span>

<span data-ttu-id="0fa9f-214">Le stime verranno effettuate nella pagina principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-214">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="0fa9f-215">Pertanto, un metodo che accetta l'input dell'utente e utilizza `PredictionEnginePool` per restituire una stima deve essere aggiunta.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-215">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="0fa9f-216">Aprire il file *index.cshtml.cs* che si trova nella directory *pages* e aggiungere le istruzioni using seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fa9f-216">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    [!code-csharp [IndexUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L7-L8)]

    <span data-ttu-id="0fa9f-217">Per utilizzare l'oggetto `PredictionEnginePool` configurato `Startup` nella classe, è necessario inserirlo nel costruttore del modello in cui si desidera utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-217">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span>

1. <span data-ttu-id="0fa9f-218">Aggiungere una variabile per fare riferimento `PredictionEnginePool` all'oggetto `IndexModel` all'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-218">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    [!code-csharp [PredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L14)]

1. <span data-ttu-id="0fa9f-219">Creare un costruttore nella `IndexModel` classe e inserire il `PredictionEnginePool` servizio al suo interno.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-219">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    [!code-csharp [IndexConstructor](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L16-L19)]

1. <span data-ttu-id="0fa9f-220">Creare un gestore metodo che usi `PredictionEnginePool` per eseguire stime dall'input dell'utente ricevuto dalla pagina Web.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-220">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="0fa9f-221">Sotto il `OnGet` metodo, creare un nuovo metodo denominato`OnGetAnalyzeSentiment`</span><span class="sxs-lookup"><span data-stu-id="0fa9f-221">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="0fa9f-222">All'interno `OnGetAnalyzeSentiment` del metodo, restituisce un sentimento *neutro* se l'input dell'utente è vuoto o null.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-222">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L28)]

    1. <span data-ttu-id="0fa9f-223">Dato un input valido, creare una nuova istanza di `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-223">Given a valid input, create a new instance of `ModelInput`.</span></span>

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L29)]

    1. <span data-ttu-id="0fa9f-224">Usare per `PredictionEnginePool` stimare i sentimenti.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-224">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        [!code-csharp [MakePrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L30)]

    1. <span data-ttu-id="0fa9f-225">Convertire il `bool` valore stimato in tossico o non tossico con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-225">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        [!code-csharp [ConvertPrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L31)]

    1. <span data-ttu-id="0fa9f-226">Infine, restituire le opinioni alla pagina Web.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-226">Finally, return the sentiment back to the web page.</span></span>

        [!code-csharp [ReturnSentiment](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L32)]

### <a name="configure-the-web-page"></a><span data-ttu-id="0fa9f-227">Configurare la pagina Web</span><span class="sxs-lookup"><span data-stu-id="0fa9f-227">Configure the web page</span></span>

<span data-ttu-id="0fa9f-228">I risultati restituiti da `OnGetAnalyzeSentiment` verranno visualizzati dinamicamente `Index` nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-228">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="0fa9f-229">Aprire il file *index. cshtml* nella directory *pages* e sostituirne il contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0fa9f-229">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span>

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="0fa9f-230">Aggiungere quindi il codice di stile CSS alla fine della pagina *site. CSS* nella directory *wwwroot\css* :</span><span class="sxs-lookup"><span data-stu-id="0fa9f-230">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="0fa9f-231">Successivamente, aggiungere il `OnGetAnalyzeSentiment` codice per inviare input dalla pagina Web al gestore.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-231">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="0fa9f-232">Nel file *site. js* che si trova nella directory *wwwroot\js* creare una funzione chiamata `getSentiment` per effettuare una richiesta GET HTTP `OnGetAnalyzeSentiment` con l'input dell'utente al gestore.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-232">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="0fa9f-233">Di seguito, aggiungere un'altra funzione `updateMarker` chiamata per aggiornare dinamicamente la posizione del marcatore nella pagina Web in modo che il sentimento venga stimato.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-233">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="0fa9f-234">Creare una funzione del gestore eventi `updateSentiment` chiamata per ottenere l'input dall'utente, inviarlo `OnGetAnalyzeSentiment` alla funzione utilizzando la `getSentiment` funzione e aggiornare il marcatore con la `updateMarker` funzione.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-234">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="0fa9f-235">Infine, registrare il gestore eventi e associarlo all' `textarea` elemento con l' `id=Message` attributo.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-235">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="0fa9f-236">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0fa9f-236">Run the application</span></span>

<span data-ttu-id="0fa9f-237">Ora che l'applicazione è configurata, eseguire l'applicazione che dovrebbe essere avviata nel browser.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-237">Now that your application is set up, run the application which should launch in your browser.</span></span>

<span data-ttu-id="0fa9f-238">Quando l'applicazione viene avviata, immettere *Generatore di modelli è interessante.*</span><span class="sxs-lookup"><span data-stu-id="0fa9f-238">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="0fa9f-239">nell'area di testo.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-239">into the text area.</span></span> <span data-ttu-id="0fa9f-240">Il sentimento stimato visualizzato non deve essere *tossico*.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-240">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="0fa9f-241">Se è necessario fare riferimento ai progetti generati dal generatore di modelli in un secondo momento all'interno di un'altra soluzione, è possibile `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` trovarli nella directory.</span><span class="sxs-lookup"><span data-stu-id="0fa9f-241">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0fa9f-242">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0fa9f-242">Next steps</span></span>

<span data-ttu-id="0fa9f-243">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="0fa9f-243">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="0fa9f-244">Creare un'applicazione Razor Pages ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0fa9f-244">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="0fa9f-245">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="0fa9f-245">Prepare and understand the data</span></span>
> - <span data-ttu-id="0fa9f-246">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="0fa9f-246">Choose a scenario</span></span>
> - <span data-ttu-id="0fa9f-247">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="0fa9f-247">Load the data</span></span>
> - <span data-ttu-id="0fa9f-248">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="0fa9f-248">Train the model</span></span>
> - <span data-ttu-id="0fa9f-249">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="0fa9f-249">Evaluate the model</span></span>
> - <span data-ttu-id="0fa9f-250">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="0fa9f-250">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0fa9f-251">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0fa9f-251">Additional Resources</span></span>

<span data-ttu-id="0fa9f-252">Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fa9f-252">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="0fa9f-253">Scenari del generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="0fa9f-253">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="0fa9f-254">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="0fa9f-254">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="0fa9f-255">Metriche del modello di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="0fa9f-255">Binary Classification Model Metrics</span></span>](../resources/metrics.md#metrics-for-binary-classification)
