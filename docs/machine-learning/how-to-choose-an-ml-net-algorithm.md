---
title: Come scegliere un algoritmo ML.NET
description: Informazioni su come scegliere un algoritmo ML.NET per il modello di Machine Learning
ms.topic: overview
ms.date: 06/05/2019
ms.openlocfilehash: 0fed33203c02303e37e47f548e08ec131eeb1c77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75739990"
---
# <a name="how-to-choose-an-mlnet-algorithm"></a>Come scegliere un algoritmo ML.NET

Per ogni [attività ML.NET](resources/tasks.md) è possibile scegliere tra diversi algoritmi di training. La scelta dipende dal problema che si risolvendo, dalle caratteristiche dei dati e dalle risorse di calcolo e archiviazione disponibili. È importante notare che il training di un modello di Machine Learning è un processo iterativo. Potrebbe essere necessario provare più algoritmi per trovare quello che funziona in modo ottimale.

Gli algoritmi operano sulle **caratteristiche**. Le caratteristiche sono valori numerici calcolati dai dati di input. Sono input ottimali per gli algoritmi di Machine Learning. I dati di input non elaborati vengono trasformati in caratteristiche usando una o più [trasformazioni di dati](resources/transforms.md). Ad esempio, i dati di testo vengono trasformati in un set di conteggi di parole e conteggi di combinazioni di parole. Dopo che le caratteristiche sono state estratte da un tipo di dati non elaborati usando le trasformazioni di dati, gli elementi vengono definiti come sottoposti a **estrazione delle caratteristiche**. Ad esempio, testo con estrazione delle caratteristiche, dati immagine con estrazione delle caratteristiche.

## <a name="trainer--algorithm--task"></a>Algoritmo di training = algoritmo + attività

Un algoritmo è la formula matematica che viene eseguita per produrre un **modello**. Algoritmi diversi producono modelli con caratteristiche diverse.

Con ML.NET è possibile applicare lo stesso algoritmo ad attività diverse. Ad esempio, Stochastic Dual Coordinated Ascent può essere usato per Classificazione binaria, Classificazione multiclasse e Regressione. La differenza sta nell'interpretazione dell'output dell'algoritmo per la corrispondenza con l'attività.

Per ogni combinazione algoritmo/attività, ML.NET include un componente che esegue l'algoritmo di training e l'interpretazione. Questi componenti sono detti algoritmi di training. Ad esempio <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer> usa l'algoritmo **StochasticDualCoordinatedAscent** applicato all'attività **Regressione**.

## <a name="linear-algorithms"></a>Algoritmi lineari

Gli algoritmi lineari producono un modello che calcola **punteggi** da una combinazione lineare dei dati di input e un set di **pesi**. I pesi sono parametri del modello definiti durante il training.

Gli algoritmi lineari funzionano in modo ottimale per le caratteristiche [separabili a livello lineare](https://en.wikipedia.org/wiki/Linear_separability).

Prima del training con un algoritmo lineare, le caratteristiche devono essere normalizzate. Ciò impedisce che una caratteristica abbia maggior influenza sul risultato rispetto alle altre.

In generale gli algoritmi lineari sono scalabili e veloci, facili da sottoporre a training ed economici in termini di previsioni. La scalabilità è basata sul numero di caratteristiche e approssimata in base alle dimensioni del training set.

Gli algoritmi lineari eseguono più passaggi sui dati di training. Se il set di dati può essere contenuto nella memoria, l'aggiunta di un [checkpoint della cache](xref:Microsoft.ML.LearningPipelineExtensions.AppendCacheCheckpoint*) alla pipeline ML.NET prima di accodare l'algoritmo di training renderà più veloce l'esecuzione del training.

**Algoritmi di training lineari**

|Algoritmo|Proprietà|Algoritmi di training|
|---------|----------|--------|
|Averaged perceptron|Ottimale per la classificazione di testo|<xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>|
|Stochastic Dual Coordinated Ascent|Ottimizzazione non necessaria per prestazioni predefinite ottimali|<xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer> <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer> <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer> <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>|
|L-BFGS|Da usare quando il numero di caratteristiche è elevato. Genera statistiche di training di regressione logistica, ma la sua scalabilità è inferiore a quella di AveragedPerceptronTrainer|<xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>|
|Symbolic stochastic gradient descent|L'algoritmo di training di classificazione binaria lineare più veloce e accurato. Scalatura ottimale con il numero di processori|<xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>|

## <a name="decision-tree-algorithms"></a>Algoritmi con albero delle decisioni

Gli algoritmi con albero delle decisioni creano un modello che contiene una serie di decisioni: di fatto si tratta di un diagramma di flusso che integra i valori dei dati.

Per l'uso di questo tipo di algoritmo non è necessario che le caratteristiche siano separabili a livello lineare. Inoltre non è necessario che le caratteristiche siano normalizzate, perché i singoli valori del vettore della caratteristica vengono usati in modo indipendente nel processo decisionale.

Gli algoritmi con albero delle decisioni sono in genere molto accurati.

Fatta eccezione per i modelli additivi generalizzati (GAM, Generalized Additive Models), i modelli ad albero possono risultare difficili da interpretare quando il numero di caratteristiche è molto elevato.

Gli algoritmi con albero delle decisioni richiedono più risorse e la loro scalabilità è inferiore a quella degli algoritmi lineari. Funzionano in modo ottimale nei set di dati che possono essere interamente adattabili in memoria.

Gli alberi delle decisioni con incremento sono un insieme di alberi di piccole dimensioni in cui ogni albero assegna un punteggio ai dati di input e passa il punteggio all'albero successivo per produrre un punteggio migliore, e così via. Ogni albero dell'insieme migliora il risultato del precedente.

**Algoritmi di training degli alberi delle decisioni**

|Algoritmo|Proprietà|Algoritmi di training|
|---------|----------|--------|
|Light gradient boosted machine|L'algoritmo di training dell'albero di classificazione binaria più veloce e accurato. Ampiamente ottimizzabile|<xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>|
|Fast tree|Da usare per i dati immagine sottoposti a estrazione delle caratteristiche. Resiliente per dati non equilibrati. Ampiamente ottimizzabile | <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>|
|Fast forest|Funziona in modo ottimale con dati non pertinenti|<xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>|
|Generalized additive model (GAM)|Ideale per scenari in cui gli algoritmi ad albero funzionano correttamente, ma la comprensibilità dei modelli è una priorità|<xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>|

## <a name="matrix-factorization"></a>Matrix factorization

|Proprietà|Algoritmi di training|
|----------|--------|
|Ideale per dati categorici di tipo sparse, con set di dati di grandi dimensioni|<xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>|

## <a name="meta-algorithms"></a>Meta algoritmi

Questi algoritmi di training creano un algoritmo di training multiclasse da un algoritmo di training binario. Usarli con <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>, <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>, <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>, <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>.

|Algoritmo|Proprietà|Algoritmi di training|
|---------|----------|--------|
|One versus all|Questo classificatore multiclasse esegue il training di un classificatore binario per ogni classe, che distingue tale classe da tutte le altre classi. È limitato in termini di scalatura dal numero di classi da categorizzare|[OneVersusAllTrainer\<BinaryClassificationTrainer>](xref:Microsoft.ML.Trainers.OneVersusAllTrainer) |
|Pairwise coupling|Questo classificatore multiclasse esegue il training di un algoritmo di classificazione binaria su ogni coppia di classi. È limitato in termini di scalatura dal numero di classi, perché è necessario eseguire il training di ogni combinazione di due classi.|[PairwiseCouplingTrainer\<BinaryClassificationTrainer>](xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer)|

## <a name="k-means"></a>K-Means

|Proprietà|Algoritmi di training|
|----------|--------|
|Usare per il clustering|<xref:Microsoft.ML.Trainers.KMeansTrainer>|

## <a name="principal-component-analysis"></a>Principal component analysis

|Proprietà|Algoritmi di training|
|----------|--------|
|Usare per il rilevamento di anomalie|<xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>|

## <a name="naive-bayes"></a>Naive Bayes

|Proprietà|Algoritmi di training|
|----------|--------|
|Usare questo algoritmo di training di classificazione multiclasse quando le caratteristiche sono indipendenti e il set di dati di training è di piccole dimensioni.|<xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>|

## <a name="prior-trainer"></a>Prior Trainer

|Proprietà|Algoritmi di training|
|----------|--------|
|Usare questo algoritmo di training di classificazione binaria per definire le prestazioni di altri algoritmi di training. Per essere efficienti, le metriche degli altri algoritmi di training devono essere migliori di quelle dell'algoritmo di training Prior. |<xref:Microsoft.ML.Trainers.PriorTrainer>|
