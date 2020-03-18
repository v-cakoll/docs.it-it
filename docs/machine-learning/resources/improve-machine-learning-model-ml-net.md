---
title: 'Procedura: Migliorare la precisione del modello'
description: Informazioni su come migliorare l'accuratezza del modello
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc
ms.openlocfilehash: 8f3b283de378a37bfe429688207ea9fb52f9ca7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75739578"
---
# <a name="improve-mlnet-model-accuracy"></a>Migliorare l'accuratezza del modello ML.NET

Di seguito viene descritto come migliorare l'accuratezza del modello.

## <a name="reframe-the-problem"></a>Riformulare il problema

In alcuni casi il miglioramento di un modello potrebbe non essere correlato ai dati o alle tecniche usate per il training del modello. È possibile invece che semplicemente sia stata posta la domanda errata. Può essere utile esaminare il problema da diverse angolazioni e usare i dati per estrarre indicatori latenti e relazioni nascoste per perfezionare la domanda.

## <a name="provide-more-data-samples"></a>Fornire più esempi di dati

Come avviene per gli esseri umani, se gli algoritmi ricevono più training, aumenta la probabilità di ottenere prestazioni migliori. Un modo per migliorare le prestazioni del modello consiste nel fornire più esempi di dati di training agli algoritmi. Maggiore è la quantità di dati su cui si basa l'apprendimento dell'algoritmo, maggiore sarà il numero di casi identificati correttamente dall'algoritmo.

## <a name="add-context-to-the-data"></a>Aggiungere contesto ai dati

È possibile che il significato di un singolo punto dati sia difficile da interpretare. La creazione di un contesto per i punti dati consente agli algoritmi e agli esperti in materia di migliorare di prendere le decisioni in modo migliore. Ad esempio, il fatto che un'abitazione abbia tre camere da letto non dà di per se stesso un'indicazione valida sul prezzo. Tuttavia, se si aggiunge un contesto e quindi l'informazione che l'abitazione si trova in una zona periferica al di fuori della principale area metropolitana in cui l'età media è di 38 anni, il reddito medio delle famiglie è di 80.000 $ e le scuole rientrano nel primo 20° percentile, l'algoritmo avrà maggiori informazioni su cui basare le decisioni. Il contesto può essere aggiunto come input del modello di Machine Learning sotto forma di caratteristiche.

## <a name="use-meaningful-data-and-features"></a>Usare caratteristiche e dati significativi

Sebbene una maggior quantità di caratteristiche e dati di esempio possano migliorare l'accuratezza del modello, è possibile che venga aumentato il rumore poiché non tutte le caratteristiche e i dati sono significativi. Per questa ragione, è importante comprendere quali caratteristiche hanno un maggior impatto sulle decisioni prese dall'algoritmo. L'uso di tecniche come Permutation Feature Importance (PFI) consente di identificare le caratteristiche salienti e oltre a descrivere il modello anche a usare l'output come metodo di selezione delle caratteristiche per ridurre la quantità di caratteristiche rumorose nel processo di training.

Per ulteriori informazioni sull'utilizzo di PFI, vedere [Spiegare le stime dei modelli utilizzando permutazione l'importanza della funzionalità](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md).

## <a name="cross-validation"></a>Convalida incrociata

La convalida incrociata è una tecnica di training e valutazione del modello che suddivide i dati in più partizioni ed esegue il training di più algoritmi nelle partizioni. Questa tecnica consente di migliorare l'affidabilità del modello offrendo dati provenienti dal processo di training. Oltre a migliorare le prestazioni sulle osservazioni non visibili, in ambienti con limiti di dati può rappresentare uno strumento efficace per il training di modelli con set di dati di dimensioni minori.

Visitare il link seguente per informazioni su [come usare la convalida incrociata in ML.NET](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md)

## <a name="hyperparameter-tuning"></a>Ottimizzazione degli iperparametri

Il training dei modelli di Machine Learning è un processo iterativo ed esplorativo. Ad esempio, qual è il numero ottimale di cluster per il training di un modello tramite l'algoritmo K-means? La risposta dipende da molti fattori, ad esempio dalla struttura dei dati. La ricerca del numero ottimale richiederebbe una sperimentazione con valori diversi per k e quindi la valutazione delle prestazioni per determinare qual è il valore migliore. La regolazione di questi parametri per l'individuazione del modello ottimale è chiamata ottimizzazione degli iperparametri.

## <a name="choose-a-different-algorithm"></a>Scegliere un algoritmo diverso

Le attività di Machine Learning come la regressione e la classificazione contengono diverse implementazioni di algoritmi. È possibile che il problema che si sta tentando di risolvere e il modo in cui sono strutturati i dati non siano particolarmente adatti all'algoritmo corrente. In questo caso può essere utile usare un algoritmo diverso per l'attività per verificare se è possibile migliorare l'apprendimento dai dati.

Visitare il link seguente per altre [informazioni sulla scelta dell'algoritmo](../how-to-choose-an-ml-net-algorithm.md).
