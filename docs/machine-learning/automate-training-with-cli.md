---
title: Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET
description: Informazioni su come usare lo strumento dell'interfaccia della riga di comando ML.NET per eseguire automaticamente il training del modello migliore dalla riga di comando.
author: CESARDELATORRE
ms.date: 04/17/2019
ms.custom: how-to
ms.openlocfilehash: e5f75dc70ea5a76951d8698ea9c0d07cb2d4ddec
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663933"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="ce8a4-103">Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="ce8a4-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="ce8a4-104">L'interfaccia della riga di comando ML.NET "democratizza" ML.NET per gli sviluppatori .NET durante l'apprendimento di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-104">The ML.NET CLI "democratizes" ML.NET for .NET developers when learning ML.NET.</span></span>

<span data-ttu-id="ce8a4-105">Per usare l'API ML.NET in modo indipendente, ovvero senza l'interfaccia della riga di comando AutoML di ML.NET, è necessario scegliere un formatore (implementazione di un algoritmo di apprendimento automatico per una determinata attività) e il set di trasformazioni dei dati (progettazione di funzionalità) da applicare ai dati.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="ce8a4-106">La pipeline ottimale varia in base al set di dati e selezionare l'algoritmo ottimale da tutte le opzioni disponibili aumenta la complessità.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="ce8a4-107">In più, ogni algoritmo ha un set di iperparametri da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="ce8a4-108">Di conseguenza, il processo di ottimizzazione del modello di apprendimento automatico può richiedere settimane, a volte mesi, poiché si tenta di trovare le combinazioni migliori di progettazione di funzionalità, algoritmi di apprendimento e iperparametri.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="ce8a4-109">Il processo si può automatizzare con l'interfaccia della riga di comando ML.NET, che implementa il motore intelligente AutoML di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-109">This process can be automated with the ML.NET CLI, which implements the ML.NET AutoML intelligent engine.</span></span>

> [!NOTE]
> <span data-ttu-id="ce8a4-110">Questo argomento fa riferimento all'**interfaccia della riga di comando** ML.NET e alla funzionalità di Machine Learning automatico (**AutoML**), attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="ce8a4-111">Informazioni sull'interfaccia della riga di comando (CLI) ML.NET</span><span class="sxs-lookup"><span data-stu-id="ce8a4-111">What is the ML.NET Command-line Interface (CLI)?</span></span>

<span data-ttu-id="ce8a4-112">È possibile eseguire l'interfaccia della riga di comando ML.NET in qualsiasi prompt dei comandi (Windows, Mac o Linux) per generare modelli e codice sorgente ML.NET di buona qualità in base ai propri set di dati di training.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-112">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on your training dataset.</span></span>

<span data-ttu-id="ce8a4-113">Come illustra l'immagine che segue, è facile generare un modello ML.NET di buona qualità (file ZIP di modello serializzato) e il codice C# di esempio per eseguire/assegnare un punteggio al modello.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-113">As shown in the figure below, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="ce8a4-114">Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello in modo da ricercare l'algoritmo e le impostazioni usate per il "modello ottimale" generato.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-114">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span>

<span data-ttu-id="ce8a4-115">![immagine](media/automate-training-with-cli/cli-high-level-process.png "Motore AutoML usato all'interno dell'interfaccia della riga di comando ML.NET")</span><span class="sxs-lookup"><span data-stu-id="ce8a4-115">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="ce8a4-116">Poiché questi asset si possono generare dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-116">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="ce8a4-117">Attualmente, le attività di apprendimento automatico supportate dall'interfaccia della riga di comando ML.NET sono:</span><span class="sxs-lookup"><span data-stu-id="ce8a4-117">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`
- <span data-ttu-id="ce8a4-118">In futuro: altre attività di apprendimento automatico, ad esempio `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span><span class="sxs-lookup"><span data-stu-id="ce8a4-118">Future: other machine learning tasks such as `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span></span>

<span data-ttu-id="ce8a4-119">Esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="ce8a4-119">Example of usage:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![immagine](media/automate-training-with-cli/cli-model-generation.gif)

<span data-ttu-id="ce8a4-121">È possibile eseguire la funzionalità come si esegue *Windows PowerShell*, \*bash di macOS/Linux o una *finestra di comando di Windows*.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-121">You can run it the same way on *Windows PowerShell*, \*macOS/Linux bash, or *Windows CMD*.</span></span> <span data-ttu-id="ce8a4-122">Tuttavia, il completamento automatico in formato tabella (suggerimento dei parametri) non funzionerà nella *finestra di comando di Windows*.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-122">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="ce8a4-123">Asset di output generati</span><span class="sxs-lookup"><span data-stu-id="ce8a4-123">Output assets generated</span></span>

<span data-ttu-id="ce8a4-124">Il comando `auto-train` dell'interfaccia della riga di comando genera gli asset seguenti nella cartella di output:</span><span class="sxs-lookup"><span data-stu-id="ce8a4-124">The CLI `auto-train` command generates the following assets in the output folder:</span></span>

- <span data-ttu-id="ce8a4-125">Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso nell'esecuzione di stime.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-125">A serialized model .zip ("best model") ready to use for running predictions.</span></span>
- <span data-ttu-id="ce8a4-126">Soluzione C# con:</span><span class="sxs-lookup"><span data-stu-id="ce8a4-126">C# solution with:</span></span>
  - <span data-ttu-id="ce8a4-127">Il codice C# per eseguire e assegnare punteggi al modello generato (per eseguire stime nelle app per utenti finali con il modello).</span><span class="sxs-lookup"><span data-stu-id="ce8a4-127">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
  - <span data-ttu-id="ce8a4-128">Il codice C# con il codice di training usato per generare il modello (a scopo di apprendimento o nuovo training del modello).</span><span class="sxs-lookup"><span data-stu-id="ce8a4-128">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="ce8a4-129">File di log con informazioni su tutte le iterazioni e gli sweep eseguiti su più algoritmi valutati, inclusa la configurazione/pipeline dettagliata.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-129">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="ce8a4-130">I primi due asset possono essere usati direttamente nelle app degli utenti finali (app Web ASP.NET Core, servizi, app desktop e così via) per effettuare previsioni con il modello di Machine Learning generato.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-130">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="ce8a4-131">Il terzo asset, ovvero il codice di training, indica quale codice API ML.NET è stato usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo che sia possibile ripetere il training del modello ed esaminare il formatore/algoritmo e gli iperparametri specifici selezionati in background dall'interfaccia della riga di comando e dalla funzionalità AutoML.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-131">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span>

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="ce8a4-132">Informazioni sulla qualità del modello</span><span class="sxs-lookup"><span data-stu-id="ce8a4-132">Understanding the quality of the model</span></span>

<span data-ttu-id="ce8a4-133">Quando si genera un "modello ottimale" con lo strumento dell'interfaccia della riga di comando vengono visualizzate metriche relative alla qualità, ad esempio accuratezza e R quadrato, in base all'attività di apprendimento automatico che interessa.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-133">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy, and R-Squared) as appropriate for the ML task you are targeting.</span></span>

<span data-ttu-id="ce8a4-134">Nel riepilogo che segue le metriche sono raggruppate per attività di apprendimento automatico per consentire all'utente di comprendere la qualità del "modello ottimale" generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-134">Here we summarize those metrics grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-binary-classification-models"></a><span data-ttu-id="ce8a4-135">Metriche per i modelli di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="ce8a4-135">Metrics for Binary Classification models</span></span>

<span data-ttu-id="ce8a4-136">Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione binaria dei primi cinque modelli individuati dall'interfaccia della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="ce8a4-136">The following displays the binary classification ML task metrics list for the top five models found by the CLI:</span></span>

![immagine](media/automate-training-with-cli/cli-binary-classification-metrics.png)

<span data-ttu-id="ce8a4-138">L'accuratezza è una metrica molto diffusa per i problemi di classificazione, tuttavia non è sempre la metrica più adatta per selezionare il modello ottimale, come spiegato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-138">Accuracy is a popular metric for classification problems, however accuracy is not always the best metric to select the best model from as explained in the references below.</span></span> <span data-ttu-id="ce8a4-139">Vi sono casi in cui è necessario valutare la qualità del modello con metriche supplementari.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-139">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="ce8a4-140">Per esaminare e comprendere le metriche generate dall'interfaccia della riga di comando, vedere [Metriche per la classificazione binaria](resources/metrics.md#metrics-for-binary-classification).</span><span class="sxs-lookup"><span data-stu-id="ce8a4-140">To explore and understand the metrics that are output by the CLI, see [Metrics for binary classification](resources/metrics.md#metrics-for-binary-classification).</span></span>

### <a name="metrics-for-multi-class-classification-models"></a><span data-ttu-id="ce8a4-141">Metriche per i modelli di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="ce8a4-141">Metrics for Multi-class Classification models</span></span>

<span data-ttu-id="ce8a4-142">Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione multiclasse dei primi cinque modelli individuati dall'interfaccia della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="ce8a4-142">The following displays the multi-class classification ML task metrics list for the top five models found by the CLI:</span></span>

![immagine](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

<span data-ttu-id="ce8a4-144">Per esaminare e comprendere le metriche generate dall'interfaccia della riga di comando, vedere [Metriche per la classificazione multiclasse](resources/metrics.md#metrics-for-multi-class-classification).</span><span class="sxs-lookup"><span data-stu-id="ce8a4-144">To explore and understand the metrics that are output by the CLI, see [Metrics for multiclass classification](resources/metrics.md#metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-models"></a><span data-ttu-id="ce8a4-145">Metriche per i modelli di regressione</span><span class="sxs-lookup"><span data-stu-id="ce8a4-145">Metrics for Regression models</span></span>

<span data-ttu-id="ce8a4-146">Un modello di regressione risulta adatto ai dati se le differenze tra i valori osservati e valori stimati del modello sono ridotti e non distorti.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-146">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="ce8a4-147">La regressione può essere valutata con alcune metriche.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-147">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="ce8a4-148">Verrà visualizzato un elenco simile di metriche per i primi cinque modelli di qualità ottimale individuati dall'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ce8a4-148">You will see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="ce8a4-149">In questo caso particolare, correlato a un'attività di regressione dell'apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="ce8a4-149">In this particular case related to a regression ML task:</span></span>

![immagine](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="ce8a4-151">Per esaminare e comprendere le metriche generate dall'interfaccia della riga di comando, vedere [Metriche per la regressione](resources/metrics.md#metrics-for-regression).</span><span class="sxs-lookup"><span data-stu-id="ce8a4-151">To explore and understand the metrics that are output by the CLI, see [Metrics for regression](resources/metrics.md#metrics-for-regression).</span></span>

## <a name="see-also"></a><span data-ttu-id="ce8a4-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce8a4-152">See also</span></span>

- [<span data-ttu-id="ce8a4-153">Come installare lo strumento dell'interfaccia della riga comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="ce8a4-153">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="ce8a4-154">Esercitazione: Generare automaticamente un classificatore binario con l'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="ce8a4-154">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](tutorials/mlnet-cli.md)
- [<span data-ttu-id="ce8a4-155">Informazioni di riferimento sui comandi dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="ce8a4-155">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="ce8a4-156">Telemetria nell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="ce8a4-156">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)
