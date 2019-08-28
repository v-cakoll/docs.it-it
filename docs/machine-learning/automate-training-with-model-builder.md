---
title: Che cos'è il generatore di modelli e come funziona?
description: Come usare il generatore di modelli di ML.NET per eseguire automaticamente il training di un modello di Machine Learning
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: a871c3a3751a93bdf0104c873215b164616f0664
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69611459"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>Che cos'è il generatore di modelli e come funziona?

Il generatore di modelli di ML.NET è un'estensione grafica intuitiva di Visual Studio che consente di compilare, eseguire il training e distribuire modelli di Machine Learning personalizzati.

Il generatore di modelli usa il Machine Learning automatico (AutoML) per esplorare diversi algoritmi di Machine Learning e impostazioni per individuare quelli più adatti allo scenario.

Non è necessario avere competenze di Machine Learning per usare il generatore di modelli. Servono solo alcuni dati e un problema da risolvere. Il generatore di modelli genera il codice per aggiungere il modello all'applicazione .NET.

![Animazione dell'interfaccia utente dell'estensione del generatore di modelli di Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="scenarios"></a>Scenari

È possibile trasferire molti scenari diversi nel generatore di modelli per generare un modello di Machine Learning per l'applicazione.

Uno scenario è una descrizione del tipo di previsione che si vuole eseguire usando i dati. Ad esempio:
- prevedere il volume di vendita futuro dei prodotti in base ai dati storici di vendita
- classificare le valutazioni come positive o negative in base alle recensioni dei clienti
- rilevare se una transazione bancaria è fraudolenta
- indirizzare i problemi dei feedback dei clienti al team corretto nell'azienda

## <a name="choose-a-model-type"></a>Scegliere un tipo di modello

Nel generatore di modelli è necessario selezionare un tipo di modello di Machine Learning. Il tipo di modello dipende dal tipo di stima che si sta tentando di eseguire.

Per gli scenari in cui viene stimato un numero, il tipo di modello di Machine Learning è chiamato `regression`.

Per gli scenari di stima di una categoria, il tipo di modello è `classification`. Sono disponibili due tipi di classificazione:
- dove sono disponibili solo 2 categorie: `binary classification`.
- dove sono disponibili tre o più categorie: `multiclass classification`.

### <a name="which-model-type-is-right-for-me"></a>Quale tipo di modello scegliere?

#### <a name="predict-a-category-when-there-are-only-two-categories"></a>Stimare una categoria (quando esistono solo due categorie)

La classificazione binaria viene usata per classificare i dati in due categorie (sì/no; superato/non superato; vero/falso; positivo/negativo).

![Diagramma che mostra esempi di classificazione binaria, tra cui il rilevamento delle frodi, la mitigazione dei rischi e lo screening delle applicazioni](media/binary-classification-examples.png)

L'analisi del sentiment può essere usata per prevedere il sentiment positivo o negativo del feedback dei clienti. È un esempio del tipo di modello di classificazione binaria.

Se lo scenario richiede la classificazione in due categorie, è possibile usare questo modello con il proprio set di dati.

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a>Stimare una categoria (quando sono presenti tre o più categorie)

La classificazione multiclasse può essere usata per classificare i dati in tre o più classi. 

![Esempi di classificazione multiclasse, tra cui la classificazione di documenti e prodotti, il routing dei ticket di supporto e l'assegnazione di priorità ai problemi dei clienti](media/multiclass-classification-examples.png)

La classificazione dei problemi può essere usata per classificare i problemi dei feedback dei clienti, ad esempio in GitHub, usando il titolo del problema e la descrizione. È un esempio del tipo di modello di classificazione multiclasse.

Se si vuole classificare i dati in tre o più categorie, è possibile usare il modello di classificazione dei problemi per il proprio scenario.

#### <a name="predict-a-number"></a>Stimare un numero

La regressione viene usata per prevedere i numeri.

![Diagramma che mostra esempi di regressione, ad esempio stime del prezzo, previsioni di vendita e manutenzione predittiva](media/regression-examples.png)

La stima dei prezzi può essere usata per stimare i prezzi delle case in base alla posizione, alla dimensione e ad altre caratteristiche della casa. È un esempio del tipo di modello di regressione.

Se si vuole prevedere un valore numerico con il proprio set di dati, è possibile usare il modello di stima dei prezzi per il proprio scenario.

#### <a name="custom-scenario-choose-your-model-type"></a>Scenario personalizzato (scegliere il tipo di modello)

Lo scenario personalizzato consente di scegliere manualmente il tipo di modello.

## <a name="data"></a>Dati

Dopo aver scelto il tipo di modello, il generatore di modelli richiede di specificare un set di dati. I dati vengono usati per il training, la valutazione e la scelta del modello più adatto per lo scenario.

![Diagramma che illustra i passaggi del generatore di modelli](media/model-builder-steps.png)

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

|Scenario|Tipo di modello|Dati|Label|Funzionalità|
|-|-|-|-|-|
|Stima dei prezzi|Regressione|[dati delle tariffe dei taxi](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Tariffe|Tempo della corsa, distanza|
|Rilevamento di anomalie|Classificazione binaria|[dati di vendita dei prodotti](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Vendita dei prodotti|Mese|
|Analisi del sentiment|Classificazione binaria|[dati dei commenti del sito Web](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|Etichetta (0 con sentiment negativo, 1 con sentiment positivo)|Commento, anno|
|Rilevamento delle frodi|Classificazione binaria|[dati della carta di credito](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Classe (1 quando fraudolento, 0 in caso contrario)|Quantità, V1-V28 (caratteristiche anonime)|
|Classificazione testo|Classificazione multiclasse|[dati del problema di GitHub](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Area|Titolo, descrizione|

## <a name="train"></a>Eseguire il training

Dopo aver selezionato lo scenario, i dati e l'etichetta, il generatore di modelli esegue il training del modello.

### <a name="what-is-training"></a>Cos'è il training?

Il training è un processo automatico tramite il quale il generatore di modelli indica al modello come rispondere alle domande per lo scenario. Dopo aver eseguito il training, il modello può effettuare previsioni con dati di input completamente nuovi. Ad esempio, se si sta eseguendo la stima dei prezzi e viene immessa sul mercato una nuova casa, è possibile prevederne il prezzo di vendita.

Poiché il generatore di modelli usa Il Machine Learning automatico (AutoML), non viene richiesto alcun input o ottimizzazione durante il training.

## <a name="evaluate"></a>Valutare

La valutazione è il processo di utilizzo del modello con training per effettuare previsioni con nuovi dati di test e quindi misurare la qualità delle previsioni.

Il generatore di modelli suddivide i dati di training in un set di training e un set di test. I dati di training (80%) vengono usati per eseguire il training del modello, mentre i dati di test (20%) vengono usati per la valutazione del modello. Il generatore di modelli usa le metriche per misurare la qualità del modello. Le metriche specifiche usate dipendono dal tipo di modello. Per altre informazioni, vedere [Metriche di valutazione dei modelli](resources/metrics.md).

## <a name="improve"></a>Migliorare

Se il punteggio delle prestazioni del modello non è quello desiderato, è possibile:

* Eseguire il training per un periodo di tempo più lungo. Con un periodo di tempo più lungo, il motore di Machine Learning automatico proverà più algoritmi e impostazioni.

* Aggiungere altri dati. A volte la quantità di dati non è sufficiente per eseguire il training di un modello di Machine Learning di qualità elevata.

* Bilanciare i dati. Per le attività di classificazione, assicurarsi che il set di training sia bilanciato tra le categorie. Ad esempio, se sono presenti quattro classi per 100 esempi di training e le prime due classi (tag1 e tag2) vengono usate per 90 record mentre le altre due classi (tag3 e tag4) vengono usate solo per i rimanenti 10 record, la mancanza di dati bilanciati può rendere più difficile per il modello prevedere correttamente tag3 o tag4.

## <a name="code"></a>Codice

Dopo la fase di valutazione, il generatore di modelli restituisce un file di modello e il codice che è possibile usare per aggiungere il modello all'applicazione. I modelli di ML.NET vengono salvati come file con estensione zip. Il codice per caricare e usare il modello viene aggiunto come nuovo progetto nella soluzione. Il generatore di modelli aggiunge anche un'app console di esempio che è possibile eseguire per visualizzare il modello in azione.

Il generatore di modelli restituisce anche il codice che ha generato il modello che consente di comprendere i passaggi eseguiti per generare il modello. È anche possibile usare il codice di training del modello per ripetere il training del modello con nuovi dati.

## <a name="whats-next"></a>Argomenti successivi

[Installare](how-to-guides/install-model-builder.md) l'estensione di Visual Studio per il generatore di modelli

Provare [uno scenario di regressione o stima dei prezzi](tutorials/predict-prices-with-model-builder.md)
