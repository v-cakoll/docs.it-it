---
title: Che cos'è il generatore di modelli e come funziona?
description: Come usare il generatore di modelli di ML.NET per eseguire automaticamente il training di un modello di Machine Learning
ms.date: 06/01/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 2ed4a0c3c94ae9f46bb1cf6ddb1e9774baf82367
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289499"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>Che cos'è il generatore di modelli e come funziona?

Il generatore di modelli di ML.NET è un'estensione grafica intuitiva di Visual Studio che consente di compilare, eseguire il training e distribuire modelli di Machine Learning personalizzati.

Il generatore di modelli usa il Machine Learning automatico (AutoML) per esplorare diversi algoritmi di Machine Learning e impostazioni per individuare quelli più adatti allo scenario.

Non è necessario avere competenze di Machine Learning per usare il generatore di modelli. Servono solo alcuni dati e un problema da risolvere. Il generatore di modelli genera il codice per aggiungere il modello all'applicazione .NET.

![Animazione dell'interfaccia utente dell'estensione del generatore di modelli di Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="scenario"></a>Scenario

È possibile trasferire molti scenari diversi nel generatore di modelli per generare un modello di Machine Learning per l'applicazione.

Uno scenario è una descrizione del tipo di previsione che si vuole eseguire usando i dati. Ad esempio:

- prevedere il volume di vendita futuro dei prodotti in base ai dati storici di vendita
- classificare le valutazioni come positive o negative in base alle recensioni dei clienti
- rilevare se una transazione bancaria è fraudolenta
- indirizzare i problemi dei feedback dei clienti al team corretto nell'azienda

### <a name="which-machine-learning-scenario-is-right-for-me"></a>Quale scenario di Machine Learning è adatto alle mie esigenze?

In Generatore di modelli è necessario selezionare uno scenario. Il tipo di scenario dipende dal tipo di stima che si sta tentando di eseguire.

#### <a name="text-classification"></a>Classificazione del testo

La classificazione viene utilizzata per categorizzare i dati in categorie.

![Diagramma che mostra esempi di classificazione binaria, tra cui il rilevamento delle frodi, la mitigazione dei rischi e lo screening delle applicazioni](media/binary-classification-examples.png)

![Esempi di classificazione multiclasse, tra cui la classificazione di documenti e prodotti, il routing dei ticket di supporto e l'assegnazione di priorità ai problemi dei clienti](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a>Stima del valore

La regressione viene usata per prevedere i numeri.

![Diagramma che mostra esempi di regressione, ad esempio stime del prezzo, previsioni di vendita e manutenzione predittiva](media/regression-examples.png)

#### <a name="image-classification"></a>Classificazione di immagini

È possibile usare la classificazione delle immagini per identificare immagini di diverse categorie. Ad esempio, diversi tipi di terreno o animali o difetti di produzione.

È possibile utilizzare lo scenario di classificazione delle immagini se si dispone di un set di immagini e si desidera classificare le immagini in categorie diverse.

#### <a name="recommendation"></a>Recommendation

Lo scenario di raccomandazione prevede un elenco di elementi consigliati per un determinato utente, in base alla somiglianza e alle dispiacenze di altri utenti.

È possibile utilizzare lo scenario di raccomandazione quando si dispone di un set di utenti e un set di "prodotti", ad esempio articoli da acquistare, filmati, libri o programmi TELEVISIVi, insieme a un set di "classificazioni" degli utenti di questi prodotti.

## <a name="environment"></a>Environment

È possibile eseguire il training del modello di Machine Learning localmente nel computer o nel cloud in Azure.

Quando si esegue il training in locale, si lavora nei vincoli delle risorse del computer (CPU, memoria e disco). Quando si esegue il training nel cloud, è possibile ridimensionare le risorse per soddisfare le esigenze dello scenario, soprattutto per i set di impostazioni di grandi dimensioni.

Il training locale è supportato per tutti gli scenari.

La formazione di Azure è supportata per la classificazione delle immagini.

## <a name="data"></a>Data

Una volta scelto lo scenario, generatore di modelli richiede di fornire un set di dati. I dati vengono usati per il training, la valutazione e la scelta del modello più adatto per lo scenario.

![Diagramma che illustra i passaggi del generatore di modelli](media/model-builder-steps.png)

Il generatore di modelli supporta i set di dati nei formati TSV, CSV, txt, oltre al formato del database SQL. Se si dispone di un file con estensione txt, le colonne devono essere separate da `,` `;` o `/t` e il file deve contenere una riga di intestazione.

Se il set di dati è costituito da immagini, i tipi di file supportati sono `.jpg` e `.png` .

Per altre informazioni, vedere [caricare i dati di training in Generatore di modelli](how-to-guides/load-data-model-builder.md).

### <a name="choose-the-output-to-predict-label"></a>Scegliere l'output da prevedere (etichetta)

Un set di dati è una tabella di righe di esempi di training e di colonne di attributi. Ogni riga include:

- un'**etichetta** (l'attributo da prevedere)
- le **caratteristiche** (gli attributi usati come input per la previsione dell'etichetta).

Per lo scenario di stima del prezzo della casa, è possibile usare le caratteristiche seguenti:

- i metri quadrati della casa
- il numero di camere da letto e bagni
- il codice postale

L'etichetta è il prezzo storico della casa per la riga dei valori dei metri quadrati, delle camere da letto e dei bagni e il codice postale.

![Tabella che mostra le righe e le colonne di dati sui prezzi delle case con le caratteristiche delle dimensioni dei locali, del codice postale e dell'etichetta del prezzo](media/model-builder-data.png)

### <a name="example-datasets"></a>Set di dati di esempio

Se non sono ancora disponibili dati, provare uno dei set di dati seguenti:

|Scenario|Esempio|Data|Label|Funzionalità|
|-|-|-|-|-|
|Classificazione|Stimare le anomalie di vendita|[dati di vendita dei prodotti](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Vendita dei prodotti|Month|
||Stimare i sentimenti dei commenti del sito Web|[dati dei commenti del sito Web](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|Etichetta (0 con sentiment negativo, 1 con sentiment positivo)|Commento, anno|
||Stimare le transazioni della carta di credito fraudolente|[dati della carta di credito](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Classe (1 quando fraudolento, 0 in caso contrario)|Quantità, V1-V28 (caratteristiche anonime)|
||Prevedere il tipo di problema in un repository GitHub|[dati del problema di GitHub](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Area|Titolo, descrizione|
|Stima del valore|Stimare il prezzo della tariffa di taxi|[dati delle tariffe dei taxi](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Tariffe|Tempo della corsa, distanza|
|Classificazione di immagini|Stimare la categoria di un fiore |[immagini floreali](http://download.tensorflow.org/example_images/flower_photos.tgz)|Tipo di fiore: Daisy, Dandelion, Roses, girasoli, tulipani|Dati dell'immagine|
|Recommendation|Prevedere i film che un utente vuole|[classificazioni film](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|Utenti, filmati|Classificazioni|

## <a name="train"></a>Eseguire il training

Dopo aver selezionato lo scenario, l'ambiente, i dati e l'etichetta, generatore di modelli esegue il training del modello.

### <a name="what-is-training"></a>Cos'è il training?

Il training è un processo automatico tramite il quale il generatore di modelli indica al modello come rispondere alle domande per lo scenario. Dopo aver eseguito il training, il modello può effettuare previsioni con dati di input completamente nuovi. Ad esempio, se si sta eseguendo la stima dei prezzi e viene immessa sul mercato una nuova casa, è possibile prevederne il prezzo di vendita.

Poiché il generatore di modelli usa Il Machine Learning automatico (AutoML), non viene richiesto alcun input o ottimizzazione durante il training.

### <a name="how-long-should-i-train-for"></a>Per quanto tempo è consigliabile eseguire il training?

Il generatore di modelli USA AutoML per esplorare più modelli per trovare il modello con le prestazioni migliori.

I periodi di training più lunghi consentono a AutoML di esplorare più modelli con una gamma più ampia di impostazioni.

La tabella seguente riepiloga il tempo medio necessario per ottenere prestazioni ottimali per una suite di set di impostazioni di esempio, in un computer locale.

|Dimensioni del set di dati|Tempo medio per il training|
|------------|---------------------|
|0-10 MB|10 sec|
|10-100 MB|10 min|
|100-500 MB|30 min|
|500-1 GB|60 min|
|1 GB +|3 + ore|

Questi numeri sono solo una guida. La lunghezza esatta del training dipende da:

- il numero di funzioni (colonne) utilizzate come input per il modello
- tipo di colonne
- attività ML
- le prestazioni della CPU, del disco e della memoria del computer utilizzato per il training

Si consiglia in genere di usare più di 100 righe come set di dati con un valore minore di quello che potrebbe non produrre alcun risultato e potrebbe richiedere un tempo molto più lungo per il training.

## <a name="evaluate"></a>Valutazione

La valutazione è il processo di misurazione della qualità del modello. Il generatore di modelli utilizza il modello sottoposto a training per eseguire stime con nuovi dati di test e quindi misura la qualità delle stime.

Il generatore di modelli suddivide i dati di training in un set di training e un set di test. I dati di training (80%) vengono usati per eseguire il training del modello, mentre i dati di test (20%) vengono usati per la valutazione del modello.

### <a name="how-do-i-understand-my-model-performance"></a>Ricerca per categorie comprendere le prestazioni del modello?

Uno scenario è mappato a un'attività di machine learning. Ogni attività ML dispone di un proprio set di metriche di valutazione.

#### <a name="value-prediction"></a>Stima del valore

La metrica predefinita per i problemi di stima del valore è RSquared, il valore di RSquared è compreso tra 0 e 1. 1 è il miglior valore possibile o, in altre parole, più il valore di RSquared è più vicino a 1 migliore sarà l'esecuzione del modello.

Altre metriche segnalate come la perdita assoluta, la perdita quadrata e la perdita di RMS sono metriche aggiuntive, che possono essere usate per comprendere il modo in cui il modello esegue e il confronto con altri modelli di stima del valore.

#### <a name="classification-2-categories"></a>Classificazione (2 categorie)

La metrica predefinita per i problemi di classificazione è l'accuratezza. L'accuratezza definisce la percentuale di stime corrette che il modello sta eseguendo sul set di dati di test. Il più vicino a 100% o 1,0 è migliore.

Altre metriche segnalate, ad esempio AUC (area sotto la curva), che misura il vero tasso positivo rispetto a. il tasso di falsi positivi deve essere maggiore di 0,50 per i modelli in modo che siano accettabili.

Metriche aggiuntive, come il Punteggio F1, possono essere usate per controllare il saldo tra precisione e richiamo.

#### <a name="classification-3-categories"></a>Classificazione (3 + categorie)

La metrica predefinita per la classificazione multiclasse è la precisione Micro. Maggiore è il modo in cui l'accuratezza Micro è più vicina al 100% o 1,0.

Un'altra metrica importante per la classificazione multiclasse è l'accuratezza della macro, analogamente alla micro-precisione, più vicina a 1,0, migliore è. Un modo efficace per considerare questi due tipi di accuratezza è:

- Micro-precisione: con quale frequenza un ticket in arrivo viene Classificato al team appropriato?
- Accuratezza macro: per un team medio, con quale frequenza un ticket in ingresso è corretto per il proprio team?

### <a name="more-information-on-evaluation-metrics"></a>Altre informazioni sulle metriche di valutazione

Per altre informazioni, vedere [Metriche di valutazione dei modelli](resources/metrics.md).

## <a name="improve"></a>Migliorare

Se il punteggio delle prestazioni del modello non è quello desiderato, è possibile:

- Eseguire il training per un periodo di tempo più lungo. Con più tempo, il motore di Machine Learning automatico sperimenta più algoritmi e impostazioni.

- Aggiungere altri dati. A volte la quantità di dati non è sufficiente per eseguire il training di un modello di apprendimento automatico di alta qualità. Ciò vale soprattutto per i set di impostazioni con un numero ridotto di esempi.

- Bilanciare i dati. Per le attività di classificazione, assicurarsi che il set di training sia bilanciato tra le categorie. Ad esempio, se sono presenti quattro classi per 100 esempi di training e le prime due classi (tag1 e tag2) vengono usate per 90 record mentre le altre due classi (tag3 e tag4) vengono usate solo per i rimanenti 10 record, la mancanza di dati bilanciati può rendere più difficile per il modello prevedere correttamente tag3 o tag4.

## <a name="code"></a>Codice

Dopo la fase di valutazione, il generatore di modelli restituisce un file di modello e il codice che è possibile usare per aggiungere il modello all'applicazione. I modelli di ML.NET vengono salvati come file con estensione zip. Il codice per caricare e usare il modello viene aggiunto come nuovo progetto nella soluzione. Il generatore di modelli aggiunge anche un'app console di esempio che è possibile eseguire per visualizzare il modello in azione.

Il generatore di modelli restituisce anche il codice che ha generato il modello che consente di comprendere i passaggi eseguiti per generare il modello. È anche possibile usare il codice di training del modello per ripetere il training del modello con nuovi dati.

## <a name="whats-next"></a>Quali sono le operazioni successive?

[Installare](how-to-guides/install-model-builder.md) l'estensione di Visual Studio per il generatore di modelli

Provare [uno scenario di regressione o stima dei prezzi](tutorials/predict-prices-with-model-builder.md)
