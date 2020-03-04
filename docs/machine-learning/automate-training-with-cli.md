---
title: Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET
description: Informazioni su come usare lo strumento dell'interfaccia della riga di comando ML.NET per eseguire automaticamente il training del modello migliore dalla riga di comando.
ms.date: 12/17/2019
ms.custom: how-to
ms.openlocfilehash: 9c493b1df0dd326ad2f0a5d1cac0fc11d7cf37e2
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240623"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="bbcf6-103">Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="bbcf6-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="bbcf6-104">L'interfaccia della riga di comando di ML.NET automatizza la generazione di modelli per gli sviluppatori .NET.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-104">The ML.NET CLI automates model generation for .NET developers.</span></span>

<span data-ttu-id="bbcf6-105">Per usare l'API ML.NET in modo indipendente, ovvero senza l'interfaccia della riga di comando AutoML di ML.NET, è necessario scegliere un formatore (implementazione di un algoritmo di apprendimento automatico per una determinata attività) e il set di trasformazioni dei dati (progettazione di funzionalità) da applicare ai dati.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="bbcf6-106">La pipeline ottimale varia in base al set di dati e selezionare l'algoritmo ottimale da tutte le opzioni disponibili aumenta la complessità.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="bbcf6-107">In più, ogni algoritmo ha un set di iperparametri da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="bbcf6-108">Di conseguenza, il processo di ottimizzazione del modello di apprendimento automatico può richiedere settimane, a volte mesi, poiché si tenta di trovare le combinazioni migliori di progettazione di funzionalità, algoritmi di apprendimento e iperparametri.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="bbcf6-109">L'interfaccia della riga di comando di ML.NET semplifica questo processo usando automazione Machine Learning (AutoML).</span><span class="sxs-lookup"><span data-stu-id="bbcf6-109">The ML.NET CLI simplifies this process using automated machine learning (AutoML).</span></span> 

> [!NOTE]
> <span data-ttu-id="bbcf6-110">Questo argomento fa riferimento all'**interfaccia della riga di comando** ML.NET e alla funzionalità di Machine Learning automatico (**AutoML**), attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="bbcf6-111">Che cos'è l'interfaccia della riga di comando di ML.NET?</span><span class="sxs-lookup"><span data-stu-id="bbcf6-111">What is the ML.NET command-line interface (CLI)?</span></span>

<span data-ttu-id="bbcf6-112">L'interfaccia della riga di comando di ML.NET è uno [strumento di .NET Core](../core/tools/global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bbcf6-112">The ML.NET CLI is a [.NET Core tool](../core/tools/global-tools.md).</span></span> <span data-ttu-id="bbcf6-113">Una volta eseguita l'installazione, viene assegnata un'attività di machine learning e un set di dati di training e viene generato un modello C# ml.NET, nonché il codice da eseguire per usare il modello nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-113">Once installed, you give it a machine learning task and a training dataset, and it generates an ML.NET model, as well as the C# code to run to use the model in your application.</span></span>

<span data-ttu-id="bbcf6-114">Come illustrato nella figura seguente, è semplice generare un modello ML.NET di qualità elevata (file con estensione zip del modello serializzato) più il codice C# di esempio per eseguire/assegnare un punteggio al modello.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-114">As shown in the following figure, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="bbcf6-115">Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello in modo da ricercare l'algoritmo e le impostazioni usate per il "modello ottimale" generato.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-115">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span>

<span data-ttu-id="bbcf6-116">![image](media/automate-training-with-cli/cli-high-level-process.png "Motore AutoML che funziona nell'interfaccia della riga di comando di ML.NET")</span><span class="sxs-lookup"><span data-stu-id="bbcf6-116">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="bbcf6-117">Poiché è possibile generare questi asset dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-117">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="bbcf6-118">Attualmente, le attività di apprendimento automatico supportate dall'interfaccia della riga di comando ML.NET sono:</span><span class="sxs-lookup"><span data-stu-id="bbcf6-118">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`
- <span data-ttu-id="bbcf6-119">In futuro: altre attività di apprendimento automatico, ad esempio `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span><span class="sxs-lookup"><span data-stu-id="bbcf6-119">Future: other machine learning tasks such as `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span></span>

<span data-ttu-id="bbcf6-120">Esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="bbcf6-120">Example of usage:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![image](media/automate-training-with-cli/cli-model-generation.gif)

<span data-ttu-id="bbcf6-122">È possibile eseguire la funzionalità come si esegue *Windows PowerShell*, \*bash di macOS/Linux o una *finestra di comando di Windows*.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-122">You can run it the same way on *Windows PowerShell*, \*macOS/Linux bash, or *Windows CMD*.</span></span> <span data-ttu-id="bbcf6-123">Tuttavia, il completamento automatico in formato tabella (suggerimento dei parametri) non funzionerà nella *finestra di comando di Windows*.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-123">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="bbcf6-124">Asset di output generati</span><span class="sxs-lookup"><span data-stu-id="bbcf6-124">Output assets generated</span></span>

<span data-ttu-id="bbcf6-125">Il comando `auto-train` dell'interfaccia della riga di comando genera gli asset seguenti nella cartella di output:</span><span class="sxs-lookup"><span data-stu-id="bbcf6-125">The CLI `auto-train` command generates the following assets in the output folder:</span></span>

- <span data-ttu-id="bbcf6-126">Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso nell'esecuzione di stime.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-126">A serialized model .zip ("best model") ready to use for running predictions.</span></span>
- <span data-ttu-id="bbcf6-127">Soluzione C# con:</span><span class="sxs-lookup"><span data-stu-id="bbcf6-127">C# solution with:</span></span>
  - <span data-ttu-id="bbcf6-128">Il codice C# per eseguire e assegnare punteggi al modello generato (per eseguire stime nelle app per utenti finali con il modello).</span><span class="sxs-lookup"><span data-stu-id="bbcf6-128">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
  - <span data-ttu-id="bbcf6-129">Il codice C# con il codice di training usato per generare il modello (a scopo di apprendimento o nuovo training del modello).</span><span class="sxs-lookup"><span data-stu-id="bbcf6-129">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="bbcf6-130">File di log con informazioni su tutte le iterazioni e gli sweep eseguiti su più algoritmi valutati, inclusa la configurazione/pipeline dettagliata.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-130">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="bbcf6-131">I primi due asset possono essere usati direttamente nelle app degli utenti finali (app Web ASP.NET Core, servizi, app desktop, ecc.) per effettuare previsioni con il modello di Machine Learning generato.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-131">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="bbcf6-132">Il terzo asset, ovvero il codice di training, indica quale codice API ML.NET è stato usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo che sia possibile ripetere il training del modello ed esaminare il formatore/algoritmo e gli iperparametri specifici selezionati in background dall'interfaccia della riga di comando e dalla funzionalità AutoML.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-132">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span>

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="bbcf6-133">Informazioni sulla qualità del modello</span><span class="sxs-lookup"><span data-stu-id="bbcf6-133">Understanding the quality of the model</span></span>

<span data-ttu-id="bbcf6-134">Quando si genera un modello "migliore" con lo strumento dell'interfaccia della riga di comando, vengono visualizzate le metriche qualitative (ad esempio l'accuratezza e il quadrato R) in base alle esigenze dell'attività ML di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-134">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy and R-Squared) as appropriate for the ML task you're targeting.</span></span>

<span data-ttu-id="bbcf6-135">Queste metriche vengono riepilogate raggruppate per attività di Machine Learning, in modo che sia possibile comprendere la qualità del "modello migliore" generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-135">Here those metrics are summarized grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-binary-classification-models"></a><span data-ttu-id="bbcf6-136">Metriche per i modelli di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="bbcf6-136">Metrics for Binary Classification models</span></span>

<span data-ttu-id="bbcf6-137">Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione binaria dei primi cinque modelli individuati dall'interfaccia della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="bbcf6-137">The following displays the binary classification ML task metrics list for the top five models found by the CLI:</span></span>

![image](media/automate-training-with-cli/cli-binary-classification-metrics.png)

<span data-ttu-id="bbcf6-139">L'accuratezza è una metrica diffusa per i problemi di classificazione, tuttavia l'accuratezza non è sempre la metrica migliore per selezionare il modello migliore da come illustrato nei riferimenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-139">Accuracy is a popular metric for classification problems, however accuracy isn't always the best metric to select the best model from as explained in the following references.</span></span> <span data-ttu-id="bbcf6-140">Vi sono casi in cui è necessario valutare la qualità del modello con metriche supplementari.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-140">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="bbcf6-141">Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la classificazione binaria](resources/metrics.md#evaluation-metrics-for-binary-classification).</span><span class="sxs-lookup"><span data-stu-id="bbcf6-141">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for binary classification](resources/metrics.md#evaluation-metrics-for-binary-classification).</span></span>

### <a name="metrics-for-multi-class-classification-models"></a><span data-ttu-id="bbcf6-142">Metriche per i modelli di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="bbcf6-142">Metrics for Multi-class Classification models</span></span>

<span data-ttu-id="bbcf6-143">Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione multiclasse dei primi cinque modelli individuati dall'interfaccia della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="bbcf6-143">The following displays the multi-class classification ML task metrics list for the top five models found by the CLI:</span></span>

![image](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

<span data-ttu-id="bbcf6-145">Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la classificazione multiclasse](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span><span class="sxs-lookup"><span data-stu-id="bbcf6-145">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for multiclass classification](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-and-recommendation-models"></a><span data-ttu-id="bbcf6-146">Metriche per i modelli di regressione e di raccomandazione</span><span class="sxs-lookup"><span data-stu-id="bbcf6-146">Metrics for Regression and Recommendation models</span></span>

<span data-ttu-id="bbcf6-147">Un modello di regressione risulta adatto ai dati se le differenze tra i valori osservati e valori stimati del modello sono ridotti e non distorti.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-147">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="bbcf6-148">La regressione può essere valutata con alcune metriche.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-148">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="bbcf6-149">Verrà visualizzato un elenco simile di metriche per i primi cinque modelli di qualità trovati dall'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="bbcf6-149">You'll see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="bbcf6-150">In questo caso particolare, correlato a un'attività di regressione dell'apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="bbcf6-150">In this particular case related to a regression ML task:</span></span>

![image](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="bbcf6-152">Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la regressione](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span><span class="sxs-lookup"><span data-stu-id="bbcf6-152">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for regression](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span></span>

## <a name="see-also"></a><span data-ttu-id="bbcf6-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbcf6-153">See also</span></span>

- [<span data-ttu-id="bbcf6-154">Come installare lo strumento dell'interfaccia della riga comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="bbcf6-154">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="bbcf6-155">Esercitazione: analizzare i sentimenti usando l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="bbcf6-155">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="bbcf6-156">Informazioni di riferimento sui comandi dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="bbcf6-156">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="bbcf6-157">Telemetria nell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="bbcf6-157">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)
