---
title: Stimare i prezzi usando la regressione con il generatore di modelli
description: Questa esercitazione illustra come creare un modello di regressione usando il generatore di modelli ML.NET per stimare i prezzi, nel caso specifico le tariffe dei taxi di New York.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: db9788e3065a0f2f21d712b2d4826efea2d8a829
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410579"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="74f12-103">Stimare i prezzi usando la regressione con il generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="74f12-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="74f12-104">Informazioni su come usare il generatore di modelli ML.NET per compilare un [modello di regressione](../resources/glossary.md#regression) per stimare i prezzi.</span><span class="sxs-lookup"><span data-stu-id="74f12-104">Learn how to use ML.NET Model Builder to build a [regression model](../resources/glossary.md#regression) to predict prices.</span></span>  <span data-ttu-id="74f12-105">L'app console .NET che viene sviluppata in questa esercitazione consente di stimare le tariffe dei taxi di New York in base ai relativi dati storici.</span><span class="sxs-lookup"><span data-stu-id="74f12-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="74f12-106">Il modello di stima dei prezzi del generatore di modelli può essere usato in qualsiasi scenario che richieda un valore numerico di stima.</span><span class="sxs-lookup"><span data-stu-id="74f12-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="74f12-107">Tra gli scenari di esempio vi sono la stima dei prezzi delle abitazioni, la stima della domanda e le previsioni di vendita.</span><span class="sxs-lookup"><span data-stu-id="74f12-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="74f12-108">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="74f12-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="74f12-109">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="74f12-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="74f12-110">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="74f12-110">Choose a scenario</span></span>
> * <span data-ttu-id="74f12-111">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="74f12-111">Load the data</span></span>
> * <span data-ttu-id="74f12-112">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="74f12-112">Train the model</span></span>
> * <span data-ttu-id="74f12-113">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="74f12-113">Evaluate the model</span></span>
> * <span data-ttu-id="74f12-114">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="74f12-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="74f12-115">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="74f12-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="74f12-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="74f12-116">Pre-requisites</span></span>

<span data-ttu-id="74f12-117">Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="74f12-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="74f12-118">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="74f12-118">Create a console application</span></span>

1. <span data-ttu-id="74f12-119">Creare un'**applicazione console di .NET Core** con nome "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="74f12-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="74f12-120">Installare il pacchetto NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="74f12-120">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="74f12-121">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="74f12-121">In **Solution Explorer**, right-click the *TaxiFarePrediction* project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="74f12-122">Scegliere "nuget.org" come Origine del pacchetto, selezionare la scheda **Sfoglia**, trovare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="74f12-122">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="74f12-123">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="74f12-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="74f12-124">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="74f12-124">Prepare and understand the data</span></span>

1. <span data-ttu-id="74f12-125">Creare una directory denominata *Dati* nel progetto per archiviare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="74f12-125">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="74f12-126">Scaricare il set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e salvarlo nella cartella *Dati* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="74f12-126">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) data set and save it to the *Data* folder you created at the previous step.</span></span> <span data-ttu-id="74f12-127">Il set di dati consente di eseguire il training del modello di Machine Learning e di valutarlo.</span><span class="sxs-lookup"><span data-stu-id="74f12-127">This data set is used to train and evaluate the machine learning model.</span></span> <span data-ttu-id="74f12-128">Questo set di dati deriva dal [set di dati NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="74f12-128">This data set is originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="74f12-129">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *taxi-fare-train.csv* e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="74f12-129">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="74f12-130">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="74f12-130">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="74f12-131">Ogni riga del set di dati `taxi-fare-train.csv` contiene i dettagli delle corse effettuate da un taxi.</span><span class="sxs-lookup"><span data-stu-id="74f12-131">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span> 

1. <span data-ttu-id="74f12-132">Aprire il set di dati **taxi-fare-train.csv**</span><span class="sxs-lookup"><span data-stu-id="74f12-132">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="74f12-133">Il set di dati fornito contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="74f12-133">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="74f12-134">**vendor_id:** l'ID della società di taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="74f12-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="74f12-135">**rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="74f12-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="74f12-136">**passenger_count:** il numero di passeggeri è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="74f12-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="74f12-137">**trip_time_in_secs:** il tempo impiegato per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="74f12-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="74f12-138">Si vuole stimare la tariffa del viaggio prima del termine.</span><span class="sxs-lookup"><span data-stu-id="74f12-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="74f12-139">Al momento non si conosce la durata del viaggio.</span><span class="sxs-lookup"><span data-stu-id="74f12-139">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="74f12-140">Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.</span><span class="sxs-lookup"><span data-stu-id="74f12-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    * <span data-ttu-id="74f12-141">**trip_distance:** la distanza del viaggio è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="74f12-141">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="74f12-142">**payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="74f12-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="74f12-143">**fare_amount:** la tariffa totale corrisposta per il viaggio in taxi è l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="74f12-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="74f12-144">`label` è la colonna sulla quale eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="74f12-144">The `label` is the column you want to predict.</span></span> <span data-ttu-id="74f12-145">Quando si esegue un'attività di regressione, l'obiettivo è stimare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="74f12-145">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="74f12-146">In questo scenario di stima dei prezzi viene stimato il costo di una corsa in taxi.</span><span class="sxs-lookup"><span data-stu-id="74f12-146">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="74f12-147">Pertanto, l'etichetta è **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="74f12-147">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="74f12-148">Gli elementi identificati `features` sono gli input che vengono dati al modello per stimare l'oggetto `label`.</span><span class="sxs-lookup"><span data-stu-id="74f12-148">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="74f12-149">In questo caso le colonne rimanenti vengono usate come input o funzionalità per stimare l'importo della tariffa.</span><span class="sxs-lookup"><span data-stu-id="74f12-149">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="74f12-150">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="74f12-150">Choose a scenario</span></span>

<span data-ttu-id="74f12-151">Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="74f12-151">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="74f12-152">In questo caso lo scenario è `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="74f12-152">In this case, the scenario is `Price Prediction`.</span></span> <span data-ttu-id="74f12-153">Per un elenco più completo, vedere l'[articolo sulla panoramica del generatore di modelli](../automate-training-with-model-builder.md#scenarios).</span><span class="sxs-lookup"><span data-stu-id="74f12-153">For a more extensive list visit the [Model Builder overview article](../automate-training-with-model-builder.md#scenarios).</span></span>

1. <span data-ttu-id="74f12-154">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Aggiungi** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="74f12-154">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="74f12-155">Nel passaggio relativo allo scenario dello strumento generatore di modelli, selezionare *Price Prediction*.</span><span class="sxs-lookup"><span data-stu-id="74f12-155">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="74f12-156">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="74f12-156">Load the data</span></span>

<span data-ttu-id="74f12-157">Il generatore di modelli accetta i dati da due origini, un database di SQL Server o un file locale con estensione csv o tsv.</span><span class="sxs-lookup"><span data-stu-id="74f12-157">Model Builder accepts data from two sources, a SQL Server database or a local file csv or tsv file.</span></span> <span data-ttu-id="74f12-158">Per altre informazioni sui requisiti di formato dei dati, selezionare il [collegamento](../how-to-guides/install-model-builder.md#limitations) seguente.</span><span class="sxs-lookup"><span data-stu-id="74f12-158">For more information on data format requirements, visit the following [link](../how-to-guides/install-model-builder.md#limitations).</span></span>

1. <span data-ttu-id="74f12-159">Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare *File* dall'elenco a discesa delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="74f12-159">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="74f12-160">Selezionare il pulsante accanto alla casella di testo *Seleziona un file* e usare Esplora File per cercare e selezionare *taxi-fare-test.csv* nella directory *Dati*.</span><span class="sxs-lookup"><span data-stu-id="74f12-160">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="74f12-161">Scegliere *fare_amount* nell'elenco a discesa *Label or Column to Predict* (Etichetta o colonna per stima) e passare al passaggio relativo al training dello strumento generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="74f12-161">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="74f12-162">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="74f12-162">Train the model</span></span>

<span data-ttu-id="74f12-163">L'attività di Machine Learning usata per eseguire il training del modello di stima dei prezzi in questa esercitazione è la regressione.</span><span class="sxs-lookup"><span data-stu-id="74f12-163">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="74f12-164">Durante il processo di training del modello, il generatore di modelli esegue il training di modelli separati usando impostazioni e algoritmi di regressione diversi per individuare il modello di prestazioni migliore per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="74f12-164">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="74f12-165">Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="74f12-165">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="74f12-166">Usare questo grafico come guida per selezionare un valore adeguato per il campo `Time to train (seconds)`:</span><span class="sxs-lookup"><span data-stu-id="74f12-166">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="74f12-167">\*Dimensioni del set di dati</span><span class="sxs-lookup"><span data-stu-id="74f12-167">\*Dataset Size</span></span>  | <span data-ttu-id="74f12-168">Tipo di set di dati</span><span class="sxs-lookup"><span data-stu-id="74f12-168">Dataset Type</span></span>       | <span data-ttu-id="74f12-169">Avg. Durata del training\*</span><span class="sxs-lookup"><span data-stu-id="74f12-169">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="74f12-170">0 - 10 MB</span><span class="sxs-lookup"><span data-stu-id="74f12-170">0 - 10 Mb</span></span>     | <span data-ttu-id="74f12-171">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="74f12-171">Numeric and Text</span></span>   | <span data-ttu-id="74f12-172">10 sec</span><span class="sxs-lookup"><span data-stu-id="74f12-172">10 sec</span></span>
<span data-ttu-id="74f12-173">10 - 100 MB</span><span class="sxs-lookup"><span data-stu-id="74f12-173">10 - 100 Mb</span></span>   | <span data-ttu-id="74f12-174">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="74f12-174">Numeric and Text</span></span>   | <span data-ttu-id="74f12-175">10 min</span><span class="sxs-lookup"><span data-stu-id="74f12-175">10 min</span></span>
<span data-ttu-id="74f12-176">100 - 500 MB</span><span class="sxs-lookup"><span data-stu-id="74f12-176">100 - 500 Mb</span></span>  | <span data-ttu-id="74f12-177">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="74f12-177">Numeric and Text</span></span>   | <span data-ttu-id="74f12-178">30 min</span><span class="sxs-lookup"><span data-stu-id="74f12-178">30 min</span></span>
<span data-ttu-id="74f12-179">500 - 1 GB</span><span class="sxs-lookup"><span data-stu-id="74f12-179">500 - 1 Gb</span></span>    | <span data-ttu-id="74f12-180">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="74f12-180">Numeric and Text</span></span>   | <span data-ttu-id="74f12-181">60 min</span><span class="sxs-lookup"><span data-stu-id="74f12-181">60 min</span></span>
<span data-ttu-id="74f12-182">1 GB+</span><span class="sxs-lookup"><span data-stu-id="74f12-182">1 Gb+</span></span>         | <span data-ttu-id="74f12-183">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="74f12-183">Numeric and Text</span></span>   | <span data-ttu-id="74f12-184">3 ore+</span><span class="sxs-lookup"><span data-stu-id="74f12-184">3 hour+</span></span>

1. <span data-ttu-id="74f12-185">Poiché il file di dati di training è più di 10MB, usare 600 secondi (10 minuti) come valore per *Time to train (seconds)* (Durata training (secondi)).</span><span class="sxs-lookup"><span data-stu-id="74f12-185">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="74f12-186">Selezionare *Start Training* (Avvia training).</span><span class="sxs-lookup"><span data-stu-id="74f12-186">Select *Start Training*.</span></span>

<span data-ttu-id="74f12-187">Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.</span><span class="sxs-lookup"><span data-stu-id="74f12-187">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="74f12-188">Stato visualizza lo stato di completamento del processo di training.</span><span class="sxs-lookup"><span data-stu-id="74f12-188">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="74f12-189">Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="74f12-189">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="74f12-190">Precisione maggiore indica il modello stimato più correttamente con i dati di test.</span><span class="sxs-lookup"><span data-stu-id="74f12-190">Higher accuracy means the model predicted more correctly on test data.</span></span> 
- <span data-ttu-id="74f12-191">Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="74f12-191">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="74f12-192">Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="74f12-192">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="74f12-193">Una volta completato il training, passare alla valutazione.</span><span class="sxs-lookup"><span data-stu-id="74f12-193">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="74f12-194">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="74f12-194">Evaluate the model</span></span>

<span data-ttu-id="74f12-195">Il risultato del passaggio relativo al training è rappresentato dal modello con le prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="74f12-195">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="74f12-196">Nel passaggio di valutazione dello strumento generatore di modelli la sezione di output conterrà l'algoritmo usato dal modello con le prestazioni migliori nella voce *Best model* (Modello migliore), insieme con le metriche in *Best Model Quality (RSquared)* (Qualità modello migliore).</span><span class="sxs-lookup"><span data-stu-id="74f12-196">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="74f12-197">Viene visualizzata anche una tabella di riepilogo con i cinque modelli migliori e le metriche relative.</span><span class="sxs-lookup"><span data-stu-id="74f12-197">Additionally, a summary table containing top five models and their metrics.</span></span> <span data-ttu-id="74f12-198">Selezionare il collegamento seguente per altre informazioni sulla [valutazione delle metriche dei modelli](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span><span class="sxs-lookup"><span data-stu-id="74f12-198">Visit the following link to learn more about [evaluating model metrics](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span></span>

<span data-ttu-id="74f12-199">Se non si è soddisfatti della precisione delle metriche,un modo semplice per migliorarla consiste nell'aumentare la durata del training del modello o nell'usare più dati.</span><span class="sxs-lookup"><span data-stu-id="74f12-199">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="74f12-200">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="74f12-200">Use the model for predictions</span></span>

<span data-ttu-id="74f12-201">Il risultato del processo di training sarà la creazione di due progetti.</span><span class="sxs-lookup"><span data-stu-id="74f12-201">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="74f12-202">TaxiFarePredictionML.ConsoleApp: un'applicazione console .NET che contiene il codice del modello di training e il consumo.</span><span class="sxs-lookup"><span data-stu-id="74f12-202">TaxiFarePredictionML.ConsoleApp: A .NET Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="74f12-203">TaxiFarePredictionML.Model: una libreria di classi .NET Standard che contiene i modelli di dati che definiscono lo schema di input e output dei dati del modello, nonché la versione persistente del modello che ha avuto le prestazioni migliori durante il training.</span><span class="sxs-lookup"><span data-stu-id="74f12-203">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="74f12-204">Nella sezione relativa al codice dello strumento generatore di modelli selezionare **Added Projects** (Progetti aggiunti) per aggiungere i progetti alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="74f12-204">In the code section of the Model Builder tool, select **Added Projects** to add the projects to the solution.</span></span>
1. <span data-ttu-id="74f12-205">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction*</span><span class="sxs-lookup"><span data-stu-id="74f12-205">In solution explorer, right-click the *TaxiFarePrediction* project.</span></span> <span data-ttu-id="74f12-206">e selezionare **Aggiungi > Elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="74f12-206">Then, select **Add > Existing Item**.</span></span> <span data-ttu-id="74f12-207">Nell'elenco a discesa del tipo di file selezionare `All Files`, passare alla directory del progetto *TaxiFarePredictionML.Model* e selezionare il file `MLModel.zip`.</span><span class="sxs-lookup"><span data-stu-id="74f12-207">For file type drop down, select `All Files`, navigate to the *TaxiFarePredictionML.Model* project directory and select the `MLModel.zip` file.</span></span> <span data-ttu-id="74f12-208">In seguito fare clic con il pulsante destro del mouse sul file `MLModel.zip` appena aggiunto e selezionare *Proprietà*.</span><span class="sxs-lookup"><span data-stu-id="74f12-208">Then right-click the recently added `MLModel.zip` file and select *Properties*.</span></span> <span data-ttu-id="74f12-209">Per l'opzione Copia nella directory di output, selezionare *Copia se più recente* dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="74f12-209">For the Copy to Output Directory option, select *Copy if Newer* from the dropdown.</span></span>
1. <span data-ttu-id="74f12-210">Fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="74f12-210">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="74f12-211">In seguito, selezionare **Aggiungi > Riferimento**.</span><span class="sxs-lookup"><span data-stu-id="74f12-211">Then, **Add > Reference**.</span></span> <span data-ttu-id="74f12-212">Scegliere il nodo **Progetti > Soluzione** e dall'elenco contrassegnare il progetto *TaxiFarePredictionML.Model* e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="74f12-212">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>

4. <span data-ttu-id="74f12-213">Aprire il file *Program.cs* nel progetto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="74f12-213">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
5. <span data-ttu-id="74f12-214">Aggiungere le istruzioni using seguenti:</span><span class="sxs-lookup"><span data-stu-id="74f12-214">Add the following using statements:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. <span data-ttu-id="74f12-215">Aggiungere il metodo `ConsumeModel` alla classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="74f12-215">Add the `ConsumeModel` method to the `Program` class.</span></span> <span data-ttu-id="74f12-216">`ConsumeModel` creerà un elemento `PredictionEngine` basato sul modello generato dal generatore di modelli per eseguire stime sui nuovi dati e stamparle sulla console.</span><span class="sxs-lookup"><span data-stu-id="74f12-216">The `ConsumeModel` will create a `PredictionEngine` based on the model generated by Model Builder to make predictions on new data and print them out to the console.</span></span>

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. <span data-ttu-id="74f12-217">Aggiungere il codice seguente al metodo `Main` ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74f12-217">Add the following code to the `Main` method and run the application.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    <span data-ttu-id="74f12-218">L'output generato dal programma dovrebbe essere simile al frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="74f12-218">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="74f12-219">Se in un secondo momento è necessario fare riferimento ai progetti generati all'interno di un'altra soluzione, è possibile trovarli all'interno della directory `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="74f12-219">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74f12-220">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="74f12-220">Next Steps</span></span>

<span data-ttu-id="74f12-221">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="74f12-221">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="74f12-222">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="74f12-222">Prepare and understand the data</span></span>
> * <span data-ttu-id="74f12-223">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="74f12-223">Choose a scenario</span></span>
> * <span data-ttu-id="74f12-224">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="74f12-224">Load the data</span></span>
> * <span data-ttu-id="74f12-225">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="74f12-225">Train the model</span></span>
> * <span data-ttu-id="74f12-226">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="74f12-226">Evaluate the model</span></span>
> * <span data-ttu-id="74f12-227">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="74f12-227">Use the model for predictions</span></span>

<span data-ttu-id="74f12-228">Per informazioni su come distribuire il modello, vedere uno degli articoli seguenti relativi a procedure.</span><span class="sxs-lookup"><span data-stu-id="74f12-228">Advance to either of the following how-to articles to learn how to deploy your model.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="74f12-229">Distribuire un modello in Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="74f12-229">Deploy a model to Azure Functions</span></span>](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="74f12-230">Distribuire un modello in un'API Web</span><span class="sxs-lookup"><span data-stu-id="74f12-230">Deploy a model to a Web API</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)
