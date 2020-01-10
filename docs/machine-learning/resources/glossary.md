---
title: Glossario dell'apprendimento automatico
description: Glossario dei principali termini relativi all'apprendimento automatico, utili per la creazione di modelli personalizzati in ML.NET.
ms.topic: reference
ms.date: 07/31/2019
ms.openlocfilehash: 32ccb6df1cb08db45ebd25a0d1c0ea4396a6c50b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739884"
---
# <a name="machine-learning-glossary-of-important-terms"></a>Glossario dell'apprendimento automatico

Di seguito sono riportati i principali termini relativi all'apprendimento automatico, utili per la creazione di modelli personalizzati in ML.NET.

## <a name="accuracy"></a>Accuratezza

Nell'ambito della [classificazione](#classification), l'accuratezza è il numero di elementi classificati correttamente diviso per il numero totale di elementi nel set di test. È compresa tra 0 (meno accurato) e 1 (più accurato). L'accuratezza è una delle metriche di valutazione delle prestazioni del modello. Deve essere considerata in combinazione con la [precisione](#precision), il [richiamo](#recall) e il [punteggio F](#f-score).

## <a name="area-under-the-curve-auc"></a>Area sottesa alla curva (AUC)

Nella [classificazione binaria](#binary-classification), una metrica di valutazione costituita dal valore dell'area sotto la curva che traccia il tasso di veri positivi (sull'asse y) rispetto al tasso di falsi positivi (sull'asse x). È compresa tra 0,5 (peggiore) e 1 (migliore). È anche nota come area sottesa alla curva ROC (Receiver Operating Characteristic). Per altre informazioni, vedere l'articolo relativo alle curve [ROC (Receiver Operating Characteristic)](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) su Wikipedia.

## <a name="binary-classification"></a>Classificazione binaria

Un caso di [classificazione](#classification) in cui l'[etichetta](#label) può essere solo una di due classi. Per altre informazioni, vedere la sezione [Classificazione binaria](tasks.md#binary-classification) dell'argomento [Attività di apprendimento automatico](tasks.md).

## <a name="calibration"></a>Calibrazione

La calibrazione è il processo di mapping di un punteggio non elaborato a un'appartenenza di classe, per la classificazione binaria e multiclasse. Alcuni formatori ML.NET hanno un suffisso `NonCalibrated`. Questi algoritmi producono un punteggio non elaborato che deve quindi essere mappato a una probabilità di classe.

## <a name="catalog"></a>di catalogo

In ML.NET un catalogo è una raccolta di funzioni di estensione, raggruppate in base a uno scopo comune.

Ad esempio, ogni attività di apprendimento automatico (classificazione binaria, regressione, ranking e così via) include un catalogo di algoritmi di apprendimento automatico disponibili (formatori). Il catalogo per i formatori di classificazione binaria è: <xref:Microsoft.ML.BinaryClassificationCatalog.BinaryClassificationTrainers>.

## <a name="classification"></a>Classificazione

Quando i dati vengono usati per stimare una categoria, l'attività di [apprendimento automatico con supervisione](#supervised-machine-learning) viene denominata classificazione. Il termine [classificazione binaria](#binary-classification) fa riferimento alla stima di due sole categorie (ad esempio, la classificazione di un'immagine come un'immagine di un "gatto" o un "cane"). Il termine [classificazione multiclasse](#multiclass-classification) fa riferimento alla stima di più categorie (ad esempio, la classificazione di un'immagine come un'immagine di una specifica razza di cani).

## <a name="coefficient-of-determination"></a>Coefficiente di determinazione

Nell'ambito della [regressione](#regression), una metrica di valutazione che indica il livello di adattamento dei dati a un modello. È compreso tra 0 e 1. Un valore pari a 0 indica che i dati sono casuali o non possono essere adattati al modello. Un valore pari a 1 indica che il modello corrisponde esattamente ai dati. È noto anche come r<sup>2</sup>, R<sup>2</sup> o r al quadrato.

## <a name="data"></a>Data

I dati sono fondamentali per qualsiasi applicazione di apprendimento automatico. In ML.NET i dati sono rappresentati da oggetti <xref:Microsoft.ML.IDataView>. Gli oggetti di visualizzazione dei dati:

- sono costituiti da colonne e righe
- vengono valutati in modalità lazy, ovvero caricano i dati solo quando li chiama un'operazione
- contengono uno schema che definisce il tipo, il formato e la lunghezza di ogni colonna

## <a name="estimator"></a>Strumento di stima

Classe di ML.NET che implementa l'interfaccia <xref:Microsoft.ML.IEstimator%601>.

Uno strumento di stima è una specifica di una trasformazione, sia la trasformazione di preparazione dei dati, sia la trasformazione del training del modello di apprendimento automatico. Gli strumenti di stima possono essere concatenati in una pipeline di trasformazioni. I parametri di uno strumento di stima o una pipeline di strumenti di stima vengono appresi quando si chiama <xref:Microsoft.ML.IEstimator%601.Fit%2A>. Il risultato di <xref:Microsoft.ML.IEstimator%601.Fit%2A> è un [trasformatore](#transformer).

## <a name="extension-method"></a>Metodo di estensione

Metodo .NET che fa parte di una classe ma è definito all'esterno della classe. Il primo parametro di un metodo di estensione è un riferimento `this` statico alla classe a cui appartiene il metodo di estensione.

I metodi di estensione vengono usati spesso in ML.NET per costruire istanze di [trasformatori](#estimator).

## <a name="feature"></a>Caratteristica

Una proprietà misurabile del fenomeno misurato, in genere un valore numerico (double). Più funzionalità sono denominate **vettore di funzionalità**, generalmente archiviato come `double[]`. Le funzionalità definiscono le caratteristiche importanti del fenomeno misurato. Per altre informazioni, vedere l'articolo relativo alle [funzionalità](https://en.wikipedia.org/wiki/Feature_(machine_learning)) su Wikipedia.

## <a name="feature-engineering"></a>Progettazione di funzionalità

La progettazione di funzionalità è il processo che comprende la definizione di un set di [funzionalità](#feature) e lo sviluppo di software che produce vettori di funzionalità dai dati disponibili sul fenomeno, ovvero l'estrazione di funzionalità. Per altre informazioni, vedere l'articolo relativo alla [progettazione di funzionalità](https://en.wikipedia.org/wiki/Feature_engineering) su Wikipedia.

## <a name="f-score"></a>Punteggio F

Nell'ambito della [classificazione](#classification), una metrica di valutazione che consente di bilanciare la [precisione](#precision) e il [richiamo](#recall).

## <a name="hyperparameter"></a>Iperparametro

Un parametro di un algoritmo di apprendimento automatico. Alcuni esempi sono il numero di alberi da apprendere in una foresta delle decisioni o la dimensione di incremento in un algoritmo di discesa del gradiente. I valori degli *iperparametri* sono impostati prima di eseguire il training del modello e gestiscono il processo di individuazione dei parametri della funzione di stima, ad esempio i punti di confronto in un albero delle decisioni o i pesi in un modello di regressione lineare. Per altre informazioni, vedere l'articolo relativo agli [iperparametri](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) su Wikipedia.

## <a name="label"></a>Label

L'elemento da stimare con il modello di apprendimento automatico. Ad esempio, la razza di un cane o il prezzo di un'azione in futuro.

## <a name="log-loss"></a>Perdita di log

Nell'ambito della [classificazione](#classification), una metrica di valutazione che caratterizza l'accuratezza di un classificatore. Minore è perdita di log, più accurato è il classificatore.

## <a name="loss-function"></a>Funzione di perdita

Una funzione di perdita è la differenza tra i valori delle etichette di training e la stima eseguita dal modello. I parametri del modello vengono stimati riducendo al minimo la funzione di perdita.

Formatori diversi possono essere configurati con funzioni di perdita diverse.

## <a name="mean-absolute-error-mae"></a>Errore assoluto medio (MAE)

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla media di tutti gli errori del modello, dove un errore del modello è la distanza tra il valore di [etichetta](#label) stimato e il valore di etichetta corretto.

## <a name="model"></a>Modello

Tradizionalmente, i parametri per la funzione di stima. Ad esempio, i pesi in un modello di regressione lineare o i punti di divisione in un albero delle decisioni. In ML.NET, un modello contiene tutte le informazioni necessarie per stimare l'[etichetta](#label) di un oggetto di dominio, ad esempio immagine o testo. Questo significa che i modelli ML.NET includono i passaggi necessari per l'estrazione delle funzionalità, nonché i parametri per la funzione di stima.

## <a name="multiclass-classification"></a>Classificazione multiclasse

Un caso di [classificazione](#classification) in cui l'[etichetta](#label) può essere di tre o più classi. Per altre informazioni, vedere la sezione [Classificazione multiclasse](tasks.md#multiclass-classification) dell'argomento [Attività di apprendimento automatico](tasks.md).

## <a name="n-gram"></a>N-gramma

Uno schema di estrazione delle funzionalità per i dati di testo: qualsiasi sequenza di N parole viene trasformata in un valore di [funzionalità](#feature).

## <a name="normalization"></a>Normalization

La normalizzazione è il processo di ridimensionamento dei dati a virgola mobile in valori compresi tra 0 e 1. Molti degli algoritmi di training usati in ML.NET richiedono la normalizzazione dei dati della funzionalità di input. ML.NET fornisce una serie di [trasformazioni per la normalizzazione](transforms.md#normalization-and-scaling)

## <a name="numerical-feature-vector"></a>Vettore di funzionalità numerico

Un vettore di [funzionalità](#feature) costituito solo da valori numerici. È simile a `double[]`.

## <a name="pipeline"></a>Pipeline

Tutte le operazioni necessarie per adattare un modello a un set di dati. Una pipeline è costituita dai passaggi di importazione dei dati, trasformazione, estrazione delle funzionalità e apprendimento. Una volta eseguito il training, una pipeline si trasforma in un modello.

## <a name="precision"></a>Precisione

Nell'ambito della [classificazione](#classification), la precisione di una classe è il numero di elementi stimati correttamente come appartenenti alla classe diviso per il numero totale di elementi previsti come appartenenti alla classe.

## <a name="recall"></a>Richiamo

Nell'ambito della [classificazione](#classification), il richiamo di una classe è il numero di elementi stimati correttamente come appartenenti alla classe diviso per il numero totale di elementi effettivamente appartenenti alla classe.

## <a name="regularization"></a>Regularization

 La regolarizzazione penalizza un modello lineare per essere troppo complicato. Sono disponibili due tipi di regolarizzazione:

- La regolarizzazione $L_1$ azzera i pesi per le funzionalità non significative. La dimensione del modello salvato può ridursi dopo questo tipo di regolarizzazione.
- $L regolarizzazione _2 $ riduce al minimo l'intervallo di ponderazione per le funzionalità non significative. Si tratta di un processo più generale ed è meno sensibile agli outlier.

## <a name="regression"></a>Regressione

Un'attività di [apprendimento automatico con supervisione](#supervised-machine-learning) in cui l'output è un valore reale, ad esempio double. Un esempio è la stima dei prezzi delle azioni. Per altre informazioni, vedere la sezione [Regressione](tasks.md#regression) dell'argomento [Attività di apprendimento automatico](tasks.md).

## <a name="relative-absolute-error"></a>Errore assoluto relativo

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla somma di tutti gli errori assoluti divisa per la somma delle distanze tra i valori di [etichetta](#label) corretti e la media di tutti i valori di etichetta corretti.

## <a name="relative-squared-error"></a>Errore quadratico relativo

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla somma di tutti gli errori assoluti al quadrato divisa per la somma delle distanze al quadrato tra i valori di [etichetta](#label) corretti e la media di tutti i valori di etichetta corretti.

## <a name="root-of-mean-squared-error-rmse"></a>Radice dell'errore quadratico medio (RMSE)

Nell'ambito della [regressione](#regression), una metrica di valutazione costituita dalla radice quadrata della media dei quadrati degli errori.

## <a name="scoring"></a>Punteggio

L'assegnazione dei punteggi è il processo di applicazione di nuovi dati a un modello di apprendimento automatico sottoposto a training e la successiva generazione di stime. L'assegnazione dei punteggi è nota anche come inferenza. A seconda del tipo di modello, il punteggio può essere un valore non elaborato, una probabilità o una categoria.

## <a name="supervised-machine-learning"></a>Apprendimento automatico con supervisione

Una sottoclasse di apprendimento automatico in cui un modello desiderato stima l'etichetta per dati non ancora visibili. Alcuni esempi sono la classificazione, la regressione e la stima strutturata. Per altre informazioni, vedere l'articolo relativo all'[apprendimento con supervisione](https://en.wikipedia.org/wiki/Supervised_learning) su Wikipedia.

## <a name="training"></a>Formazione

Il processo di identificazione di un [modello](#model) per un determinato training set. Per un modello lineare, rappresenta l'individuazione dei pesi. Per un albero, implica l'identificazione dei punti di divisione.

## <a name="transformer"></a>Trasformatore

Classe ML.NET che implementa l'interfaccia <xref:Microsoft.ML.ITransformer>.

Un trasformatore consente di trasformare un oggetto <xref:Microsoft.ML.IDataView> in un altro. Viene creato eseguendo il training di uno [strumento di stima](#estimator) o di una pipeline di strumenti di stima.

## <a name="unsupervised-machine-learning"></a>Apprendimento automatico senza supervisione

Una sottoclasse dell'apprendimento automatico in cui un modello desiderato individua una struttura nascosta (o latente) nei dati. Alcuni esempi sono il clustering, la modellazione degli argomenti e la riduzione della dimensionalità. Per altre informazioni, vedere l'articolo relativo all'[apprendimento senza supervisione](https://en.wikipedia.org/wiki/Unsupervised_learning) su Wikipedia.
