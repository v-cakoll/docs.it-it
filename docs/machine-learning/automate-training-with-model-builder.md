---
title: Che cos'è il generatore di modelli e come funziona?
description: Come usare il generatore di modelli di ML.NET per eseguire automaticamente il training di un modello di Machine Learning
author: natke
ms.date: 06/26/2019
ms.custom: overview
ms.openlocfilehash: 6f5bbe3c389e3ca42550a48ef3e6edbc963ac2e9
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410589"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>Che cos'è il generatore di modelli e come funziona?

Il generatore di modelli di ML.NET è una semplice estensione grafica di Visual Studio che consente di compilare, eseguire il training e distribuire modelli di Machine Learning personalizzati. 

Il generatore di modelli usa il Machine Learning automatico (AutoML) per esplorare diversi algoritmi di Machine Learning e impostazioni per individuare quelli più adatti allo scenario.

Non è necessario avere competenze di Machine Learning per usare il generatore di modelli. Servono solo alcuni dati e un problema da risolvere. Il generatore di modelli genera il codice per aggiungere il modello all'applicazione .NET.

![Animazione dell'interfaccia utente dell'estensione del generatore di modelli di Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="scenarios"></a>Scenari

È possibile trasferire molti scenari diversi nel generatore di modelli per generare un modello di Machine Learning per l'applicazione.

Uno scenario è una descrizione del tipo di previsione che si vuole eseguire sui dati. Ad esempio:
- prevedere il volume di vendita futuro dei prodotti in base ai dati storici di vendita
- classificare le valutazioni come positive o negative in base alle recensioni dei clienti
- rilevare se una transazione bancaria è fraudolenta
- indirizzare i problemi dei feedback dei clienti al team corretto nell'azienda

Nel generatore di modelli è necessario eseguire il mapping dello scenario in un'[attività di ML.NET](resources/tasks.md). È possibile usare il generatore di modelli per la **regressione** (previsione dei numeri) e la **classificazione** (previsione delle categorie).

### <a name="which-machine-learning-scenario-is-right-for-me"></a>Quale scenario di Machine Learning è adatto alle mie esigenze?

Il generatore di modelli include modelli per l'analisi del sentiment, la classificazione dei problemi, la stima dei prezzi e scenari personalizzati. Questi modelli possono essere usati come punto di partenza per lo scenario di ML.NET specifico.

#### <a name="sentiment-analysis-binary-classification"></a>Analisi del sentiment (classificazione binaria)

L'analisi del sentiment può essere usata per prevedere il sentiment positivo o negativo del feedback dei clienti. È un esempio dell'attività di classificazione binaria.

La classificazione binaria viene usata per classificare i dati in due classi (sì/no; superato/non superato; vero/falso positivo/negativo). Può essere usata per rispondere alle domande seguenti:

- Questo messaggio è posta indesiderata? (rilevamento di posta indesiderata)
- Quali richiedenti possono diventare membri? (screening dell'applicazione)
- Quali account potrebbero non pagare le fatture puntualmente? (mitigazione dei rischi)
- Questa transazione con carta di credito è fraudolenta? (rilevamento delle frodi)

Se lo scenario richiede la classificazione in due categorie, è possibile usare questo modello con il proprio set di dati.
 
#### <a name="issue-classification-multiclass-classification"></a>Classificazione dei problemi (classificazione multiclasse)

La classificazione dei problemi può essere usata per classificare i problemi dei feedback dei clienti, ad esempio in GitHub, usando il titolo del problema e la descrizione. È un esempio dell'attività di classificazione multiclasse.

La classificazione multiclasse può essere usata per classificare i dati in tre o più classi. Può essere usata per rispondere alle domande seguenti:

- A quale reparto deve essere indirizzato un ticket di supporto? (indirizzamento dei ticket di supporto)
- Qual è la priorità di un problema del cliente? (assegnazione della priorità ai problemi dei clienti)
- A quale categoria appartiene un prodotto? (classificazione dei prodotti)
- Di quale tipo di documento si tratta? (classificazione documento/messaggio di posta elettronica)

Se si vuole classificare i dati in tre o più categorie, è possibile usare il modello di classificazione dei problemi per il proprio scenario.

#### <a name="price-prediction-regression"></a>Stima dei prezzi (regressione)

La stima dei prezzi può essere usata per stimare i prezzi delle case in base alla posizione, alla dimensione e ad altre caratteristiche della casa. È un esempio dell'attività di regressione.

La regressione viene usata per prevedere i numeri. Può essere usata per rispondere alle domande seguenti:

- A quale prezzo verrà venduta una casa? (stima dei prezzi)
- Dopo quanto tempo un componente meccanico richiede manutenzione? (manutenzione predittiva)
- Quant'è l'umidità in questa asciugatrice? (monitoraggio delle macchine)
- Qual sarà il totale vendite annuali per quest'area? (previsione delle vendite)

Se si vuole prevedere un valore numerico con il proprio set di dati, è possibile usare il modello di stima dei prezzi per il proprio scenario.

#### <a name="custom-scenario-choose-your-task"></a>Scenario personalizzato (scegliere l'attività)

Lo scenario personalizzato consente di scegliere l'attività. Scegliere lo scenario più appropriato per il problema.

Lo scenario personalizzato consente di scegliere l'attività di Machine Learning. Nei modelli precedenti l'attività di Machine Learning dello scenario era fissa: classificazione binaria, classificazione multiclasse o regressione. In questo modello è possibile scegliere l'attività di Machine Learning da usare per i dati.

## <a name="data"></a>Dati

Dopo aver eseguito il mapping dello scenario in un'attività, il generatore di modelli richiede di specificare un set di dati. I dati vengono usati per il training, la valutazione e la scelta del modello più adatto per lo scenario. È anche necessario scegliere l'output da prevedere.

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

### <a name="data-formats"></a>Formati dei dati

Il generatore di modelli impone le limitazioni seguenti sui dati:

- I dati devono essere archiviati in un file (con estensione csv o tsv con una riga di intestazione) o in un database SQL Server.
- Un limite di 1 GB per il set di dati di training
- SQL Server ha un limite di 100.000 righe per il training
- I dati di SQL Server vengono copiati dal server nel computer locale prima del training

### <a name="example-datasets"></a>Set di dati di esempio

Se non sono ancora disponibili dati, provare uno dei set di dati seguenti:

|Scenario|Attività di Machine Learning|Dati|Label|Funzionalità|
|-|-|-|-|-|
|Stima dei prezzi|Regressione|[dati delle tariffe dei taxi](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Tariffe|Tempo della corsa, distanza|
|Rilevamento di anomalie|Classificazione binaria|[dati di vendita dei prodotti](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Vendita dei prodotti|Mese|
|Analisi del sentiment|Classificazione binaria|[dati dei commenti del sito Web](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_SentimentAnalysis/SentimentAnalysis/Data/wikiDetoxAnnotated40kRows.tsv)|Etichetta (0 con sentiment negativo, 1 con sentiment positivo)|Commento, anno|
|Rilevamento delle frodi|Classificazione binaria|[dati della carta di credito](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Classe (1 quando fraudolento, 0 in caso contrario)|Quantità, V1-V28 (caratteristiche anonime)|
|Classificazione testo|Classificazione multiclasse|[dati del problema di GitHub](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Area|Titolo, descrizione|

## <a name="train"></a>Eseguire il training

Dopo aver selezionato lo scenario, i dati e l'etichetta, il generatore di modelli esegue il training del modello.

### <a name="what-is-training"></a>Cos'è il training?

Il training è un processo automatico tramite il quale il generatore di modelli indica al modello come rispondere alle domande per lo scenario. Dopo aver eseguito il training, il modello può effettuare previsioni con dati di input completamente nuovi. Ad esempio, se si sta eseguendo la stima dei prezzi e viene immessa sul mercato una nuova casa, è possibile prevederne il prezzo di vendita.

Poiché il generatore di modelli usa Il Machine Learning automatico (AutoML), non viene richiesto alcun input o ottimizzazione durante il training.

### <a name="how-long-should-i-train-for"></a>Per quanto tempo è consigliabile eseguire il training?

È possibile specificare la durata del training. In generale, un training più lungo produce un modello più accurato. Inoltre, la durata del training aumenta con l'incremento delle dimensioni del set di dati. La tabella seguente offre alcune linee guida sulla durata del training per i set di dati con dimensioni in aumento.

Dimensioni del set di dati  | Tipo di set di dati       | Avg. Durata del training
------------- | ------------------ | --------------
0 - 10 MB     | Numerico e testo   | 10 sec
10 - 100 MB   | Numerico e testo   | 10 min 
100 - 500 MB  | Numerico e testo   | 30 min 
500 - 1 GB    | Numerico e testo   | 60 min 
1 GB+         | Numerico e testo   | 3 ore+ 

La durata esatta del training dipende anche dagli elementi seguenti:

- tipo di colonne, ovvero testo o numerico
- tipo di attività di Machine Learning (regressione o classificazione)
- numero di righe usate per il training
- numero di colonne delle caratteristiche usate per il training

Sebbene il generatore di modelli sia stato testato per la scalabilità con un set di dati di 1 TB, la compilazione di un modello di alta qualità per un set di dati di queste dimensioni può richiedere fino a quattro giorni.

## <a name="evaluate"></a>Valutare

La valutazione è il processo di utilizzo del modello con training per effettuare previsioni con nuovi dati di test e quindi misurare la qualità delle previsioni.

Il generatore di modelli suddivide i dati di training in un set di training e un set di test. I dati di training (80%) vengono usati per eseguire il training del modello, mentre i dati di test (20%) vengono usati per la valutazione del modello.  Le metriche usate per la valutazione variano a seconda dell'attività di Machine Learning. Per altre informazioni, vedere [Metriche di valutazione dei modelli](resources/metrics.md).  

### <a name="sentiment-analysis-binary-classification"></a>Analisi del sentiment (classificazione binaria)

La metrica predefinita per i problemi di classificazione binaria è l'**accuratezza**. L'accuratezza definisce la percentuale di previsioni corrette eseguite dal modello sul set di dati di test. L'**accuratezza migliore è quella più vicina al 100%** .

Le altre metriche indicate come AUC (Area Under the Curve), che misurano il tasso di veri positivi rispetto al tasso di falsi positivi, devono essere maggiori di 0,50 nei modelli accettabili. 

Le metriche aggiuntive, ad esempio il punteggio F1, possono essere usate per controllare il bilanciamento tra precisione (percentuale di previsioni corrette sul totale delle previsioni della classe) e richiamo (percentuale di previsioni corrette sul totale dei membri effettivi della classe).

### <a name="issue-classification-multiclass-classification"></a>Classificazione dei problemi (classificazione multiclasse)

La metrica predefinita per i problemi di classificazione binaria è l'**accuratezza micrometrica**. L'**accuratezza migliore è quella più vicina al 100%** .

Per i problemi in cui i dati sono suddivisi in più classi sono disponibili due tipi di accuratezza:

- Accuratezza micrometrica: la frazione di previsioni corrette in tutte le istanze. Nello scenario di classificazione dei problemi l'accuratezza micrometrica è la percentuale di problemi in ingresso che vengono assegnati alla categoria corretta. 
- Accuratezza macrometrica: l'accuratezza media a livello di classe. Nello scenario di classificazione dei problemi viene misurata l'accuratezza di ogni categoria e viene quindi calcolata la media dell'accuratezza delle categorie. Per questa metrica viene assegnato lo stesso peso a tutte le classi. Nei set di dati perfettamente bilanciati (con lo stesso numero di esempi di ogni categoria) l'accuratezza micrometrica e l'accuratezza macrometrica corrispondono.


### <a name="price-prediction-regression"></a>Stima dei prezzi (regressione)

La metrica predefinita per i problemi di regressione è **R al quadrato**. 1 è il valore migliore possibile. Il modello migliore è quello con R al quadrato più vicino a 1.

Le altre metriche indicate, ad esempio la perdita di valore assoluto, la perdita di R al quadrato e la perdita di RMS, possono essere usate per comprendere il modello e confrontarlo con altri modelli di regressione. 

## <a name="improve"></a>Migliorare

Se il punteggio delle prestazioni del modello non è quello desiderato, è possibile:

* Eseguire il training per un periodo di tempo più lungo. Con un periodo di tempo più lungo, il motore di Machine Learning automatico proverà più algoritmi e impostazioni.

* Aggiungere altri dati. A volte la quantità di dati non è sufficiente per eseguire il training di un modello di Machine Learning di qualità elevata. 

* Bilanciare i dati. Per le attività di classificazione, assicurarsi che il set di training sia bilanciato tra le categorie. Ad esempio, se sono presenti quattro classi per 100 esempi di training e le prime due classi (tag1 e tag2) vengono usate per 90 record mentre le altre due classi (tag3 e tag4) vengono usate solo per i rimanenti 10 record, la mancanza di dati bilanciati può rendere più difficile per il modello prevedere correttamente tag3 o tag4.

## <a name="code"></a>Codice

Dopo la fase di valutazione, il generatore di modelli restituisce un file di modello e il codice che è possibile usare per aggiungere il modello all'applicazione. I modelli di ML.NET vengono salvati come file con estensione zip. Il codice per caricare e usare il modello viene aggiunto come nuovo progetto nella soluzione. Il generatore di modelli aggiunge anche un'app console di esempio che è possibile eseguire per visualizzare il modello in azione.

Il generatore di modelli restituisce anche il codice che ha generato il modello che consente di comprendere i passaggi eseguiti per generare il modello. È anche possibile usare il codice di training del modello per ripetere il training del modello con nuovi dati.

## <a name="whats-next"></a>Argomenti successivi

Provare [uno scenario di regressione o stima dei prezzi](tutorials/predict-prices-with-model-builder.md)
