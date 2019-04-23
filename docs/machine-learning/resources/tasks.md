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
# <a name="machine-learning-tasks-in-mlnet"></a>Attività di apprendimento automatico in ML.NET

Quando si compila un modello di apprendimento automatico, è innanzitutto necessario definire quale risultato si vuole ottenere con i dati. In tal modo è possibile scegliere l'attività di apprendimento automatico più adatta alla specifica situazione. Nell'elenco seguente sono descritte le diverse attività di apprendimento automatico tra cui è possibile scegliere e alcuni casi d'uso comuni.

Dopo aver deciso quale attività è appropriata per il proprio scenario, è necessario scegliere l'algoritmo migliore per il training del modello. Gli algoritmi disponibili sono elencati nella sezione per ogni attività.

## <a name="binary-classification"></a>Classificazione binaria

Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stabilire a quale di due classi (categorie) appartiene un'istanza di dati. L'input di un algoritmo di classificazione è un set di esempi con etichette, in cui ogni etichetta è un numero intero 0 o 1. L'output di un algoritmo di classificazione binaria è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette. Alcuni esempi di scenari di classificazione binaria sono i seguenti:

* [Comprensione del sentiment dei commenti di Twitter](../tutorials/sentiment-analysis.md) come "positivi" o "negativi".
* Diagnosi per stabilire se un paziente ha o meno una determinata malattia.
* Decisione di contrassegnare o meno un messaggio di posta elettronica come "posta indesiderata".
* Identificazione di un cane o di un frutto all'interno di una foto.

Per altre informazioni, vedere l'articolo relativo alla [classificazione binaria](https://en.wikipedia.org/wiki/Binary_classification) su Wikipedia.

### <a name="binary-classification-training-algorithms"></a>Algoritmi di training di classificazione binaria

È possibile eseguire il training di un modello di classificazione binaria usando gli algoritmi seguenti:

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

## <a name="multiclass-classification"></a>Classificazione multiclasse

Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare la classe (categoria) di un'istanza di dati. L'input di un algoritmo di classificazione è un set di esempi con etichette. In genere ogni etichetta è inizialmente costituita da testo. Viene quindi elaborata da TermTransform, che la converte nel tipo Key (numerico). L'output di un algoritmo di classificazione è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette. Alcuni esempi di scenari di classificazione multiclasse sono i seguenti:

* Determinare la razza di un cane come "siberian husky", "golden retriever", "barboncino" e così via.
* Classificare recensioni di film come "positive", "neutrali" o "negative".
* Classificare recensioni di hotel in base a "posizione", "prezzo", "pulizia" e così via.

Per altre informazioni, vedere l'articolo relativo alla [classificazione multiclasse](https://en.wikipedia.org/wiki/Multiclass_classification) su Wikipedia.

>[!NOTE]
>Il modello "uno contro tutti" aggiorna gli [algoritmi di apprendimento per la classificazione binaria](#binary-classification) in modo che possano agire sui set di dati multiclasse. Per altre informazioni, vedere [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).

### <a name="multiclass-classification-training-algorithms"></a>Algoritmi di training di classificazione multiclasse

È possibile eseguire il training di un modello di classificazione multiclasse usando gli algoritmi di training seguenti:

* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

## <a name="regression"></a>Regressione

Un attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare il valore dell'etichetta da un set di funzionalità correlate. L'etichetta può essere relativa a qualsiasi valore reale e non appartiene a un set finito di valori come nelle attività di classificazione. Gli algoritmi di regressione modellano la dipendenza dell'etichetta in base alle relative funzionalità correlate per determinare come cambierà l'etichetta quando variano i valori delle funzionalità. L'input di un algoritmo di regressione è un set di esempi con etichette di valori noti. L'output di un algoritmo di regressione è una funzione, che è possibile usare per stimare il valore dell'etichetta per qualsiasi nuovo set di funzionalità di input. Alcuni esempi di scenari di regressione sono i seguenti:

* Stima dei prezzi delle case in base alle caratteristiche, come numero di camere da letto, posizione o dimensione.
* Stima dei prezzi futuri delle azioni in base ai dati cronologici e alle tendenze di mercato correnti.
* Stima delle vendite di un prodotto in base ai budget pubblicitari.

### <a name="regression-training-algorithms"></a>Algoritmi di training di regressione

È possibile eseguire il training di un modello di regressione usando gli algoritmi seguenti:

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>

## <a name="clustering"></a>Clustering

Un'[attività di apprendimento automatico senza supervisione](glossary.md#unsupervised-machine-learning) che viene usata per raggruppare le istanze dei dati in cluster con caratteristiche simili. Il clustering può anche essere usato per identificare relazioni in un set di dati che potrebbe essere impossibile ricavare logicamente dall'esplorazione o dalla semplice osservazione. Gli input e gli output di un algoritmo di clustering dipendono dalla metodologia scelta. È possibile adottare un approccio basato su distribuzione, centroide, connettività o densità. ML.NET attualmente supporta un approccio basato su centroide che usa il clustering K-Means. Alcuni esempi di scenari di clustering sono i seguenti:

* Comprensione dei segmenti degli ospiti degli hotel in base alle abitudini e alle caratteristiche delle scelte degli hotel.
* Identificazione di segmenti di clienti e dati demografici per la creazione di campagne pubblicitarie mirate.
* Classificazione di inventari in base alle metriche di produzione.

### <a name="clustering-training-algorithms"></a>Algoritmi di training di clustering

È possibile eseguire il training di un modello di clustering usando l'algoritmo seguente:

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

## <a name="anomaly-detection"></a>Rilevamento di anomalie

Questa attività crea un modello per il rilevamento di anomalie tramite l'analisi delle componenti principali. Il rilevamento di anomalie basato su questo tipo di analisi consente di creare un modello in scenari in cui è facile ottenere dati di training da una singola classe, ad esempio le transazioni valide, ma è difficile ottenere campioni sufficienti delle anomalie da rilevare.

L'analisi delle componenti principali è una tecnica consolidata nell'apprendimento automatico che viene spesso usata per l'analisi esplorativa dei dati perché rivela la struttura interna dei dati e ne spiega la varianza. Questa tecnica consiste nell'eseguire l'analisi di dati che contengono più variabili. Cerca le correlazioni tra le variabili e determina la combinazione di valori che meglio rappresenta le differenze nei risultati. Questi valori di caratteristica combinati vengono usati per creare uno spazio di caratteristiche più compatto, denominato componenti principali.

Il rilevamento di anomalie comprende molte attività importanti correlate all'apprendimento automatico:

* Identificazione di transazioni potenzialmente illecite.
* Criteri di apprendimento indicanti che si è verificata un'intrusione nella rete.
* Ricerca di gruppi anomali di pazienti.
* Verifica dei valori immessi in un sistema.

Poiché le anomalie sono per definizione eventi rari, può essere difficile raccogliere un campione rappresentativo di dati da usare per la modellazione. Gli algoritmi inclusi in questa categoria sono stati appositamente progettati per risolvere i problemi principali relativi alla creazione e al training dei modelli tramite set di dati non bilanciati.

### <a name="anomaly-detection-training-algorithms"></a>Algoritmi di training di rilevamento anomalie

È possibile eseguire il training di un modello di rilevamento anomalie usando l'algoritmo seguente:

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

## <a name="ranking"></a>Ranking

Un'attività di ranking crea un modello di ranking in base a un set di esempi con etichetta. Questo set è costituito da gruppi di istanze a cui può essere assegnato un punteggio con determinati criteri. Le etichette di ranking sono {0, 1, 2, 3, 4} per ogni istanza.  Il modello di ranking viene sottoposto a training in modo da classificare in ordine di priorità nuovi gruppi di istanze con punteggi sconosciuti per ogni istanza. Gli algoritmi di apprendimento per il ranking di ML.NET sono basati sulla tecnica di [ranking con apprendimento automatico](https://en.wikipedia.org/wiki/Learning_to_rank).

### <a name="ranking-training-algorithms"></a>Algoritmi di training di classificazione

È possibile eseguire il training di un modello di classificazione con gli algoritmi seguenti:

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>

## <a name="recommendation"></a>Consiglio

Un'attività di raccomandazione consente di generare un elenco di servizi o prodotti consigliati. ML.NET usa la [fattorizzazione di matrice](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) e un algoritmo di [filtraggio collaborativo](https://en.wikipedia.org/wiki/Collaborative_filtering) per le raccomandazioni quando si hanno dati cronologici di classificazione dei prodotti nel proprio catalogo. Ad esempio, quando sono presenti dati cronologici di classificazione di film per gli utenti e si vogliono raccomandare altri film a cui questi potrebbero essere interessati.

### <a name="recommendation-training-algorithms"></a>Algoritmi di training di raccomandazione

È possibile eseguire il training di un modello di raccomandazione con l'algoritmo seguente:

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
