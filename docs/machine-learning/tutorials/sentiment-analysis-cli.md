---
title: Analizzare il sentiment usando l'interfaccia della riga di comando di ML.NET
description: Generare automaticamente un modello di ML e il codice C# correlato per un set di dati di esempio
author: cesardl
ms.author: cesardl
ms.date: 06/03/2020
ms.custom: mvc,mlnet-tooling
ms.topic: tutorial
ms.openlocfilehash: 64190546157bc9386314a3080c5364fd854d7704
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602237"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a><span data-ttu-id="24a36-103">Analizzare il sentiment usando l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="24a36-103">Analyze sentiment using the ML.NET CLI</span></span>

<span data-ttu-id="24a36-104">Di seguito sono riportate informazioni su come usare l'interfaccia della riga di comando ML.NET per generare automaticamente un modello ML.NET e il codice C# sottostante.</span><span class="sxs-lookup"><span data-stu-id="24a36-104">Learn how to use ML.NET CLI to automatically generate an ML.NET model and underlying C# code.</span></span> <span data-ttu-id="24a36-105">Fornire il set di dati e l'attività di machine learning da implementare e l'interfaccia della riga di comando usa il motore AutoML per creare il codice sorgente di generazione e distribuzione del modello, nonché il modello di classificazione.</span><span class="sxs-lookup"><span data-stu-id="24a36-105">You provide your dataset and the machine learning task you want to implement, and the CLI uses the AutoML engine to create model generation and deployment source code, as well as the classification model.</span></span>

<span data-ttu-id="24a36-106">In questa esercitazione verranno eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24a36-106">In this tutorial, you will do the following steps:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="24a36-107">Preparare i dati per l'attività di Machine Learning selezionata</span><span class="sxs-lookup"><span data-stu-id="24a36-107">Prepare your data for the selected machine learning task</span></span>
> - <span data-ttu-id="24a36-108">Eseguire il comando ' mlnet Classification ' dall'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="24a36-108">Run the 'mlnet classification' command from the CLI</span></span>
> - <span data-ttu-id="24a36-109">Rivedere i risultati delle metriche di qualità</span><span class="sxs-lookup"><span data-stu-id="24a36-109">Review the quality metric results</span></span>
> - <span data-ttu-id="24a36-110">Comprendere il codice C# generato per usare il modello nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="24a36-110">Understand the generated C# code to use the model in your application</span></span>
> - <span data-ttu-id="24a36-111">Esplorare il codice C# generato usato per il training del modello</span><span class="sxs-lookup"><span data-stu-id="24a36-111">Explore the generated C# code that was used to train the model</span></span>

> [!NOTE]
> <span data-ttu-id="24a36-112">Questo argomento si riferisce all'interfaccia della riga di comando ML.NET, attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="24a36-112">This topic refers to the ML.NET CLI tool, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="24a36-113">Per ulteriori informazioni, visitare la pagina [ml.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) .</span><span class="sxs-lookup"><span data-stu-id="24a36-113">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="24a36-114">L'interfaccia della riga di comando ML.NET fa parte di ML.NET e l'obiettivo principale è "democratizzare" ML.NET per gli sviluppatori di .NET in modo che non sia necessario scrivere codice da zero quando iniziano a usarlo.</span><span class="sxs-lookup"><span data-stu-id="24a36-114">The ML.NET CLI is part of ML.NET and its main goal is to "democratize" ML.NET for .NET developers when learning ML.NET so you don't need to code from scratch to get started.</span></span>

<span data-ttu-id="24a36-115">È possibile eseguire l'interfaccia della riga di comando ML.NET in qualsiasi prompt dei comandi (Windows, Mac o Linux) per generare modelli e codice sorgente ML.NET di buona qualità in base ai set di dati di training specificati.</span><span class="sxs-lookup"><span data-stu-id="24a36-115">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) to generate good quality ML.NET models and source code based on training datasets you provide.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="24a36-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="24a36-116">Pre-requisites</span></span>

- <span data-ttu-id="24a36-117">[.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="24a36-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) or later</span></span>
- <span data-ttu-id="24a36-118">Opzionale [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="24a36-118">(Optional) [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span></span>
- [<span data-ttu-id="24a36-119">Interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="24a36-119">ML.NET CLI</span></span>](../how-to-guides/install-ml-net-cli.md)

<span data-ttu-id="24a36-120">È possibile eseguire i progetti in codice C# generati in Visual Studio o con `dotnet run` (interfaccia della riga di comando di .NET Core).</span><span class="sxs-lookup"><span data-stu-id="24a36-120">You can either run the generated C# code projects from Visual Studio or with `dotnet run` (.NET Core CLI).</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="24a36-121">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="24a36-121">Prepare your data</span></span>

<span data-ttu-id="24a36-122">Verrà usato un set di dati esistente per uno scenario di 'analisi del sentiment', che è un'attività di Machine Learning con classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="24a36-122">We are going to use an existing dataset used for a 'Sentiment Analysis' scenario, which is a binary classification machine learning task.</span></span> <span data-ttu-id="24a36-123">È possibile usare in modo simile un set di dati personalizzato, con il modello e il codice che verranno generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="24a36-123">You can use your own dataset in a similar way, and the model and code will be generated for you.</span></span>

1. <span data-ttu-id="24a36-124">Scaricare il [file ZIP del set di dati Sentiment Labeled Sentences UCI (vedere le citazioni nella nota seguente)](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) e decomprimerlo in una cartella a scelta.</span><span class="sxs-lookup"><span data-stu-id="24a36-124">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip it on any folder you choose.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24a36-125">I set di dati usati in questa esercitazione provengono da 'From Group to Individual Labels using Deep Features', Kotzias et al,</span><span class="sxs-lookup"><span data-stu-id="24a36-125">The datasets this tutorial uses a dataset from the 'From Group to Individual Labels using Deep Features', Kotzias et al,.</span></span> <span data-ttu-id="24a36-126">KDD 2015 e ospitato nel repository di Machine Learning UCI-Dua, D. e Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="24a36-126">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="24a36-127">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="24a36-127">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="24a36-128">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="24a36-128">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

2. <span data-ttu-id="24a36-129">Copiare il file `yelp_labelled.txt` in qualsiasi cartella creata in precedenza, ad esempio `/cli-test`.</span><span class="sxs-lookup"><span data-stu-id="24a36-129">Copy the `yelp_labelled.txt` file into any folder you previously created (such as `/cli-test`).</span></span>

3. <span data-ttu-id="24a36-130">Aprire un prompt dei comandi e passare alla cartella in cui è stato copiato il file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="24a36-130">Open your preferred command prompt and move to the folder where you copied the dataset file.</span></span> <span data-ttu-id="24a36-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="24a36-131">For example:</span></span>

    ```console
    cd /cli-test
    ```

    <span data-ttu-id="24a36-132">Usando qualsiasi editor di testo, ad esempio Visual Studio Code, è possibile aprire ed esplorare il file del set di dati `yelp_labelled.txt`.</span><span class="sxs-lookup"><span data-stu-id="24a36-132">Using any text editor such as Visual Studio Code, you can open, and explore the `yelp_labelled.txt` dataset file.</span></span> <span data-ttu-id="24a36-133">La struttura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="24a36-133">You can see that the structure is:</span></span>

    - <span data-ttu-id="24a36-134">Il file non ha intestazione.</span><span class="sxs-lookup"><span data-stu-id="24a36-134">The file has no header.</span></span> <span data-ttu-id="24a36-135">Verrà usato l'indice della colonna.</span><span class="sxs-lookup"><span data-stu-id="24a36-135">You will use the column's index.</span></span>

    - <span data-ttu-id="24a36-136">Sono presenti solo due colonne:</span><span class="sxs-lookup"><span data-stu-id="24a36-136">There are just two columns:</span></span>

        | <span data-ttu-id="24a36-137">Testo (indice di colonna 0)</span><span class="sxs-lookup"><span data-stu-id="24a36-137">Text (Column index 0)</span></span> | <span data-ttu-id="24a36-138">Etichetta (indice di colonna 1)</span><span class="sxs-lookup"><span data-stu-id="24a36-138">Label (Column index 1)</span></span>|
        |--------------------------|-------|
        | <span data-ttu-id="24a36-139">Wow... Questo posto è stato apprezzato.</span><span class="sxs-lookup"><span data-stu-id="24a36-139">Wow... Loved this place.</span></span> | <span data-ttu-id="24a36-140">1</span><span class="sxs-lookup"><span data-stu-id="24a36-140">1</span></span> |
        | <span data-ttu-id="24a36-141">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="24a36-141">Crust is not good.</span></span> | <span data-ttu-id="24a36-142">0</span><span class="sxs-lookup"><span data-stu-id="24a36-142">0</span></span> |
        | <span data-ttu-id="24a36-143">Not tasty and the texture was just nasty.</span><span class="sxs-lookup"><span data-stu-id="24a36-143">Not tasty and the texture was just nasty.</span></span> | <span data-ttu-id="24a36-144">0</span><span class="sxs-lookup"><span data-stu-id="24a36-144">0</span></span> |
        | <span data-ttu-id="24a36-145">...MOLTE ALTRE RIGHE DI TESTO...</span><span class="sxs-lookup"><span data-stu-id="24a36-145">...MANY MORE TEXT ROWS...</span></span> | <span data-ttu-id="24a36-146">...(1 o 0)...</span><span class="sxs-lookup"><span data-stu-id="24a36-146">...(1 or 0)...</span></span> |

    <span data-ttu-id="24a36-147">Assicurarsi di chiudere il file del set di dati nell'editor.</span><span class="sxs-lookup"><span data-stu-id="24a36-147">Make sure you close the dataset file from the editor.</span></span>

    <span data-ttu-id="24a36-148">Ora è possibile iniziare a usare l'interfaccia della riga di comando per questo scenario di 'analisi del sentiment'.</span><span class="sxs-lookup"><span data-stu-id="24a36-148">Now, you are ready to start using the CLI for this 'Sentiment Analysis' scenario.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24a36-149">Al termine di questa esercitazione, è anche possibile provare con i propri set di impostazioni purché siano pronti per essere usati per le attività ML attualmente supportate dall'anteprima dell'interfaccia della riga di comando di ML.NET, ovvero *"classificazione binaria", "classificazione", "regressione"* e *"raccomandazione"*.</span><span class="sxs-lookup"><span data-stu-id="24a36-149">After finishing this tutorial you can also try with your own datasets as long as they are ready to be used for any of the ML tasks currently supported by the ML.NET CLI Preview which are *'Binary Classification', 'Classification', 'Regression',* and *'Recommendation'*.</span></span>

## <a name="run-the-mlnet-classification-command"></a><span data-ttu-id="24a36-150">Eseguire il comando ' mlnet Classification '</span><span class="sxs-lookup"><span data-stu-id="24a36-150">Run the 'mlnet classification' command</span></span>

1. <span data-ttu-id="24a36-151">Eseguire il comando seguente dell'interfaccia della riga di comando ML.NET:</span><span class="sxs-lookup"><span data-stu-id="24a36-151">Run the following ML.NET CLI command:</span></span>

    ```console
    mlnet classification --dataset "yelp_labelled.txt" --label-col 1 --has-header false --train-time 10
    ```

    <span data-ttu-id="24a36-152">Questo comando esegue il \*\* `mlnet classification` comando\*\*:</span><span class="sxs-lookup"><span data-stu-id="24a36-152">This command runs the **`mlnet classification` command**:</span></span>
    - <span data-ttu-id="24a36-153">per l' **attività** di *classificazione* ml</span><span class="sxs-lookup"><span data-stu-id="24a36-153">for the **ML task** of *classification*</span></span>
    - <span data-ttu-id="24a36-154">Usa il **file del set di dati `yelp_labelled.txt`** come set di dati di training e di test (internamente l'interfaccia della riga di comando usa la convalida incrociata oppure lo divide in due set di dati, uno per il training e l'altro per il test)</span><span class="sxs-lookup"><span data-stu-id="24a36-154">uses the **dataset file `yelp_labelled.txt`** as training and testing dataset (internally the CLI will either use cross-validation or split it in two datasets, one for training and one for testing)</span></span>
    - <span data-ttu-id="24a36-155">Dove la **colonna obiettivo/destinazione** da stimare (solitamente definita **'etichetta'**) è la **colonna con indice 1**, ossia la seconda colonna, perché l'indice è a base zero</span><span class="sxs-lookup"><span data-stu-id="24a36-155">where the **objective/target column** you want to predict (commonly called **'label'**) is the **column with index 1** (that is the second column, since the index is zero-based)</span></span>
    - <span data-ttu-id="24a36-156">Non **usa un'intestazione di file** con i nomi di colonna perché questo specifico set di dati non ha un'intestazione</span><span class="sxs-lookup"><span data-stu-id="24a36-156">does **not use a file header** with column names since this particular dataset file doesn't have a header</span></span>
    - <span data-ttu-id="24a36-157">il **tempo di esplorazione/training di destinazione** per l'esperimento è **10 secondi**</span><span class="sxs-lookup"><span data-stu-id="24a36-157">the **targeted exploration/train time** for the experiment is **10 seconds**</span></span>

    <span data-ttu-id="24a36-158">L'output dell'interfaccia della riga di comando sarà simile a:</span><span class="sxs-lookup"><span data-stu-id="24a36-158">You will see output from the CLI, similar to:</span></span>

    <!-- markdownlint-disable MD023 MD025 -->

    ![Classificazione dell'interfaccia della riga di comando ML.NET in PowerShell](./media/mlnet-cli/mlnet-classification-powershell.gif)

    <span data-ttu-id="24a36-160">In questo caso specifico, in appena 10 secondi e con il piccolo set di dati fornito, l'interfaccia della riga di comando è in grado di eseguire poche iterazioni, il che significa che il training viene ripetuto più volte in base a diverse combinazioni di algoritmi/configurazione con trasformazioni interne dei dati e iperparametri dell'algoritmo differenti.</span><span class="sxs-lookup"><span data-stu-id="24a36-160">In this particular case, in only 10 seconds and with the small dataset provided, the CLI tool was able to run quite a few iterations, meaning training multiple times based on different combinations of algorithms/configuration with different internal data transformations and algorithm's hyper-parameters.</span></span>

    <span data-ttu-id="24a36-161">Infine, il modello di "qualità migliore" trovato in 10 secondi usa uno specifico trainer/algoritmo con qualsiasi specifica configurazione.</span><span class="sxs-lookup"><span data-stu-id="24a36-161">Finally, the "best quality" model found in 10 seconds is a model using a particular trainer/algorithm with any specific configuration.</span></span> <span data-ttu-id="24a36-162">A seconda del tempo di esplorazione, il comando può produrre un risultato diverso.</span><span class="sxs-lookup"><span data-stu-id="24a36-162">Depending on the exploration time, the command can produce a different result.</span></span> <span data-ttu-id="24a36-163">La selezione si basa sulle diverse metriche illustrate, ad esempio `Accuracy`.</span><span class="sxs-lookup"><span data-stu-id="24a36-163">The selection is based on the multiple metrics shown, such as `Accuracy`.</span></span>

    <span data-ttu-id="24a36-164">**Informazioni sulle metriche di qualità del modello**</span><span class="sxs-lookup"><span data-stu-id="24a36-164">**Understanding the model's quality metrics**</span></span>

    <span data-ttu-id="24a36-165">La prima metrica, e anche la più facile, per valutare un modello di classificazione binaria è l'accuratezza, semplice da comprendere.</span><span class="sxs-lookup"><span data-stu-id="24a36-165">The first and easiest metric to evaluate a binary-classification model is the accuracy, which is simple to understand.</span></span> <span data-ttu-id="24a36-166">L'accuratezza corrisponde alla percentuale di stime corrette con un set di dati di test,</span><span class="sxs-lookup"><span data-stu-id="24a36-166">"Accuracy is the proportion of correct predictions with a test data set.".</span></span> <span data-ttu-id="24a36-167">che dovrebbe essere quanto più vicino possibile al 100% (1,00).</span><span class="sxs-lookup"><span data-stu-id="24a36-167">The closer to 100% (1.00), the better.</span></span>

    <span data-ttu-id="24a36-168">Tuttavia, in alcuni casi la misurazione con la semplice metrica dell'accuratezza non è sufficiente, in particolare quando l'etichetta (0 e 1 in questo esempio) non è bilanciata nel set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="24a36-168">However, there are cases where just measuring with the Accuracy metric is not enough, especially when the label (0 and 1 in this case) is unbalanced in the test dataset.</span></span>

    <span data-ttu-id="24a36-169">Per altre metriche e informazioni più **dettagliate sulle metriche** , ad esempio l'accuratezza, l'AUC, il AUCPR e il Punteggio F1 usati per valutare i diversi modelli, vedere informazioni sulle [metriche di ml.NET](../resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="24a36-169">For additional metrics and more **detailed information about the metrics** such as Accuracy, AUC, AUCPR, and F1-score used to evaluate the different models, see [Understanding ML.NET metrics](../resources/metrics.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="24a36-170">È possibile provare questo stesso set di dati e specificare alcuni minuti per `--max-exploration-time` (ad esempio, tre minuti in modo da specificare 180 secondi) in modo da trovare un "modello ottimale" migliore con una configurazione della pipeline di training diversa per questo set di dati, che con 1000 righe è piuttosto piccolo.</span><span class="sxs-lookup"><span data-stu-id="24a36-170">You can try this very same dataset and specify a few minutes for `--max-exploration-time` (for instance three minutes so you specify 180 seconds) which will find a better "best model" for you with a different training pipeline configuration for this dataset (which is pretty small, 1000 rows).</span></span>

    <span data-ttu-id="24a36-171">Per trovare un modello di "qualità migliore/buona" pronto per la produzione e destinato a set di dati più grandi, è consigliabile sperimentare con l'interfaccia della riga di comando specificando in genere una quantità molto maggiore di tempo di esplorazione a seconda delle dimensioni del set di dati.</span><span class="sxs-lookup"><span data-stu-id="24a36-171">In order to find a "best/good quality" model that is a "production-ready model" targeting larger datasets, you should make experiments with the CLI usually specifying much more exploration time depending on the size of the dataset.</span></span> <span data-ttu-id="24a36-172">Infatti, in molti casi potrebbero essere necessarie diverse ore di tempo di esplorazione, soprattutto se il set di dati contiene molte righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="24a36-172">In fact, in many cases you might require multiple hours of exploration time especially if the dataset is large on rows and columns.</span></span>

1. <span data-ttu-id="24a36-173">L'esecuzione del comando precedente ha generato gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="24a36-173">The previous command execution has generated the following assets:</span></span>

    - <span data-ttu-id="24a36-174">Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="24a36-174">A serialized model .zip ("best model") ready to use.</span></span>
    - <span data-ttu-id="24a36-175">Il codice C# per eseguire e assegnare punteggi al modello generato (per eseguire stime nelle app per utenti finali con il modello).</span><span class="sxs-lookup"><span data-stu-id="24a36-175">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="24a36-176">Il codice di training C# usato per generare il modello (a scopo di apprendimento).</span><span class="sxs-lookup"><span data-stu-id="24a36-176">C# training code used to generate that model (Learning purposes).</span></span>
    - <span data-ttu-id="24a36-177">Un file di log con tutte le iterazioni esplorate che include specifiche informazioni dettagliate su ogni algoritmo provato con la relativa combinazione di iperparametri e trasformazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="24a36-177">A log file with all the iterations explored having specific detailed information about each algorithm tried with its combination of hyper-parameters and data transformations.</span></span>

    <span data-ttu-id="24a36-178">I primi due asset (il modello del file ZIP e il codice C# per eseguirlo) possono essere usati direttamente nelle app per utenti finali (app Web ASP.NET Core, servizi, app desktop e così via) per eseguire stime con il modello di ML generato.</span><span class="sxs-lookup"><span data-stu-id="24a36-178">The first two assets (.ZIP file model and C# code to run that model) can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

    <span data-ttu-id="24a36-179">Il terzo asset, ossia il codice di training, mostra quale codice API ML.NET è stato usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo che sia possibile esaminare il trainer/algoritmo e gli iperparametri specifici selezionati dall'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="24a36-179">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-parameters were selected by the CLI.</span></span>

<span data-ttu-id="24a36-180">Questi asset enumerati vengono descritti nei passaggi successivi dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="24a36-180">Those enumerated assets are explained in the following steps of the tutorial.</span></span>

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a><span data-ttu-id="24a36-181">Esplorare il codice C# generato da usare per eseguire le stime con il modello</span><span class="sxs-lookup"><span data-stu-id="24a36-181">Explore the generated C# code to use for running the model to make predictions</span></span>

1. <span data-ttu-id="24a36-182">In Visual Studio (2017 o 2019) aprire la soluzione generata nella cartella denominata `SampleClassification` all'interno della cartella di destinazione originale, che per questa esercitazione è `/cli-test`.</span><span class="sxs-lookup"><span data-stu-id="24a36-182">In Visual Studio (2017 or 2019) open the solution generated in the folder named `SampleClassification` within your original destination folder (in the tutorial was named `/cli-test`).</span></span> <span data-ttu-id="24a36-183">Dovrebbe essere visualizzata una soluzione simile a:</span><span class="sxs-lookup"><span data-stu-id="24a36-183">You should see a solution similar to:</span></span>

    > [!NOTE]
    > <span data-ttu-id="24a36-184">Nell'esercitazione suggeriamo di usare Visual Studio, ma è anche possibile esplorare il codice C# generato (due progetti) con qualsiasi editor di testo ed eseguire l'app console generata con `dotnet CLI` in un computer macOS, Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="24a36-184">In the tutorial we suggest to use Visual Studio, but you can also explore the generated C# code (two projects) with any text editor and run the generated console app with the `dotnet CLI` on macOS, Linux or Windows machine.</span></span>

    ![Soluzione VS generata dall'interfaccia della riga di comando](./media/mlnet-cli/mlnet-cli-solution-explorer.png)

    - <span data-ttu-id="24a36-186">La **libreria di classi** generata, contenente il modello di ML serializzato (file ZIP) e le classi di dati (modelli di dati), si può usare direttamente nell'applicazione per utenti finali, anche facendovi riferimento direttamente o, se si preferisce, spostando il codice.</span><span class="sxs-lookup"><span data-stu-id="24a36-186">The generated **class library** containing the serialized ML model (.zip file) and the data classes (data models) is something you can directly use in your end-user application, even by directly referencing that class library (or moving the code, as you prefer).</span></span>
    - <span data-ttu-id="24a36-187">L'**app console** generata contiene codice di esecuzione che è necessario rivedere. Quindi in genere si riutilizza il 'codice di assegnazione punteggi' (che esegue il modello di ML per le stime), spostando questo semplice codice, composto da poche righe, nell'applicazione per utenti finali in cui si vogliono eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="24a36-187">The generated **console app** contains execution code that you must review and then you usually reuse the 'scoring code' (code that runs the ML model to make predictions) by moving that simple code (just a few lines) to your end-user application where you want to make the predictions.</span></span>

1. <span data-ttu-id="24a36-188">Aprire i file delle classi **ModelInput.cs** e **ModelOutput.cs** all'interno del progetto di libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="24a36-188">Open the **ModelInput.cs** and **ModelOutput.cs** class files within the class library project.</span></span> <span data-ttu-id="24a36-189">Si noterà che queste classi sono 'classi di dati' o POCO usate per memorizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="24a36-189">You will see that these classes are 'data classes' or POCO classes used to hold data.</span></span> <span data-ttu-id="24a36-190">Si tratta di 'codice boilerplate', ma è utile generarlo se il set di dati contiene decine o anche centinaia di colonne.</span><span class="sxs-lookup"><span data-stu-id="24a36-190">It is 'boilerplate code' but useful to have it generated if your dataset has tens or even hundreds of columns.</span></span>
    - <span data-ttu-id="24a36-191">La classe `ModelInput` viene usata durante la lettura di dati dal set di dati.</span><span class="sxs-lookup"><span data-stu-id="24a36-191">The `ModelInput` class is used when reading data from the dataset.</span></span>
    - <span data-ttu-id="24a36-192">La classe `ModelOutput` viene usata per ottenere il risultato di stima (dati di stima).</span><span class="sxs-lookup"><span data-stu-id="24a36-192">The `ModelOutput` class is used to get the prediction result (prediction data).</span></span>

1. <span data-ttu-id="24a36-193">Aprire il file Program.cs ed esplorare il codice.</span><span class="sxs-lookup"><span data-stu-id="24a36-193">Open the Program.cs file and explore the code.</span></span> <span data-ttu-id="24a36-194">Con poche righe è possibile eseguire il modello ed eseguire una stima del campione.</span><span class="sxs-lookup"><span data-stu-id="24a36-194">In just a few lines, you are able to run the model and make a sample prediction.</span></span>

    ```csharp
    static void Main(string[] args)
    {
        // Create single instance of sample data from first line of dataset for model input
        ModelInput sampleData = new ModelInput()
        {
            Col0 = @"Wow... Loved this place.",
        };

        // Make a single prediction on the sample data and print results
        var predictionResult = ConsumeModel.Predict(sampleData);

        Console.WriteLine("Using model to make single prediction -- Comparing actual Col1 with predicted Col1 from sample data...\n\n");
        Console.WriteLine($"Col0: {sampleData.Col0}");
        Console.WriteLine($"\n\nPredicted Col1 value {predictionResult.Prediction} \nPredicted Col1 scores: [{String.Join(",", predictionResult.Score)}]\n\n");
        Console.WriteLine("=============== End of process, hit any key to finish ===============");
        Console.ReadKey();
    }
    ```

    - Le prime righe di codice creano un *solo dato di esempio*, in questo caso basato sulla prima riga del set di dati da utilizzare per la stima. <span data-ttu-id="24a36-196">È anche possibile creare i propri dati hardcoded aggiornando il codice:</span><span class="sxs-lookup"><span data-stu-id="24a36-196">You can also create you own 'hard-coded' data by updating the code:</span></span>

        ```csharp
        ModelInput sampleData = new ModelInput()
        {
            Col0 = "The ML.NET CLI is great for getting started. Very cool!"
        };
        ```

    - <span data-ttu-id="24a36-197">La riga di codice successiva usa il `ConsumeModel.Predict()` metodo sui dati di input specificati per eseguire una stima e restituire i risultati in base allo schema ModelOutput.cs.</span><span class="sxs-lookup"><span data-stu-id="24a36-197">The next line of code uses the `ConsumeModel.Predict()` method on the specified input data to make a prediction and return the results (based on the ModelOutput.cs schema).</span></span>
    - <span data-ttu-id="24a36-198">Le ultime righe del codice stampano il proprietà dei dati di esempio (in questo caso il commento), nonché la stima del sentimento e i punteggi corrispondenti per i sentimenti positivi (1) e il sentimento negativo (2).</span><span class="sxs-lookup"><span data-stu-id="24a36-198">The last lines of code print out the proprties of the sample data (in this case the Comment) as well as the Sentiment prediction and corresponding Scores for positive sentiment (1) and negative sentiment (2).</span></span>

1. <span data-ttu-id="24a36-199">Eseguire il progetto, usando i dati di esempio originali caricati dalla prima riga del set di dati oppure i dati hardcoded personalizzati.</span><span class="sxs-lookup"><span data-stu-id="24a36-199">Run the project, either using the original sample data loaded from the first row of the dataset or by providing your own custom hard-coded sample data.</span></span> <span data-ttu-id="24a36-200">Si dovrebbe ottenere una stima simile a:</span><span class="sxs-lookup"><span data-stu-id="24a36-200">You should get a prediction comparable to:</span></span>

![INTERFACCIA della riga di comando di ML.NET eseguire l'app da Visual Studio](./media/mlnet-cli/mlnet-cli-console-app.png)<span data-ttu-id="24a36-202">)</span><span class="sxs-lookup"><span data-stu-id="24a36-202">)</span></span>

1. <span data-ttu-id="24a36-203">Provare a sostituire i dati di esempio hardcoded con altre frasi con sentiment diverso e vedere come viene stimato un sentiment positivo o negativo dal modello.</span><span class="sxs-lookup"><span data-stu-id="24a36-203">Try changing the hard-coded sample data to other sentences with different sentiment and see how the model predicts positive or negative sentiment.</span></span>

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a><span data-ttu-id="24a36-204">Inserire le stime del modello di ML nelle applicazioni per utenti finali</span><span class="sxs-lookup"><span data-stu-id="24a36-204">Infuse your end-user applications with ML model predictions</span></span>

<span data-ttu-id="24a36-205">È possibile usare un codice di assegnazione punteggi simile a quello del modello di ML per eseguirlo nell'applicazione per utenti finali ed eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="24a36-205">You can use similar 'ML model scoring code' to run the model in your end-user application and make predictions.</span></span>

<span data-ttu-id="24a36-206">È ad esempio possibile spostare direttamente il codice in qualsiasi applicazione desktop Windows, come **WPF** e **WinForms**, ed eseguire il modello come è stato fatto nell'app console.</span><span class="sxs-lookup"><span data-stu-id="24a36-206">For instance, you could directly move that code to any Windows desktop application such as **WPF** and **WinForms** and run the model in the same way than it was done in the console app.</span></span>

<span data-ttu-id="24a36-207">È tuttavia necessario ottimizzare il modo in cui vengono implementate queste righe di codice per eseguire un modello di ML, ossia memorizzare nella cache il file ZIP e caricarlo una sola volta, e avere oggetti singleton invece di crearli per ogni richiesta, soprattutto se l'applicazione deve essere scalabile, ad esempio un'applicazione Web o un servizio distribuito, come descritto nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="24a36-207">However, the way you implement those lines of code to run an ML model should be optimized (that is, cache the model .zip file and load it once) and have singleton objects instead of creating them on every request, especially if your application needs to be scalable such as a web application or distributed service, as explained in the following section.</span></span>

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a><span data-ttu-id="24a36-208">Esecuzione di modelli ML.NET in app Web e servizi ASP.NET Core scalabili (app multithread)</span><span class="sxs-lookup"><span data-stu-id="24a36-208">Running ML.NET models in scalable ASP.NET Core web apps and services (multi-threaded apps)</span></span>

<span data-ttu-id="24a36-209">La creazione dell'oggetto del modello (`ITransformer` caricato da un file ZIP del modello) e dell'oggetto `PredictionEngine` deve essere ottimizzata in particolare per l'esecuzione in app Web scalabili e servizi distribuiti.</span><span class="sxs-lookup"><span data-stu-id="24a36-209">The creation of the model object (`ITransformer` loaded from a model's .zip file) and the `PredictionEngine` object should be optimized especially when running on scalable web apps and distributed services.</span></span> <span data-ttu-id="24a36-210">Per il primo caso, l'oggetto del modello `ITransformer`, l'ottimizzazione è semplice e diretta.</span><span class="sxs-lookup"><span data-stu-id="24a36-210">For the first case, the model object (`ITransformer`) the optimization is straightforward.</span></span> <span data-ttu-id="24a36-211">Poiché l'oggetto `ITransformer` è thread-safe, è possibile memorizzarlo nella cache come oggetto singleton o statico in modo da caricare il modello una sola volta.</span><span class="sxs-lookup"><span data-stu-id="24a36-211">Since the `ITransformer` object is thread-safe, you can cache the object as a singleton or static object so you load the model once.</span></span>

<span data-ttu-id="24a36-212">Per il secondo oggetto, `PredictionEngine`, non è così facile perché l'oggetto `PredictionEngine` non è thread-safe, quindi non è possibile crearne un'istanza come oggetto singleton o statico in un'app ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="24a36-212">For the second object, the `PredictionEngine` object, it is not so easy because the `PredictionEngine` object is not thread-safe, therefore you cannot instantiate this object as singleton or static object in an ASP.NET Core app.</span></span> <span data-ttu-id="24a36-213">Questo problema relativo a scalabilità e thread-safe viene descritto in dettaglio in questo [post di blog](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="24a36-213">This thread-safe and scalability problem is deeply discussed in this [Blog Post](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>

<span data-ttu-id="24a36-214">Tuttavia, la situazione è più semplice rispetto a quanto spiegato in questo post.</span><span class="sxs-lookup"><span data-stu-id="24a36-214">However, things got a lot easier for you than what's explained in that blog post.</span></span> <span data-ttu-id="24a36-215">Abbiamo adottato un approccio più semplice e abbiamo creato un utile **'pacchetto di integrazione .NET Core'** che è possibile usare con facilità nelle app e nei servizi ASP.NET Core registrandolo nei servizi DI (Dependency Injection) per poi usarlo direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="24a36-215">We worked on a simpler approach for you and have created a nice **'.NET Core Integration Package'** that you can  easily use in your ASP.NET Core apps and services by registering it in the application DI services (Dependency Injection services) and then directly use it from your code.</span></span> <span data-ttu-id="24a36-216">Per informazioni, vedere l'esercitazione e l'esempio seguenti:</span><span class="sxs-lookup"><span data-stu-id="24a36-216">Check the following tutorial and example for doing that:</span></span>

- [<span data-ttu-id="24a36-217">Esercitazione: esecuzione di modelli ML.NET su app Web scalabili ASP.NET Core e WebAPI</span><span class="sxs-lookup"><span data-stu-id="24a36-217">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="24a36-218">Esempio: modello di ML.NET scalabile in ASP.NET Core WebAPI</span><span class="sxs-lookup"><span data-stu-id="24a36-218">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a><span data-ttu-id="24a36-219">Esplorare il codice C# generato usato per il training del modello di "qualità ottimale"</span><span class="sxs-lookup"><span data-stu-id="24a36-219">Explore the generated C# code that was used to train the "best quality" model</span></span>

<span data-ttu-id="24a36-220">Per un livello di formazione più avanzato, è anche possibile esplorare il codice C# generato usato dall'interfaccia della riga di comando per il training del modello generato.</span><span class="sxs-lookup"><span data-stu-id="24a36-220">For more advanced learning purposes, you can also explore the generated C# code that was used by the CLI tool to train the generated model.</span></span>

<span data-ttu-id="24a36-221">Questo 'codice di training del modello' viene attualmente generato nella classe personalizzata generata, denominata `ModelBuilder`, quindi è possibile esaminarlo.</span><span class="sxs-lookup"><span data-stu-id="24a36-221">That 'training model code' is currently generated in the custom class generated named `ModelBuilder` so you can investigate that training code.</span></span>

<span data-ttu-id="24a36-222">Soprattutto, per questo specifico scenario (modello di analisi del sentiment) è anche possibile confrontare il codice di training generato con il codice descritto nell'esercitazione seguente:</span><span class="sxs-lookup"><span data-stu-id="24a36-222">More importantly, for this particular scenario (Sentiment Analysis model) you can also compare that generated training code with the code explained in the following tutorial:</span></span>

- <span data-ttu-id="24a36-223">Confrontare: [esercitazione: usare ml.NET in uno scenario di classificazione binaria di analisi dei sentimenti](sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="24a36-223">Compare: [Tutorial: Use ML.NET in a sentiment analysis binary classification scenario](sentiment-analysis.md).</span></span>

<span data-ttu-id="24a36-224">È interessante confrontare l'algoritmo scelto e la configurazione della pipeline dell'esercitazione con il codice generato dall'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="24a36-224">It is interesting to compare the chosen algorithm and pipeline configuration in the tutorial with the code generated by the CLI tool.</span></span> <span data-ttu-id="24a36-225">A seconda del tempo dedicato all'iterazione e alla ricerca di modelli migliori, l'algoritmo scelto può essere diverso, così come gli specifici iperparametri e la configurazione della pipeline.</span><span class="sxs-lookup"><span data-stu-id="24a36-225">Depending on how much time you spend iterating and searching for better models, the chosen algorithm might be different along with its particular hyper-parameters and pipeline configuration.</span></span>

<span data-ttu-id="24a36-226">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="24a36-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="24a36-227">Preparare i dati per l'attività di ML selezionata (problema da risolvere)</span><span class="sxs-lookup"><span data-stu-id="24a36-227">Prepare your data for the selected ML task (problem to solve)</span></span>
> - <span data-ttu-id="24a36-228">Eseguire il comando "mlnet Classification" nello strumento dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="24a36-228">Run the 'mlnet classification' command in the CLI tool</span></span>
> - <span data-ttu-id="24a36-229">Rivedere i risultati delle metriche di qualità</span><span class="sxs-lookup"><span data-stu-id="24a36-229">Review the quality metric results</span></span>
> - <span data-ttu-id="24a36-230">Comprendere il codice C# generato per l'esecuzione del modello (codice da usare nell'app per utenti finali)</span><span class="sxs-lookup"><span data-stu-id="24a36-230">Understand the generated C# code to run the model (Code to use in your end-user app)</span></span>
> - <span data-ttu-id="24a36-231">Esplorare il codice C# generato usato per eseguire il training del modello "qualità migliore" (a scopo di guadagno)</span><span class="sxs-lookup"><span data-stu-id="24a36-231">Explore the generated C# code that was used to train the "best quality" model (earning purposes)</span></span>

## <a name="see-also"></a><span data-ttu-id="24a36-232">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24a36-232">See also</span></span>

- [<span data-ttu-id="24a36-233">Automatizzare il training del modello con l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="24a36-233">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="24a36-234">Esercitazione: esecuzione di modelli ML.NET su app Web scalabili ASP.NET Core e WebAPI</span><span class="sxs-lookup"><span data-stu-id="24a36-234">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="24a36-235">Esempio: modello di ML.NET scalabile in ASP.NET Core WebAPI</span><span class="sxs-lookup"><span data-stu-id="24a36-235">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [<span data-ttu-id="24a36-236">Guida di riferimento per i comandi di training automatico dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="24a36-236">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="24a36-237">Telemetria nell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="24a36-237">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
