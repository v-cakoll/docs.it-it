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
# <a name="machine-learning-tasks-in-mlnet"></a>Attività di apprendimento automatico in ML.NET

Un'attività di Machine Learning è il tipo di stima o di inferenza effettuata, in base al problema o alla domanda richiesta e ai dati disponibili. Ad esempio, l'attività di classificazione assegna i dati alle categorie e l'attività di Clustering raggruppa i dati in base alla somiglianza.

Le attività di Machine Learning si basano sui modelli nei dati anziché essere programmati in modo esplicito.

Questo articolo descrive le diverse attività di Machine Learning tra cui è possibile scegliere in ML.NET e alcuni casi d'uso comuni.

Dopo aver deciso quale attività è appropriata per il proprio scenario, è necessario scegliere l'algoritmo migliore per il training del modello. Gli algoritmi disponibili sono elencati nella sezione per ogni attività.

## <a name="binary-classification"></a>Classificazione binaria

Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stabilire a quale di due classi (categorie) appartiene un'istanza di dati. L'input di un algoritmo di classificazione è un set di esempi con etichette, in cui ogni etichetta è un numero intero 0 o 1. L'output di un algoritmo di classificazione binaria è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette. Alcuni esempi di scenari di classificazione binaria sono i seguenti:

* [Comprensione del sentiment dei commenti di Twitter](../tutorials/sentiment-analysis.md) come "positivi" o "negativi".
* Diagnosi per stabilire se un paziente ha o meno una determinata malattia.
* Decisione di contrassegnare o meno un messaggio di posta elettronica come "posta indesiderata".
* Determinare se una foto contiene o meno un particolare elemento, ad esempio un cane o un frutto.

Per altre informazioni, vedere l'articolo relativo alla [classificazione binaria](https://en.wikipedia.org/wiki/Binary_classification) su Wikipedia.

### <a name="binary-classification-trainers"></a>Algoritmi di training di classificazione binaria

È possibile eseguire il training di un modello di classificazione binaria usando gli algoritmi seguenti:

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

### <a name="binary-classification-inputs-and-outputs"></a>Input e output di classificazione binaria

Per ottenere risultati ottimali con la classificazione binaria, i dati di training devono essere bilanciati, vale a dire avere un numero uguale di dati di training positivi e negativi. I valori mancanti devono essere gestiti prima del training.

I dati della colonna dell'etichetta di input devono essere <xref:System.Boolean>.
I dati della colonna delle funzionalità di input devono essere un vettore a dimensione fissa di <xref:System.Single>.

Questi istruttori restituiscono le colonne seguenti:

| Nome colonna di output | Tipo di colonna | Descrizione|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Il punteggio non elaborato calcolato dal modello|
| `PredictedLabel` | <xref:System.Boolean> | L'etichetta stimata, in base al segno del punteggio. Un punteggio negativo esegue il mapping a `false` e un punteggio negativo esegue il mapping a `true`.|

## <a name="multiclass-classification"></a>Classificazione multiclasse

Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare la classe (categoria) di un'istanza di dati. L'input di un algoritmo di classificazione è un set di esempi con etichette. In genere ogni etichetta è inizialmente costituita da testo. Viene quindi elaborata da TermTransform, che la converte nel tipo Key (numerico). L'output di un algoritmo di classificazione è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette. Alcuni esempi di scenari di classificazione multiclasse sono i seguenti:

* Determinare la razza di un cane come "siberian husky", "golden retriever", "barboncino" e così via.
* Classificare recensioni di film come "positive", "neutrali" o "negative".
* Classificare recensioni di hotel in base a "posizione", "prezzo", "pulizia" e così via.

Per altre informazioni, vedere l'articolo relativo alla [classificazione multiclasse](https://en.wikipedia.org/wiki/Multiclass_classification) su Wikipedia.

>[!NOTE]
>Il modello "uno contro tutti" aggiorna gli [algoritmi di apprendimento per la classificazione binaria](#binary-classification) in modo che possano agire sui set di dati multiclasse. Per altre informazioni, vedere [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).

### <a name="multiclass-classification-trainers"></a>Algoritmi di training di classificazione multiclasse

È possibile eseguire il training di un modello di classificazione multiclasse usando gli algoritmi di training seguenti:

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>
* <xref:Microsoft.ML.Vision.ImageClassificationTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a>Input e output di classificazione multiclasse

I dati della colonna dell'etichetta di input devono essere di tipo [key](xref:Microsoft.ML.Data.KeyDataViewType).
La colonna delle funzionalità deve essere un vettore di dimensioni fisse di <xref:System.Single>.

Questo algoritmo di training restituisce quanto segue:

| Nome output | Type | Descrizione|
| -- | -- | -- |
| `Score` | Vettore di <xref:System.Single> | I punteggi di tutte le classi. Valori più alti indicano maggiori probabilità di rientrare nella classe associata. Se l'elemento i-esimo ha il valore più elevato, l'indice delle etichette stimate sarà i. Si noti che i è l'indice a base zero. |
| `PredictedLabel` | Tipo [key](xref:Microsoft.ML.Data.KeyDataViewType) | L'indice dell'etichetta stimata. Se il valore è i, l'etichetta effettiva potrebbe essere la categoria i-esima nel tipo di etichetta di input con valori key. |

## <a name="regression"></a>Regressione

Un attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare il valore dell'etichetta da un set di funzionalità correlate. L'etichetta può essere relativa a qualsiasi valore reale e non appartiene a un set finito di valori come nelle attività di classificazione. Gli algoritmi di regressione modellano la dipendenza dell'etichetta in base alle relative funzionalità correlate per determinare come cambierà l'etichetta quando variano i valori delle funzionalità. L'input di un algoritmo di regressione è un set di esempi con etichette di valori noti. L'output di un algoritmo di regressione è una funzione, che è possibile usare per stimare il valore dell'etichetta per qualsiasi nuovo set di funzionalità di input. Alcuni esempi di scenari di regressione sono i seguenti:

* Stima dei prezzi delle case in base alle caratteristiche, come numero di camere da letto, posizione o dimensione.
* Stima dei prezzi futuri delle azioni in base ai dati cronologici e alle tendenze di mercato correnti.
* Stima delle vendite di un prodotto in base ai budget pubblicitari.

### <a name="regression-trainers"></a>Algoritmi di training di regressione

È possibile eseguire il training di un modello di regressione usando gli algoritmi seguenti:

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a>Input e output di regressione

I dati della colonna dell'etichetta di input devono essere <xref:System.Single>.

Gli algoritmi di training per questa attività restituiscono quanto segue:

| Nome output | Type | Descrizione|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Il punteggio non elaborato stimato dal modello |

## <a name="clustering"></a>Clustering

Un'[attività di apprendimento automatico senza supervisione](glossary.md#unsupervised-machine-learning) che viene usata per raggruppare le istanze dei dati in cluster con caratteristiche simili. Il clustering può anche essere usato per identificare relazioni in un set di dati che potrebbe essere impossibile ricavare logicamente dall'esplorazione o dalla semplice osservazione. Gli input e gli output di un algoritmo di clustering dipendono dalla metodologia scelta. È possibile adottare un approccio basato su distribuzione, centroide, connettività o densità. ML.NET attualmente supporta un approccio basato su centroide che usa il clustering K-Means. Alcuni esempi di scenari di clustering sono i seguenti:

* Comprensione dei segmenti degli ospiti degli hotel in base alle abitudini e alle caratteristiche delle scelte degli hotel.
* Identificazione di segmenti di clienti e dati demografici per la creazione di campagne pubblicitarie mirate.
* Classificazione di inventari in base alle metriche di produzione.

### <a name="clustering-trainer"></a>Algoritmi di training di clustering

È possibile eseguire il training di un modello di clustering usando l'algoritmo seguente:

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a>Input e output di clustering

I dati delle funzionalità di input devono essere <xref:System.Single>. Non sono necessarie etichette.

Questo algoritmo di training restituisce quanto segue:

| Nome output | Type | Descrizione|
| -- | -- | -- |
| `Score` | vettore di <xref:System.Single> | Le distanze del punto dati specificato dai baricentri di tutti i cluster |
| `PredictedLabel` | Tipo [key](xref:Microsoft.ML.Data.KeyDataViewType) | L'indice del cluster più vicino stimato dal modello. |

## <a name="anomaly-detection"></a>Rilevamento di anomalie

Questa attività crea un modello per il rilevamento di anomalie tramite l'analisi delle componenti principali. Il rilevamento di anomalie basato su questo tipo di analisi consente di creare un modello in scenari in cui è facile ottenere dati di training da una singola classe, ad esempio le transazioni valide, ma è difficile ottenere campioni sufficienti delle anomalie da rilevare.

L'analisi delle componenti principali è una tecnica consolidata nell'apprendimento automatico che viene spesso usata per l'analisi esplorativa dei dati perché rivela la struttura interna dei dati e ne spiega la varianza. Questa tecnica consiste nell'eseguire l'analisi di dati che contengono più variabili. Cerca le correlazioni tra le variabili e determina la combinazione di valori che meglio rappresenta le differenze nei risultati. Questi valori di caratteristica combinati vengono usati per creare uno spazio di caratteristiche più compatto, denominato componenti principali.

Il rilevamento di anomalie comprende molte attività importanti correlate all'apprendimento automatico:

* Identificazione di transazioni potenzialmente illecite.
* Criteri di apprendimento indicanti che si è verificata un'intrusione nella rete.
* Ricerca di gruppi anomali di pazienti.
* Verifica dei valori immessi in un sistema.

Poiché le anomalie sono per definizione eventi rari, può essere difficile raccogliere un campione rappresentativo di dati da usare per la modellazione. Gli algoritmi inclusi in questa categoria sono stati appositamente progettati per risolvere i problemi principali relativi alla creazione e al training dei modelli tramite set di dati non bilanciati.

### <a name="anomaly-detection-trainer"></a>Algoritmo di training di rilevamento anomalie

È possibile eseguire il training di un modello di rilevamento anomalie usando l'algoritmo seguente:

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a>Input e output di rilevamento anomalie

Le funzionalità di input devono essere un vettore a dimensione fissa di <xref:System.Single>.

Questo algoritmo di training restituisce quanto segue:

| Nome output | Type | Descrizione|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Il punteggio non negativo, illimitato calcolato dal modello di rilevamento anomalie |
| `PredictedLabel` | <xref:System.Boolean> | Valore true/false che indica se l'input è un'anomalia (PredictedLabel = true) o meno (PredictedLabel = false) |

## <a name="ranking"></a>Ranking

Un'attività di ranking crea un modello di ranking in base a un set di esempi con etichetta. Questo set è costituito da gruppi di istanze a cui può essere assegnato un punteggio con determinati criteri. Le etichette di ranking sono {0, 1, 2, 3, 4} per ogni istanza.  Il modello di ranking viene sottoposto a training in modo da classificare in ordine di priorità nuovi gruppi di istanze con punteggi sconosciuti per ogni istanza. Gli algoritmi di apprendimento per il ranking di ML.NET sono basati sulla tecnica di [ranking con apprendimento automatico](https://en.wikipedia.org/wiki/Learning_to_rank).

### <a name="ranking-training-algorithms"></a>Algoritmi di training di classificazione

È possibile eseguire il training di un modello di classificazione con gli algoritmi seguenti:

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a>Input e output di classificazione

Il tipo di dati dell'etichetta di input deve essere [key](xref:Microsoft.ML.Data.KeyDataViewType) o <xref:System.Single>. Il valore dell'etichetta determina la pertinenza, dove valori più alti indicano maggior pertinenza. Se l'etichetta è un tipo [key](xref:Microsoft.ML.Data.KeyDataViewType), l'indice di chiave è il valore di pertinenza, dove l'indice più basso è il meno pertinente. Se l'etichetta è un tipo <xref:System.Single>, valori più alti indicano maggior pertinenza.

I dati della funzionalità devono essere un vettore di dimensioni fisse di <xref:System.Single> e la colonna gruppo di righe di input deve essere un tipo [key](xref:Microsoft.ML.Data.KeyDataViewType).

Questo algoritmo di training restituisce quanto segue:

| Nome output | Type | Descrizione|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Il punteggio illimitato calcolato dal modello per determinare la stima |

## <a name="recommendation"></a>Indicazione

Un'attività di raccomandazione consente di generare un elenco di servizi o prodotti consigliati. ML.NET usa la [fattorizzazione di matrice](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) e un algoritmo di [filtraggio collaborativo](https://en.wikipedia.org/wiki/Collaborative_filtering) per le raccomandazioni quando si hanno dati cronologici di classificazione dei prodotti nel proprio catalogo. Ad esempio, quando sono presenti dati cronologici di classificazione di film per gli utenti e si vogliono raccomandare altri film a cui questi potrebbero essere interessati.

### <a name="recommendation-training-algorithms"></a>Algoritmi di training di raccomandazione

È possibile eseguire il training di un modello di raccomandazione con l'algoritmo seguente:

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>

## <a name="forecasting"></a>Previsione

L'attività di previsione usa i dati precedenti della serie temporale per eseguire stime sul comportamento futuro. Gli scenari applicabili alla previsione includono previsioni meteorologiche, previsioni di vendita stagionali e manutenzione predittiva,

### <a name="forecasting-trainers"></a>Formazione per la previsione

È possibile eseguire il training di un modello di previsione con l'algoritmo seguente:

<xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa*>
