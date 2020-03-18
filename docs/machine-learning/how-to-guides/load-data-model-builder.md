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
# <a name="load-training-data-into-model-builder"></a><span data-ttu-id="87dbe-103">Caricare i dati di training in Model BuilderLoad training data into Model Builder</span><span class="sxs-lookup"><span data-stu-id="87dbe-103">Load training data into Model Builder</span></span>

<span data-ttu-id="87dbe-104">Informazioni su come caricare i set di dati di training da un file o da un database di SQL Serversql Server da usare in uno degli scenari di Model Builder per ML.NET.</span><span class="sxs-lookup"><span data-stu-id="87dbe-104">Learn how to load your training datasets from a file or a SQL Server database for use in one of the Model Builder scenarios for ML.NET.</span></span> <span data-ttu-id="87dbe-105">Gli scenari di Generatore di modelli possono usare database di SQL Server, file di immagine e formati di file CSV o TSV come dati di training.</span><span class="sxs-lookup"><span data-stu-id="87dbe-105">Model Builder scenarios can use SQL Server databases, image files, and CSV or TSV file formats as training data.</span></span>

## <a name="training-dataset-limitations-in-model-builder"></a><span data-ttu-id="87dbe-106">Limitazioni dei set di dati di training in Model Builder</span><span class="sxs-lookup"><span data-stu-id="87dbe-106">Training dataset limitations in Model Builder</span></span>

<span data-ttu-id="87dbe-107">Model Builder limita la quantità e il tipo di dati che è possibile utilizzare per i modelli di training:</span><span class="sxs-lookup"><span data-stu-id="87dbe-107">Model Builder limits the amount and type of data you can use for training models:</span></span>

- <span data-ttu-id="87dbe-108">Dati di SQL Server: 100.000 righe</span><span class="sxs-lookup"><span data-stu-id="87dbe-108">SQL Server data: 100,000 rows</span></span>
- <span data-ttu-id="87dbe-109">File CSV e TSV: nessun limite di dimensione</span><span class="sxs-lookup"><span data-stu-id="87dbe-109">CSV and TSV files: No size limit</span></span>
- <span data-ttu-id="87dbe-110">Immagini: solo PNG e JPG.</span><span class="sxs-lookup"><span data-stu-id="87dbe-110">Images: PNG and JPG only.</span></span>

## <a name="model-builder-scenarios"></a><span data-ttu-id="87dbe-111">Scenari di Model Builder</span><span class="sxs-lookup"><span data-stu-id="87dbe-111">Model Builder scenarios</span></span>

<span data-ttu-id="87dbe-112">Model Builder consente di creare modelli per i seguenti scenari di apprendimento automatico:</span><span class="sxs-lookup"><span data-stu-id="87dbe-112">Model Builder helps you create models for the following machine learning scenarios:</span></span>

- <span data-ttu-id="87dbe-113">Analisi del sentiment (classificazione binaria): classificare i dati testuali in due categorie.</span><span class="sxs-lookup"><span data-stu-id="87dbe-113">Sentiment analysis (binary classification): Classify textual data into two categories.</span></span>
- <span data-ttu-id="87dbe-114">Classificazione dei problemi (classificazione multiclasse): classificare i dati testuali in 3 o più categorie.</span><span class="sxs-lookup"><span data-stu-id="87dbe-114">Issue classification (multiclass classification): Classify textual data into 3 or more categories.</span></span>
- <span data-ttu-id="87dbe-115">Previsione prezzo (regressione): stima redimare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="87dbe-115">Price prediction (regression): Predict a numeric value.</span></span>
- <span data-ttu-id="87dbe-116">Classificazione delle immagini (apprendimento approfondito): categorizza le immagini in base alle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="87dbe-116">Image classification (deep learning): Categorize images based on characteristics.</span></span>
- <span data-ttu-id="87dbe-117">Scenario personalizzato: creare scenari personalizzati dai dati usando la regressione, la classificazione e altre attività.</span><span class="sxs-lookup"><span data-stu-id="87dbe-117">Custom scenario: Build custom scenarios from your data using regression, classification, and other tasks.</span></span>

<span data-ttu-id="87dbe-118">Questo articolo illustra gli scenari di classificazione e regressione con dati testuali o numerici e scenari di classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="87dbe-118">This article covers classification and regression scenarios with textual or numerical data, and image classification scenarios.</span></span>

## <a name="load-text-or-numeric-data-from-a-file"></a><span data-ttu-id="87dbe-119">Caricare testo o dati numerici da un file</span><span class="sxs-lookup"><span data-stu-id="87dbe-119">Load text or numeric data from a file</span></span>

<span data-ttu-id="87dbe-120">È possibile caricare dati di testo o numerici da un file in Model Builder.</span><span class="sxs-lookup"><span data-stu-id="87dbe-120">You can load text or numeric data from a file into Model Builder.</span></span> <span data-ttu-id="87dbe-121">Accetta formati di file delimitati da virgole (CSV) o da tabulazioni (TSV).</span><span class="sxs-lookup"><span data-stu-id="87dbe-121">It accepts comma-delimited (CSV) or tab-delimited (TSV) file formats.</span></span>

1. <span data-ttu-id="87dbe-122">Nel passaggio dati di Model Builder selezionare **File** dall'elenco a discesa dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="87dbe-122">In the data step of Model Builder, select **File** from the data source dropdown.</span></span>
2. <span data-ttu-id="87dbe-123">Selezionare il pulsante accanto alla casella di testo **Selezionare un file** e utilizzare Esplora file per sfogliare e selezionare il file di dati.</span><span class="sxs-lookup"><span data-stu-id="87dbe-123">Select the button next to the **Select a file** text box, and use File Explorer to browse and select the data file.</span></span>
3. <span data-ttu-id="87dbe-124">Scegliere una categoria nell'elenco a discesa **Colonna da stimare (etichetta).**</span><span class="sxs-lookup"><span data-stu-id="87dbe-124">Choose a category in the **Column to Predict (Label)** dropdown.</span></span>
4. <span data-ttu-id="87dbe-125">Nell'elenco a discesa Colonne di **input (funzionalità)** verificare che le colonne di dati da includere siano selezionate.</span><span class="sxs-lookup"><span data-stu-id="87dbe-125">From the **Input Columns (Features)** dropdown, confirm the data columns you want to include are checked.</span></span>

<span data-ttu-id="87dbe-126">La configurazione del file di origine dati per Model Builder è stata completata.</span><span class="sxs-lookup"><span data-stu-id="87dbe-126">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="87dbe-127">Selezionare il collegamento **Allenatore** per passare al passaggio successivo in Generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="87dbe-127">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="load-data-from-a-sql-server-database"></a><span data-ttu-id="87dbe-128">Caricare dati da un database di SQL ServerLoad data from a SQL Server database</span><span class="sxs-lookup"><span data-stu-id="87dbe-128">Load data from a SQL Server database</span></span>

<span data-ttu-id="87dbe-129">Model Builder supporta il caricamento di dati da database SQL Server locali e remoti.</span><span class="sxs-lookup"><span data-stu-id="87dbe-129">Model Builder supports loading data from local and remote SQL Server databases.</span></span>

<span data-ttu-id="87dbe-130">Per caricare dati da un database di SQL Server in Module Builder:</span><span class="sxs-lookup"><span data-stu-id="87dbe-130">To load data from a SQL Server database into Module Builder:</span></span>

1. <span data-ttu-id="87dbe-131">Nel passaggio dati di Model Builder selezionare **SQL Server** dall'elenco a discesa dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="87dbe-131">In the data step of Model Builder, select **SQL Server** from the data source dropdown.</span></span>
1. <span data-ttu-id="87dbe-132">Selezionare il pulsante accanto alla casella di testo **Connetti al database sql Server.**</span><span class="sxs-lookup"><span data-stu-id="87dbe-132">Select the button next to the **Connect to SQL Server database** text box.</span></span>
    1. <span data-ttu-id="87dbe-133">Nella finestra di dialogo **Scegli dati** selezionare File di database di Microsoft **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="87dbe-133">In the **Choose Data** dialog, select **Microsoft SQL Server Database File**.</span></span>
    1. <span data-ttu-id="87dbe-134">Deselezionare la casella di controllo **Usa sempre questa selezione** e selezionare **Continua**</span><span class="sxs-lookup"><span data-stu-id="87dbe-134">Uncheck the **Always use this selection** checkbox and select **Continue**</span></span>
    1. <span data-ttu-id="87dbe-135">Nella finestra di dialogo **Proprietà connessione,** selezionare **Sfoglia** e selezionare il file scaricato . MDF.</span><span class="sxs-lookup"><span data-stu-id="87dbe-135">In the **Connection Properties** dialog, select **Browse** and select the downloaded .MDF file.</span></span>
    1. <span data-ttu-id="87dbe-136">Seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="87dbe-136">Select **OK**</span></span>
1. <span data-ttu-id="87dbe-137">Scegliere il nome del set di dati dall'elenco a discesa **Nome tabella.**</span><span class="sxs-lookup"><span data-stu-id="87dbe-137">Choose the dataset name from the **Table Name** dropdown.</span></span>
1. <span data-ttu-id="87dbe-138">Dall'elenco a discesa **Da colonna a previsione (etichetta)** scegliere la categoria di dati in cui si vuole eseguire una stima.</span><span class="sxs-lookup"><span data-stu-id="87dbe-138">From the **Column to Predict (Label)** dropdown, choose the data category on which you want to make a prediction.</span></span>
1. <span data-ttu-id="87dbe-139">Nell'elenco a discesa Colonne di **input (funzionalità)** verificare che le colonne da includere siano selezionate.</span><span class="sxs-lookup"><span data-stu-id="87dbe-139">From the **Input Columns (Features)** dropdown, confirm the columns you want to include are checked.</span></span>

<span data-ttu-id="87dbe-140">La configurazione del file di origine dati per Model Builder è stata completata.</span><span class="sxs-lookup"><span data-stu-id="87dbe-140">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="87dbe-141">Selezionare il collegamento **Allenatore** per passare al passaggio successivo in Generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="87dbe-141">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="set-up-image-data-files"></a><span data-ttu-id="87dbe-142">Impostare i file di dati immagine</span><span class="sxs-lookup"><span data-stu-id="87dbe-142">Set up image data files</span></span>

<span data-ttu-id="87dbe-143">Model Builder prevede che i dati immagine siano file JPG o PNG organizzati in cartelle che corrispondono alle categorie della classificazione.</span><span class="sxs-lookup"><span data-stu-id="87dbe-143">Model Builder expects image data to be JPG or PNG files organized in folders that correspond to the categories of the classification.</span></span>

<span data-ttu-id="87dbe-144">Per caricare le immagini in Model Builder, fornire il percorso di una singola directory di primo livello:To load images into Model Builder, provide the path to a single top-level directory:</span><span class="sxs-lookup"><span data-stu-id="87dbe-144">To load images into Model Builder, provide the path to a single top-level directory:</span></span>

- <span data-ttu-id="87dbe-145">Questa directory di primo livello contiene una sottocartella per ciascuna delle categorie da stimare.</span><span class="sxs-lookup"><span data-stu-id="87dbe-145">This top-level directory contains one subfolder for each of the categories to predict.</span></span>
- <span data-ttu-id="87dbe-146">Ogni sottocartella contiene i file di immagine appartenenti alla relativa categoria.</span><span class="sxs-lookup"><span data-stu-id="87dbe-146">Each subfolder contains the image files belonging to its category.</span></span>

<span data-ttu-id="87dbe-147">Nella struttura di cartelle illustrata di seguito, la directory di primo livello è *flower_photos*.</span><span class="sxs-lookup"><span data-stu-id="87dbe-147">In the folder structure illustrated below, the top-level directory is *flower_photos*.</span></span> <span data-ttu-id="87dbe-148">Ci sono cinque sottodirectory corrispondenti alle categorie che si desidera prevedere: margherita, dente di leone, rose, girasoli e tulipani.</span><span class="sxs-lookup"><span data-stu-id="87dbe-148">There are five subdirectories corresponding to the categories you want to predict: daisy, dandelion, roses, sunflowers, and tulips.</span></span> <span data-ttu-id="87dbe-149">Ognuna di queste sottodirectory contiene immagini appartenenti alla rispettiva categoria.</span><span class="sxs-lookup"><span data-stu-id="87dbe-149">Each of these subdirectories contains images belonging to its respective category.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="87dbe-150">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="87dbe-150">Next steps</span></span>

<span data-ttu-id="87dbe-151">Seguire queste esercitazioni per creare app di apprendimento automatico con Model Builder:Follow these tutorials to build machine learning apps with Model Builder:</span><span class="sxs-lookup"><span data-stu-id="87dbe-151">Follow these tutorials to build machine learning apps with Model Builder:</span></span>

- [<span data-ttu-id="87dbe-152">Stimare i prezzi usando la regressione</span><span class="sxs-lookup"><span data-stu-id="87dbe-152">Predict prices using regression</span></span>](../tutorials/predict-prices-with-model-builder.md)
- [<span data-ttu-id="87dbe-153">Analizzare il sentiment in un'applicazione Web usando la classificazione binariaAnalyze sentiment in a web application using binary classification</span><span class="sxs-lookup"><span data-stu-id="87dbe-153">Analyze sentiment in a web application using binary classification</span></span>](../tutorials/sentiment-analysis-model-builder.md )

<span data-ttu-id="87dbe-154">Se si sta visualizzando il training di un modello usando il codice, vedere come caricare i [dati usando l'API ML.NET.](load-data-ml-net.md)</span><span class="sxs-lookup"><span data-stu-id="87dbe-154">If you're training a model using code, [learn how to load data using the ML.NET API](load-data-ml-net.md).</span></span>
