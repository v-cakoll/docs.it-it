---
title: Stimare i prezzi usando la regressione con il generatore di modelli
description: Questa esercitazione illustra come creare un modello di regressione usando il generatore di modelli ML.NET per stimare i prezzi, nel caso specifico le tariffe dei taxi di New York.
author: luisquintanilla
ms.author: luquinta
ms.date: 07/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b4a08a9866bbc8816b57c95bdb22766bd1b07fdc
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331706"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="7fef6-103">Stimare i prezzi usando la regressione con il generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="7fef6-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="7fef6-104">Informazioni su come usare il generatore di modelli ML.NET per compilare un modello di regressione per stimare i prezzi.</span><span class="sxs-lookup"><span data-stu-id="7fef6-104">Learn how to use ML.NET Model Builder to build a regression model() to predict prices.</span></span>  <span data-ttu-id="7fef6-105">L'app console .NET che viene sviluppata in questa esercitazione consente di stimare le tariffe dei taxi di New York in base ai relativi dati storici.</span><span class="sxs-lookup"><span data-stu-id="7fef6-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="7fef6-106">Il modello di stima dei prezzi del generatore di modelli può essere usato in qualsiasi scenario che richieda un valore numerico di stima.</span><span class="sxs-lookup"><span data-stu-id="7fef6-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="7fef6-107">Tra gli scenari di esempio vi sono la stima dei prezzi delle abitazioni, la stima della domanda e le previsioni di vendita.</span><span class="sxs-lookup"><span data-stu-id="7fef6-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="7fef6-108">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="7fef6-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="7fef6-109">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="7fef6-110">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="7fef6-110">Choose a scenario</span></span>
> * <span data-ttu-id="7fef6-111">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-111">Load the data</span></span>
> * <span data-ttu-id="7fef6-112">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="7fef6-112">Train the model</span></span>
> * <span data-ttu-id="7fef6-113">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="7fef6-113">Evaluate the model</span></span>
> * <span data-ttu-id="7fef6-114">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="7fef6-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="7fef6-115">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="7fef6-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="7fef6-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7fef6-116">Pre-requisites</span></span>

<span data-ttu-id="7fef6-117">Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7fef6-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="7fef6-118">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="7fef6-118">Create a console application</span></span>

1. <span data-ttu-id="7fef6-119">Creare un'**applicazione console di .NET Core** con nome "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="7fef6-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="7fef6-120">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="7fef6-121">Creare una directory denominata *Dati* nel progetto per archiviare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="7fef6-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="7fef6-122">Il set di dati usato per il training e la valutazione del modello di Machine Learning è ricavato in origine dal set di dati NYC TLC Taxi Trip.</span><span class="sxs-lookup"><span data-stu-id="7fef6-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    <span data-ttu-id="7fef6-123">Per scaricare il set di dati, passare al [collegamento per il download di taxi-fare-train.csv](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="7fef6-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    <span data-ttu-id="7fef6-124">Quando si carica la pagina, fare clic con il pulsante destro del mouse in un punto qualsiasi della pagina e scegliere **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="7fef6-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    <span data-ttu-id="7fef6-125">Usare la **finestra di dialogo Salva con nome** per salvare il file nella cartella *Dati* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="7fef6-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="7fef6-126">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *taxi-fare-train.csv* e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7fef6-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="7fef6-127">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="7fef6-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="7fef6-128">Ogni riga del set di dati `taxi-fare-train.csv` contiene i dettagli delle corse effettuate da un taxi.</span><span class="sxs-lookup"><span data-stu-id="7fef6-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="7fef6-129">Aprire il set di dati **taxi-fare-train.csv**</span><span class="sxs-lookup"><span data-stu-id="7fef6-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="7fef6-130">Il set di dati fornito contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fef6-130">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="7fef6-131">**vendor_id:** l'ID della società di taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7fef6-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="7fef6-132">**rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7fef6-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="7fef6-133">**passenger_count:** il numero di passeggeri è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7fef6-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="7fef6-134">**trip_time_in_secs:** il tempo impiegato per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="7fef6-134">**trip_time_in_secs:** The amount of time the trip took.</span></span>
    * <span data-ttu-id="7fef6-135">**trip_distance:** la distanza del viaggio è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7fef6-135">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="7fef6-136">**payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7fef6-136">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="7fef6-137">**fare_amount:** la tariffa totale corrisposta per il viaggio in taxi è l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="7fef6-137">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="7fef6-138">`label` è la colonna sulla quale eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="7fef6-138">The `label` is the column you want to predict.</span></span> <span data-ttu-id="7fef6-139">Quando si esegue un'attività di regressione, l'obiettivo è stimare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="7fef6-139">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="7fef6-140">In questo scenario di stima dei prezzi viene stimato il costo di una corsa in taxi.</span><span class="sxs-lookup"><span data-stu-id="7fef6-140">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="7fef6-141">Pertanto, l'etichetta è **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="7fef6-141">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="7fef6-142">Gli elementi identificati `features` sono gli input che vengono dati al modello per stimare l'oggetto `label`.</span><span class="sxs-lookup"><span data-stu-id="7fef6-142">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="7fef6-143">In questo caso le colonne rimanenti vengono usate come input o funzionalità per stimare l'importo della tariffa.</span><span class="sxs-lookup"><span data-stu-id="7fef6-143">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="7fef6-144">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="7fef6-144">Choose a scenario</span></span>

<span data-ttu-id="7fef6-145">Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="7fef6-145">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="7fef6-146">In questo caso lo scenario è `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="7fef6-146">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="7fef6-147">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Aggiungi** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="7fef6-147">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="7fef6-148">Nel passaggio relativo allo scenario dello strumento generatore di modelli, selezionare *Price Prediction*.</span><span class="sxs-lookup"><span data-stu-id="7fef6-148">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="7fef6-149">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-149">Load the data</span></span>

<span data-ttu-id="7fef6-150">Il generatore di modelli accetta i dati da due origini, un database di SQL Server o un file locale in formato csv o tsv.</span><span class="sxs-lookup"><span data-stu-id="7fef6-150">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="7fef6-151">Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare *File* dall'elenco a discesa delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="7fef6-151">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="7fef6-152">Selezionare il pulsante accanto alla casella di testo *Seleziona un file* e usare Esplora File per cercare e selezionare *taxi-fare-test.csv* nella directory *Dati*.</span><span class="sxs-lookup"><span data-stu-id="7fef6-152">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="7fef6-153">Scegliere *fare_amount* nell'elenco a discesa *Label or Column to Predict* (Etichetta o colonna per stima) e passare al passaggio relativo al training dello strumento generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="7fef6-153">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="7fef6-154">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="7fef6-154">Train the model</span></span>

<span data-ttu-id="7fef6-155">L'attività di Machine Learning usata per eseguire il training del modello di stima dei prezzi in questa esercitazione è la regressione.</span><span class="sxs-lookup"><span data-stu-id="7fef6-155">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="7fef6-156">Durante il processo di training del modello, il generatore di modelli esegue il training di modelli separati usando impostazioni e algoritmi di regressione diversi per individuare il modello di prestazioni migliore per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="7fef6-156">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="7fef6-157">Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="7fef6-157">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="7fef6-158">Usare questo grafico come guida per selezionare un valore adeguato per il campo `Time to train (seconds)`:</span><span class="sxs-lookup"><span data-stu-id="7fef6-158">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="7fef6-159">\*Dimensioni del set di dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-159">\*Dataset Size</span></span>  | <span data-ttu-id="7fef6-160">Tipo di set di dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-160">Dataset Type</span></span>       | <span data-ttu-id="7fef6-161">Avg. Durata del training\*</span><span class="sxs-lookup"><span data-stu-id="7fef6-161">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="7fef6-162">0 - 10 MB</span><span class="sxs-lookup"><span data-stu-id="7fef6-162">0 - 10 Mb</span></span>     | <span data-ttu-id="7fef6-163">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="7fef6-163">Numeric and Text</span></span>   | <span data-ttu-id="7fef6-164">10 sec</span><span class="sxs-lookup"><span data-stu-id="7fef6-164">10 sec</span></span>
<span data-ttu-id="7fef6-165">10 - 100 MB</span><span class="sxs-lookup"><span data-stu-id="7fef6-165">10 - 100 Mb</span></span>   | <span data-ttu-id="7fef6-166">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="7fef6-166">Numeric and Text</span></span>   | <span data-ttu-id="7fef6-167">10 min</span><span class="sxs-lookup"><span data-stu-id="7fef6-167">10 min</span></span>
<span data-ttu-id="7fef6-168">100 - 500 MB</span><span class="sxs-lookup"><span data-stu-id="7fef6-168">100 - 500 Mb</span></span>  | <span data-ttu-id="7fef6-169">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="7fef6-169">Numeric and Text</span></span>   | <span data-ttu-id="7fef6-170">30 min</span><span class="sxs-lookup"><span data-stu-id="7fef6-170">30 min</span></span>
<span data-ttu-id="7fef6-171">500 - 1 GB</span><span class="sxs-lookup"><span data-stu-id="7fef6-171">500 - 1 Gb</span></span>    | <span data-ttu-id="7fef6-172">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="7fef6-172">Numeric and Text</span></span>   | <span data-ttu-id="7fef6-173">60 min</span><span class="sxs-lookup"><span data-stu-id="7fef6-173">60 min</span></span>
<span data-ttu-id="7fef6-174">1 GB+</span><span class="sxs-lookup"><span data-stu-id="7fef6-174">1 Gb+</span></span>         | <span data-ttu-id="7fef6-175">Numerico e testo</span><span class="sxs-lookup"><span data-stu-id="7fef6-175">Numeric and Text</span></span>   | <span data-ttu-id="7fef6-176">3 ore+</span><span class="sxs-lookup"><span data-stu-id="7fef6-176">3 hour+</span></span>

1. <span data-ttu-id="7fef6-177">Poiché il file di dati di training è più di 10MB, usare 600 secondi (10 minuti) come valore per *Time to train (seconds)* (Durata training (secondi)).</span><span class="sxs-lookup"><span data-stu-id="7fef6-177">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="7fef6-178">Selezionare *Start Training* (Avvia training).</span><span class="sxs-lookup"><span data-stu-id="7fef6-178">Select *Start Training*.</span></span>

<span data-ttu-id="7fef6-179">Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.</span><span class="sxs-lookup"><span data-stu-id="7fef6-179">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="7fef6-180">Stato visualizza lo stato di completamento del processo di training.</span><span class="sxs-lookup"><span data-stu-id="7fef6-180">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="7fef6-181">Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="7fef6-181">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="7fef6-182">Precisione maggiore indica il modello stimato più correttamente con i dati di test.</span><span class="sxs-lookup"><span data-stu-id="7fef6-182">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="7fef6-183">Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="7fef6-183">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="7fef6-184">Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="7fef6-184">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="7fef6-185">Una volta completato il training, passare alla valutazione.</span><span class="sxs-lookup"><span data-stu-id="7fef6-185">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="7fef6-186">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="7fef6-186">Evaluate the model</span></span>

<span data-ttu-id="7fef6-187">Il risultato del passaggio relativo al training è rappresentato dal modello con le prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="7fef6-187">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="7fef6-188">Nel passaggio di valutazione dello strumento generatore di modelli la sezione di output conterrà l'algoritmo usato dal modello con le prestazioni migliori nella voce *Best model* (Modello migliore), insieme con le metriche in *Best Model Quality (RSquared)* (Qualità modello migliore).</span><span class="sxs-lookup"><span data-stu-id="7fef6-188">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="7fef6-189">Viene visualizzata anche una tabella di riepilogo con i cinque modelli migliori e le metriche relative.</span><span class="sxs-lookup"><span data-stu-id="7fef6-189">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="7fef6-190">Se non si è soddisfatti della precisione delle metriche,un modo semplice per migliorarla consiste nell'aumentare la durata del training del modello o nell'usare più dati.</span><span class="sxs-lookup"><span data-stu-id="7fef6-190">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="7fef6-191">In caso contrario, passare al passaggio del codice.</span><span class="sxs-lookup"><span data-stu-id="7fef6-191">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="7fef6-192">Aggiungere il codice per eseguire stime</span><span class="sxs-lookup"><span data-stu-id="7fef6-192">Add the code to make predictions</span></span>

<span data-ttu-id="7fef6-193">Il risultato del processo di training sarà la creazione di due progetti.</span><span class="sxs-lookup"><span data-stu-id="7fef6-193">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="7fef6-194">TaxiFarePredictionML.ConsoleApp: un'applicazione console .NET Core che contiene il codice del modello di training e il consumo.</span><span class="sxs-lookup"><span data-stu-id="7fef6-194">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="7fef6-195">TaxiFarePredictionML.Model: una libreria di classi .NET Standard che contiene i modelli di dati che definiscono lo schema di input e output dei dati del modello, nonché la versione persistente del modello che ha avuto le prestazioni migliori durante il training.</span><span class="sxs-lookup"><span data-stu-id="7fef6-195">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="7fef6-196">Nel passaggio del codice dello strumento generatore di modelli selezionare **Add Projects** (Aggiungi progetti) per aggiungere i progetti generati automaticamente alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="7fef6-196">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="7fef6-197">Fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="7fef6-197">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="7fef6-198">In seguito, selezionare **Aggiungi > Riferimento**.</span><span class="sxs-lookup"><span data-stu-id="7fef6-198">Then, **Add > Reference**.</span></span> <span data-ttu-id="7fef6-199">Scegliere il nodo **Progetti > Soluzione** e dall'elenco contrassegnare il progetto *TaxiFarePredictionML.Model* e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7fef6-199">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>
1. <span data-ttu-id="7fef6-200">Aprire il file *Program.cs* nel progetto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="7fef6-200">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="7fef6-201">Aggiungere le istruzioni using seguenti per fare riferimento al pacchetto NuGet *Microsoft.ML* e al progetto *TaxiFarePredictionML.Model*:</span><span class="sxs-lookup"><span data-stu-id="7fef6-201">Add the following using statements to reference the *Microsoft.ML* NuGet package and *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

1. <span data-ttu-id="7fef6-202">Aggiungere il metodo `ConsumeModel` alla classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="7fef6-202">Add the `ConsumeModel` method to the `Program` class.</span></span>

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

    <span data-ttu-id="7fef6-203">`ConsumeModel` caricherà il modello sottoposto a training, creerà un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) per il modello e lo userà per eseguire stime sui nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="7fef6-203">The `ConsumeModel` will load the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and use it to make predictions on new data.</span></span>

1. <span data-ttu-id="7fef6-204">Per eseguire una stima sui nuovi dati usando il modello, creare una nuova istanza della classe `ModelInput` e usare il metodo `ConsumeModel`.</span><span class="sxs-lookup"><span data-stu-id="7fef6-204">To make a prediction on new data using the model, create a new instance of the `ModelInput` class and use the `ConsumeModel` method.</span></span> <span data-ttu-id="7fef6-205">Si noti che l'importo della tariffa non fa parte dell'input,</span><span class="sxs-lookup"><span data-stu-id="7fef6-205">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="7fef6-206">perché il modello genererà la stima per tale importo.</span><span class="sxs-lookup"><span data-stu-id="7fef6-206">This is because the model will generate the prediction for it.</span></span> <span data-ttu-id="7fef6-207">Aggiungere il codice seguente al metodo `Main` ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7fef6-207">Add the following code to the `Main` method and run the application</span></span>

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

    <span data-ttu-id="7fef6-208">L'output generato dal programma dovrebbe essere simile al frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="7fef6-208">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="7fef6-209">Se in un secondo momento è necessario fare riferimento ai progetti generati all'interno di un'altra soluzione, è possibile trovarli all'interno della directory `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="7fef6-209">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7fef6-210">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7fef6-210">Next Steps</span></span>

<span data-ttu-id="7fef6-211">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="7fef6-211">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="7fef6-212">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-212">Prepare and understand the data</span></span>
> * <span data-ttu-id="7fef6-213">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="7fef6-213">Choose a scenario</span></span>
> * <span data-ttu-id="7fef6-214">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="7fef6-214">Load the data</span></span>
> * <span data-ttu-id="7fef6-215">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="7fef6-215">Train the model</span></span>
> * <span data-ttu-id="7fef6-216">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="7fef6-216">Evaluate the model</span></span>
> * <span data-ttu-id="7fef6-217">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="7fef6-217">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7fef6-218">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7fef6-218">Additional Resources</span></span>

<span data-ttu-id="7fef6-219">Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fef6-219">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="7fef6-220">Scenari del generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="7fef6-220">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="7fef6-221">Formati di dati del generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="7fef6-221">Model Builder Data Formats</span></span>](../automate-training-with-model-builder.md#data-formats)
- [<span data-ttu-id="7fef6-222">Regressione</span><span class="sxs-lookup"><span data-stu-id="7fef6-222">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="7fef6-223">Metriche del modello di regressione</span><span class="sxs-lookup"><span data-stu-id="7fef6-223">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="7fef6-224">Set di dati NYC TLC Taxi Trip</span><span class="sxs-lookup"><span data-stu-id="7fef6-224">NYC TLC Taxi Trip data set</span></span>](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)
