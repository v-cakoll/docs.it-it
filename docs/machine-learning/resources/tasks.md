---
title: Attività di apprendimento automatico
description: Esplorare le diverse attività di apprendimento automatico e le attività associate supportate in ML.NET.
ms.custom: seodec18
ms.date: 04/23/2019
author: natke
ms.openlocfilehash: bcd967c11156ca9b837631560e78722b13fc7ae0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630059"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="340c7-103">Attività di apprendimento automatico in ML.NET</span><span class="sxs-lookup"><span data-stu-id="340c7-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="340c7-104">Quando si compila un modello di apprendimento automatico, è innanzitutto necessario definire quale risultato si vuole ottenere con i dati.</span><span class="sxs-lookup"><span data-stu-id="340c7-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="340c7-105">In tal modo è possibile scegliere l'attività di apprendimento automatico più adatta alla specifica situazione.</span><span class="sxs-lookup"><span data-stu-id="340c7-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="340c7-106">Nell'elenco seguente sono descritte le diverse attività di apprendimento automatico tra cui è possibile scegliere e alcuni casi d'uso comuni.</span><span class="sxs-lookup"><span data-stu-id="340c7-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="340c7-107">Dopo aver deciso quale attività è appropriata per il proprio scenario, è necessario scegliere l'algoritmo migliore per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="340c7-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="340c7-108">Gli algoritmi disponibili sono elencati nella sezione per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="340c7-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="340c7-109">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="340c7-109">Binary classification</span></span>

<span data-ttu-id="340c7-110">Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stabilire a quale di due classi (categorie) appartiene un'istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="340c7-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="340c7-111">L'input di un algoritmo di classificazione è un set di esempi con etichette, in cui ogni etichetta è un numero intero 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="340c7-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="340c7-112">L'output di un algoritmo di classificazione binaria è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette.</span><span class="sxs-lookup"><span data-stu-id="340c7-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="340c7-113">Alcuni esempi di scenari di classificazione binaria sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="340c7-114">[Comprensione del sentiment dei commenti di Twitter](../tutorials/sentiment-analysis.md) come "positivi" o "negativi".</span><span class="sxs-lookup"><span data-stu-id="340c7-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="340c7-115">Diagnosi per stabilire se un paziente ha o meno una determinata malattia.</span><span class="sxs-lookup"><span data-stu-id="340c7-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="340c7-116">Decisione di contrassegnare o meno un messaggio di posta elettronica come "posta indesiderata".</span><span class="sxs-lookup"><span data-stu-id="340c7-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="340c7-117">Identificazione di un cane o di un frutto all'interno di una foto.</span><span class="sxs-lookup"><span data-stu-id="340c7-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="340c7-118">Per altre informazioni, vedere l'articolo relativo alla [classificazione binaria](https://en.wikipedia.org/wiki/Binary_classification) su Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="340c7-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="340c7-119">Algoritmi di training di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="340c7-119">Binary classification trainers</span></span>

<span data-ttu-id="340c7-120">È possibile eseguire il training di un modello di classificazione binaria usando gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer> 
* <xref:Microsoft.ML.Trainers.PriorTrainer> 
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="340c7-121">Input e output di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="340c7-121">Binary classification inputs and outputs</span></span>

<span data-ttu-id="340c7-122">Per ottenere risultati ottimali con la classificazione binaria, i dati di training devono essere bilanciati, vale a dire avere un numero uguale di dati di training positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="340c7-122">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="340c7-123">I valori mancanti devono essere gestiti prima del training.</span><span class="sxs-lookup"><span data-stu-id="340c7-123">Missing values should be handled before training.</span></span>

<span data-ttu-id="340c7-124">I dati della colonna dell'etichetta di input devono essere <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="340c7-124">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="340c7-125">I dati della colonna delle funzionalità di input devono essere un vettore a dimensione fissa di <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="340c7-125">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="340c7-126">Questi algoritmi di training restituiscono le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-126">These trainers outputs the following columns:</span></span>

| <span data-ttu-id="340c7-127">Nome colonna di output</span><span class="sxs-lookup"><span data-stu-id="340c7-127">Output Column Name</span></span> | <span data-ttu-id="340c7-128">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="340c7-128">Column Type</span></span> | <span data-ttu-id="340c7-129">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="340c7-129">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="340c7-130">Il punteggio non elaborato calcolato dal modello</span><span class="sxs-lookup"><span data-stu-id="340c7-130">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="340c7-131">L'etichetta stimata, in base al segno del punteggio.</span><span class="sxs-lookup"><span data-stu-id="340c7-131">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="340c7-132">Un punteggio negativo esegue il mapping a `false` e un punteggio negativo esegue il mapping a `true`.</span><span class="sxs-lookup"><span data-stu-id="340c7-132">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="340c7-133">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="340c7-133">Multiclass classification</span></span>

<span data-ttu-id="340c7-134">Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare la classe (categoria) di un'istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="340c7-134">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="340c7-135">L'input di un algoritmo di classificazione è un set di esempi con etichette.</span><span class="sxs-lookup"><span data-stu-id="340c7-135">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="340c7-136">In genere ogni etichetta è inizialmente costituita da testo.</span><span class="sxs-lookup"><span data-stu-id="340c7-136">Each label normally starts as text.</span></span> <span data-ttu-id="340c7-137">Viene quindi elaborata da TermTransform, che la converte nel tipo Key (numerico).</span><span class="sxs-lookup"><span data-stu-id="340c7-137">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="340c7-138">L'output di un algoritmo di classificazione è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette.</span><span class="sxs-lookup"><span data-stu-id="340c7-138">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="340c7-139">Alcuni esempi di scenari di classificazione multiclasse sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-139">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="340c7-140">Determinare la razza di un cane come "siberian husky", "golden retriever", "barboncino" e così via.</span><span class="sxs-lookup"><span data-stu-id="340c7-140">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="340c7-141">Classificare recensioni di film come "positive", "neutrali" o "negative".</span><span class="sxs-lookup"><span data-stu-id="340c7-141">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="340c7-142">Classificare recensioni di hotel in base a "posizione", "prezzo", "pulizia" e così via.</span><span class="sxs-lookup"><span data-stu-id="340c7-142">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="340c7-143">Per altre informazioni, vedere l'articolo relativo alla [classificazione multiclasse](https://en.wikipedia.org/wiki/Multiclass_classification) su Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="340c7-143">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="340c7-144">Il modello "uno contro tutti" aggiorna gli [algoritmi di apprendimento per la classificazione binaria](#binary-classification) in modo che possano agire sui set di dati multiclasse.</span><span class="sxs-lookup"><span data-stu-id="340c7-144">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="340c7-145">Per altre informazioni, vedere [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="340c7-145">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="340c7-146">Algoritmi di training di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="340c7-146">Multiclass classification trainers</span></span>

<span data-ttu-id="340c7-147">È possibile eseguire il training di un modello di classificazione multiclasse usando gli algoritmi di training seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-147">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer> 

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="340c7-148">Input e output di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="340c7-148">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="340c7-149">I dati della colonna dell'etichetta di input devono essere di tipo [key](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="340c7-149">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="340c7-150">La colonna delle funzionalità deve essere un vettore di dimensioni fisse di <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="340c7-150">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="340c7-151">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="340c7-151">This trainer outputs the following:</span></span>

| <span data-ttu-id="340c7-152">Nome output</span><span class="sxs-lookup"><span data-stu-id="340c7-152">Output Name</span></span> | <span data-ttu-id="340c7-153">Tipo</span><span class="sxs-lookup"><span data-stu-id="340c7-153">Type</span></span> | <span data-ttu-id="340c7-154">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="340c7-154">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="340c7-155">Vettore di <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="340c7-155">Vector of <xref:System.Single></span></span> | <span data-ttu-id="340c7-156">I punteggi di tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="340c7-156">The scores of all classes.</span></span> <span data-ttu-id="340c7-157">Valori più alti indicano maggiori probabilità di rientrare nella classe associata.</span><span class="sxs-lookup"><span data-stu-id="340c7-157">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="340c7-158">Se l'elemento i-esimo ha il valore più elevato, l'indice delle etichette stimate sarà i.</span><span class="sxs-lookup"><span data-stu-id="340c7-158">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="340c7-159">Si noti che i è l'indice a base zero.</span><span class="sxs-lookup"><span data-stu-id="340c7-159">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="340c7-160">Tipo [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="340c7-160">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="340c7-161">L'indice dell'etichetta stimata.</span><span class="sxs-lookup"><span data-stu-id="340c7-161">The predicted label's index.</span></span> <span data-ttu-id="340c7-162">Se il valore è i, l'etichetta effettiva potrebbe essere la categoria i-esima nel tipo di etichetta di input con valori key.</span><span class="sxs-lookup"><span data-stu-id="340c7-162">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="340c7-163">Regressione</span><span class="sxs-lookup"><span data-stu-id="340c7-163">Regression</span></span>

<span data-ttu-id="340c7-164">Un attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare il valore dell'etichetta da un set di funzionalità correlate.</span><span class="sxs-lookup"><span data-stu-id="340c7-164">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="340c7-165">L'etichetta può essere relativa a qualsiasi valore reale e non appartiene a un set finito di valori come nelle attività di classificazione.</span><span class="sxs-lookup"><span data-stu-id="340c7-165">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="340c7-166">Gli algoritmi di regressione modellano la dipendenza dell'etichetta in base alle relative funzionalità correlate per determinare come cambierà l'etichetta quando variano i valori delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="340c7-166">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="340c7-167">L'input di un algoritmo di regressione è un set di esempi con etichette di valori noti.</span><span class="sxs-lookup"><span data-stu-id="340c7-167">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="340c7-168">L'output di un algoritmo di regressione è una funzione, che è possibile usare per stimare il valore dell'etichetta per qualsiasi nuovo set di funzionalità di input.</span><span class="sxs-lookup"><span data-stu-id="340c7-168">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="340c7-169">Alcuni esempi di scenari di regressione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-169">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="340c7-170">Stima dei prezzi delle case in base alle caratteristiche, come numero di camere da letto, posizione o dimensione.</span><span class="sxs-lookup"><span data-stu-id="340c7-170">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="340c7-171">Stima dei prezzi futuri delle azioni in base ai dati cronologici e alle tendenze di mercato correnti.</span><span class="sxs-lookup"><span data-stu-id="340c7-171">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="340c7-172">Stima delle vendite di un prodotto in base ai budget pubblicitari.</span><span class="sxs-lookup"><span data-stu-id="340c7-172">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="340c7-173">Algoritmi di training di regressione</span><span class="sxs-lookup"><span data-stu-id="340c7-173">Regression trainers</span></span>

<span data-ttu-id="340c7-174">È possibile eseguire il training di un modello di regressione usando gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-174">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="340c7-175">Input e output di regressione</span><span class="sxs-lookup"><span data-stu-id="340c7-175">Regression inputs and outputs</span></span>

<span data-ttu-id="340c7-176">I dati della colonna dell'etichetta di input devono essere <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="340c7-176">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="340c7-177">Gli algoritmi di training per questa attività restituiscono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="340c7-177">The trainers for this task output the following:</span></span>

| <span data-ttu-id="340c7-178">Nome output</span><span class="sxs-lookup"><span data-stu-id="340c7-178">Output Name</span></span> | <span data-ttu-id="340c7-179">Tipo</span><span class="sxs-lookup"><span data-stu-id="340c7-179">Type</span></span> | <span data-ttu-id="340c7-180">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="340c7-180">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="340c7-181">Il punteggio non elaborato stimato dal modello</span><span class="sxs-lookup"><span data-stu-id="340c7-181">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="340c7-182">Clustering</span><span class="sxs-lookup"><span data-stu-id="340c7-182">Clustering</span></span>

<span data-ttu-id="340c7-183">Un'[attività di apprendimento automatico senza supervisione](glossary.md#unsupervised-machine-learning) che viene usata per raggruppare le istanze dei dati in cluster con caratteristiche simili.</span><span class="sxs-lookup"><span data-stu-id="340c7-183">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="340c7-184">Il clustering può anche essere usato per identificare relazioni in un set di dati che potrebbe essere impossibile ricavare logicamente dall'esplorazione o dalla semplice osservazione.</span><span class="sxs-lookup"><span data-stu-id="340c7-184">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="340c7-185">Gli input e gli output di un algoritmo di clustering dipendono dalla metodologia scelta.</span><span class="sxs-lookup"><span data-stu-id="340c7-185">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="340c7-186">È possibile adottare un approccio basato su distribuzione, centroide, connettività o densità.</span><span class="sxs-lookup"><span data-stu-id="340c7-186">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="340c7-187">ML.NET attualmente supporta un approccio basato su centroide che usa il clustering K-Means.</span><span class="sxs-lookup"><span data-stu-id="340c7-187">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="340c7-188">Alcuni esempi di scenari di clustering sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-188">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="340c7-189">Comprensione dei segmenti degli ospiti degli hotel in base alle abitudini e alle caratteristiche delle scelte degli hotel.</span><span class="sxs-lookup"><span data-stu-id="340c7-189">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="340c7-190">Identificazione di segmenti di clienti e dati demografici per la creazione di campagne pubblicitarie mirate.</span><span class="sxs-lookup"><span data-stu-id="340c7-190">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="340c7-191">Classificazione di inventari in base alle metriche di produzione.</span><span class="sxs-lookup"><span data-stu-id="340c7-191">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="340c7-192">Algoritmi di training di clustering</span><span class="sxs-lookup"><span data-stu-id="340c7-192">Clustering trainer</span></span>

<span data-ttu-id="340c7-193">È possibile eseguire il training di un modello di clustering usando l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="340c7-193">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer> 

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="340c7-194">Input e output di clustering</span><span class="sxs-lookup"><span data-stu-id="340c7-194">Clustering inputs and outputs</span></span>

<span data-ttu-id="340c7-195">I dati delle funzionalità di input devono essere <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="340c7-195">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="340c7-196">Non sono necessarie etichette.</span><span class="sxs-lookup"><span data-stu-id="340c7-196">No labels are needed.</span></span>

<span data-ttu-id="340c7-197">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="340c7-197">This trainer outputs the following:</span></span>

| <span data-ttu-id="340c7-198">Nome output</span><span class="sxs-lookup"><span data-stu-id="340c7-198">Output Name</span></span> | <span data-ttu-id="340c7-199">Tipo</span><span class="sxs-lookup"><span data-stu-id="340c7-199">Type</span></span> | <span data-ttu-id="340c7-200">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="340c7-200">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="340c7-201">vettore di <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="340c7-201">vector of <xref:System.Single></span></span> | <span data-ttu-id="340c7-202">Le distanze del punto dati specificato dai baricentri di tutti i cluster</span><span class="sxs-lookup"><span data-stu-id="340c7-202">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="340c7-203">Tipo [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="340c7-203">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="340c7-204">L'indice del cluster più vicino stimato dal modello.</span><span class="sxs-lookup"><span data-stu-id="340c7-204">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="340c7-205">Rilevamento di anomalie</span><span class="sxs-lookup"><span data-stu-id="340c7-205">Anomaly detection</span></span>

<span data-ttu-id="340c7-206">Questa attività crea un modello per il rilevamento di anomalie tramite l'analisi delle componenti principali.</span><span class="sxs-lookup"><span data-stu-id="340c7-206">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="340c7-207">Il rilevamento di anomalie basato su questo tipo di analisi consente di creare un modello in scenari in cui è facile ottenere dati di training da una singola classe, ad esempio le transazioni valide, ma è difficile ottenere campioni sufficienti delle anomalie da rilevare.</span><span class="sxs-lookup"><span data-stu-id="340c7-207">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="340c7-208">L'analisi delle componenti principali è una tecnica consolidata nell'apprendimento automatico che viene spesso usata per l'analisi esplorativa dei dati perché rivela la struttura interna dei dati e ne spiega la varianza.</span><span class="sxs-lookup"><span data-stu-id="340c7-208">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="340c7-209">Questa tecnica consiste nell'eseguire l'analisi di dati che contengono più variabili.</span><span class="sxs-lookup"><span data-stu-id="340c7-209">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="340c7-210">Cerca le correlazioni tra le variabili e determina la combinazione di valori che meglio rappresenta le differenze nei risultati.</span><span class="sxs-lookup"><span data-stu-id="340c7-210">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="340c7-211">Questi valori di caratteristica combinati vengono usati per creare uno spazio di caratteristiche più compatto, denominato componenti principali.</span><span class="sxs-lookup"><span data-stu-id="340c7-211">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="340c7-212">Il rilevamento di anomalie comprende molte attività importanti correlate all'apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="340c7-212">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="340c7-213">Identificazione di transazioni potenzialmente illecite.</span><span class="sxs-lookup"><span data-stu-id="340c7-213">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="340c7-214">Criteri di apprendimento indicanti che si è verificata un'intrusione nella rete.</span><span class="sxs-lookup"><span data-stu-id="340c7-214">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="340c7-215">Ricerca di gruppi anomali di pazienti.</span><span class="sxs-lookup"><span data-stu-id="340c7-215">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="340c7-216">Verifica dei valori immessi in un sistema.</span><span class="sxs-lookup"><span data-stu-id="340c7-216">Checking values entered into a system.</span></span>

<span data-ttu-id="340c7-217">Poiché le anomalie sono per definizione eventi rari, può essere difficile raccogliere un campione rappresentativo di dati da usare per la modellazione.</span><span class="sxs-lookup"><span data-stu-id="340c7-217">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="340c7-218">Gli algoritmi inclusi in questa categoria sono stati appositamente progettati per risolvere i problemi principali relativi alla creazione e al training dei modelli tramite set di dati non bilanciati.</span><span class="sxs-lookup"><span data-stu-id="340c7-218">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="340c7-219">Algoritmo di training di rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="340c7-219">Anomaly detection trainer</span></span>

<span data-ttu-id="340c7-220">È possibile eseguire il training di un modello di rilevamento anomalie usando l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="340c7-220">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="340c7-221">Input e output di rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="340c7-221">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="340c7-222">Le funzionalità di input devono essere un vettore a dimensione fissa di <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="340c7-222">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="340c7-223">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="340c7-223">This trainer outputs the following:</span></span>

| <span data-ttu-id="340c7-224">Nome output</span><span class="sxs-lookup"><span data-stu-id="340c7-224">Output Name</span></span> | <span data-ttu-id="340c7-225">Tipo</span><span class="sxs-lookup"><span data-stu-id="340c7-225">Type</span></span> | <span data-ttu-id="340c7-226">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="340c7-226">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="340c7-227">Il punteggio non negativo, illimitato calcolato dal modello di rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="340c7-227">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |

## <a name="ranking"></a><span data-ttu-id="340c7-228">Ranking</span><span class="sxs-lookup"><span data-stu-id="340c7-228">Ranking</span></span>

<span data-ttu-id="340c7-229">Un'attività di ranking crea un modello di ranking in base a un set di esempi con etichetta.</span><span class="sxs-lookup"><span data-stu-id="340c7-229">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="340c7-230">Questo set è costituito da gruppi di istanze a cui può essere assegnato un punteggio con determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="340c7-230">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="340c7-231">Le etichette di ranking sono {0, 1, 2, 3, 4} per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="340c7-231">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="340c7-232">Il modello di ranking viene sottoposto a training in modo da classificare in ordine di priorità nuovi gruppi di istanze con punteggi sconosciuti per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="340c7-232">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="340c7-233">Gli algoritmi di apprendimento per il ranking di ML.NET sono basati sulla tecnica di [ranking con apprendimento automatico](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="340c7-233">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="340c7-234">Algoritmi di training di classificazione</span><span class="sxs-lookup"><span data-stu-id="340c7-234">Ranking training algorithms</span></span>

<span data-ttu-id="340c7-235">È possibile eseguire il training di un modello di classificazione con gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="340c7-235">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer> 

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="340c7-236">Input e output di classificazione</span><span class="sxs-lookup"><span data-stu-id="340c7-236">Ranking input and outputs</span></span>

<span data-ttu-id="340c7-237">Il tipo di dati dell'etichetta di input deve essere [key](xref:Microsoft.ML.Data.KeyDataViewType) o <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="340c7-237">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="340c7-238">Il valore dell'etichetta determina la pertinenza, dove valori più alti indicano maggior pertinenza.</span><span class="sxs-lookup"><span data-stu-id="340c7-238">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="340c7-239">Se l'etichetta è un tipo [key](xref:Microsoft.ML.Data.KeyDataViewType), l'indice di chiave è il valore di pertinenza, dove l'indice più basso è il meno pertinente.</span><span class="sxs-lookup"><span data-stu-id="340c7-239">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="340c7-240">Se l'etichetta è un tipo <xref:System.Single>, valori più alti indicano maggior pertinenza.</span><span class="sxs-lookup"><span data-stu-id="340c7-240">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="340c7-241">I dati della funzionalità devono essere un vettore di dimensioni fisse di <xref:System.Single> e la colonna gruppo di righe di input deve essere un tipo [key](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="340c7-241">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="340c7-242">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="340c7-242">This trainer outputs the following:</span></span>

| <span data-ttu-id="340c7-243">Nome output</span><span class="sxs-lookup"><span data-stu-id="340c7-243">Output Name</span></span> | <span data-ttu-id="340c7-244">Tipo</span><span class="sxs-lookup"><span data-stu-id="340c7-244">Type</span></span> | <span data-ttu-id="340c7-245">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="340c7-245">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="340c7-246">Il punteggio illimitato calcolato dal modello per determinare la stima</span><span class="sxs-lookup"><span data-stu-id="340c7-246">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="340c7-247">Consiglio</span><span class="sxs-lookup"><span data-stu-id="340c7-247">Recommendation</span></span>

<span data-ttu-id="340c7-248">Un'attività di raccomandazione consente di generare un elenco di servizi o prodotti consigliati.</span><span class="sxs-lookup"><span data-stu-id="340c7-248">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="340c7-249">ML.NET usa la [fattorizzazione di matrice](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) e un algoritmo di [filtraggio collaborativo](https://en.wikipedia.org/wiki/Collaborative_filtering) per le raccomandazioni quando si hanno dati cronologici di classificazione dei prodotti nel proprio catalogo.</span><span class="sxs-lookup"><span data-stu-id="340c7-249">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="340c7-250">Ad esempio, quando sono presenti dati cronologici di classificazione di film per gli utenti e si vogliono raccomandare altri film a cui questi potrebbero essere interessati.</span><span class="sxs-lookup"><span data-stu-id="340c7-250">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="340c7-251">Algoritmi di training di raccomandazione</span><span class="sxs-lookup"><span data-stu-id="340c7-251">Recommendation training algorithms</span></span>

<span data-ttu-id="340c7-252">È possibile eseguire il training di un modello di raccomandazione con l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="340c7-252">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
