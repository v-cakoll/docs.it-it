---
title: Attività di apprendimento automatico - ML.NET
description: Esplorare le diverse attività di apprendimento automatico e le attività associate supportate in ML.NET.
ms.custom: seodec18
ms.date: 04/12/2019
author: natke
ms.openlocfilehash: bfed9cf12f8d539c4327549e5305415ce096e022
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613161"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="ac36a-103">Attività di apprendimento automatico in ML.NET</span><span class="sxs-lookup"><span data-stu-id="ac36a-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="ac36a-104">Quando si compila un modello di apprendimento automatico, è innanzitutto necessario definire quale risultato si vuole ottenere con i dati.</span><span class="sxs-lookup"><span data-stu-id="ac36a-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="ac36a-105">In tal modo è possibile scegliere l'attività di apprendimento automatico più adatta alla specifica situazione.</span><span class="sxs-lookup"><span data-stu-id="ac36a-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="ac36a-106">Nell'elenco seguente sono descritte le diverse attività di apprendimento automatico tra cui è possibile scegliere e alcuni casi d'uso comuni.</span><span class="sxs-lookup"><span data-stu-id="ac36a-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="ac36a-107">Dopo aver deciso quale attività è appropriata per il proprio scenario, è necessario scegliere l'algoritmo migliore per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ac36a-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="ac36a-108">Gli algoritmi disponibili sono elencati nella sezione per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="ac36a-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="ac36a-109">Classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="ac36a-109">Binary classification</span></span>

<span data-ttu-id="ac36a-110">Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stabilire a quale di due classi (categorie) appartiene un'istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="ac36a-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="ac36a-111">L'input di un algoritmo di classificazione è un set di esempi con etichette, in cui ogni etichetta è un numero intero 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="ac36a-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="ac36a-112">L'output di un algoritmo di classificazione binaria è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette.</span><span class="sxs-lookup"><span data-stu-id="ac36a-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="ac36a-113">Alcuni esempi di scenari di classificazione binaria sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="ac36a-114">[Comprensione del sentiment dei commenti di Twitter](../tutorials/sentiment-analysis.md) come "positivi" o "negativi".</span><span class="sxs-lookup"><span data-stu-id="ac36a-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="ac36a-115">Diagnosi per stabilire se un paziente ha o meno una determinata malattia.</span><span class="sxs-lookup"><span data-stu-id="ac36a-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="ac36a-116">Decisione di contrassegnare o meno un messaggio di posta elettronica come "posta indesiderata".</span><span class="sxs-lookup"><span data-stu-id="ac36a-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="ac36a-117">Identificazione di un cane o di un frutto all'interno di una foto.</span><span class="sxs-lookup"><span data-stu-id="ac36a-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="ac36a-118">Per altre informazioni, vedere l'articolo relativo alla [classificazione binaria](https://en.wikipedia.org/wiki/Binary_classification) su Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="ac36a-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-training-algorithms"></a><span data-ttu-id="ac36a-119">Algoritmi di training di classificazione binaria</span><span class="sxs-lookup"><span data-stu-id="ac36a-119">Binary Classification Training Algorithms</span></span>

<span data-ttu-id="ac36a-120">È possibile eseguire il training di un modello di classificazione binaria usando gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>

## <a name="multiclass-classification"></a><span data-ttu-id="ac36a-121">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="ac36a-121">Multiclass classification</span></span>

<span data-ttu-id="ac36a-122">Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare la classe (categoria) di un'istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="ac36a-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="ac36a-123">L'input di un algoritmo di classificazione è un set di esempi con etichette.</span><span class="sxs-lookup"><span data-stu-id="ac36a-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="ac36a-124">In genere ogni etichetta è inizialmente costituita da testo.</span><span class="sxs-lookup"><span data-stu-id="ac36a-124">Each label normally starts as text.</span></span> <span data-ttu-id="ac36a-125">Viene quindi elaborata da TermTransform, che la converte nel tipo Key (numerico).</span><span class="sxs-lookup"><span data-stu-id="ac36a-125">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="ac36a-126">L'output di un algoritmo di classificazione è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette.</span><span class="sxs-lookup"><span data-stu-id="ac36a-126">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="ac36a-127">Alcuni esempi di scenari di classificazione multiclasse sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-127">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="ac36a-128">Determinare la razza di un cane come "siberian husky", "golden retriever", "barboncino" e così via.</span><span class="sxs-lookup"><span data-stu-id="ac36a-128">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="ac36a-129">Classificare recensioni di film come "positive", "neutrali" o "negative".</span><span class="sxs-lookup"><span data-stu-id="ac36a-129">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="ac36a-130">Classificare recensioni di hotel in base a "posizione", "prezzo", "pulizia" e così via.</span><span class="sxs-lookup"><span data-stu-id="ac36a-130">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="ac36a-131">Per altre informazioni, vedere l'articolo relativo alla [classificazione multiclasse](https://en.wikipedia.org/wiki/Multiclass_classification) su Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="ac36a-131">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="ac36a-132">Il modello "uno contro tutti" aggiorna gli [algoritmi di apprendimento per la classificazione binaria](#binary-classification) in modo che possano agire sui set di dati multiclasse.</span><span class="sxs-lookup"><span data-stu-id="ac36a-132">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="ac36a-133">Per altre informazioni, vedere [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="ac36a-133">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-training-algorithms"></a><span data-ttu-id="ac36a-134">Algoritmi di training di classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="ac36a-134">Multiclass Classification training algorithms</span></span>

<span data-ttu-id="ac36a-135">È possibile eseguire il training di un modello di classificazione multiclasse usando gli algoritmi di training seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-135">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

## <a name="regression"></a><span data-ttu-id="ac36a-136">Regressione</span><span class="sxs-lookup"><span data-stu-id="ac36a-136">Regression</span></span>

<span data-ttu-id="ac36a-137">Un attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare il valore dell'etichetta da un set di funzionalità correlate.</span><span class="sxs-lookup"><span data-stu-id="ac36a-137">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="ac36a-138">L'etichetta può essere relativa a qualsiasi valore reale e non appartiene a un set finito di valori come nelle attività di classificazione.</span><span class="sxs-lookup"><span data-stu-id="ac36a-138">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="ac36a-139">Gli algoritmi di regressione modellano la dipendenza dell'etichetta in base alle relative funzionalità correlate per determinare come cambierà l'etichetta quando variano i valori delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ac36a-139">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="ac36a-140">L'input di un algoritmo di regressione è un set di esempi con etichette di valori noti.</span><span class="sxs-lookup"><span data-stu-id="ac36a-140">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="ac36a-141">L'output di un algoritmo di regressione è una funzione, che è possibile usare per stimare il valore dell'etichetta per qualsiasi nuovo set di funzionalità di input.</span><span class="sxs-lookup"><span data-stu-id="ac36a-141">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="ac36a-142">Alcuni esempi di scenari di regressione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-142">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="ac36a-143">Stima dei prezzi delle case in base alle caratteristiche, come numero di camere da letto, posizione o dimensione.</span><span class="sxs-lookup"><span data-stu-id="ac36a-143">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="ac36a-144">Stima dei prezzi futuri delle azioni in base ai dati cronologici e alle tendenze di mercato correnti.</span><span class="sxs-lookup"><span data-stu-id="ac36a-144">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="ac36a-145">Stima delle vendite di un prodotto in base ai budget pubblicitari.</span><span class="sxs-lookup"><span data-stu-id="ac36a-145">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-training-algorithms"></a><span data-ttu-id="ac36a-146">Algoritmi di training di regressione</span><span class="sxs-lookup"><span data-stu-id="ac36a-146">Regression training algorithms</span></span>

<span data-ttu-id="ac36a-147">È possibile eseguire il training di un modello di regressione usando gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-147">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>

## <a name="clustering"></a><span data-ttu-id="ac36a-148">Clustering</span><span class="sxs-lookup"><span data-stu-id="ac36a-148">Clustering</span></span>

<span data-ttu-id="ac36a-149">Un'[attività di apprendimento automatico senza supervisione](glossary.md#unsupervised-machine-learning) che viene usata per raggruppare le istanze dei dati in cluster con caratteristiche simili.</span><span class="sxs-lookup"><span data-stu-id="ac36a-149">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="ac36a-150">Il clustering può anche essere usato per identificare relazioni in un set di dati che potrebbe essere impossibile ricavare logicamente dall'esplorazione o dalla semplice osservazione.</span><span class="sxs-lookup"><span data-stu-id="ac36a-150">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="ac36a-151">Gli input e gli output di un algoritmo di clustering dipendono dalla metodologia scelta.</span><span class="sxs-lookup"><span data-stu-id="ac36a-151">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="ac36a-152">È possibile adottare un approccio basato su distribuzione, centroide, connettività o densità.</span><span class="sxs-lookup"><span data-stu-id="ac36a-152">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="ac36a-153">ML.NET attualmente supporta un approccio basato su centroide che usa il clustering K-Means.</span><span class="sxs-lookup"><span data-stu-id="ac36a-153">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="ac36a-154">Alcuni esempi di scenari di clustering sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-154">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="ac36a-155">Comprensione dei segmenti degli ospiti degli hotel in base alle abitudini e alle caratteristiche delle scelte degli hotel.</span><span class="sxs-lookup"><span data-stu-id="ac36a-155">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="ac36a-156">Identificazione di segmenti di clienti e dati demografici per la creazione di campagne pubblicitarie mirate.</span><span class="sxs-lookup"><span data-stu-id="ac36a-156">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="ac36a-157">Classificazione di inventari in base alle metriche di produzione.</span><span class="sxs-lookup"><span data-stu-id="ac36a-157">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-training-algorithms"></a><span data-ttu-id="ac36a-158">Algoritmi di training di clustering</span><span class="sxs-lookup"><span data-stu-id="ac36a-158">Clustering training algorithms</span></span>

<span data-ttu-id="ac36a-159">È possibile eseguire il training di un modello di clustering usando l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="ac36a-159">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

## <a name="anomaly-detection"></a><span data-ttu-id="ac36a-160">Rilevamento di anomalie</span><span class="sxs-lookup"><span data-stu-id="ac36a-160">Anomaly detection</span></span>

<span data-ttu-id="ac36a-161">Questa attività crea un modello per il rilevamento di anomalie tramite l'analisi delle componenti principali.</span><span class="sxs-lookup"><span data-stu-id="ac36a-161">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="ac36a-162">Il rilevamento di anomalie basato su questo tipo di analisi consente di creare un modello in scenari in cui è facile ottenere dati di training da una singola classe, ad esempio le transazioni valide, ma è difficile ottenere campioni sufficienti delle anomalie da rilevare.</span><span class="sxs-lookup"><span data-stu-id="ac36a-162">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="ac36a-163">L'analisi delle componenti principali è una tecnica consolidata nell'apprendimento automatico che viene spesso usata per l'analisi esplorativa dei dati perché rivela la struttura interna dei dati e ne spiega la varianza.</span><span class="sxs-lookup"><span data-stu-id="ac36a-163">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="ac36a-164">Questa tecnica consiste nell'eseguire l'analisi di dati che contengono più variabili.</span><span class="sxs-lookup"><span data-stu-id="ac36a-164">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="ac36a-165">Cerca le correlazioni tra le variabili e determina la combinazione di valori che meglio rappresenta le differenze nei risultati.</span><span class="sxs-lookup"><span data-stu-id="ac36a-165">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="ac36a-166">Questi valori di caratteristica combinati vengono usati per creare uno spazio di caratteristiche più compatto, denominato componenti principali.</span><span class="sxs-lookup"><span data-stu-id="ac36a-166">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="ac36a-167">Il rilevamento di anomalie comprende molte attività importanti correlate all'apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="ac36a-167">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="ac36a-168">Identificazione di transazioni potenzialmente illecite.</span><span class="sxs-lookup"><span data-stu-id="ac36a-168">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="ac36a-169">Criteri di apprendimento indicanti che si è verificata un'intrusione nella rete.</span><span class="sxs-lookup"><span data-stu-id="ac36a-169">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="ac36a-170">Ricerca di gruppi anomali di pazienti.</span><span class="sxs-lookup"><span data-stu-id="ac36a-170">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="ac36a-171">Verifica dei valori immessi in un sistema.</span><span class="sxs-lookup"><span data-stu-id="ac36a-171">Checking values entered into a system.</span></span>

<span data-ttu-id="ac36a-172">Poiché le anomalie sono per definizione eventi rari, può essere difficile raccogliere un campione rappresentativo di dati da usare per la modellazione.</span><span class="sxs-lookup"><span data-stu-id="ac36a-172">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="ac36a-173">Gli algoritmi inclusi in questa categoria sono stati appositamente progettati per risolvere i problemi principali relativi alla creazione e al training dei modelli tramite set di dati non bilanciati.</span><span class="sxs-lookup"><span data-stu-id="ac36a-173">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-training-algorithms"></a><span data-ttu-id="ac36a-174">Algoritmi di training di rilevamento anomalie</span><span class="sxs-lookup"><span data-stu-id="ac36a-174">Anomaly detection training algorithms</span></span>

<span data-ttu-id="ac36a-175">È possibile eseguire il training di un modello di rilevamento anomalie usando l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="ac36a-175">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

## <a name="ranking"></a><span data-ttu-id="ac36a-176">Ranking</span><span class="sxs-lookup"><span data-stu-id="ac36a-176">Ranking</span></span>

<span data-ttu-id="ac36a-177">Un'attività di ranking crea un modello di ranking in base a un set di esempi con etichetta.</span><span class="sxs-lookup"><span data-stu-id="ac36a-177">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="ac36a-178">Questo set è costituito da gruppi di istanze a cui può essere assegnato un punteggio con determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="ac36a-178">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="ac36a-179">Le etichette di ranking sono {0, 1, 2, 3, 4} per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="ac36a-179">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="ac36a-180">Il modello di ranking viene sottoposto a training in modo da classificare in ordine di priorità nuovi gruppi di istanze con punteggi sconosciuti per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="ac36a-180">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="ac36a-181">Gli algoritmi di apprendimento per il ranking di ML.NET sono basati sulla tecnica di [ranking con apprendimento automatico](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="ac36a-181">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="ac36a-182">Algoritmi di training di classificazione</span><span class="sxs-lookup"><span data-stu-id="ac36a-182">Ranking training algorithms</span></span>

<span data-ttu-id="ac36a-183">È possibile eseguire il training di un modello di classificazione con gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac36a-183">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>

## <a name="recommendation"></a><span data-ttu-id="ac36a-184">Consiglio</span><span class="sxs-lookup"><span data-stu-id="ac36a-184">Recommendation</span></span>

<span data-ttu-id="ac36a-185">Un'attività di raccomandazione consente di generare un elenco di servizi o prodotti consigliati.</span><span class="sxs-lookup"><span data-stu-id="ac36a-185">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="ac36a-186">ML.NET usa la [fattorizzazione di matrice](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) e un algoritmo di [filtraggio collaborativo](https://en.wikipedia.org/wiki/Collaborative_filtering) per le raccomandazioni quando si hanno dati cronologici di classificazione dei prodotti nel proprio catalogo.</span><span class="sxs-lookup"><span data-stu-id="ac36a-186">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="ac36a-187">Ad esempio, quando sono presenti dati cronologici di classificazione di film per gli utenti e si vogliono raccomandare altri film a cui questi potrebbero essere interessati.</span><span class="sxs-lookup"><span data-stu-id="ac36a-187">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="ac36a-188">Algoritmi di training di raccomandazione</span><span class="sxs-lookup"><span data-stu-id="ac36a-188">Recommendation training algorithms</span></span>

<span data-ttu-id="ac36a-189">È possibile eseguire il training di un modello di raccomandazione con l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="ac36a-189">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
