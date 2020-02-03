---
title: Attività di apprendimento automatico
description: Esplorare le diverse attività di apprendimento automatico e le attività associate supportate in ML.NET.
ms.date: 12/23/2019
ms.openlocfilehash: 6cd41065e668375537b9816ef7a208a65e0a523b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745110"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="3aa83-103">Attività di apprendimento automatico in ML.NET</span><span class="sxs-lookup"><span data-stu-id="3aa83-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="3aa83-104">Un'attività di Machine Learning è il tipo di stima o di inferenza effettuata, in base al problema o alla domanda richiesta e ai dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="3aa83-104">A machine learning task is the type of prediction or inference being made, based on the problem or question that is being asked, and the available data.</span></span> <span data-ttu-id="3aa83-105">Ad esempio, l'attività di classificazione assegna i dati alle categorie e l'attività di Clustering raggruppa i dati in base alla somiglianza.</span><span class="sxs-lookup"><span data-stu-id="3aa83-105">For example, the classification task assigns data to categories, and the clustering task groups data according to similarity.</span></span>

<span data-ttu-id="3aa83-106">Le attività di Machine Learning si basano sui modelli nei dati anziché essere programmati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="3aa83-106">Machine learning tasks rely on patterns in the data rather than being explicitly programmed.</span></span>

<span data-ttu-id="3aa83-107">Questo articolo descrive le diverse attività di Machine Learning tra cui è possibile scegliere in ML.NET e alcuni casi d'uso comuni.</span><span class="sxs-lookup"><span data-stu-id="3aa83-107">This article describes the different machine learning tasks that you can choose from in ML.NET and some common use cases.</span></span>

<span data-ttu-id="3aa83-108">Dopo aver deciso quale attività è appropriata per il proprio scenario, è necessario scegliere l'algoritmo migliore per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="3aa83-108">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="3aa83-109">Gli algoritmi disponibili sono elencati nella sezione per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="3aa83-109">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="3aa83-110">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="3aa83-110">Binary classification</span></span>

<span data-ttu-id="3aa83-111">Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stabilire a quale di due classi (categorie) appartiene un'istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="3aa83-111">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="3aa83-112">L'input di un algoritmo di classificazione è un set di esempi con etichette, in cui ogni etichetta è un numero intero 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="3aa83-112">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="3aa83-113">L'output di un algoritmo di classificazione binaria è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette.</span><span class="sxs-lookup"><span data-stu-id="3aa83-113">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="3aa83-114">Alcuni esempi di scenari di classificazione binaria sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-114">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="3aa83-115">[Comprensione del sentiment dei commenti di Twitter](../tutorials/sentiment-analysis.md) come "positivi" o "negativi".</span><span class="sxs-lookup"><span data-stu-id="3aa83-115">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="3aa83-116">Diagnosi per stabilire se un paziente ha o meno una determinata malattia.</span><span class="sxs-lookup"><span data-stu-id="3aa83-116">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="3aa83-117">Decisione di contrassegnare o meno un messaggio di posta elettronica come "posta indesiderata".</span><span class="sxs-lookup"><span data-stu-id="3aa83-117">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="3aa83-118">Determinare se una foto contiene o meno un particolare elemento, ad esempio un cane o un frutto.</span><span class="sxs-lookup"><span data-stu-id="3aa83-118">Determining if a photo contains a particular item or not, such as a dog or fruit.</span></span>

<span data-ttu-id="3aa83-119">Per altre informazioni, vedere l'articolo relativo alla [classificazione binaria](https://en.wikipedia.org/wiki/Binary_classification) su Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="3aa83-119">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="3aa83-120">Algoritmi di training di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="3aa83-120">Binary classification trainers</span></span>

<span data-ttu-id="3aa83-121">È possibile eseguire il training di un modello di classificazione binaria usando gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-121">You can train a binary classification model using the following algorithms:</span></span>

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

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="3aa83-122">Input e output di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="3aa83-122">Binary classification inputs and outputs</span></span>

<span data-ttu-id="3aa83-123">Per ottenere risultati ottimali con la classificazione binaria, i dati di training devono essere bilanciati, vale a dire avere un numero uguale di dati di training positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="3aa83-123">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="3aa83-124">I valori mancanti devono essere gestiti prima del training.</span><span class="sxs-lookup"><span data-stu-id="3aa83-124">Missing values should be handled before training.</span></span>

<span data-ttu-id="3aa83-125">I dati della colonna dell'etichetta di input devono essere <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="3aa83-125">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="3aa83-126">I dati della colonna delle funzionalità di input devono essere un vettore a dimensione fissa di <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="3aa83-126">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="3aa83-127">Questi istruttori restituiscono le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-127">These trainers output the following columns:</span></span>

| <span data-ttu-id="3aa83-128">Nome colonna di output</span><span class="sxs-lookup"><span data-stu-id="3aa83-128">Output Column Name</span></span> | <span data-ttu-id="3aa83-129">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="3aa83-129">Column Type</span></span> | <span data-ttu-id="3aa83-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa83-130">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="3aa83-131">Il punteggio non elaborato calcolato dal modello</span><span class="sxs-lookup"><span data-stu-id="3aa83-131">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="3aa83-132">L'etichetta stimata, in base al segno del punteggio.</span><span class="sxs-lookup"><span data-stu-id="3aa83-132">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="3aa83-133">Un punteggio negativo esegue il mapping a `false` e un punteggio negativo esegue il mapping a `true`.</span><span class="sxs-lookup"><span data-stu-id="3aa83-133">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="3aa83-134">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="3aa83-134">Multiclass classification</span></span>

<span data-ttu-id="3aa83-135">Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare la classe (categoria) di un'istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="3aa83-135">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="3aa83-136">L'input di un algoritmo di classificazione è un set di esempi con etichette.</span><span class="sxs-lookup"><span data-stu-id="3aa83-136">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="3aa83-137">In genere ogni etichetta è inizialmente costituita da testo.</span><span class="sxs-lookup"><span data-stu-id="3aa83-137">Each label normally starts as text.</span></span> <span data-ttu-id="3aa83-138">Viene quindi elaborata da TermTransform, che la converte nel tipo Key (numerico).</span><span class="sxs-lookup"><span data-stu-id="3aa83-138">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="3aa83-139">L'output di un algoritmo di classificazione è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette.</span><span class="sxs-lookup"><span data-stu-id="3aa83-139">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="3aa83-140">Alcuni esempi di scenari di classificazione multiclasse sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-140">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="3aa83-141">Determinare la razza di un cane come "siberian husky", "golden retriever", "barboncino" e così via.</span><span class="sxs-lookup"><span data-stu-id="3aa83-141">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="3aa83-142">Classificare recensioni di film come "positive", "neutrali" o "negative".</span><span class="sxs-lookup"><span data-stu-id="3aa83-142">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="3aa83-143">Classificare recensioni di hotel in base a "posizione", "prezzo", "pulizia" e così via.</span><span class="sxs-lookup"><span data-stu-id="3aa83-143">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="3aa83-144">Per altre informazioni, vedere l'articolo relativo alla [classificazione multiclasse](https://en.wikipedia.org/wiki/Multiclass_classification) su Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="3aa83-144">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="3aa83-145">Il modello "uno contro tutti" aggiorna gli [algoritmi di apprendimento per la classificazione binaria](#binary-classification) in modo che possano agire sui set di dati multiclasse.</span><span class="sxs-lookup"><span data-stu-id="3aa83-145">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="3aa83-146">Per altre informazioni, vedere [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="3aa83-146">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="3aa83-147">Algoritmi di training di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="3aa83-147">Multiclass classification trainers</span></span>

<span data-ttu-id="3aa83-148">È possibile eseguire il training di un modello di classificazione multiclasse usando gli algoritmi di training seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-148">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>
* <xref:Microsoft.ML.Vision.ImageClassificationTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="3aa83-149">Input e output di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="3aa83-149">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="3aa83-150">I dati della colonna dell'etichetta di input devono essere di tipo [key](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="3aa83-150">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="3aa83-151">La colonna delle funzionalità deve essere un vettore di dimensioni fisse di <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="3aa83-151">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="3aa83-152">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3aa83-152">This trainer outputs the following:</span></span>

| <span data-ttu-id="3aa83-153">Nome output</span><span class="sxs-lookup"><span data-stu-id="3aa83-153">Output Name</span></span> | <span data-ttu-id="3aa83-154">Type</span><span class="sxs-lookup"><span data-stu-id="3aa83-154">Type</span></span> | <span data-ttu-id="3aa83-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa83-155">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="3aa83-156">Vettore di <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="3aa83-156">Vector of <xref:System.Single></span></span> | <span data-ttu-id="3aa83-157">I punteggi di tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="3aa83-157">The scores of all classes.</span></span> <span data-ttu-id="3aa83-158">Valori più alti indicano maggiori probabilità di rientrare nella classe associata.</span><span class="sxs-lookup"><span data-stu-id="3aa83-158">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="3aa83-159">Se l'elemento i-esimo ha il valore più elevato, l'indice delle etichette stimate sarà i.</span><span class="sxs-lookup"><span data-stu-id="3aa83-159">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="3aa83-160">Si noti che i è l'indice a base zero.</span><span class="sxs-lookup"><span data-stu-id="3aa83-160">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="3aa83-161">Tipo [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="3aa83-161">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="3aa83-162">L'indice dell'etichetta stimata.</span><span class="sxs-lookup"><span data-stu-id="3aa83-162">The predicted label's index.</span></span> <span data-ttu-id="3aa83-163">Se il valore è i, l'etichetta effettiva potrebbe essere la categoria i-esima nel tipo di etichetta di input con valori key.</span><span class="sxs-lookup"><span data-stu-id="3aa83-163">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="3aa83-164">Regressione</span><span class="sxs-lookup"><span data-stu-id="3aa83-164">Regression</span></span>

<span data-ttu-id="3aa83-165">Un attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare il valore dell'etichetta da un set di funzionalità correlate.</span><span class="sxs-lookup"><span data-stu-id="3aa83-165">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="3aa83-166">L'etichetta può essere relativa a qualsiasi valore reale e non appartiene a un set finito di valori come nelle attività di classificazione.</span><span class="sxs-lookup"><span data-stu-id="3aa83-166">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="3aa83-167">Gli algoritmi di regressione modellano la dipendenza dell'etichetta in base alle relative funzionalità correlate per determinare come cambierà l'etichetta quando variano i valori delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3aa83-167">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="3aa83-168">L'input di un algoritmo di regressione è un set di esempi con etichette di valori noti.</span><span class="sxs-lookup"><span data-stu-id="3aa83-168">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="3aa83-169">L'output di un algoritmo di regressione è una funzione, che è possibile usare per stimare il valore dell'etichetta per qualsiasi nuovo set di funzionalità di input.</span><span class="sxs-lookup"><span data-stu-id="3aa83-169">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="3aa83-170">Alcuni esempi di scenari di regressione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-170">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="3aa83-171">Stima dei prezzi delle case in base alle caratteristiche, come numero di camere da letto, posizione o dimensione.</span><span class="sxs-lookup"><span data-stu-id="3aa83-171">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="3aa83-172">Stima dei prezzi futuri delle azioni in base ai dati cronologici e alle tendenze di mercato correnti.</span><span class="sxs-lookup"><span data-stu-id="3aa83-172">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="3aa83-173">Stima delle vendite di un prodotto in base ai budget pubblicitari.</span><span class="sxs-lookup"><span data-stu-id="3aa83-173">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="3aa83-174">Algoritmi di training di regressione</span><span class="sxs-lookup"><span data-stu-id="3aa83-174">Regression trainers</span></span>

<span data-ttu-id="3aa83-175">È possibile eseguire il training di un modello di regressione usando gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-175">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="3aa83-176">Input e output di regressione</span><span class="sxs-lookup"><span data-stu-id="3aa83-176">Regression inputs and outputs</span></span>

<span data-ttu-id="3aa83-177">I dati della colonna dell'etichetta di input devono essere <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="3aa83-177">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="3aa83-178">Gli algoritmi di training per questa attività restituiscono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3aa83-178">The trainers for this task output the following:</span></span>

| <span data-ttu-id="3aa83-179">Nome output</span><span class="sxs-lookup"><span data-stu-id="3aa83-179">Output Name</span></span> | <span data-ttu-id="3aa83-180">Type</span><span class="sxs-lookup"><span data-stu-id="3aa83-180">Type</span></span> | <span data-ttu-id="3aa83-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa83-181">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="3aa83-182">Il punteggio non elaborato stimato dal modello</span><span class="sxs-lookup"><span data-stu-id="3aa83-182">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="3aa83-183">Clustering</span><span class="sxs-lookup"><span data-stu-id="3aa83-183">Clustering</span></span>

<span data-ttu-id="3aa83-184">Un'[attività di apprendimento automatico senza supervisione](glossary.md#unsupervised-machine-learning) che viene usata per raggruppare le istanze dei dati in cluster con caratteristiche simili.</span><span class="sxs-lookup"><span data-stu-id="3aa83-184">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="3aa83-185">Il clustering può anche essere usato per identificare relazioni in un set di dati che potrebbe essere impossibile ricavare logicamente dall'esplorazione o dalla semplice osservazione.</span><span class="sxs-lookup"><span data-stu-id="3aa83-185">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="3aa83-186">Gli input e gli output di un algoritmo di clustering dipendono dalla metodologia scelta.</span><span class="sxs-lookup"><span data-stu-id="3aa83-186">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="3aa83-187">È possibile adottare un approccio basato su distribuzione, centroide, connettività o densità.</span><span class="sxs-lookup"><span data-stu-id="3aa83-187">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="3aa83-188">ML.NET attualmente supporta un approccio basato su centroide che usa il clustering K-Means.</span><span class="sxs-lookup"><span data-stu-id="3aa83-188">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="3aa83-189">Alcuni esempi di scenari di clustering sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-189">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="3aa83-190">Comprensione dei segmenti degli ospiti degli hotel in base alle abitudini e alle caratteristiche delle scelte degli hotel.</span><span class="sxs-lookup"><span data-stu-id="3aa83-190">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="3aa83-191">Identificazione di segmenti di clienti e dati demografici per la creazione di campagne pubblicitarie mirate.</span><span class="sxs-lookup"><span data-stu-id="3aa83-191">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="3aa83-192">Classificazione di inventari in base alle metriche di produzione.</span><span class="sxs-lookup"><span data-stu-id="3aa83-192">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="3aa83-193">Algoritmi di training di clustering</span><span class="sxs-lookup"><span data-stu-id="3aa83-193">Clustering trainer</span></span>

<span data-ttu-id="3aa83-194">È possibile eseguire il training di un modello di clustering usando l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="3aa83-194">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="3aa83-195">Input e output di clustering</span><span class="sxs-lookup"><span data-stu-id="3aa83-195">Clustering inputs and outputs</span></span>

<span data-ttu-id="3aa83-196">I dati delle funzionalità di input devono essere <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="3aa83-196">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="3aa83-197">Non sono necessarie etichette.</span><span class="sxs-lookup"><span data-stu-id="3aa83-197">No labels are needed.</span></span>

<span data-ttu-id="3aa83-198">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3aa83-198">This trainer outputs the following:</span></span>

| <span data-ttu-id="3aa83-199">Nome output</span><span class="sxs-lookup"><span data-stu-id="3aa83-199">Output Name</span></span> | <span data-ttu-id="3aa83-200">Type</span><span class="sxs-lookup"><span data-stu-id="3aa83-200">Type</span></span> | <span data-ttu-id="3aa83-201">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa83-201">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="3aa83-202">vettore di <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="3aa83-202">vector of <xref:System.Single></span></span> | <span data-ttu-id="3aa83-203">Le distanze del punto dati specificato dai baricentri di tutti i cluster</span><span class="sxs-lookup"><span data-stu-id="3aa83-203">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="3aa83-204">Tipo [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="3aa83-204">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="3aa83-205">L'indice del cluster più vicino stimato dal modello.</span><span class="sxs-lookup"><span data-stu-id="3aa83-205">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="3aa83-206">Rilevamento di anomalie</span><span class="sxs-lookup"><span data-stu-id="3aa83-206">Anomaly detection</span></span>

<span data-ttu-id="3aa83-207">Questa attività crea un modello per il rilevamento di anomalie tramite l'analisi delle componenti principali.</span><span class="sxs-lookup"><span data-stu-id="3aa83-207">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="3aa83-208">Il rilevamento di anomalie basato su questo tipo di analisi consente di creare un modello in scenari in cui è facile ottenere dati di training da una singola classe, ad esempio le transazioni valide, ma è difficile ottenere campioni sufficienti delle anomalie da rilevare.</span><span class="sxs-lookup"><span data-stu-id="3aa83-208">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="3aa83-209">L'analisi delle componenti principali è una tecnica consolidata nell'apprendimento automatico che viene spesso usata per l'analisi esplorativa dei dati perché rivela la struttura interna dei dati e ne spiega la varianza.</span><span class="sxs-lookup"><span data-stu-id="3aa83-209">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="3aa83-210">Questa tecnica consiste nell'eseguire l'analisi di dati che contengono più variabili.</span><span class="sxs-lookup"><span data-stu-id="3aa83-210">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="3aa83-211">Cerca le correlazioni tra le variabili e determina la combinazione di valori che meglio rappresenta le differenze nei risultati.</span><span class="sxs-lookup"><span data-stu-id="3aa83-211">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="3aa83-212">Questi valori di caratteristica combinati vengono usati per creare uno spazio di caratteristiche più compatto, denominato componenti principali.</span><span class="sxs-lookup"><span data-stu-id="3aa83-212">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="3aa83-213">Il rilevamento di anomalie comprende molte attività importanti correlate all'apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="3aa83-213">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="3aa83-214">Identificazione di transazioni potenzialmente illecite.</span><span class="sxs-lookup"><span data-stu-id="3aa83-214">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="3aa83-215">Criteri di apprendimento indicanti che si è verificata un'intrusione nella rete.</span><span class="sxs-lookup"><span data-stu-id="3aa83-215">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="3aa83-216">Ricerca di gruppi anomali di pazienti.</span><span class="sxs-lookup"><span data-stu-id="3aa83-216">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="3aa83-217">Verifica dei valori immessi in un sistema.</span><span class="sxs-lookup"><span data-stu-id="3aa83-217">Checking values entered into a system.</span></span>

<span data-ttu-id="3aa83-218">Poiché le anomalie sono per definizione eventi rari, può essere difficile raccogliere un campione rappresentativo di dati da usare per la modellazione.</span><span class="sxs-lookup"><span data-stu-id="3aa83-218">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="3aa83-219">Gli algoritmi inclusi in questa categoria sono stati appositamente progettati per risolvere i problemi principali relativi alla creazione e al training dei modelli tramite set di dati non bilanciati.</span><span class="sxs-lookup"><span data-stu-id="3aa83-219">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="3aa83-220">Algoritmo di training di rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="3aa83-220">Anomaly detection trainer</span></span>

<span data-ttu-id="3aa83-221">È possibile eseguire il training di un modello di rilevamento anomalie usando l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="3aa83-221">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="3aa83-222">Input e output di rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="3aa83-222">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="3aa83-223">Le funzionalità di input devono essere un vettore a dimensione fissa di <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="3aa83-223">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="3aa83-224">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3aa83-224">This trainer outputs the following:</span></span>

| <span data-ttu-id="3aa83-225">Nome output</span><span class="sxs-lookup"><span data-stu-id="3aa83-225">Output Name</span></span> | <span data-ttu-id="3aa83-226">Type</span><span class="sxs-lookup"><span data-stu-id="3aa83-226">Type</span></span> | <span data-ttu-id="3aa83-227">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa83-227">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="3aa83-228">Il punteggio non negativo, illimitato calcolato dal modello di rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="3aa83-228">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="3aa83-229">Valore true/false che indica se l'input è un'anomalia (PredictedLabel = true) o meno (PredictedLabel = false)</span><span class="sxs-lookup"><span data-stu-id="3aa83-229">A true/false value representing whether the input is an anomaly (PredictedLabel=true) or not (PredictedLabel=false)</span></span> |

## <a name="ranking"></a><span data-ttu-id="3aa83-230">Ranking</span><span class="sxs-lookup"><span data-stu-id="3aa83-230">Ranking</span></span>

<span data-ttu-id="3aa83-231">Un'attività di ranking crea un modello di ranking in base a un set di esempi con etichetta.</span><span class="sxs-lookup"><span data-stu-id="3aa83-231">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="3aa83-232">Questo set è costituito da gruppi di istanze a cui può essere assegnato un punteggio con determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="3aa83-232">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="3aa83-233">Le etichette di ranking sono {0, 1, 2, 3, 4} per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="3aa83-233">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="3aa83-234">Il modello di ranking viene sottoposto a training in modo da classificare in ordine di priorità nuovi gruppi di istanze con punteggi sconosciuti per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="3aa83-234">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="3aa83-235">Gli algoritmi di apprendimento per il ranking di ML.NET sono basati sulla tecnica di [ranking con apprendimento automatico](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="3aa83-235">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="3aa83-236">Algoritmi di training di classificazione</span><span class="sxs-lookup"><span data-stu-id="3aa83-236">Ranking training algorithms</span></span>

<span data-ttu-id="3aa83-237">È possibile eseguire il training di un modello di classificazione con gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa83-237">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="3aa83-238">Input e output di classificazione</span><span class="sxs-lookup"><span data-stu-id="3aa83-238">Ranking input and outputs</span></span>

<span data-ttu-id="3aa83-239">Il tipo di dati dell'etichetta di input deve essere [key](xref:Microsoft.ML.Data.KeyDataViewType) o <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="3aa83-239">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="3aa83-240">Il valore dell'etichetta determina la pertinenza, dove valori più alti indicano maggior pertinenza.</span><span class="sxs-lookup"><span data-stu-id="3aa83-240">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="3aa83-241">Se l'etichetta è un tipo [key](xref:Microsoft.ML.Data.KeyDataViewType), l'indice di chiave è il valore di pertinenza, dove l'indice più basso è il meno pertinente.</span><span class="sxs-lookup"><span data-stu-id="3aa83-241">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="3aa83-242">Se l'etichetta è un tipo <xref:System.Single>, valori più alti indicano maggior pertinenza.</span><span class="sxs-lookup"><span data-stu-id="3aa83-242">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="3aa83-243">I dati della funzionalità devono essere un vettore di dimensioni fisse di <xref:System.Single> e la colonna gruppo di righe di input deve essere un tipo [key](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="3aa83-243">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="3aa83-244">Questo algoritmo di training restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3aa83-244">This trainer outputs the following:</span></span>

| <span data-ttu-id="3aa83-245">Nome output</span><span class="sxs-lookup"><span data-stu-id="3aa83-245">Output Name</span></span> | <span data-ttu-id="3aa83-246">Type</span><span class="sxs-lookup"><span data-stu-id="3aa83-246">Type</span></span> | <span data-ttu-id="3aa83-247">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa83-247">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="3aa83-248">Il punteggio illimitato calcolato dal modello per determinare la stima</span><span class="sxs-lookup"><span data-stu-id="3aa83-248">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="3aa83-249">Indicazione</span><span class="sxs-lookup"><span data-stu-id="3aa83-249">Recommendation</span></span>

<span data-ttu-id="3aa83-250">Un'attività di raccomandazione consente di generare un elenco di servizi o prodotti consigliati.</span><span class="sxs-lookup"><span data-stu-id="3aa83-250">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="3aa83-251">ML.NET usa la [fattorizzazione di matrice](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) e un algoritmo di [filtraggio collaborativo](https://en.wikipedia.org/wiki/Collaborative_filtering) per le raccomandazioni quando si hanno dati cronologici di classificazione dei prodotti nel proprio catalogo.</span><span class="sxs-lookup"><span data-stu-id="3aa83-251">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="3aa83-252">Ad esempio, quando sono presenti dati cronologici di classificazione di film per gli utenti e si vogliono raccomandare altri film a cui questi potrebbero essere interessati.</span><span class="sxs-lookup"><span data-stu-id="3aa83-252">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="3aa83-253">Algoritmi di training di raccomandazione</span><span class="sxs-lookup"><span data-stu-id="3aa83-253">Recommendation training algorithms</span></span>

<span data-ttu-id="3aa83-254">È possibile eseguire il training di un modello di raccomandazione con l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="3aa83-254">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>

## <a name="forecasting"></a><span data-ttu-id="3aa83-255">Previsione</span><span class="sxs-lookup"><span data-stu-id="3aa83-255">Forecasting</span></span>

<span data-ttu-id="3aa83-256">L'attività di previsione usa i dati precedenti della serie temporale per eseguire stime sul comportamento futuro.</span><span class="sxs-lookup"><span data-stu-id="3aa83-256">The forecasting task use past time-series data to make predictions about future behavior.</span></span> <span data-ttu-id="3aa83-257">Gli scenari applicabili alla previsione includono previsioni meteorologiche, previsioni di vendita stagionali e manutenzione predittiva,</span><span class="sxs-lookup"><span data-stu-id="3aa83-257">Scenarios applicable to forecasting include weather forecasting, seasonal sales predictions, and predictive maintenance,</span></span>

### <a name="forecasting-trainers"></a><span data-ttu-id="3aa83-258">Formazione per la previsione</span><span class="sxs-lookup"><span data-stu-id="3aa83-258">Forecasting trainers</span></span>

<span data-ttu-id="3aa83-259">È possibile eseguire il training di un modello di previsione con l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="3aa83-259">You can train a forecasting model with the following algorithm:</span></span>

<xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa*>
