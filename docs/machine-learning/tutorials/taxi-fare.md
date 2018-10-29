---
title: Usare ML.NET per stimare le tariffe dei taxi a New York (regressione)
description: Informazioni su come usare ML.NET in uno scenario di regressione.
author: aditidugar
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bfae97d65ec192e9289841c82d84807b4937b09a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183815"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="248a9-103">Esercitazione: Usare ML.NET per stimare le tariffe dei taxi a New York (regressione)</span><span class="sxs-lookup"><span data-stu-id="248a9-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="248a9-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="248a9-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="248a9-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="248a9-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="248a9-106">Questa esercitazione illustra come usare ML.NET per creare un [modello di regressione](../resources/glossary.md#regression) per la stima delle tariffe dei taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="248a9-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="248a9-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="248a9-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="248a9-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="248a9-108">Understand the problem</span></span>
> * <span data-ttu-id="248a9-109">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="248a9-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="248a9-110">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="248a9-110">Prepare and understand the data</span></span>
> * <span data-ttu-id="248a9-111">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="248a9-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="248a9-112">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="248a9-112">Load and transform the data</span></span>
> * <span data-ttu-id="248a9-113">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="248a9-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="248a9-114">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="248a9-114">Train the model</span></span>
> * <span data-ttu-id="248a9-115">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="248a9-115">Evaluate the model</span></span>
> * <span data-ttu-id="248a9-116">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="248a9-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="248a9-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="248a9-117">Prerequisites</span></span>

* <span data-ttu-id="248a9-118">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="248a9-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="248a9-119">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="248a9-119">Understand the problem</span></span>

<span data-ttu-id="248a9-120">Questo problema riguarda la stima della tariffa di un viaggio in taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="248a9-120">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="248a9-121">A prima vista, potrebbe sembrare dipendere semplicemente dalla distanza percorsa.</span><span class="sxs-lookup"><span data-stu-id="248a9-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="248a9-122">Tuttavia, le società di taxi di New York applicano un addebito per quantità variabili di altri fattori, come i passeggeri aggiuntivi o il pagamento tramite carta di credito anziché in contanti.</span><span class="sxs-lookup"><span data-stu-id="248a9-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="248a9-123">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="248a9-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="248a9-124">Si vuole stimare il valore del prezzo, ovvero un valore reale, in base ad altri fattori nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="248a9-124">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="248a9-125">Per fare ciò, scegliere un'attività di apprendimento automatico di tipo [regressione](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="248a9-125">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="248a9-126">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="248a9-126">Create a console application</span></span>

1. <span data-ttu-id="248a9-127">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="248a9-127">Open Visual Studio 2017.</span></span> <span data-ttu-id="248a9-128">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="248a9-128">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="248a9-129">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="248a9-129">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="248a9-130">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="248a9-130">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="248a9-131">Nella casella di testo **Nome** digitare "TaxiFarePrediction" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="248a9-131">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="248a9-132">Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati e del modello:</span><span class="sxs-lookup"><span data-stu-id="248a9-132">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="248a9-133">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="248a9-133">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="248a9-134">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="248a9-134">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="248a9-135">Installare il pacchetto NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="248a9-135">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="248a9-136">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="248a9-136">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="248a9-137">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda **Sfoglia**, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="248a9-137">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="248a9-138">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="248a9-138">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="248a9-139">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="248a9-139">Prepare and understand the data</span></span>

1. <span data-ttu-id="248a9-140">Scaricare i set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) e salvarli nella cartella *Data* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="248a9-140">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="248a9-141">Questi set di dati vengono usati per eseguire il training del modello di machine learning e quindi valutarne l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="248a9-141">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="248a9-142">Questi set di dati sono originariamente ricavati dal [set di dati NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="248a9-142">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="248a9-143">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su ognuno dei file \*.csv e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="248a9-143">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="248a9-144">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="248a9-144">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="248a9-145">Aprire il set di dati **taxi-fare-train.csv** e controllare le intestazioni di colonna nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="248a9-145">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="248a9-146">Esaminare ognuna delle colonne.</span><span class="sxs-lookup"><span data-stu-id="248a9-146">Take a look at each of the columns.</span></span> <span data-ttu-id="248a9-147">Identificare i dati e decidere quali colonne sono **funzionalità** e qual è l'**etichetta**.</span><span class="sxs-lookup"><span data-stu-id="248a9-147">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="248a9-148">L'**etichetta** è l'identificatore della colonna che si vuole stimare.</span><span class="sxs-lookup"><span data-stu-id="248a9-148">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="248a9-149">Le **funzionalità** identificate vengono usate per stimare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="248a9-149">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="248a9-150">Il set di dati fornito contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="248a9-150">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="248a9-151">**vendor_id:** l'ID della società di taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="248a9-151">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="248a9-152">**rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="248a9-152">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="248a9-153">**passenger_count:** il numero di passeggeri è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="248a9-153">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="248a9-154">**trip_time_in_secs:** il tempo impiegato per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="248a9-154">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="248a9-155">Si vuole stimare la tariffa del viaggio prima del termine.</span><span class="sxs-lookup"><span data-stu-id="248a9-155">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="248a9-156">Al momento non si conosce la durata del viaggio.</span><span class="sxs-lookup"><span data-stu-id="248a9-156">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="248a9-157">Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-157">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="248a9-158">**trip_distance:** la distanza del viaggio è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="248a9-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="248a9-159">**payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="248a9-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="248a9-160">**fare_amount:** la tariffa totale per il viaggio in taxi è l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="248a9-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="248a9-161">Creare classi di dati</span><span class="sxs-lookup"><span data-stu-id="248a9-161">Create data classes</span></span>

<span data-ttu-id="248a9-162">Creare le classi per i dati di input e le stime:</span><span class="sxs-lookup"><span data-stu-id="248a9-162">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="248a9-163">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="248a9-163">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="248a9-164">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="248a9-164">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="248a9-165">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="248a9-165">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="248a9-166">Aggiungere le direttive `using` seguenti al nuovo file:</span><span class="sxs-lookup"><span data-stu-id="248a9-166">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="248a9-167">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="248a9-167">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="248a9-168">`TaxiTrip` è la classe dei dati di input e contiene le definizioni per ognuna delle colonne del set di dati.</span><span class="sxs-lookup"><span data-stu-id="248a9-168">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="248a9-169">Usare l'attributo [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) per specificare gli indici delle colonne di origine nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="248a9-169">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="248a9-170">La classe `TaxiTripFarePrediction` rappresenta i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="248a9-170">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="248a9-171">Ha un singolo campo float, `FareAmount`, a cui è applicato un attributo `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="248a9-171">It has a single float field, `FareAmount`, with a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span> <span data-ttu-id="248a9-172">Nel caso dell'attività di regressione, la colonna **Score** contiene i valori delle etichette previsti.</span><span class="sxs-lookup"><span data-stu-id="248a9-172">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="248a9-173">Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.</span><span class="sxs-lookup"><span data-stu-id="248a9-173">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="248a9-174">Definire i percorsi dei dati e del modello</span><span class="sxs-lookup"><span data-stu-id="248a9-174">Define data and model paths</span></span>

<span data-ttu-id="248a9-175">Tornare al file *Program.cs* e aggiungere tre campi per i percorsi dei file con i set di dati e del file per il salvataggio del modello:</span><span class="sxs-lookup"><span data-stu-id="248a9-175">Go back to the *Program.cs* file and add three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="248a9-176">`_datapath` contiene il percorso del file con il set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-176">`_datapath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="248a9-177">`_testdatapath` contiene il percorso del file con il set di dati usato per la valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-177">`_testdatapath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="248a9-178">`_modelpath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="248a9-178">`_modelpath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="248a9-179">Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi:</span><span class="sxs-lookup"><span data-stu-id="248a9-179">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="248a9-180">Per consentire la compilazione del codice precedente, aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="248a9-180">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="248a9-181">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="248a9-181">Create a learning pipeline</span></span>

<span data-ttu-id="248a9-182">Aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="248a9-182">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="248a9-183">Nel metodo `Main` sostituire `Console.WriteLine("Hello World!")` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-183">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="248a9-184">Il metodo `Train` esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-184">The `Train` method trains the model.</span></span> <span data-ttu-id="248a9-185">Creare il metodo subito sotto `Main` usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-185">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

<span data-ttu-id="248a9-186">La pipeline di apprendimento carica tutti i dati e gli algoritmi necessari per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-186">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="248a9-187">Aggiungere nel metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-187">Add the following code into the `Train` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a><span data-ttu-id="248a9-188">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="248a9-188">Load and transform data</span></span>

<span data-ttu-id="248a9-189">Il primo passaggio da eseguire consiste nel caricare i dati dal training set.</span><span class="sxs-lookup"><span data-stu-id="248a9-189">The first step to perform is to load data from the training data set.</span></span> <span data-ttu-id="248a9-190">Nel caso di questo esempio il training set è archiviato nel file di testo con un percorso definito dal campo `_datapath`.</span><span class="sxs-lookup"><span data-stu-id="248a9-190">In our case, training data set is stored in the text file with a path defined by the `_datapath` field.</span></span> <span data-ttu-id="248a9-191">Il file include l'intestazione con i nomi di colonna, quindi la prima riga deve essere ignorata durante il caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="248a9-191">That file has the header with the column names, so the first row should be ignored while loading data.</span></span> <span data-ttu-id="248a9-192">Le colonne nel file sono separate da una virgola (",").</span><span class="sxs-lookup"><span data-stu-id="248a9-192">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="248a9-193">Aggiungere nel metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-193">Add the following code into the `Train` method:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

<span data-ttu-id="248a9-194">Nei passaggi successivi si fa riferimento alle colonne in base ai nomi definiti nella classe `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="248a9-194">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="248a9-195">Quando vengono eseguiti il training e la valutazione del modello, i valori nella colonna **Label** vengono considerati per impostazione predefinita come valori corretti da stimare.</span><span class="sxs-lookup"><span data-stu-id="248a9-195">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="248a9-196">Dato che si vuole stimare la tariffa del viaggio in taxi, copiare la colonna `FareAmount` nella colonna **Label**.</span><span class="sxs-lookup"><span data-stu-id="248a9-196">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="248a9-197">A questo scopo usare <xref:Microsoft.ML.Legacy.Transforms.ColumnCopier> e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-197">To do that, use <xref:Microsoft.ML.Legacy.Transforms.ColumnCopier> and add the following code:</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="248a9-198">Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri.</span><span class="sxs-lookup"><span data-stu-id="248a9-198">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers.</span></span> <span data-ttu-id="248a9-199">A questo scopo usare <xref:Microsoft.ML.Legacy.Transforms.CategoricalOneHotVectorizer>, che assegna valori chiave numerici diversi ai diversi valori in ogni colonna e aggiunge il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-199">To do that, use <xref:Microsoft.ML.Legacy.Transforms.CategoricalOneHotVectorizer>, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="248a9-200">L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator>.</span><span class="sxs-lookup"><span data-stu-id="248a9-200">The last step in data preparation combines all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="248a9-201">Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**.</span><span class="sxs-lookup"><span data-stu-id="248a9-201">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="248a9-202">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-202">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="248a9-203">Si noti che la colonna `TripTime`, che corrisponde alla colonna `trip_time_in_secs` nel file del set di dati, non è inclusa.</span><span class="sxs-lookup"><span data-stu-id="248a9-203">Notice that the `TripTime` column, which corresponds to the `trip_time_in_secs` column in the data set file, isn't included.</span></span> <span data-ttu-id="248a9-204">È già stato determinato che non si tratta di una funzionalità di stima utile.</span><span class="sxs-lookup"><span data-stu-id="248a9-204">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="248a9-205">Questi passaggi devono essere aggiunti alla pipeline nell'ordine specificato in precedenza per garantire la corretta esecuzione.</span><span class="sxs-lookup"><span data-stu-id="248a9-205">These steps must be added to the pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="248a9-206">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="248a9-206">Choose a learning algorithm</span></span>

<span data-ttu-id="248a9-207">Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, selezionare un **algoritmo di apprendimento**.</span><span class="sxs-lookup"><span data-stu-id="248a9-207">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="248a9-208">L'algoritmo di apprendimento esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-208">The learner trains the model.</span></span> <span data-ttu-id="248a9-209">Per questo problema è stata scelta un'attività di **regressione**, quindi occorre aggiungere un algoritmo di apprendimento <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor>, che è uno degli algoritmi di apprendimento di regressione specificati da ML.NET.</span><span class="sxs-lookup"><span data-stu-id="248a9-209">You chose a **regression** task for this problem, so you use a <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="248a9-210">L'algoritmo di apprendimento <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> utilizza l'incremento dei gradienti.</span><span class="sxs-lookup"><span data-stu-id="248a9-210"><xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> learner utilizes gradient boosting.</span></span> <span data-ttu-id="248a9-211">L'incremento dei gradienti è una tecnica di apprendimento automatico per i problemi di regressione.</span><span class="sxs-lookup"><span data-stu-id="248a9-211">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="248a9-212">Compila ogni albero di regressione tenendo conto dei singoli passaggi.</span><span class="sxs-lookup"><span data-stu-id="248a9-212">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="248a9-213">Usa una funzione di perdita predefinita per misurare l'errore in ogni passaggio e correggerlo in quello successivo.</span><span class="sxs-lookup"><span data-stu-id="248a9-213">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="248a9-214">Il risultato è un modello di stima che è effettivamente un insieme dei modelli di stima più deboli.</span><span class="sxs-lookup"><span data-stu-id="248a9-214">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="248a9-215">Per altre informazioni sull'incremento dei gradienti, vedere [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regressione dell'albero delle decisioni con incremento).</span><span class="sxs-lookup"><span data-stu-id="248a9-215">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="248a9-216">Aggiungere il codice seguente nel metodo `Train` dopo il codice di elaborazione dei dati aggiunto nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="248a9-216">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="248a9-217">Tutti i passaggi precedenti sono stati aggiunti alla pipeline come singole istruzioni, ma C# presenta un'utile sintassi di inizializzazione della raccolta che rende più semplice creare e inizializzare la pipeline.</span><span class="sxs-lookup"><span data-stu-id="248a9-217">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="248a9-218">Sostituire il codice aggiunto finora al metodo `Train` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-218">Replace the code you added so far to the `Train` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="248a9-219">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="248a9-219">Train the model</span></span>

<span data-ttu-id="248a9-220">Il passaggio finale consiste nel training del modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-220">The final step is to train the model.</span></span> <span data-ttu-id="248a9-221">Fino a questo punto, non è stato eseguito alcun elemento nella pipeline.</span><span class="sxs-lookup"><span data-stu-id="248a9-221">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="248a9-222">Il metodo `pipeline.Train<TInput, TOutput>` produce il modello che accetta un'istanza del tipo `TInput` e restituisce un'istanza del tipo `TOutput`.</span><span class="sxs-lookup"><span data-stu-id="248a9-222">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="248a9-223">Aggiungere nel metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-223">Add the following code into the `Train` method:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="248a9-224">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="248a9-224">And that's it!</span></span> <span data-ttu-id="248a9-225">È stato eseguito il training di un modello di apprendimento automatico in grado di prevedere le tariffe dei taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="248a9-225">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="248a9-226">A questo punto occorre determinare il livello di accuratezza del modello e imparare a usarlo per stimare i valori delle tariffe dei taxi.</span><span class="sxs-lookup"><span data-stu-id="248a9-226">Now let's take a look to understand how accurate the model is and learn how to use it to predict taxi fare values.</span></span>

### <a name="save-the-model"></a><span data-ttu-id="248a9-227">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="248a9-227">Save the model</span></span>

<span data-ttu-id="248a9-228">A questo punto, è disponibile un modello che può essere integrato in tutte le applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="248a9-228">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="248a9-229">Per salvare il modello in un file con estensione zip, aggiungere il codice seguente alla fine del metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="248a9-229">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="248a9-230">L'aggiunta dell'istruzione `await` alla chiamata `model.WriteAsync` significa che il metodo `Train` deve essere cambiato in un metodo asincrono che restituisce un'attività.</span><span class="sxs-lookup"><span data-stu-id="248a9-230">Adding the `await` statement to the `model.WriteAsync` call means that the `Train` method must be changed to an async method that returns a task.</span></span> <span data-ttu-id="248a9-231">Modificare la firma di `Train` come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-231">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="248a9-232">Con la modifica del tipo restituito del metodo `Train`, è necessario aggiungere un `await` al codice che chiama `Train` nel metodo `Main`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-232">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="248a9-233">L'uso di `await` nel metodo `Main` implica che il metodo `Main` deve avere il modificatore `async` e restituire un elemento `Task`:</span><span class="sxs-lookup"><span data-stu-id="248a9-233">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="248a9-234">È anche necessario aggiungere la direttiva `using` seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="248a9-234">You also need to add the following `using` directive at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="248a9-235">Poiché il metodo `async Main` è la funzionalità aggiunta in C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="248a9-235">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="248a9-236">A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="248a9-236">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="248a9-237">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="248a9-237">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="248a9-238">Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="248a9-238">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="248a9-239">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="248a9-239">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="248a9-240">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="248a9-240">Evaluate the model</span></span>

<span data-ttu-id="248a9-241">La valutazione è il processo di verifica dell'efficacia del modello nella stima dei valori delle etichette.</span><span class="sxs-lookup"><span data-stu-id="248a9-241">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="248a9-242">È importante che il modello formuli stime corrette su dati che non sono stati usati per eseguire il training del modello stesso.</span><span class="sxs-lookup"><span data-stu-id="248a9-242">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="248a9-243">Un modo per eseguire questa operazione è suddividere i dati in training set e set di dati di test, come descritto in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="248a9-243">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="248a9-244">Ora che è stato eseguito il training del modello sui dati di training, è possibile verificarne le prestazioni sui dati di test.</span><span class="sxs-lookup"><span data-stu-id="248a9-244">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="248a9-245">Tornare al metodo `Main` e aggiungere il codice seguente dopo la chiamata al metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="248a9-245">Go back to the `Main` method and add the following code beneath the call to the `Train`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="248a9-246">Il metodo `Evaluate` valuta il modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-246">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="248a9-247">Per creare tale metodo, aggiungere il codice seguente dopo il metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="248a9-247">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="248a9-248">Aggiungere il codice seguente nel metodo `Evaluate` per configurare il caricamento dei dati di test:</span><span class="sxs-lookup"><span data-stu-id="248a9-248">Add the following code into the `Evaluate` method to setup loading of the test data:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="248a9-249">Aggiungere il codice seguente per valutare il modello e produrre le metriche di valutazione:</span><span class="sxs-lookup"><span data-stu-id="248a9-249">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="248a9-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) è una delle metriche di valutazione del modello di regressione.</span><span class="sxs-lookup"><span data-stu-id="248a9-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="248a9-251">Più basso è il valore, migliore è il modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-251">The lower it is, the better the model is.</span></span> <span data-ttu-id="248a9-252">Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RMS:</span><span class="sxs-lookup"><span data-stu-id="248a9-252">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="248a9-253">[RSquared](../resources/glossary.md#coefficient-of-determination) è un'altra metrica di valutazione dei modelli di regressione.</span><span class="sxs-lookup"><span data-stu-id="248a9-253">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="248a9-254">Accetta valori compresi tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="248a9-254">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="248a9-255">I valori più vicini a 1 producono modelli migliori.</span><span class="sxs-lookup"><span data-stu-id="248a9-255">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="248a9-256">Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RSquared:</span><span class="sxs-lookup"><span data-stu-id="248a9-256">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="248a9-257">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="248a9-257">Use the model for predictions</span></span>

<span data-ttu-id="248a9-258">Creare una classe per ospitare le istanze dei dati di test:</span><span class="sxs-lookup"><span data-stu-id="248a9-258">Create a class to house test data instances:</span></span>

1. <span data-ttu-id="248a9-259">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="248a9-259">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="248a9-260">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="248a9-260">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="248a9-261">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="248a9-261">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="248a9-262">Modificare la classe in modo da renderla statica, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="248a9-262">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="248a9-263">In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe.</span><span class="sxs-lookup"><span data-stu-id="248a9-263">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="248a9-264">Successivamente, è possibile aggiungere altri scenari da sperimentare con il modello.</span><span class="sxs-lookup"><span data-stu-id="248a9-264">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="248a9-265">Aggiungere il codice seguente nella classe `TestTrips`:</span><span class="sxs-lookup"><span data-stu-id="248a9-265">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="248a9-266">La tariffa effettiva del viaggio è 29,5.</span><span class="sxs-lookup"><span data-stu-id="248a9-266">This trip's actual fare is 29.5.</span></span> <span data-ttu-id="248a9-267">Usare 0 come segnaposto, in quanto il modello stimerà la tariffa.</span><span class="sxs-lookup"><span data-stu-id="248a9-267">Use 0 as a placeholder, as the model will predict the fare.</span></span>

<span data-ttu-id="248a9-268">Per stimare la tariffa del viaggio specificato, tornare al file *Program.cs* e aggiungere il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="248a9-268">To predict the fare of the specified trip, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="248a9-269">Eseguire il programma per visualizzare la tariffa del taxi stimata per il test case.</span><span class="sxs-lookup"><span data-stu-id="248a9-269">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="248a9-270">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="248a9-270">Congratulations!</span></span> <span data-ttu-id="248a9-271">È stato creato un modello di machine learning per la stima delle tariffe delle corse in taxi e ne è stata valutata l'accuratezza, quindi il modello è stato usato per produrre stime.</span><span class="sxs-lookup"><span data-stu-id="248a9-271">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="248a9-272">È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="248a9-272">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="248a9-273">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="248a9-273">Next steps</span></span>

<span data-ttu-id="248a9-274">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="248a9-274">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="248a9-275">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="248a9-275">Understand the problem</span></span>
> * <span data-ttu-id="248a9-276">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="248a9-276">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="248a9-277">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="248a9-277">Prepare and understand the data</span></span>
> * <span data-ttu-id="248a9-278">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="248a9-278">Create a learning pipeline</span></span>
> * <span data-ttu-id="248a9-279">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="248a9-279">Load and transform the data</span></span>
> * <span data-ttu-id="248a9-280">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="248a9-280">Choose a learning algorithm</span></span>
> * <span data-ttu-id="248a9-281">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="248a9-281">Train the model</span></span>
> * <span data-ttu-id="248a9-282">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="248a9-282">Evaluate the model</span></span>
> * <span data-ttu-id="248a9-283">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="248a9-283">Use the model for predictions</span></span>

<span data-ttu-id="248a9-284">Passare all'esercitazione successiva per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="248a9-284">Advance to the next tutorial to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="248a9-285">Clustering Iris</span><span class="sxs-lookup"><span data-stu-id="248a9-285">Iris clustering</span></span>](iris-clustering.md)
