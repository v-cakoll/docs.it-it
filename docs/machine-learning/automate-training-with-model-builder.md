---
title: Che cos'è il generatore di modelli e come funziona?
description: Come usare il generatore di modelli di ML.NET per eseguire automaticamente il training di un modello di Machine Learning
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77b5e75fede1a4aa93eadcf7e21591d82f565cab
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929473"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="c7da6-103">Che cos'è il generatore di modelli e come funziona?</span><span class="sxs-lookup"><span data-stu-id="c7da6-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="c7da6-104">Il generatore di modelli di ML.NET è un'estensione grafica intuitiva di Visual Studio che consente di compilare, eseguire il training e distribuire modelli di Machine Learning personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c7da6-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="c7da6-105">Il generatore di modelli usa il Machine Learning automatico (AutoML) per esplorare diversi algoritmi di Machine Learning e impostazioni per individuare quelli più adatti allo scenario.</span><span class="sxs-lookup"><span data-stu-id="c7da6-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="c7da6-106">Non è necessario avere competenze di Machine Learning per usare il generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="c7da6-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="c7da6-107">Servono solo alcuni dati e un problema da risolvere.</span><span class="sxs-lookup"><span data-stu-id="c7da6-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="c7da6-108">Il generatore di modelli genera il codice per aggiungere il modello all'applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="c7da6-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Animazione dell'interfaccia utente dell'estensione del generatore di modelli di Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="c7da6-110">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="c7da6-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="c7da6-111">Scenari</span><span class="sxs-lookup"><span data-stu-id="c7da6-111">Scenarios</span></span>

<span data-ttu-id="c7da6-112">È possibile trasferire molti scenari diversi nel generatore di modelli per generare un modello di Machine Learning per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7da6-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="c7da6-113">Uno scenario è una descrizione del tipo di previsione che si vuole eseguire usando i dati.</span><span class="sxs-lookup"><span data-stu-id="c7da6-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="c7da6-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c7da6-114">For example:</span></span>

- <span data-ttu-id="c7da6-115">prevedere il volume di vendita futuro dei prodotti in base ai dati storici di vendita</span><span class="sxs-lookup"><span data-stu-id="c7da6-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="c7da6-116">classificare le valutazioni come positive o negative in base alle recensioni dei clienti</span><span class="sxs-lookup"><span data-stu-id="c7da6-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="c7da6-117">rilevare se una transazione bancaria è fraudolenta</span><span class="sxs-lookup"><span data-stu-id="c7da6-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="c7da6-118">indirizzare i problemi dei feedback dei clienti al team corretto nell'azienda</span><span class="sxs-lookup"><span data-stu-id="c7da6-118">route customer feedback issues to the correct team in your company</span></span>

## <a name="choose-a-model-type"></a><span data-ttu-id="c7da6-119">Scegliere un tipo di modello</span><span class="sxs-lookup"><span data-stu-id="c7da6-119">Choose a model type</span></span>

<span data-ttu-id="c7da6-120">Nel generatore di modelli è necessario selezionare un tipo di modello di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="c7da6-120">In Model Builder, you need to select a machine learning model type.</span></span> <span data-ttu-id="c7da6-121">Il tipo di modello dipende dal tipo di stima che si sta tentando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="c7da6-121">The type of model depends on what sort of prediction you are trying to make.</span></span>

<span data-ttu-id="c7da6-122">Per gli scenari in cui viene stimato un numero, il tipo di modello di Machine Learning è chiamato `regression`.</span><span class="sxs-lookup"><span data-stu-id="c7da6-122">For scenarios that predict a number, the machine learning model type is called `regression`.</span></span>

<span data-ttu-id="c7da6-123">Per gli scenari di stima di una categoria, il tipo di modello è `classification`.</span><span class="sxs-lookup"><span data-stu-id="c7da6-123">For scenarios that predict a category, the model type is `classification`.</span></span> <span data-ttu-id="c7da6-124">Sono disponibili due tipi di classificazione:</span><span class="sxs-lookup"><span data-stu-id="c7da6-124">There are two types of classification:</span></span>

- <span data-ttu-id="c7da6-125">dove sono disponibili solo 2 categorie: `binary classification`.</span><span class="sxs-lookup"><span data-stu-id="c7da6-125">where there are only 2 categories: `binary classification`.</span></span>
- <span data-ttu-id="c7da6-126">dove sono disponibili tre o più categorie: `multiclass classification`.</span><span class="sxs-lookup"><span data-stu-id="c7da6-126">where there are three or more categories: `multiclass classification`.</span></span>

### <a name="which-model-type-is-right-for-me"></a><span data-ttu-id="c7da6-127">Quale tipo di modello scegliere?</span><span class="sxs-lookup"><span data-stu-id="c7da6-127">Which model type is right for me?</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="c7da6-128">Stimare una categoria (quando esistono solo due categorie)</span><span class="sxs-lookup"><span data-stu-id="c7da6-128">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="c7da6-129">La classificazione binaria viene usata per classificare i dati in due categorie (sì/no; superato/non superato; vero/falso; positivo/negativo).</span><span class="sxs-lookup"><span data-stu-id="c7da6-129">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![Diagramma che mostra esempi di classificazione binaria, tra cui il rilevamento delle frodi, la mitigazione dei rischi e lo screening delle applicazioni](media/binary-classification-examples.png)

<span data-ttu-id="c7da6-131">L'analisi del sentiment può essere usata per prevedere il sentiment positivo o negativo del feedback dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c7da6-131">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="c7da6-132">È un esempio del tipo di modello di classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="c7da6-132">It is an example of a binary classification model type.</span></span>

<span data-ttu-id="c7da6-133">Se lo scenario richiede la classificazione in due categorie, è possibile usare questo modello con il proprio set di dati.</span><span class="sxs-lookup"><span data-stu-id="c7da6-133">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="c7da6-134">Stimare una categoria (quando sono presenti tre o più categorie)</span><span class="sxs-lookup"><span data-stu-id="c7da6-134">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="c7da6-135">La classificazione multiclasse può essere usata per classificare i dati in tre o più classi.</span><span class="sxs-lookup"><span data-stu-id="c7da6-135">Multiclass classification can be used to categorize data into three or more classes.</span></span> 

![Esempi di classificazione multiclasse, tra cui la classificazione di documenti e prodotti, il routing dei ticket di supporto e l'assegnazione di priorità ai problemi dei clienti](media/multiclass-classification-examples.png)

<span data-ttu-id="c7da6-137">La classificazione dei problemi può essere usata per classificare i problemi dei feedback dei clienti, ad esempio in GitHub, usando il titolo del problema e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="c7da6-137">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="c7da6-138">È un esempio del tipo di modello di classificazione multiclasse.</span><span class="sxs-lookup"><span data-stu-id="c7da6-138">It is an example of the multi-class classification model type.</span></span>

<span data-ttu-id="c7da6-139">Se si vuole classificare i dati in tre o più categorie, è possibile usare il modello di classificazione dei problemi per il proprio scenario.</span><span class="sxs-lookup"><span data-stu-id="c7da6-139">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="c7da6-140">Stimare un numero</span><span class="sxs-lookup"><span data-stu-id="c7da6-140">Predict a number</span></span>

<span data-ttu-id="c7da6-141">La regressione viene usata per prevedere i numeri.</span><span class="sxs-lookup"><span data-stu-id="c7da6-141">Regression is used to predict numbers.</span></span>

![Diagramma che mostra esempi di regressione, ad esempio stime del prezzo, previsioni di vendita e manutenzione predittiva](media/regression-examples.png)

<span data-ttu-id="c7da6-143">La stima dei prezzi può essere usata per stimare i prezzi delle case in base alla posizione, alla dimensione e ad altre caratteristiche della casa.</span><span class="sxs-lookup"><span data-stu-id="c7da6-143">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="c7da6-144">È un esempio del tipo di modello di regressione.</span><span class="sxs-lookup"><span data-stu-id="c7da6-144">It is an example of a regression model type.</span></span>

<span data-ttu-id="c7da6-145">Se si vuole prevedere un valore numerico con il proprio set di dati, è possibile usare il modello di stima dei prezzi per il proprio scenario.</span><span class="sxs-lookup"><span data-stu-id="c7da6-145">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-model-type"></a><span data-ttu-id="c7da6-146">Scenario personalizzato (scegliere il tipo di modello)</span><span class="sxs-lookup"><span data-stu-id="c7da6-146">Custom scenario (choose your model type)</span></span>

<span data-ttu-id="c7da6-147">Lo scenario personalizzato consente di scegliere manualmente il tipo di modello.</span><span class="sxs-lookup"><span data-stu-id="c7da6-147">The custom scenario allows you to manually choose your model type.</span></span>

## <a name="data"></a><span data-ttu-id="c7da6-148">Data</span><span class="sxs-lookup"><span data-stu-id="c7da6-148">Data</span></span>

<span data-ttu-id="c7da6-149">Dopo aver scelto il tipo di modello, il generatore di modelli richiede di specificare un set di dati.</span><span class="sxs-lookup"><span data-stu-id="c7da6-149">Once you have chosen your model type, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="c7da6-150">I dati vengono usati per il training, la valutazione e la scelta del modello più adatto per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="c7da6-150">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Diagramma che illustra i passaggi del generatore di modelli](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="c7da6-152">Scegliere l'output da prevedere (etichetta)</span><span class="sxs-lookup"><span data-stu-id="c7da6-152">Choose the output to predict (label)</span></span>

<span data-ttu-id="c7da6-153">Un set di dati è una tabella di righe di esempi di training e di colonne di attributi.</span><span class="sxs-lookup"><span data-stu-id="c7da6-153">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="c7da6-154">Ogni riga include:</span><span class="sxs-lookup"><span data-stu-id="c7da6-154">Each row has:</span></span>

- <span data-ttu-id="c7da6-155">un'**etichetta** (l'attributo da prevedere)</span><span class="sxs-lookup"><span data-stu-id="c7da6-155">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="c7da6-156">le **caratteristiche** (gli attributi usati come input per la previsione dell'etichetta).</span><span class="sxs-lookup"><span data-stu-id="c7da6-156">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="c7da6-157">Per lo scenario di stima del prezzo della casa, è possibile usare le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7da6-157">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="c7da6-158">i metri quadrati della casa</span><span class="sxs-lookup"><span data-stu-id="c7da6-158">the square footage of the house</span></span>
- <span data-ttu-id="c7da6-159">il numero di camere da letto e bagni</span><span class="sxs-lookup"><span data-stu-id="c7da6-159">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="c7da6-160">il codice postale</span><span class="sxs-lookup"><span data-stu-id="c7da6-160">the zip code</span></span>

<span data-ttu-id="c7da6-161">L'etichetta è il prezzo storico della casa per la riga dei valori dei metri quadrati, delle camere da letto e dei bagni e il codice postale.</span><span class="sxs-lookup"><span data-stu-id="c7da6-161">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Tabella che mostra le righe e le colonne di dati sui prezzi delle case con le caratteristiche delle dimensioni dei locali, del codice postale e dell'etichetta del prezzo](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="c7da6-163">Set di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="c7da6-163">Example datasets</span></span>

<span data-ttu-id="c7da6-164">Se non sono ancora disponibili dati, provare uno dei set di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7da6-164">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="c7da6-165">Scenario</span><span class="sxs-lookup"><span data-stu-id="c7da6-165">Scenario</span></span>|<span data-ttu-id="c7da6-166">Tipo di modello</span><span class="sxs-lookup"><span data-stu-id="c7da6-166">Model Type</span></span>|<span data-ttu-id="c7da6-167">Data</span><span class="sxs-lookup"><span data-stu-id="c7da6-167">Data</span></span>|<span data-ttu-id="c7da6-168">Label</span><span class="sxs-lookup"><span data-stu-id="c7da6-168">Label</span></span>|<span data-ttu-id="c7da6-169">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="c7da6-169">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="c7da6-170">Stima dei prezzi</span><span class="sxs-lookup"><span data-stu-id="c7da6-170">Price prediction</span></span>|<span data-ttu-id="c7da6-171">Regressione</span><span class="sxs-lookup"><span data-stu-id="c7da6-171">regression</span></span>|[<span data-ttu-id="c7da6-172">dati delle tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="c7da6-172">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="c7da6-173">Tariffe</span><span class="sxs-lookup"><span data-stu-id="c7da6-173">Fare</span></span>|<span data-ttu-id="c7da6-174">Tempo della corsa, distanza</span><span class="sxs-lookup"><span data-stu-id="c7da6-174">Trip time, distance</span></span>|
|<span data-ttu-id="c7da6-175">Rilevamento di anomalie</span><span class="sxs-lookup"><span data-stu-id="c7da6-175">Anomaly detection</span></span>|<span data-ttu-id="c7da6-176">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="c7da6-176">binary classification</span></span>|[<span data-ttu-id="c7da6-177">dati di vendita dei prodotti</span><span class="sxs-lookup"><span data-stu-id="c7da6-177">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="c7da6-178">Vendita dei prodotti</span><span class="sxs-lookup"><span data-stu-id="c7da6-178">Product Sales</span></span>|<span data-ttu-id="c7da6-179">Mese</span><span class="sxs-lookup"><span data-stu-id="c7da6-179">Month</span></span>|
|<span data-ttu-id="c7da6-180">Analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="c7da6-180">Sentiment analysis</span></span>|<span data-ttu-id="c7da6-181">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="c7da6-181">binary classification</span></span>|[<span data-ttu-id="c7da6-182">dati dei commenti del sito Web</span><span class="sxs-lookup"><span data-stu-id="c7da6-182">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="c7da6-183">Etichetta (0 con sentiment negativo, 1 con sentiment positivo)</span><span class="sxs-lookup"><span data-stu-id="c7da6-183">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="c7da6-184">Commento, anno</span><span class="sxs-lookup"><span data-stu-id="c7da6-184">Comment, Year</span></span>|
|<span data-ttu-id="c7da6-185">Rilevamento di frodi</span><span class="sxs-lookup"><span data-stu-id="c7da6-185">Fraud detection</span></span>|<span data-ttu-id="c7da6-186">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="c7da6-186">binary classification</span></span>|[<span data-ttu-id="c7da6-187">dati della carta di credito</span><span class="sxs-lookup"><span data-stu-id="c7da6-187">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="c7da6-188">Classe (1 quando fraudolento, 0 in caso contrario)</span><span class="sxs-lookup"><span data-stu-id="c7da6-188">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="c7da6-189">Quantità, V1-V28 (caratteristiche anonime)</span><span class="sxs-lookup"><span data-stu-id="c7da6-189">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="c7da6-190">Classificazione testo</span><span class="sxs-lookup"><span data-stu-id="c7da6-190">Text classification</span></span>|<span data-ttu-id="c7da6-191">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="c7da6-191">multiclass classification</span></span>|[<span data-ttu-id="c7da6-192">dati del problema di GitHub</span><span class="sxs-lookup"><span data-stu-id="c7da6-192">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="c7da6-193">Area</span><span class="sxs-lookup"><span data-stu-id="c7da6-193">Area</span></span>|<span data-ttu-id="c7da6-194">Titolo, descrizione</span><span class="sxs-lookup"><span data-stu-id="c7da6-194">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="c7da6-195">Eseguire il training</span><span class="sxs-lookup"><span data-stu-id="c7da6-195">Train</span></span>

<span data-ttu-id="c7da6-196">Dopo aver selezionato lo scenario, i dati e l'etichetta, il generatore di modelli esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="c7da6-196">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="c7da6-197">Cos'è il training?</span><span class="sxs-lookup"><span data-stu-id="c7da6-197">What is training?</span></span>

<span data-ttu-id="c7da6-198">Il training è un processo automatico tramite il quale il generatore di modelli indica al modello come rispondere alle domande per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="c7da6-198">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="c7da6-199">Dopo aver eseguito il training, il modello può effettuare previsioni con dati di input completamente nuovi.</span><span class="sxs-lookup"><span data-stu-id="c7da6-199">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="c7da6-200">Ad esempio, se si sta eseguendo la stima dei prezzi e viene immessa sul mercato una nuova casa, è possibile prevederne il prezzo di vendita.</span><span class="sxs-lookup"><span data-stu-id="c7da6-200">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="c7da6-201">Poiché il generatore di modelli usa Il Machine Learning automatico (AutoML), non viene richiesto alcun input o ottimizzazione durante il training.</span><span class="sxs-lookup"><span data-stu-id="c7da6-201">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

## <a name="evaluate"></a><span data-ttu-id="c7da6-202">Valutare</span><span class="sxs-lookup"><span data-stu-id="c7da6-202">Evaluate</span></span>

<span data-ttu-id="c7da6-203">La valutazione è il processo di utilizzo del modello con training per effettuare previsioni con nuovi dati di test e quindi misurare la qualità delle previsioni.</span><span class="sxs-lookup"><span data-stu-id="c7da6-203">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="c7da6-204">Il generatore di modelli suddivide i dati di training in un set di training e un set di test.</span><span class="sxs-lookup"><span data-stu-id="c7da6-204">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="c7da6-205">I dati di training (80%) vengono usati per eseguire il training del modello, mentre i dati di test (20%) vengono usati per la valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="c7da6-205">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> <span data-ttu-id="c7da6-206">Il generatore di modelli usa le metriche per misurare la qualità del modello.</span><span class="sxs-lookup"><span data-stu-id="c7da6-206">Model Builder uses metrics to measure how good the model is.</span></span> <span data-ttu-id="c7da6-207">Le metriche specifiche usate dipendono dal tipo di modello.</span><span class="sxs-lookup"><span data-stu-id="c7da6-207">The specific metrics used are dependent on the type of model.</span></span> <span data-ttu-id="c7da6-208">Per altre informazioni, vedere [Metriche di valutazione dei modelli](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="c7da6-208">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="c7da6-209">Migliorare</span><span class="sxs-lookup"><span data-stu-id="c7da6-209">Improve</span></span>

<span data-ttu-id="c7da6-210">Se il punteggio delle prestazioni del modello non è quello desiderato, è possibile:</span><span class="sxs-lookup"><span data-stu-id="c7da6-210">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="c7da6-211">Eseguire il training per un periodo di tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="c7da6-211">Train for a longer period of time.</span></span> <span data-ttu-id="c7da6-212">Con un periodo di tempo più lungo, il motore di Machine Learning automatico proverà più algoritmi e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c7da6-212">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="c7da6-213">Aggiungere altri dati.</span><span class="sxs-lookup"><span data-stu-id="c7da6-213">Add more data.</span></span> <span data-ttu-id="c7da6-214">A volte la quantità di dati non è sufficiente per eseguire il training di un modello di Machine Learning di qualità elevata.</span><span class="sxs-lookup"><span data-stu-id="c7da6-214">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="c7da6-215">Bilanciare i dati.</span><span class="sxs-lookup"><span data-stu-id="c7da6-215">Balance your data.</span></span> <span data-ttu-id="c7da6-216">Per le attività di classificazione, assicurarsi che il set di training sia bilanciato tra le categorie.</span><span class="sxs-lookup"><span data-stu-id="c7da6-216">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="c7da6-217">Ad esempio, se sono presenti quattro classi per 100 esempi di training e le prime due classi (tag1 e tag2) vengono usate per 90 record mentre le altre due classi (tag3 e tag4) vengono usate solo per i rimanenti 10 record, la mancanza di dati bilanciati può rendere più difficile per il modello prevedere correttamente tag3 o tag4.</span><span class="sxs-lookup"><span data-stu-id="c7da6-217">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="c7da6-218">Codice</span><span class="sxs-lookup"><span data-stu-id="c7da6-218">Code</span></span>

<span data-ttu-id="c7da6-219">Dopo la fase di valutazione, il generatore di modelli restituisce un file di modello e il codice che è possibile usare per aggiungere il modello all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7da6-219">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="c7da6-220">I modelli di ML.NET vengono salvati come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="c7da6-220">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="c7da6-221">Il codice per caricare e usare il modello viene aggiunto come nuovo progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="c7da6-221">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="c7da6-222">Il generatore di modelli aggiunge anche un'app console di esempio che è possibile eseguire per visualizzare il modello in azione.</span><span class="sxs-lookup"><span data-stu-id="c7da6-222">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="c7da6-223">Il generatore di modelli restituisce anche il codice che ha generato il modello che consente di comprendere i passaggi eseguiti per generare il modello.</span><span class="sxs-lookup"><span data-stu-id="c7da6-223">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="c7da6-224">È anche possibile usare il codice di training del modello per ripetere il training del modello con nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="c7da6-224">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="c7da6-225">Argomenti successivi</span><span class="sxs-lookup"><span data-stu-id="c7da6-225">What's next?</span></span>

<span data-ttu-id="c7da6-226">[Installare](how-to-guides/install-model-builder.md) l'estensione di Visual Studio per il generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="c7da6-226">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="c7da6-227">Provare [uno scenario di regressione o stima dei prezzi](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="c7da6-227">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
