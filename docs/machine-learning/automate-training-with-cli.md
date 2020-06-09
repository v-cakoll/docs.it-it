---
title: Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET
description: Informazioni su come usare lo strumento dell'interfaccia della riga di comando ML.NET per eseguire automaticamente il training del modello migliore dalla riga di comando.
ms.date: 06/03/2020
ms.custom: how-to, mlnet-tooling
ms.openlocfilehash: d7c6102c2257be1daa613fde0edabce83d04b414
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589662"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="7cc11-103">Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="7cc11-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="7cc11-104">L'interfaccia della riga di comando di ML.NET automatizza la generazione di modelli per gli sviluppatori .NET.</span><span class="sxs-lookup"><span data-stu-id="7cc11-104">The ML.NET CLI automates model generation for .NET developers.</span></span>

<span data-ttu-id="7cc11-105">Per usare l'API ML.NET in modo indipendente, ovvero senza l'interfaccia della riga di comando AutoML di ML.NET, è necessario scegliere un formatore (implementazione di un algoritmo di apprendimento automatico per una determinata attività) e il set di trasformazioni dei dati (progettazione di funzionalità) da applicare ai dati.</span><span class="sxs-lookup"><span data-stu-id="7cc11-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="7cc11-106">La pipeline ottimale varia in base al set di dati e selezionare l'algoritmo ottimale da tutte le opzioni disponibili aumenta la complessità.</span><span class="sxs-lookup"><span data-stu-id="7cc11-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="7cc11-107">In più, ogni algoritmo ha un set di iperparametri da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="7cc11-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="7cc11-108">Di conseguenza, il processo di ottimizzazione del modello di apprendimento automatico può richiedere settimane, a volte mesi, poiché si tenta di trovare le combinazioni migliori di progettazione di funzionalità, algoritmi di apprendimento e iperparametri.</span><span class="sxs-lookup"><span data-stu-id="7cc11-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="7cc11-109">L'interfaccia della riga di comando di ML.NET semplifica questo processo usando automazione Machine Learning (AutoML).</span><span class="sxs-lookup"><span data-stu-id="7cc11-109">The ML.NET CLI simplifies this process using automated machine learning (AutoML).</span></span>

> [!NOTE]
> <span data-ttu-id="7cc11-110">Questo argomento fa riferimento all'**interfaccia della riga di comando** ML.NET e alla funzionalità di Machine Learning automatico (**AutoML**), attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="7cc11-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="7cc11-111">Che cos'è l'interfaccia della riga di comando di ML.NET?</span><span class="sxs-lookup"><span data-stu-id="7cc11-111">What is the ML.NET command-line interface (CLI)?</span></span>

<span data-ttu-id="7cc11-112">L'interfaccia della riga di comando di ML.NET è uno [strumento di .NET Core](../core/tools/global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7cc11-112">The ML.NET CLI is a [.NET Core tool](../core/tools/global-tools.md).</span></span> <span data-ttu-id="7cc11-113">Una volta eseguita l'installazione, viene assegnata un'attività di machine learning e un set di dati di training e viene generato un modello ML.NET, nonché il codice C# da eseguire per usare il modello nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7cc11-113">Once installed, you give it a machine learning task and a training dataset, and it generates an ML.NET model, as well as the C# code to run to use the model in your application.</span></span>

<span data-ttu-id="7cc11-114">Come illustrato nella figura seguente, è semplice generare un modello ML.NET di qualità elevata (file con estensione zip del modello serializzato) più il codice C# di esempio per eseguire/assegnare un punteggio a tale modello.</span><span class="sxs-lookup"><span data-stu-id="7cc11-114">As shown in the following figure, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="7cc11-115">Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello in modo da ricercare l'algoritmo e le impostazioni usate per il "modello ottimale" generato.</span><span class="sxs-lookup"><span data-stu-id="7cc11-115">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span>

<span data-ttu-id="7cc11-116">![image](media/automate-training-with-cli/cli-high-level-process.png "Motore AutoML che funziona nell'interfaccia della riga di comando di ML.NET")</span><span class="sxs-lookup"><span data-stu-id="7cc11-116">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="7cc11-117">Poiché questi asset si possono generare dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7cc11-117">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="7cc11-118">Attualmente, le attività di Machine Learning supportate dall'interfaccia della riga di comando di ML.NET sono:</span><span class="sxs-lookup"><span data-stu-id="7cc11-118">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- <span data-ttu-id="7cc11-119">classificazione (binaria e multiclasse)</span><span class="sxs-lookup"><span data-stu-id="7cc11-119">classification (binary and multi-class)</span></span>
- <span data-ttu-id="7cc11-120">Regressione</span><span class="sxs-lookup"><span data-stu-id="7cc11-120">regression</span></span>
- <span data-ttu-id="7cc11-121">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7cc11-121">recommendation</span></span>
- <span data-ttu-id="7cc11-122">Futuro: altre attività di Machine Learning, ad esempio classificazione delle immagini, rango, rilevamento di anomalie, clustering</span><span class="sxs-lookup"><span data-stu-id="7cc11-122">Future: other machine learning tasks such as image-classification, ranking, anomaly-detection, clustering</span></span>

<span data-ttu-id="7cc11-123">Esempio di utilizzo (scenario di classificazione):</span><span class="sxs-lookup"><span data-stu-id="7cc11-123">Example of usage (classification scenario):</span></span>

```console
mlnet classification --dataset "yelp_labelled.txt" --label-col 1 --has-header false --train-time 10
```

![image](media/automate-training-with-cli/mlnet-classification-powershell.gif)

<span data-ttu-id="7cc11-125">È possibile eseguirlo nello stesso modo in *Windows PowerShell*, *MacOS/Linux Bash*o *Windows cmd*.</span><span class="sxs-lookup"><span data-stu-id="7cc11-125">You can run it the same way on *Windows PowerShell*, *macOS/Linux bash*, or *Windows CMD*.</span></span> <span data-ttu-id="7cc11-126">Tuttavia, il completamento automatico in formato tabella (suggerimento dei parametri) non funzionerà nella *finestra di comando di Windows*.</span><span class="sxs-lookup"><span data-stu-id="7cc11-126">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="7cc11-127">Asset di output generati</span><span class="sxs-lookup"><span data-stu-id="7cc11-127">Output assets generated</span></span>

<span data-ttu-id="7cc11-128">I comandi dell'attività ML nell'interfaccia della riga di comando generano gli asset seguenti nella cartella di output:</span><span class="sxs-lookup"><span data-stu-id="7cc11-128">The ML task commands in the CLI generate the following assets in the output folder:</span></span>

- <span data-ttu-id="7cc11-129">Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso nell'esecuzione di stime.</span><span class="sxs-lookup"><span data-stu-id="7cc11-129">A serialized model .zip ("best model") ready to use for running predictions.</span></span>
- <span data-ttu-id="7cc11-130">Soluzione C# con:</span><span class="sxs-lookup"><span data-stu-id="7cc11-130">C# solution with:</span></span>
  - <span data-ttu-id="7cc11-131">Il codice C# per eseguire e assegnare punteggi al modello generato (per eseguire stime nelle app per utenti finali con il modello).</span><span class="sxs-lookup"><span data-stu-id="7cc11-131">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
  - <span data-ttu-id="7cc11-132">Il codice C# con il codice di training usato per generare il modello (a scopo di apprendimento o nuovo training del modello).</span><span class="sxs-lookup"><span data-stu-id="7cc11-132">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="7cc11-133">File di log con informazioni su tutte le iterazioni e gli sweep eseguiti su più algoritmi valutati, inclusa la configurazione/pipeline dettagliata.</span><span class="sxs-lookup"><span data-stu-id="7cc11-133">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="7cc11-134">I primi due asset possono essere usati direttamente nelle app degli utenti finali (app Web ASP.NET Core, servizi, app desktop e così via) per effettuare previsioni con il modello di Machine Learning generato.</span><span class="sxs-lookup"><span data-stu-id="7cc11-134">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="7cc11-135">Il terzo asset, ovvero il codice di training, indica quale codice API ML.NET è stato usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo che sia possibile ripetere il training del modello ed esaminare il formatore/algoritmo e gli iperparametri specifici selezionati in background dall'interfaccia della riga di comando e dalla funzionalità AutoML.</span><span class="sxs-lookup"><span data-stu-id="7cc11-135">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span>

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="7cc11-136">Informazioni sulla qualità del modello</span><span class="sxs-lookup"><span data-stu-id="7cc11-136">Understanding the quality of the model</span></span>

<span data-ttu-id="7cc11-137">Quando si genera un modello "migliore" con lo strumento dell'interfaccia della riga di comando, vengono visualizzate le metriche qualitative (ad esempio l'accuratezza e il quadrato R) in base alle esigenze dell'attività ML di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7cc11-137">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy and R-Squared) as appropriate for the ML task you're targeting.</span></span>

<span data-ttu-id="7cc11-138">Queste metriche vengono riepilogate raggruppate per attività di Machine Learning, in modo che sia possibile comprendere la qualità del "modello migliore" generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7cc11-138">Here those metrics are summarized grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-classification-models"></a><span data-ttu-id="7cc11-139">Metriche per i modelli di classificazione</span><span class="sxs-lookup"><span data-stu-id="7cc11-139">Metrics for Classification models</span></span>

<span data-ttu-id="7cc11-140">Di seguito viene visualizzato l'elenco delle metriche di classificazione per i primi cinque modelli trovati dall'interfaccia della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="7cc11-140">The following displays the classification metrics list for the top five models found by the CLI:</span></span>

![image](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

 <span data-ttu-id="7cc11-142">L'accuratezza è una metrica diffusa per i problemi di classificazione, tuttavia l'accuratezza non è sempre la metrica migliore per selezionare il modello migliore da come illustrato nei riferimenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="7cc11-142">Accuracy is a popular metric for classification problems, however accuracy isn't always the best metric to select the best model from as explained in the following references.</span></span> <span data-ttu-id="7cc11-143">Vi sono casi in cui è necessario valutare la qualità del modello con metriche supplementari.</span><span class="sxs-lookup"><span data-stu-id="7cc11-143">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="7cc11-144">Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la classificazione](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span><span class="sxs-lookup"><span data-stu-id="7cc11-144">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for classification](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-and-recommendation-models"></a><span data-ttu-id="7cc11-145">Metriche per i modelli di regressione e di raccomandazione</span><span class="sxs-lookup"><span data-stu-id="7cc11-145">Metrics for Regression and Recommendation models</span></span>

<span data-ttu-id="7cc11-146">Un modello di regressione risulta adatto ai dati se le differenze tra i valori osservati e valori stimati del modello sono ridotti e non distorti.</span><span class="sxs-lookup"><span data-stu-id="7cc11-146">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="7cc11-147">La regressione può essere valutata con alcune metriche.</span><span class="sxs-lookup"><span data-stu-id="7cc11-147">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="7cc11-148">Verrà visualizzato un elenco simile di metriche per i primi cinque modelli di qualità trovati dall'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7cc11-148">You'll see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="7cc11-149">In questo caso particolare, correlato a un'attività di regressione dell'apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="7cc11-149">In this particular case related to a regression ML task:</span></span>

![image](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="7cc11-151">Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la regressione](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span><span class="sxs-lookup"><span data-stu-id="7cc11-151">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for regression](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span></span>

## <a name="see-also"></a><span data-ttu-id="7cc11-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cc11-152">See also</span></span>

- [<span data-ttu-id="7cc11-153">Come installare lo strumento dell'interfaccia della riga comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="7cc11-153">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="7cc11-154">Esercitazione: analizzare i sentimenti usando l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="7cc11-154">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="7cc11-155">Informazioni di riferimento sui comandi dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="7cc11-155">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="7cc11-156">Telemetria nell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="7cc11-156">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)
