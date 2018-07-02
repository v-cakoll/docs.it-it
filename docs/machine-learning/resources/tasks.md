---
title: Attività di apprendimento automatico
description: Esplorare le diverse attività di apprendimento automatico supportate in ML.NET.
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 875006a9cddb87b5f9436b78773420858fd842dd
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207726"
---
# <a name="machine-learning-tasks"></a>Attività di apprendimento automatico

Quando si compila un modello di apprendimento automatico, è innanzitutto necessario definire quale risultato si vuole ottenere con i dati. È quindi possibile scegliere l'attività di apprendimento automatico più adatta per la specifica situazione. Nell'elenco seguente sono descritte le diverse attività di apprendimento automatico tra cui è possibile scegliere e alcuni casi d'uso comuni. 

> [!NOTE]
> ML.NET è attualmente in anteprima. Non tutte le attività di apprendimento automatico sono attualmente supportate. Per inviare una richiesta per una determinata attività, aprire un problema nel [repository dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

> [!NOTE]
> Attualmente, ML.NET non supporta le attività di apprendimento automatico con immagini. Il supporto verrà aggiunto nelle versioni future. 

## <a name="binary-classification"></a>Classificazione binaria

Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stabilire a quale di due classi (categorie) appartiene un'istanza di dati. L'input di un algoritmo di classificazione è un set di esempi con etichette, in cui ogni etichetta è un numero intero 0 o 1. L'output di un algoritmo di classificazione binaria è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette. Alcuni esempi di scenari di classificazione binaria sono i seguenti:

* [Comprensione del sentiment dei commenti di Twitter](../tutorials/sentiment-analysis.md) come "positivi" o "negativi".
* Diagnosi per stabilire se un paziente ha o meno una determinata malattia.
* Decisione di contrassegnare o meno un messaggio di posta elettronica come "posta indesiderata".

Per altre informazioni, vedere l'articolo relativo alla [classificazione binaria](https://en.wikipedia.org/wiki/Binary_classification) su Wikipedia.

## <a name="multiclass-classification"></a>Classificazione multiclasse

Un'attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare la classe (categoria) di un'istanza di dati. L'input di un algoritmo di classificazione è un set di esempi con etichette. Ogni etichetta è un numero intero compreso tra 0 e k-1, dove k è il numero di classi. L'output di un algoritmo di classificazione è un classificatore, che può essere usato per stimare la classe di nuove istanze senza etichette. Alcuni esempi di scenari di classificazione multiclasse sono i seguenti:

* Determinare la razza di un cane come "siberian husky", "golden retriever", "barboncino" e così via.
* Classificare recensioni di film come "positive", "neutrali" o "negative".
* Classificare recensioni di hotel in base a "posizione", "prezzo", "pulizia" e così via.

Per altre informazioni, vedere l'articolo relativo alla [classificazione multiclasse](https://en.wikipedia.org/wiki/Multiclass_classification) su Wikipedia.

## <a name="regression"></a>Regressione

Un attività di [apprendimento automatico con supervisione](glossary.md#supervised-machine-learning) che viene usata per stimare il valore dell'etichetta da un set di funzionalità correlate. L'etichetta può essere relativa a qualsiasi valore reale e non appartiene a un set finito di valori come nelle attività di classificazione. Gli algoritmi di regressione modellano la dipendenza dell'etichetta in base alle relative funzionalità correlate per determinare come cambierà l'etichetta quando variano i valori delle funzionalità. L'input di un algoritmo di regressione è un set di esempi con etichette di valori noti. L'output di un algoritmo di regressione è una funzione, che è possibile usare per stimare il valore dell'etichetta per qualsiasi nuovo set di funzionalità di input. Alcuni esempi di scenari di regressione sono i seguenti:

* Stima dei prezzi delle case in base alle caratteristiche, come numero di camere da letto, posizione o dimensione.
* Stima dei prezzi futuri delle azioni in base ai dati cronologici e alle tendenze di mercato correnti.
* Stima delle vendite di un prodotto in base ai budget pubblicitari.

> [!NOTE]
> Attualmente è ancora in corso l'introduzione in ML.NET del supporto per le attività di regressione che coinvolgono serie temporali.

## <a name="clustering"></a>Clustering

Un'[attività di apprendimento automatico senza supervisione](glossary.md#unsupervised-machine-learning) che viene usata per raggruppare le istanze dei dati in cluster con caratteristiche simili. Il clustering può anche essere usato per identificare relazioni in un set di dati che potrebbe essere impossibile ricavare logicamente dall'esplorazione o dalla semplice osservazione. Gli input e gli output di un algoritmo di clustering dipendono dalla metodologia scelta. È possibile adottare un approccio basato su distribuzione, centroide, connettività o densità. ML.NET attualmente supporta un approccio basato su centroide che usa il clustering K-Means. Alcuni esempi di scenari di clustering sono i seguenti:

* Comprensione dei segmenti degli ospiti degli hotel in base alle abitudini e alle caratteristiche delle scelte degli hotel.
* Identificazione di segmenti di clienti e dati demografici per la creazione di campagne pubblicitarie mirate.
* Classificazione di inventari in base alle metriche di produzione.

## <a name="anomaly-detection-coming-soon"></a>Rilevamento di anomalie (*presto disponibile*)

## <a name="ranking-coming-soon"></a>Classificazione in ordine di priorità (*presto disponibile*)

## <a name="recommendation-coming-soon"></a>Elementi consigliati (*presto disponibile*)

