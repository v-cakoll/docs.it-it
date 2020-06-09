---
title: Caricare i dati di training per il generatore di modelli
description: Informazioni su come caricare i dati di training da un database SQL Server o da un file da usare in uno degli scenari di generatore di modelli per ML.NET.
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: 64e366b3c66427ccd2810324abeb880f6cb9ebc1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602206"
---
# <a name="load-training-data-into-model-builder"></a>Caricare i dati di training in Generatore di modelli

Informazioni su come caricare i set di dati di training da un file o da un database di SQL Server per l'uso in uno degli scenari di generatore di modelli per ML.NET. Gli scenari di generatore di modelli possono utilizzare database SQL Server, file di immagine e formati di file CSV o TSV come dati di training.

## <a name="training-dataset-limitations-in-model-builder"></a>Limitazioni del set di dati di training in Generatore di modelli

Il generatore di modelli limita la quantità e il tipo di dati che è possibile usare per i modelli di training:

- Dati SQL Server: 100.000 righe
- File CSV e TSV: nessun limite di dimensione
- Immagini: solo PNG e JPG.

## <a name="model-builder-scenarios"></a>Scenari di generatore di modelli

Il generatore di modelli consente di creare modelli per gli scenari di apprendimento automatico seguenti:

- Analisi dei sentimenti (classificazione binaria): classificare i dati testuali in due categorie.
- Classificazione dei problemi (classificazione multiclasse): classificare i dati testuali in 3 o più categorie.
- Stima del prezzo (regressione): stimare un valore numerico.
- Classificazione immagini (Deep Learning): categorizzare le immagini in base alle caratteristiche.
- Scenario personalizzato: creare scenari personalizzati dai dati tramite regressione, classificazione e altre attività.

Questo articolo illustra gli scenari di classificazione e regressione con dati testuali o numerici e scenari di classificazione delle immagini.

## <a name="load-text-or-numeric-data-from-a-file"></a>Carica dati numerici o di testo da un file

È possibile caricare dati di tipo text o numeric da un file in Generatore di modelli. Accetta formati di file delimitati da virgole (CSV) o di tabulazione (TSV).

1. Nel passaggio dati di generatore modelli selezionare **file** dall'elenco a discesa origine dati.
2. Selezionare il pulsante accanto alla casella di testo **selezionare un file** e utilizzare Esplora file per individuare e selezionare il file di dati.
3. Scegliere una categoria nell'elenco **a discesa colonna da stimare (etichetta)** .
4. Dall'elenco a discesa **colonne di input (funzionalità)** verificare che le colonne di dati che si desidera includere siano selezionate.

La configurazione del file di origine dati per il generatore di modelli è stata eseguita. Selezionare il collegamento **Train (Train** ) per passare al passaggio successivo in Generatore di modelli.

## <a name="load-data-from-a-sql-server-database"></a>Caricare dati da un database di SQL Server

Il generatore di modelli supporta il caricamento di dati da database SQL Server locali e remoti.

Per caricare i dati da un database di SQL Server in Module Builder:

1. Nel passaggio dati di generatore modelli selezionare **SQL Server** dall'elenco a discesa origine dati.
1. Selezionare il pulsante accanto alla casella di testo **Connetti a SQL Server database** .
    1. Nella finestra di dialogo **Scegli dati** selezionare **Microsoft SQL Server file di database**.
    1. Deselezionare la casella di controllo **Usa sempre questa selezione** e selezionare **continua** .
    1. Nella finestra di dialogo **Proprietà connessione** selezionare **Sfoglia** e selezionare il scaricato. File MDF.
    1. Seleziona **OK**.
1. Scegliere il nome del set di dati dall'elenco a discesa **nome tabella** .
1. Dall'elenco **a discesa colonna da stimare (etichetta)** scegliere la categoria di dati in base alla quale si desidera eseguire una stima.
1. Dall'elenco a discesa **colonne di input (funzionalità)** verificare che le colonne che si desidera includere siano selezionate.

La configurazione del file di origine dati per il generatore di modelli è stata eseguita. Selezionare il collegamento **Train (Train** ) per passare al passaggio successivo in Generatore di modelli.

## <a name="set-up-image-data-files"></a>Configurare i file di dati di immagine

Il generatore di modelli prevede che i dati dell'immagine siano file JPG o PNG organizzati in cartelle che corrispondono alle categorie della classificazione.

Per caricare immagini in Generatore di modelli, specificare il percorso di una singola directory di primo livello:

- Questa directory di livello superiore contiene una sottocartella per ogni categoria da stimare.
- Ogni sottocartella contiene i file di immagine appartenenti alla relativa categoria.

Nella struttura di cartelle illustrata di seguito, la directory di primo livello è *flower_photos*. Sono presenti cinque sottodirectory che corrispondono alle categorie che si desidera stimare: Daisy, Dandelion, Roses, girasoli e tulipani. Ognuna di queste sottodirectory contiene immagini appartenenti alla rispettiva categoria.

```text
\---flower_photos
    +---daisy
    |       100080576_f52e8ee070_n.jpg
    |       102841525_bd6628ae3c.jpg
    |       105806915_a9c13e2106_n.jpg
    |
    +---dandelion
    |       10443973_aeb97513fc_m.jpg
    |       10683189_bd6e371b97.jpg
    |       10919961_0af657c4e8.jpg
    |
    +---roses
    |       102501987_3cdb8e5394_n.jpg
    |       110472418_87b6a3aa98_m.jpg
    |       118974357_0faa23cce9_n.jpg
    |
    +---sunflowers
    |       127192624_afa3d9cb84.jpg
    |       145303599_2627e23815_n.jpg
    |       147804446_ef9244c8ce_m.jpg
    |
    \---tulips
            100930342_92e8746431_n.jpg
            107693873_86021ac4ea_n.jpg
            10791227_7168491604.jpg
```

## <a name="next-steps"></a>Passaggi successivi

Segui queste esercitazioni per creare app di Machine Learning con generatore di modelli:

- [Stimare i prezzi usando la regressione](../tutorials/predict-prices-with-model-builder.md)
- [Analizzare i sentimenti in un'applicazione Web usando la classificazione binaria](../tutorials/sentiment-analysis-model-builder.md)

Se si sta eseguendo il training di un modello usando il codice, vedere [informazioni su come caricare i dati usando l'API ml.NET](load-data-ml-net.md).
