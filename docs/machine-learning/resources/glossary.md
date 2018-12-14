---
title: Glossario dell'apprendimento automatico - ML.NET
description: Glossario dei principali termini relativi all'apprendimento automatico, utili per la creazione di modelli personalizzati in ML.NET.
ms.custom: seodec18
ms.date: 12/06/2018
ms.openlocfilehash: 4db28a62fccca2e8bedc9f48485a61b6f4ab1801
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150576"
---
# <a name="machine-learning-glossary-of-important-terms"></a>Glossario dell'apprendimento automatico

Di seguito sono riportati i principali termini relativi all'apprendimento automatico, utili per la creazione di modelli personalizzati in ML.NET.

## <a name="accuracy"></a>Accuratezza

Nell'ambito della [classificazione](#classification), l'accuratezza è il numero di elementi classificati correttamente diviso per il numero totale di elementi nel set di test. È compresa tra 0 (meno accurato) e 1 (più accurato). L'accuratezza è una delle metriche di valutazione delle prestazioni del modello. Deve essere considerata in combinazione con la [precisione](#precision), il [richiamo](#recall) e il [punteggio F](#f-score).

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Accuracy?displayProperty=nameWithType>.

## <a name="area-under-the-curve-auc"></a>Area sottesa alla curva (AUC)

Nella [classificazione binaria](#binary-classification), una metrica di valutazione costituita dal valore dell'area sotto la curva che traccia il tasso di veri positivi (sull'asse y) rispetto al tasso di falsi positivi (sull'asse x). È compresa tra 0,5 (peggiore) e 1 (migliore). È anche nota come area sottesa alla curva ROC (Receiver Operating Characteristic). Per altre informazioni, vedere l'articolo relativo alle curve [ROC (Receiver Operating Characteristic)](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) su Wikipedia.

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Auc?displayProperty=nameWithType>.

## <a name="binary-classification"></a>Classificazione binaria

Un caso di [classificazione](#classification) in cui l'[etichetta](#label) può essere solo una di due classi. Per altre informazioni, vedere la sezione [Classificazione binaria](tasks.md#binary-classification) dell'argomento [Attività di apprendimento automatico](tasks.md).

## <a name="classification"></a>Classificazione

Quando i dati vengono usati per stimare una categoria, l'attività di [apprendimento automatico con supervisione](#supervised-machine-learning) viene denominata classificazione. Il termine [classificazione binaria](#binary-classification) fa riferimento alla stima di due sole categorie (ad esempio, la classificazione di un'immagine come un'immagine di un "gatto" o un "cane"). Il termine [classificazione multiclasse](#multiclass-classification) fa riferimento alla stima di più categorie (ad esempio, la classificazione di un'immagine come un'immagine di una specifica razza di cani).

## <a name="coefficient-of-determination"></a>Coefficiente di determinazione

Nell'ambito della [regressione](#regression), una metrica di valutazione che indica il livello di adattamento dei dati a un modello. È compreso tra 0 e 1. Un valore pari a 0 indica che i dati sono casuali o non possono essere adattati al modello. Un valore pari a 1 indica che il modello corrisponde esattamente ai dati. È noto anche come r<sup>2</sup>, R<sup>2</sup> o r al quadrato.

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.RegressionMetrics.RSquared?displayProperty=nameWithType>.

## <a name="feature"></a>Caratteristica

Una proprietà misurabile del fenomeno misurato, in genere un valore numerico (double). Più caratteristiche sono denominate **vettore di caratteristiche**, generalmente archiviato come `double[]`. Le caratteristiche definiscono gli aspetti importanti del fenomeno misurato. Per altre informazioni, vedere l'articolo relativo alle [caratteristiche](https://en.wikipedia.org/wiki/Feature_(machine_learning)) su Wikipedia.

## <a name="feature-engineering"></a>Progettazione di caratteristiche

La progettazione di caratteristiche è il processo che comprende la definizione di un set di [caratteristiche](#feature) e lo sviluppo di software che produce vettori di caratteristiche dai dati disponibili sul fenomeno, ovvero l'estrazione di caratteristiche. Per altre informazioni, vedere l'articolo relativo alla [progettazione di caratteristiche](https://en.wikipedia.org/wiki/Feature_engineering) su Wikipedia.

## <a name="f-score"></a>Punteggio F

Nell'ambito della [classificazione](#classification), una metrica di valutazione che consente di bilanciare la [precisione](#precision) e il [richiamo](#recall).

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.F1Score?displayProperty=nameWithType>.

## <a name="hyperparameter"></a>Iperparametro

Un parametro di un algoritmo di apprendimento automatico. Alcuni esempi sono il numero di alberi da apprendere in una foresta delle decisioni o la dimensione di incremento in un algoritmo di discesa del gradiente. I valori degli *iperparametri* sono impostati prima di eseguire il training del modello e gestiscono il processo di individuazione dei parametri della funzione di stima, ad esempio i punti di confronto in un albero delle decisioni o i pesi in un modello di regressione lineare. Per altre informazioni, vedere l'articolo relativo agli [iperparametri](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) su Wikipedia.

## <a name="label"></a>Etichetta

L'elemento da stimare con il modello di apprendimento automatico. Ad esempio, la razza di un cane o il prezzo di un'azione in futuro.

## <a name="log-loss"></a>Perdita di log

Nell'ambito della [classificazione](#classification), una metrica di valutazione che caratterizza l'accuratezza di un classificatore. Minore è perdita di log, più accurato è il classificatore.

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.LogLoss?displayProperty=nameWithType>.

## <a name="mean-absolute-error-mae"></a>Errore assoluto medio (MAE)

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla media di tutti gli errori del modello, dove un errore del modello è la distanza tra il valore di [etichetta](#label) stimato e il valore di etichetta corretto.

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.RegressionMetrics.L1?displayProperty=nameWithType>.

## <a name="model"></a>Modello

Tradizionalmente, i parametri per la funzione di stima. Ad esempio, i pesi in un modello di regressione lineare o i punti di divisione in un albero delle decisioni. In ML.NET, un modello contiene tutte le informazioni necessarie per stimare l'[etichetta](#label) di un oggetto di dominio, ad esempio immagine o testo. Questo significa che i modelli ML.NET includono i passaggi necessari per l'estrazione delle caratteristiche, nonché i parametri per la funzione di stima.

## <a name="multiclass-classification"></a>Classificazione multiclasse

Un caso di [classificazione](#classification) in cui l'[etichetta](#label) può essere di tre o più classi. Per altre informazioni, vedere la sezione [Classificazione multiclasse](tasks.md#multiclass-classification) dell'argomento [Attività di apprendimento automatico](tasks.md).

## <a name="n-gram"></a>N-gramma

Uno schema di estrazione delle caratteristiche per i dati di testo: qualsiasi sequenza di N parole viene trasformata in un valore di [caratteristica](#feature).

## <a name="numerical-feature-vector"></a>Vettore di caratteristiche numerico

Un vettore di [caratteristiche](#feature) costituito solo da valori numerici. È simile a `double[]`.

## <a name="pipeline"></a>Pipeline

Tutte le operazioni necessarie per adattare un modello a un set di dati. Una pipeline è costituita dai passaggi di importazione dei dati, trasformazione, estrazione delle caratteristiche e apprendimento. Una volta eseguito il training, una pipeline si trasforma in un modello.

## <a name="precision"></a>Precisione

Nell'ambito della [classificazione](#classification), la precisione di una classe è il numero di elementi stimati correttamente come appartenenti alla classe diviso per il numero totale di elementi previsti come appartenenti alla classe.

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativePrecision?displayProperty=nameWithType>, <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositivePrecision?displayProperty=nameWithType>.

## <a name="recall"></a>Richiamo

Nell'ambito della [classificazione](#classification), il richiamo di una classe è il numero di elementi stimati correttamente come appartenenti alla classe diviso per il numero totale di elementi effettivamente appartenenti alla classe.

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativeRecall?displayProperty=nameWithType>, <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositiveRecall?displayProperty=nameWithType>.

## <a name="regression"></a>Regressione

Un'attività di [apprendimento automatico con supervisione](#supervised-machine-learning) in cui l'output è un valore reale, ad esempio double. Un esempio è la stima dei prezzi delle azioni. Per altre informazioni, vedere la sezione [Regressione](tasks.md#regression) dell'argomento [Attività di apprendimento automatico](tasks.md).

## <a name="relative-absolute-error"></a>Errore assoluto relativo

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla somma di tutti gli errori assoluti divisa per la somma delle distanze tra i valori di [etichetta](#label) corretti e la media di tutti i valori di etichetta corretti.

## <a name="relative-squared-error"></a>Errore quadratico relativo

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla somma di tutti gli errori assoluti al quadrato divisa per la somma delle distanze al quadrato tra i valori di [etichetta](#label) corretti e la media di tutti i valori di etichetta corretti.

## <a name="root-of-mean-squared-error-rmse"></a>Radice dell'errore quadratico medio (RMSE)

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla radice quadrata della media dei quadrati degli errori.

API ML.NET correlate: <xref:Microsoft.ML.Legacy.Models.RegressionMetrics.Rms?displayProperty=nameWithType>.

## <a name="supervised-machine-learning"></a>Apprendimento automatico con supervisione

Una sottoclasse di apprendimento automatico in cui un modello desiderato stima l'etichetta per dati non ancora visibili. Alcuni esempi sono la classificazione, la regressione e la stima strutturata. Per altre informazioni, vedere l'articolo relativo all'[apprendimento con supervisione](https://en.wikipedia.org/wiki/Supervised_learning) su Wikipedia.

## <a name="training"></a>Training

Il processo di identificazione di un [modello](#model) per un determinato training set. Per un modello lineare, rappresenta l'individuazione dei pesi. Per una struttura ad albero, implica l'identificazione dei punti di divisione.

## <a name="transform"></a>Trasformazione

Un componente della [pipeline](#pipeline) che trasforma i dati, ad esempio da testo a vettori di numeri.

## <a name="unsupervised-machine-learning"></a>Apprendimento automatico senza supervisione

Una sottoclasse dell'apprendimento automatico in cui un modello desiderato individua una struttura nascosta (o latente) nei dati. Alcuni esempi sono il clustering, la modellazione degli argomenti e la riduzione della dimensionalità. Per altre informazioni, vedere l'articolo relativo all'[apprendimento senza supervisione](https://en.wikipedia.org/wiki/Unsupervised_learning) su Wikipedia.
