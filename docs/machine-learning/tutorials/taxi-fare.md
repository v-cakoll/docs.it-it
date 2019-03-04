---
title: Eseguire una stima dei prezzi usando un algoritmo di apprendimento basato sulla regressione con ML.NET
description: Eseguire una stima dei prezzi usando un algoritmo di apprendimento basato sulla regressione con ML.NET.
author: aditidugar
ms.author: johalex
ms.date: 02/08/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: d9c87c4f4a81c02979259a47e8c4167d80f06377
ms.sourcegitcommit: a532e8314c3a4b5b039656567fedff9787a31957
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251092"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a><span data-ttu-id="ac784-103">Esercitazione: Eseguire una stima dei prezzi usando un algoritmo di apprendimento basato sulla regressione con ML.NET</span><span class="sxs-lookup"><span data-stu-id="ac784-103">Tutorial: Predict prices using a regression learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="ac784-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="ac784-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ac784-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="ac784-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ac784-106">Questa esercitazione illustra come usare ML.NET per creare un [modello di regressione](../resources/glossary.md#regression) per la stima dei prezzi, precisamente delle tariffe dei taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="ac784-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting prices, specifically, New York City taxi fares.</span></span>

<span data-ttu-id="ac784-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="ac784-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="ac784-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ac784-108">Understand the problem</span></span>
> * <span data-ttu-id="ac784-109">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="ac784-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="ac784-110">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="ac784-110">Prepare and understand the data</span></span>
> * <span data-ttu-id="ac784-111">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ac784-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="ac784-112">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="ac784-112">Load and transform the data</span></span>
> * <span data-ttu-id="ac784-113">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ac784-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="ac784-114">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ac784-114">Train the model</span></span>
> * <span data-ttu-id="ac784-115">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="ac784-115">Evaluate the model</span></span>
> * <span data-ttu-id="ac784-116">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="ac784-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac784-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ac784-117">Prerequisites</span></span>

* <span data-ttu-id="ac784-118">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="ac784-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="ac784-119">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ac784-119">Understand the problem</span></span>

<span data-ttu-id="ac784-120">Questo problema riguarda la stima della tariffa di un viaggio in taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="ac784-120">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="ac784-121">A prima vista, potrebbe sembrare dipendere semplicemente dalla distanza percorsa.</span><span class="sxs-lookup"><span data-stu-id="ac784-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="ac784-122">Tuttavia, le società di taxi di New York applicano un addebito per quantità variabili di altri fattori, come i passeggeri aggiuntivi o il pagamento tramite carta di credito anziché in contanti.</span><span class="sxs-lookup"><span data-stu-id="ac784-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="ac784-123">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="ac784-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="ac784-124">Si vuole stimare il valore del prezzo, ovvero un valore reale, in base ad altri fattori nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-124">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="ac784-125">Per fare ciò, scegliere un'attività di apprendimento automatico di tipo [regressione](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="ac784-125">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="ac784-126">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="ac784-126">Create a console application</span></span>

1. <span data-ttu-id="ac784-127">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ac784-127">Open Visual Studio 2017.</span></span> <span data-ttu-id="ac784-128">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="ac784-128">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="ac784-129">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="ac784-129">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="ac784-130">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="ac784-130">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="ac784-131">Nella casella di testo **Nome** digitare "TaxiFarePrediction" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac784-131">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="ac784-132">Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati e del modello:</span><span class="sxs-lookup"><span data-stu-id="ac784-132">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="ac784-133">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="ac784-133">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="ac784-134">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="ac784-134">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="ac784-135">Installare il pacchetto NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="ac784-135">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="ac784-136">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="ac784-136">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="ac784-137">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda **Sfoglia**, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="ac784-137">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="ac784-138">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="ac784-138">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="ac784-139">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="ac784-139">Prepare and understand the data</span></span>

1. <span data-ttu-id="ac784-140">Scaricare i set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) e salvarli nella cartella *Data* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="ac784-140">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="ac784-141">Questi set di dati vengono usati per eseguire il training del modello di machine learning e quindi valutarne l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="ac784-141">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="ac784-142">Questi set di dati sono originariamente ricavati dal [set di dati NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="ac784-142">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="ac784-143">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su ognuno dei file \*.csv e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ac784-143">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="ac784-144">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="ac784-144">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="ac784-145">Aprire il set di dati **taxi-fare-train.csv** e controllare le intestazioni di colonna nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="ac784-145">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="ac784-146">Esaminare ognuna delle colonne.</span><span class="sxs-lookup"><span data-stu-id="ac784-146">Take a look at each of the columns.</span></span> <span data-ttu-id="ac784-147">Identificare i dati e decidere quali colonne sono **funzionalità** e qual è l'**etichetta**.</span><span class="sxs-lookup"><span data-stu-id="ac784-147">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="ac784-148">L'**etichetta** è l'identificatore della colonna che si vuole stimare.</span><span class="sxs-lookup"><span data-stu-id="ac784-148">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="ac784-149">Le **funzionalità** identificate vengono usate per stimare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="ac784-149">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="ac784-150">Il set di dati fornito contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac784-150">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="ac784-151">**vendor_id:** l'ID della società di taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ac784-151">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="ac784-152">**rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ac784-152">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="ac784-153">**passenger_count:** il numero di passeggeri è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ac784-153">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="ac784-154">**trip_time_in_secs:** il tempo impiegato per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="ac784-154">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="ac784-155">Si vuole stimare la tariffa del viaggio prima del termine.</span><span class="sxs-lookup"><span data-stu-id="ac784-155">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="ac784-156">Al momento non si conosce la durata del viaggio.</span><span class="sxs-lookup"><span data-stu-id="ac784-156">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="ac784-157">Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-157">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="ac784-158">**trip_distance:** la distanza del viaggio è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ac784-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="ac784-159">**payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ac784-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="ac784-160">**fare_amount:** la tariffa totale corrisposta per il viaggio in taxi è l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="ac784-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="ac784-161">Creare classi di dati</span><span class="sxs-lookup"><span data-stu-id="ac784-161">Create data classes</span></span>

<span data-ttu-id="ac784-162">Creare le classi per i dati di input e le stime:</span><span class="sxs-lookup"><span data-stu-id="ac784-162">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="ac784-163">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ac784-163">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="ac784-164">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="ac784-164">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="ac784-165">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ac784-165">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="ac784-166">Aggiungere le direttive `using` seguenti al nuovo file:</span><span class="sxs-lookup"><span data-stu-id="ac784-166">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="ac784-167">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="ac784-167">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="ac784-168">`TaxiTrip` è la classe dei dati di input e contiene le definizioni per ognuna delle colonne del set di dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-168">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="ac784-169">Usare l'attributo <xref:Microsoft.ML.Data.ColumnAttribute> per specificare gli indici delle colonne di origine nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-169">Use the <xref:Microsoft.ML.Data.ColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="ac784-170">La classe `TaxiTripFarePrediction` rappresenta i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="ac784-170">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="ac784-171">Ha un singolo campo float, `FareAmount`, a cui è applicato un attributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ac784-171">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="ac784-172">Nel caso dell'attività di regressione, la colonna **Score** contiene i valori delle etichette previsti.</span><span class="sxs-lookup"><span data-stu-id="ac784-172">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="ac784-173">Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.</span><span class="sxs-lookup"><span data-stu-id="ac784-173">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="ac784-174">Definire i percorsi dei dati e del modello</span><span class="sxs-lookup"><span data-stu-id="ac784-174">Define data and model paths</span></span>

<span data-ttu-id="ac784-175">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ac784-175">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="ac784-176">È necessario creare tre campi per i percorsi dei file con i set di dati e del file per il salvataggio del modello, oltre a una variabile globale per l'istanza di `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="ac784-176">You need to create three fields to hold the paths to the files with data sets and the file to save the model, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="ac784-177">`_trainDataPath` contiene il percorso del file con il set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-177">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="ac784-178">`_testDataPath` contiene il percorso del file con il set di dati usato per la valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-178">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="ac784-179">`_modelPath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="ac784-179">`_modelPath` contains the path to the file where the trained model is stored.</span></span>
* <span data-ttu-id="ac784-180">`_textLoader` è l'istanza della classe <xref:Microsoft.ML.Data.TextLoader> usata per caricare e trasformare i set di dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-180">`_textLoader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="ac784-181">Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi e per la variabile `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="ac784-181">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="ac784-182">Quando si crea un modello con ML.NET, si inizia creando un contesto di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="ac784-182">When building a model with ML.NET you start by creating an ML Context.</span></span> <span data-ttu-id="ac784-183">A livello concettuale questa operazione è paragonabile all'uso di `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ac784-183">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="ac784-184">L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ac784-184">The environment provides a context for your machine learning job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="ac784-185">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="ac784-185">Initialize variables in Main</span></span>

<span data-ttu-id="ac784-186">Creare una variabile denominata `mlContext` e inizializzarla con una nuova istanza di `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="ac784-186">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="ac784-187">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="ac784-187">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="ac784-188">Successivamente, per configurare il caricamento dei dati, inizializzare la variabile globale `_textLoader` in modo da poterla riutilizzare.</span><span class="sxs-lookup"><span data-stu-id="ac784-188">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span> <span data-ttu-id="ac784-189">Quando si crea un'istanza di `TextLoader` si passa il contesto necessario e la classe <xref:Microsoft.ML.Data.TextLoader.Arguments>che consente la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac784-189">When you create a `TextLoader`, you pass in the context needed and the <xref:Microsoft.ML.Data.TextLoader.Arguments> class which enables customization.</span></span> <span data-ttu-id="ac784-190">Specificare lo schema di dati passando una matrice di oggetti <xref:Microsoft.ML.Data.TextLoader.Column> all'istanza di `TextLoader` contenente tutti i nomi delle colonne e i relativi tipi.</span><span class="sxs-lookup"><span data-stu-id="ac784-190">Specify the data schema by passing an array of <xref:Microsoft.ML.Data.TextLoader.Column> objects to the `TextLoader` containing all the column names and their types.</span></span> <span data-ttu-id="ac784-191">Lo schema di dati è stato definito in precedenza quando si è creata la classe `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="ac784-191">We defined the data schema previously when we created our `TaxiTrip` class.</span></span>

<span data-ttu-id="ac784-192">La classe `TextLoader` restituisce un'istanza di <xref:Microsoft.ML.Data.TextLoader> completamente inizializzata.</span><span class="sxs-lookup"><span data-stu-id="ac784-192">The `TextLoader` class returns a fully initialized <xref:Microsoft.ML.Data.TextLoader></span></span>  

<span data-ttu-id="ac784-193">Per inizializzare la variabile globale `_textLoader` in modo da riutilizzarla per i set di dati necessari, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="ac784-193">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Initialize the TextLoader")]

<span data-ttu-id="ac784-194">Aggiungere il codice seguente come riga successiva nel metodo `Main` per chiamare il metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="ac784-194">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="ac784-195">Il metodo `Train` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac784-195">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="ac784-196">Carica i dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-196">Loads the data.</span></span>
* <span data-ttu-id="ac784-197">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-197">Extracts and transforms the data.</span></span>
* <span data-ttu-id="ac784-198">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-198">Trains the model.</span></span>
* <span data-ttu-id="ac784-199">Salva il modello come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="ac784-199">Saves the model as .zip file.</span></span>
* <span data-ttu-id="ac784-200">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-200">Returns the model.</span></span>

<span data-ttu-id="ac784-201">Il metodo `Train` esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-201">The `Train` method trains the model.</span></span> <span data-ttu-id="ac784-202">Creare il metodo subito sotto `Main` usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-202">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="ac784-203">In questo modo vengono passati due parametri al metodo `Train`: `MLContext` per il contesto (`mlContext`) e una stringa per il percorso del set di dati (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="ac784-203">We are passing two parameters into the `Train` method; an `MLContext` for the context (`mlContext`), and a string for the dataset path (`dataPath`).</span></span> <span data-ttu-id="ac784-204">Questo metodo verrà usato di nuovo per il caricamento dei set di dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-204">We're going to reuse this method for loading datasets.</span></span>

## <a name="load-and-transform-data"></a><span data-ttu-id="ac784-205">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="ac784-205">Load and transform data</span></span>

<span data-ttu-id="ac784-206">Si caricheranno i dati usando la variabile globale `_textLoader` con il parametro `dataPath`.</span><span class="sxs-lookup"><span data-stu-id="ac784-206">We'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="ac784-207">Verrà restituita un'istanza di <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="ac784-207">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> <span data-ttu-id="ac784-208">Come input e output delle trasformazioni, una `IDataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="ac784-208">As the input and output of Transforms, an `IDataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="ac784-209">In ML.NET i dati sono simili a una visualizzazione SQL.</span><span class="sxs-lookup"><span data-stu-id="ac784-209">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="ac784-210">Vengono valutati in modalità differita, sono schematizzati ed eterogenei.</span><span class="sxs-lookup"><span data-stu-id="ac784-210">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="ac784-211">L'oggetto è la prima parte della pipeline e carica i dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-211">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="ac784-212">Per questa esercitazione, carica un set di dati con le informazioni sulle corse in taxi che sono utili per eseguire una stima delle tariffe.</span><span class="sxs-lookup"><span data-stu-id="ac784-212">For this tutorial, it loads a dataset with taxi trip information useful to predict fares.</span></span> <span data-ttu-id="ac784-213">Queste informazioni vengono usate per creare il modello ed eseguirne il training.</span><span class="sxs-lookup"><span data-stu-id="ac784-213">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="ac784-214">Aggiungere il codice seguente come prima riga del metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="ac784-214">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="ac784-215">Nei passaggi successivi si fa riferimento alle colonne in base ai nomi definiti nella classe `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="ac784-215">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="ac784-216">Quando vengono eseguiti il training e la valutazione del modello, i valori nella colonna **Label** vengono considerati per impostazione predefinita come valori corretti da stimare.</span><span class="sxs-lookup"><span data-stu-id="ac784-216">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="ac784-217">Dato che si vuole stimare la tariffa del viaggio in taxi, copiare la colonna `FareAmount` nella colonna **Label**.</span><span class="sxs-lookup"><span data-stu-id="ac784-217">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="ac784-218">A tale scopo, usare la classe di trasformazione `CopyColumnsEstimator` e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-218">To do that, use the `CopyColumnsEstimator` transformation class, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="ac784-219">Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri.</span><span class="sxs-lookup"><span data-stu-id="ac784-219">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers.</span></span> <span data-ttu-id="ac784-220">A questo scopo, usare la classe di trasformazione `OneHotEncodingEstimator`, che assegna valori chiave numerici diversi ai vari valori in ogni colonna e aggiunge il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-220">To do that, use the `OneHotEncodingEstimator` transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="ac784-221">L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione `ColumnConcatenatingEstimator`.</span><span class="sxs-lookup"><span data-stu-id="ac784-221">The last step in data preparation combines all of the feature columns into the **Features** column using the `ColumnConcatenatingEstimator` transformation class.</span></span> <span data-ttu-id="ac784-222">Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**.</span><span class="sxs-lookup"><span data-stu-id="ac784-222">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="ac784-223">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-223">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="ac784-224">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ac784-224">Choose a learning algorithm</span></span>

<span data-ttu-id="ac784-225">Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, si seleziona un **algoritmo di apprendimento**.</span><span class="sxs-lookup"><span data-stu-id="ac784-225">After adding the data to the pipeline and transforming it into the correct input format, we select a learning algorithm (**learner**).</span></span> <span data-ttu-id="ac784-226">L'algoritmo di apprendimento esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-226">The learner trains the model.</span></span> <span data-ttu-id="ac784-227">Per questo problema è stata scelta un'attività di **regressione** ed è quindi necessario usare un algoritmo di apprendimento `FastTreeRegressionTrainer`, che è uno degli algoritmi di apprendimento basati sulla regressione disponibili in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ac784-227">We chose a **regression** task for this problem, so we use a `FastTreeRegressionTrainer` learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="ac784-228">L'algoritmo di apprendimento `FastTreeRegressionTrainer` utilizza la tecnica di gradient boosting.</span><span class="sxs-lookup"><span data-stu-id="ac784-228">The `FastTreeRegressionTrainer` learner utilizes gradient boosting.</span></span> <span data-ttu-id="ac784-229">L'incremento dei gradienti è una tecnica di apprendimento automatico per i problemi di regressione.</span><span class="sxs-lookup"><span data-stu-id="ac784-229">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="ac784-230">Compila ogni albero di regressione tenendo conto dei singoli passaggi.</span><span class="sxs-lookup"><span data-stu-id="ac784-230">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="ac784-231">Usa una funzione di perdita predefinita per misurare l'errore in ogni passaggio e correggerlo in quello successivo.</span><span class="sxs-lookup"><span data-stu-id="ac784-231">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="ac784-232">Il risultato è un modello di stima che è effettivamente un insieme dei modelli di stima più deboli.</span><span class="sxs-lookup"><span data-stu-id="ac784-232">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="ac784-233">Per altre informazioni sull'incremento dei gradienti, vedere [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regressione dell'albero delle decisioni con incremento).</span><span class="sxs-lookup"><span data-stu-id="ac784-233">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="ac784-234">Aggiungere il codice seguente nel metodo `Train` per includere l'algoritmo `FastTreeRegressionTrainer` nel codice di elaborazione dei dati aggiunto nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="ac784-234">Add the following code into the `Train` method to add the `FastTreeRegressionTrainer` to the data processing code added in the previous step:</span></span>

[!code-csharp[FastTreeRegressionTrainer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="ac784-235">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ac784-235">Train the model</span></span>

<span data-ttu-id="ac784-236">Il passaggio finale consiste nel training del modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-236">The final step is to train the model.</span></span> <span data-ttu-id="ac784-237">Il training del modello, <xref:Microsoft.ML.Data.TransformerChain>, viene eseguito in base al set di dati caricato e trasformato.</span><span class="sxs-lookup"><span data-stu-id="ac784-237">We train the model, <xref:Microsoft.ML.Data.TransformerChain>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="ac784-238">Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati.</span><span class="sxs-lookup"><span data-stu-id="ac784-238">Once the estimator has been defined, we train the model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="ac784-239">Viene così restituito un modello da usare per le stime.</span><span class="sxs-lookup"><span data-stu-id="ac784-239">This returns a model to use for predictions.</span></span> <span data-ttu-id="ac784-240">`pipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata.</span><span class="sxs-lookup"><span data-stu-id="ac784-240">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="ac784-241">L'esperimento non viene eseguito finché questa operazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ac784-241">The experiment is not executed until this happens.</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

<span data-ttu-id="ac784-242">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="ac784-242">And that's it!</span></span> <span data-ttu-id="ac784-243">È stato eseguito il training di un modello di apprendimento automatico in grado di prevedere le tariffe dei taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="ac784-243">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="ac784-244">A questo punto occorre determinare il livello di accuratezza del modello e imparare a usarlo per stimare i valori delle tariffe dei taxi.</span><span class="sxs-lookup"><span data-stu-id="ac784-244">Now let's take a look to understand how accurate the model is and learn how to use it to predict taxi fare values.</span></span>

### <a name="save-the-model"></a><span data-ttu-id="ac784-245">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="ac784-245">Save the model</span></span>

<span data-ttu-id="ac784-246">A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain> che può essere integrato nelle applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="ac784-246">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="ac784-247">Per salvare il modello in un file con estensione zip, aggiungere il codice seguente alla fine del metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="ac784-247">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="ac784-248">Salvare il modello come file con estensione zip</span><span class="sxs-lookup"><span data-stu-id="ac784-248">Save the model as a .zip file</span></span>

<span data-ttu-id="ac784-249">Creare il metodo `SaveModelAsFile` subito dopo il metodo `Train`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-249">Create the `SaveModelAsFile` method, just after the `Train` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="ac784-250">Il metodo `SaveModelAsFile` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac784-250">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="ac784-251">Salva il modello come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="ac784-251">Saves the model as a .zip file.</span></span>

<span data-ttu-id="ac784-252">È necessario creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ac784-252">We need to create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="ac784-253">L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="ac784-253">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="ac784-254">Poiché si vuole salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="ac784-254">Since we want to save this as a zip file, we'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="ac784-255">Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="ac784-255">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

<span data-ttu-id="ac784-256">È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-256">We could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="ac784-257">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="ac784-257">Evaluate the model</span></span>

<span data-ttu-id="ac784-258">La valutazione è il processo di verifica dell'efficacia del modello nella stima dei valori delle etichette.</span><span class="sxs-lookup"><span data-stu-id="ac784-258">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="ac784-259">È importante che il modello formuli stime corrette su dati che non sono stati usati per eseguire il training del modello stesso.</span><span class="sxs-lookup"><span data-stu-id="ac784-259">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="ac784-260">Un modo per eseguire questa operazione è suddividere i dati in training set e set di dati di test, come descritto in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="ac784-260">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="ac784-261">Ora che è stato eseguito il training del modello sui dati di training, è possibile verificarne le prestazioni sui dati di test.</span><span class="sxs-lookup"><span data-stu-id="ac784-261">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="ac784-262">Il metodo `Evaluate` valuta il modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-262">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="ac784-263">Per creare tale metodo, aggiungere il codice seguente dopo il metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="ac784-263">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```
<span data-ttu-id="ac784-264">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac784-264">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="ac784-265">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="ac784-265">Loads the test dataset.</span></span>
* <span data-ttu-id="ac784-266">Crea l'analizzatore della regressione.</span><span class="sxs-lookup"><span data-stu-id="ac784-266">Creates the regression evaluator.</span></span>
* <span data-ttu-id="ac784-267">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="ac784-267">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="ac784-268">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="ac784-268">Displays the metrics.</span></span>

<span data-ttu-id="ac784-269">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-269">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="ac784-270">Si caricherà il set di dati di test usando la variabile globale `_textLoader` inizializzata in precedenza con il campo globale `_testDataPath`.</span><span class="sxs-lookup"><span data-stu-id="ac784-270">We'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="ac784-271">È possibile valutare il modello usando questo set di dati come controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="ac784-271">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="ac784-272">Aggiungere al metodo `Evaluate` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-272">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="ac784-273">Si userà quindi il parametro `model` di apprendimento automatico (un oggetto Transformer) per l'input di caratteristiche e la generazione di stime.</span><span class="sxs-lookup"><span data-stu-id="ac784-273">Next, we'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="ac784-274">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="ac784-274">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="ac784-275">Il metodo `RegressionContext.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="ac784-275">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="ac784-276">Restituisce un oggetto <xref:Microsoft.ML.Data.RegressionMetrics> che contiene le metriche complessive calcolate dagli analizzatori della regressione.</span><span class="sxs-lookup"><span data-stu-id="ac784-276">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span> <span data-ttu-id="ac784-277">Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche.</span><span class="sxs-lookup"><span data-stu-id="ac784-277">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="ac784-278">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="ac784-278">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="ac784-279">Aggiungere il codice seguente per valutare il modello e produrre le metriche di valutazione:</span><span class="sxs-lookup"><span data-stu-id="ac784-279">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="ac784-280">[RSquared](../resources/glossary.md#coefficient-of-determination) è un'altra metrica di valutazione dei modelli di regressione.</span><span class="sxs-lookup"><span data-stu-id="ac784-280">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="ac784-281">Accetta valori compresi tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="ac784-281">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="ac784-282">I valori più vicini a 1 producono modelli migliori.</span><span class="sxs-lookup"><span data-stu-id="ac784-282">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="ac784-283">Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RSquared:</span><span class="sxs-lookup"><span data-stu-id="ac784-283">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="ac784-284">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) è una delle metriche di valutazione del modello di regressione.</span><span class="sxs-lookup"><span data-stu-id="ac784-284">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="ac784-285">Più basso è il valore, migliore è il modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-285">The lower it is, the better the model is.</span></span> <span data-ttu-id="ac784-286">Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RMS:</span><span class="sxs-lookup"><span data-stu-id="ac784-286">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="ac784-287">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="ac784-287">Use the model for predictions</span></span>


## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="ac784-288">Stimare il risultato dei dati di test con il modello e un singolo commento</span><span class="sxs-lookup"><span data-stu-id="ac784-288">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="ac784-289">Creare il metodo `TestSinglePrediction` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-289">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

<span data-ttu-id="ac784-290">Il metodo `TestSinglePrediction` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac784-290">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="ac784-291">Crea un singolo commento di dati di test.</span><span class="sxs-lookup"><span data-stu-id="ac784-291">Creates a single comment of test data.</span></span>
* <span data-ttu-id="ac784-292">Esegue la stima dell'importo della tariffa in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="ac784-292">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="ac784-293">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="ac784-293">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="ac784-294">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="ac784-294">Displays the predicted results.</span></span>

<span data-ttu-id="ac784-295">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac784-295">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="ac784-296">Poiché si vuole caricare il modello dal file con estensione zip salvato, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `Load`.</span><span class="sxs-lookup"><span data-stu-id="ac784-296">Since we want to load the model from the zip file we saved, we'll create the `FileStream` immediately before calling the `Load` method.</span></span> <span data-ttu-id="ac784-297">Aggiungere il codice seguente al metodo `TestSinglePrediction` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="ac784-297">Add the following code to the `TestSinglePrediction` method as the next line:</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

<span data-ttu-id="ac784-298">`model` è un oggetto `transformer` che opera su molte righe di dati, ma in un ambiente produzione è spesso necessario eseguire stime su singoli esempi.</span><span class="sxs-lookup"><span data-stu-id="ac784-298">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="ac784-299"><xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="ac784-299">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="ac784-300">A questo punto si aggiunge il codice seguente per creare `PredictionEngine` come riga successiva nel metodo `TestSinglePrediction`:</span><span class="sxs-lookup"><span data-stu-id="ac784-300">Let's add the following code to create the `PredictionEngine` as the next line in the `TestSinglePrediction` Method:</span></span>

[!code-csharp[MakePredictionEngine](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
<span data-ttu-id="ac784-301">In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe.</span><span class="sxs-lookup"><span data-stu-id="ac784-301">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="ac784-302">Successivamente, è possibile aggiungere altri scenari da sperimentare con il modello.</span><span class="sxs-lookup"><span data-stu-id="ac784-302">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="ac784-303">Aggiungere una corsa per testare la stima dei costi del modello sottoposto a training nel metodo `TestSinglePrediction` creando un'istanza di `TaxiTrip`:</span><span class="sxs-lookup"><span data-stu-id="ac784-303">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 <span data-ttu-id="ac784-304">È possibile usare questa corsa per stimare la tariffa in base a una singola istanza dei dati relativi alle corse in taxi.</span><span class="sxs-lookup"><span data-stu-id="ac784-304">We can use that to predict the fare based on a single instance of the taxi trip data.</span></span> <span data-ttu-id="ac784-305">Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati.</span><span class="sxs-lookup"><span data-stu-id="ac784-305">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="ac784-306">Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ac784-306">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="ac784-307">La pipeline è sincronizzata durante il training e la stima.</span><span class="sxs-lookup"><span data-stu-id="ac784-307">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="ac784-308">Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ac784-308">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="ac784-309">Per visualizzare la tariffa stimata della corsa specificata, aggiungere il codice seguente nel metodo `TestSinglePrediction`:</span><span class="sxs-lookup"><span data-stu-id="ac784-309">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="ac784-310">Eseguire il programma per visualizzare la tariffa del taxi stimata per il test case.</span><span class="sxs-lookup"><span data-stu-id="ac784-310">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="ac784-311">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ac784-311">Congratulations!</span></span> <span data-ttu-id="ac784-312">È stato creato un modello di machine learning per la stima delle tariffe delle corse in taxi e ne è stata valutata l'accuratezza, quindi il modello è stato usato per produrre stime.</span><span class="sxs-lookup"><span data-stu-id="ac784-312">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="ac784-313">È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="ac784-313">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ac784-314">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ac784-314">Next steps</span></span>

<span data-ttu-id="ac784-315">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="ac784-315">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="ac784-316">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ac784-316">Understand the problem</span></span>
> * <span data-ttu-id="ac784-317">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="ac784-317">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="ac784-318">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="ac784-318">Prepare and understand the data</span></span>
> * <span data-ttu-id="ac784-319">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ac784-319">Create a learning pipeline</span></span>
> * <span data-ttu-id="ac784-320">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="ac784-320">Load and transform the data</span></span>
> * <span data-ttu-id="ac784-321">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ac784-321">Choose a learning algorithm</span></span>
> * <span data-ttu-id="ac784-322">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ac784-322">Train the model</span></span>
> * <span data-ttu-id="ac784-323">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="ac784-323">Evaluate the model</span></span>
> * <span data-ttu-id="ac784-324">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="ac784-324">Use the model for predictions</span></span>

<span data-ttu-id="ac784-325">Passare all'esercitazione successiva per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="ac784-325">Advance to the next tutorial to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ac784-326">Clustering Iris</span><span class="sxs-lookup"><span data-stu-id="ac784-326">Iris clustering</span></span>](iris-clustering.md)
