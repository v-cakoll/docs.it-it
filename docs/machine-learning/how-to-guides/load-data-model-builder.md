---
title: Caricare i dati di training per Model BuilderLoad training data for Model Builder
description: Informazioni su come caricare i dati di training da un database di SQL ServerSQL Server o un file da usare in uno degli scenari di Model Builder per ML.NET.
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: 23de2d06090f4c1eaa2c79178ba4c346698d45e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78849159"
---
# <a name="load-training-data-into-model-builder"></a>Caricare i dati di training in Model BuilderLoad training data into Model Builder

Informazioni su come caricare i set di dati di training da un file o da un database di SQL Serversql Server da usare in uno degli scenari di Model Builder per ML.NET. Gli scenari di Generatore di modelli possono usare database di SQL Server, file di immagine e formati di file CSV o TSV come dati di training.

## <a name="training-dataset-limitations-in-model-builder"></a>Limitazioni dei set di dati di training in Model Builder

Model Builder limita la quantità e il tipo di dati che è possibile utilizzare per i modelli di training:

- Dati di SQL Server: 100.000 righe
- File CSV e TSV: nessun limite di dimensione
- Immagini: solo PNG e JPG.

## <a name="model-builder-scenarios"></a>Scenari di Model Builder

Model Builder consente di creare modelli per i seguenti scenari di apprendimento automatico:

- Analisi del sentiment (classificazione binaria): classificare i dati testuali in due categorie.
- Classificazione dei problemi (classificazione multiclasse): classificare i dati testuali in 3 o più categorie.
- Previsione prezzo (regressione): stima redimare un valore numerico.
- Classificazione delle immagini (apprendimento approfondito): categorizza le immagini in base alle caratteristiche.
- Scenario personalizzato: creare scenari personalizzati dai dati usando la regressione, la classificazione e altre attività.

Questo articolo illustra gli scenari di classificazione e regressione con dati testuali o numerici e scenari di classificazione delle immagini.

## <a name="load-text-or-numeric-data-from-a-file"></a>Caricare testo o dati numerici da un file

È possibile caricare dati di testo o numerici da un file in Model Builder. Accetta formati di file delimitati da virgole (CSV) o da tabulazioni (TSV).

1. Nel passaggio dati di Model Builder selezionare **File** dall'elenco a discesa dell'origine dati.
2. Selezionare il pulsante accanto alla casella di testo **Selezionare un file** e utilizzare Esplora file per sfogliare e selezionare il file di dati.
3. Scegliere una categoria nell'elenco a discesa **Colonna da stimare (etichetta).**
4. Nell'elenco a discesa Colonne di **input (funzionalità)** verificare che le colonne di dati da includere siano selezionate.

La configurazione del file di origine dati per Model Builder è stata completata. Selezionare il collegamento **Allenatore** per passare al passaggio successivo in Generatore di modelli.

## <a name="load-data-from-a-sql-server-database"></a>Caricare dati da un database di SQL ServerLoad data from a SQL Server database

Model Builder supporta il caricamento di dati da database SQL Server locali e remoti.

Per caricare dati da un database di SQL Server in Module Builder:

1. Nel passaggio dati di Model Builder selezionare **SQL Server** dall'elenco a discesa dell'origine dati.
1. Selezionare il pulsante accanto alla casella di testo **Connetti al database sql Server.**
    1. Nella finestra di dialogo **Scegli dati** selezionare File di database di Microsoft **SQL Server**.
    1. Deselezionare la casella di controllo **Usa sempre questa selezione** e selezionare **Continua**
    1. Nella finestra di dialogo **Proprietà connessione,** selezionare **Sfoglia** e selezionare il file scaricato . MDF.
    1. Seleziona **OK**.
1. Scegliere il nome del set di dati dall'elenco a discesa **Nome tabella.**
1. Dall'elenco a discesa **Da colonna a previsione (etichetta)** scegliere la categoria di dati in cui si vuole eseguire una stima.
1. Nell'elenco a discesa Colonne di **input (funzionalità)** verificare che le colonne da includere siano selezionate.

La configurazione del file di origine dati per Model Builder è stata completata. Selezionare il collegamento **Allenatore** per passare al passaggio successivo in Generatore di modelli.

## <a name="set-up-image-data-files"></a>Impostare i file di dati immagine

Model Builder prevede che i dati immagine siano file JPG o PNG organizzati in cartelle che corrispondono alle categorie della classificazione.

Per caricare le immagini in Model Builder, fornire il percorso di una singola directory di primo livello:To load images into Model Builder, provide the path to a single top-level directory:

- Questa directory di primo livello contiene una sottocartella per ciascuna delle categorie da stimare.
- Ogni sottocartella contiene i file di immagine appartenenti alla relativa categoria.

Nella struttura di cartelle illustrata di seguito, la directory di primo livello è *flower_photos*. Ci sono cinque sottodirectory corrispondenti alle categorie che si desidera prevedere: margherita, dente di leone, rose, girasoli e tulipani. Ognuna di queste sottodirectory contiene immagini appartenenti alla rispettiva categoria.

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

Seguire queste esercitazioni per creare app di apprendimento automatico con Model Builder:Follow these tutorials to build machine learning apps with Model Builder:

- [Stimare i prezzi usando la regressione](../tutorials/predict-prices-with-model-builder.md)
- [Analizzare il sentiment in un'applicazione Web usando la classificazione binariaAnalyze sentiment in a web application using binary classification](../tutorials/sentiment-analysis-model-builder.md )

Se si sta visualizzando il training di un modello usando il codice, vedere come caricare i [dati usando l'API ML.NET.](load-data-ml-net.md)
