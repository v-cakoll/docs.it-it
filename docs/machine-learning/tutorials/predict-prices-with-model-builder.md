---
title: 'Esercitazione: Stimare i prezzi usando la regressione con il generatore di modelli'
description: Questa esercitazione illustra come creare un modello di regressione usando il generatore di modelli ML.NET per stimare i prezzi, nel caso specifico le tariffe dei taxi di New York.
author: luisquintanilla
ms.author: luquinta
ms.date: 10/08/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a851bf3c405d15243bc1457b8c3dff815d072ebe
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180278"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="f54a2-103">Esercitazione: Stimare i prezzi usando la regressione con il generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="f54a2-103">Tutorial: Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="f54a2-104">Informazioni su come usare il generatore di modelli ML.NET per creare un modello di regressione per stimare i prezzi.</span><span class="sxs-lookup"><span data-stu-id="f54a2-104">Learn how to use ML.NET Model Builder to build a regression model to predict prices.</span></span>  <span data-ttu-id="f54a2-105">L'app console .NET che viene sviluppata in questa esercitazione consente di stimare le tariffe dei taxi di New York in base ai relativi dati storici.</span><span class="sxs-lookup"><span data-stu-id="f54a2-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="f54a2-106">Il modello di stima dei prezzi del generatore di modelli può essere usato in qualsiasi scenario che richieda un valore numerico di stima.</span><span class="sxs-lookup"><span data-stu-id="f54a2-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="f54a2-107">Tra gli scenari di esempio vi sono la stima dei prezzi delle abitazioni, la stima della domanda e le previsioni di vendita.</span><span class="sxs-lookup"><span data-stu-id="f54a2-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="f54a2-108">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="f54a2-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f54a2-109">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="f54a2-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="f54a2-110">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="f54a2-110">Choose a scenario</span></span>
> - <span data-ttu-id="f54a2-111">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="f54a2-111">Load the data</span></span>
> - <span data-ttu-id="f54a2-112">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="f54a2-112">Train the model</span></span>
> - <span data-ttu-id="f54a2-113">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="f54a2-113">Evaluate the model</span></span>
> - <span data-ttu-id="f54a2-114">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="f54a2-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="f54a2-115">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="f54a2-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="f54a2-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f54a2-116">Pre-requisites</span></span>

<span data-ttu-id="f54a2-117">Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f54a2-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f54a2-118">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="f54a2-118">Create a console application</span></span>

1. <span data-ttu-id="f54a2-119">Creare un'**applicazione console di .NET Core** con nome "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="f54a2-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="f54a2-120">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="f54a2-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="f54a2-121">Creare una directory denominata *Dati* nel progetto per archiviare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="f54a2-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="f54a2-122">Il set di dati usato per il training e la valutazione del modello di Machine Learning è ricavato in origine dal set di dati NYC TLC Taxi Trip.</span><span class="sxs-lookup"><span data-stu-id="f54a2-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    1. <span data-ttu-id="f54a2-123">Per scaricare il set di dati, passare al [collegamento per il download di taxi-fare-train.csv](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="f54a2-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    1. <span data-ttu-id="f54a2-124">Quando si carica la pagina, fare clic con il pulsante destro del mouse in un punto qualsiasi della pagina e scegliere **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="f54a2-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    1. <span data-ttu-id="f54a2-125">Usare la **finestra di dialogo Salva con nome** per salvare il file nella cartella *Dati* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="f54a2-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="f54a2-126">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *taxi-fare-train.csv* e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f54a2-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="f54a2-127">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="f54a2-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="f54a2-128">Ogni riga del set di dati `taxi-fare-train.csv` contiene i dettagli delle corse effettuate da un taxi.</span><span class="sxs-lookup"><span data-stu-id="f54a2-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="f54a2-129">Aprire il set di dati **taxi-fare-train.csv**</span><span class="sxs-lookup"><span data-stu-id="f54a2-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="f54a2-130">Il set di dati fornito contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="f54a2-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="f54a2-131">**vendor_id:** l'ID della società di taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f54a2-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="f54a2-132">**rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f54a2-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="f54a2-133">**passenger_count:** il numero di passeggeri è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f54a2-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="f54a2-134">**trip_time_in_secs:** il tempo impiegato per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="f54a2-134">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f54a2-135">Si vuole stimare la tariffa del viaggio prima del termine.</span><span class="sxs-lookup"><span data-stu-id="f54a2-135">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="f54a2-136">Al momento non si conosce la durata del viaggio.</span><span class="sxs-lookup"><span data-stu-id="f54a2-136">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="f54a2-137">Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.</span><span class="sxs-lookup"><span data-stu-id="f54a2-137">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    - <span data-ttu-id="f54a2-138">**trip_distance:** la distanza del viaggio è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f54a2-138">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="f54a2-139">**payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f54a2-139">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="f54a2-140">**fare_amount:** la tariffa totale corrisposta per il viaggio in taxi è l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f54a2-140">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="f54a2-141">`label` è la colonna sulla quale eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="f54a2-141">The `label` is the column you want to predict.</span></span> <span data-ttu-id="f54a2-142">Quando si esegue un'attività di regressione, l'obiettivo è stimare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="f54a2-142">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="f54a2-143">In questo scenario di stima dei prezzi viene stimato il costo di una corsa in taxi.</span><span class="sxs-lookup"><span data-stu-id="f54a2-143">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="f54a2-144">Pertanto, l'etichetta è **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="f54a2-144">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="f54a2-145">Gli elementi identificati `features` sono gli input che vengono dati al modello per stimare l'oggetto `label`.</span><span class="sxs-lookup"><span data-stu-id="f54a2-145">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="f54a2-146">In questo caso, il resto delle colonne, ad eccezione di **trip_time_in_secs** , viene usato come funzionalità o input per stimare l'importo della tariffa.</span><span class="sxs-lookup"><span data-stu-id="f54a2-146">In this case, the rest of the columns with the exception of **trip_time_in_secs** are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="f54a2-147">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="f54a2-147">Choose a scenario</span></span>

<span data-ttu-id="f54a2-148">Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="f54a2-148">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="f54a2-149">In questo caso lo scenario è `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="f54a2-149">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="f54a2-150">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Aggiungi** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="f54a2-150">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="f54a2-151">Nel passaggio relativo allo scenario dello strumento generatore di modelli, selezionare *Price Prediction*.</span><span class="sxs-lookup"><span data-stu-id="f54a2-151">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="f54a2-152">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="f54a2-152">Load the data</span></span>

<span data-ttu-id="f54a2-153">Il generatore di modelli accetta i dati da due origini, un database di SQL Server o un file locale in formato csv o tsv.</span><span class="sxs-lookup"><span data-stu-id="f54a2-153">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="f54a2-154">Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare *File* dall'elenco a discesa delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="f54a2-154">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="f54a2-155">Selezionare il pulsante accanto alla casella di testo *Seleziona un file* e usare Esplora File per cercare e selezionare *taxi-fare-test.csv* nella directory *Dati*.</span><span class="sxs-lookup"><span data-stu-id="f54a2-155">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="f54a2-156">Scegliere *fare_amount* nell'elenco *a discesa colonna da stimare (etichetta)* e passare al passaggio del training dello strumento generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="f54a2-156">Choose *fare_amount* in the *Column to Predict (Label)* dropdown and navigate to the train step of the Model Builder tool.</span></span>
1. <span data-ttu-id="f54a2-157">Espandere l'elenco a discesa *colonne di input (funzionalità)* e deselezionare la colonna *trip_time_in_secs* per escluderla come funzionalità durante il training.</span><span class="sxs-lookup"><span data-stu-id="f54a2-157">Expand the *Input Columns (Features)* dropdown and uncheck the *trip_time_in_secs* column to exclude it as a feature during training.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="f54a2-158">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="f54a2-158">Train the model</span></span>

<span data-ttu-id="f54a2-159">L'attività di Machine Learning usata per eseguire il training del modello di stima dei prezzi in questa esercitazione è la regressione.</span><span class="sxs-lookup"><span data-stu-id="f54a2-159">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="f54a2-160">Durante il processo di training del modello, il generatore di modelli esegue il training di modelli separati usando impostazioni e algoritmi di regressione diversi per individuare il modello di prestazioni migliore per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="f54a2-160">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="f54a2-161">Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="f54a2-161">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="f54a2-162">Generatore di modelli seleziona automaticamente un valore predefinito per il **tempo di training (secondi)** in base alle dimensioni dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f54a2-162">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="f54a2-163">Lasciare il valore predefinito così come è il *tempo per il training (secondi)* , a meno che non si preferisca eseguire il training per un periodo di tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="f54a2-163">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="f54a2-164">Selezionare *Start Training* (Avvia training).</span><span class="sxs-lookup"><span data-stu-id="f54a2-164">Select *Start Training*.</span></span>

<span data-ttu-id="f54a2-165">Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.</span><span class="sxs-lookup"><span data-stu-id="f54a2-165">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="f54a2-166">Stato visualizza lo stato di completamento del processo di training.</span><span class="sxs-lookup"><span data-stu-id="f54a2-166">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="f54a2-167">Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="f54a2-167">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="f54a2-168">Precisione maggiore indica il modello stimato più correttamente con i dati di test.</span><span class="sxs-lookup"><span data-stu-id="f54a2-168">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="f54a2-169">Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="f54a2-169">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="f54a2-170">Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="f54a2-170">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="f54a2-171">Una volta completato il training, passare alla valutazione.</span><span class="sxs-lookup"><span data-stu-id="f54a2-171">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="f54a2-172">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="f54a2-172">Evaluate the model</span></span>

<span data-ttu-id="f54a2-173">Il risultato del passaggio relativo al training è rappresentato dal modello con le prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="f54a2-173">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="f54a2-174">Nel passaggio di valutazione dello strumento generatore di modelli la sezione di output conterrà l'algoritmo usato dal modello con le prestazioni migliori nella voce *Best model* (Modello migliore), insieme con le metriche in *Best Model Quality (RSquared)* (Qualità modello migliore).</span><span class="sxs-lookup"><span data-stu-id="f54a2-174">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="f54a2-175">Viene visualizzata anche una tabella di riepilogo con i cinque modelli migliori e le metriche relative.</span><span class="sxs-lookup"><span data-stu-id="f54a2-175">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="f54a2-176">Se non si è soddisfatti della precisione delle metriche,un modo semplice per migliorarla consiste nell'aumentare la durata del training del modello o nell'usare più dati.</span><span class="sxs-lookup"><span data-stu-id="f54a2-176">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="f54a2-177">In caso contrario, passare al passaggio del codice.</span><span class="sxs-lookup"><span data-stu-id="f54a2-177">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="f54a2-178">Aggiungere il codice per eseguire stime</span><span class="sxs-lookup"><span data-stu-id="f54a2-178">Add the code to make predictions</span></span>

<span data-ttu-id="f54a2-179">Il risultato del processo di training sarà la creazione di due progetti.</span><span class="sxs-lookup"><span data-stu-id="f54a2-179">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="f54a2-180">TaxiFarePredictionML.ConsoleApp: Applicazione console .NET Core che contiene il codice di training del modello e il codice di consumo di esempio.</span><span class="sxs-lookup"><span data-stu-id="f54a2-180">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and sample consumption code.</span></span>
- <span data-ttu-id="f54a2-181">TaxiFarePredictionML.Model: Una libreria di classi .NET Standard contenente i modelli di dati che definiscono lo schema dei dati del modello di input e di output, la versione salvata del modello con le prestazioni migliori durante il training e una classe helper denominata `ConsumeModel` per eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="f54a2-181">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data, the saved version of the best performing model during training and a helper class called `ConsumeModel` to make predictions.</span></span>

1. <span data-ttu-id="f54a2-182">Nel passaggio del codice dello strumento generatore di modelli selezionare **Add Projects** (Aggiungi progetti) per aggiungere i progetti generati automaticamente alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f54a2-182">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="f54a2-183">Aprire il file *Program.cs* nel progetto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="f54a2-183">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="f54a2-184">Aggiungere l'istruzione using seguente per fare riferimento al progetto *TaxiFarePredictionML. Model* :</span><span class="sxs-lookup"><span data-stu-id="f54a2-184">Add the following using statement to reference the *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. <span data-ttu-id="f54a2-185">Per eseguire una stima sui nuovi dati utilizzando il modello, creare una nuova istanza della classe `ModelInput` all'interno del metodo `Main` dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f54a2-185">To make a prediction on new data using the model, create a new instance of the `ModelInput` class inside the `Main` method of your application.</span></span> <span data-ttu-id="f54a2-186">Si noti che l'importo della tariffa non fa parte dell'input,</span><span class="sxs-lookup"><span data-stu-id="f54a2-186">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="f54a2-187">perché il modello genererà la stima per tale importo.</span><span class="sxs-lookup"><span data-stu-id="f54a2-187">This is because the model will generate the prediction for it.</span></span> 

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. <span data-ttu-id="f54a2-188">Usare il metodo `Predict` dalla classe `ConsumeModel`.</span><span class="sxs-lookup"><span data-stu-id="f54a2-188">Use the `Predict` method from the `ConsumeModel` class.</span></span> <span data-ttu-id="f54a2-189">Il metodo `Predict` carica il modello sottoposto a training, crea una [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) per il modello e la utilizza per eseguire stime sui nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="f54a2-189">The `Predict` method loads the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and uses it to make predictions on new data.</span></span> 

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. <span data-ttu-id="f54a2-190">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f54a2-190">Run the application.</span></span>

    <span data-ttu-id="f54a2-191">L'output generato dal programma dovrebbe essere simile al frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f54a2-191">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 14.96086
    ```

<span data-ttu-id="f54a2-192">Se in un secondo momento è necessario fare riferimento ai progetti generati all'interno di un'altra soluzione, è possibile trovarli all'interno della directory `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="f54a2-192">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f54a2-193">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f54a2-193">Next Steps</span></span>

<span data-ttu-id="f54a2-194">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="f54a2-194">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f54a2-195">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="f54a2-195">Prepare and understand the data</span></span>
> - <span data-ttu-id="f54a2-196">Scegliere uno scenario</span><span class="sxs-lookup"><span data-stu-id="f54a2-196">Choose a scenario</span></span>
> - <span data-ttu-id="f54a2-197">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="f54a2-197">Load the data</span></span>
> - <span data-ttu-id="f54a2-198">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="f54a2-198">Train the model</span></span>
> - <span data-ttu-id="f54a2-199">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="f54a2-199">Evaluate the model</span></span>
> - <span data-ttu-id="f54a2-200">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="f54a2-200">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f54a2-201">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f54a2-201">Additional Resources</span></span>

<span data-ttu-id="f54a2-202">Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="f54a2-202">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="f54a2-203">Scenari del generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="f54a2-203">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="f54a2-204">Regressione</span><span class="sxs-lookup"><span data-stu-id="f54a2-204">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="f54a2-205">Metriche del modello di regressione</span><span class="sxs-lookup"><span data-stu-id="f54a2-205">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="f54a2-206">Set di dati NYC TLC Taxi Trip</span><span class="sxs-lookup"><span data-stu-id="f54a2-206">NYC TLC Taxi Trip data set</span></span>](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)
