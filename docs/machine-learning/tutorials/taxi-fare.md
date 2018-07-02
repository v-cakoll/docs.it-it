---
title: Usare ML.NET per stimare le tariffe dei taxi a New York (regressione)
description: Informazioni su come usare ML.NET in uno scenario di regressione.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860673"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="f6b0d-103">Esercitazione: Usare ML.NET per stimare le tariffe dei taxi a New York (regressione)</span><span class="sxs-lookup"><span data-stu-id="f6b0d-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="f6b0d-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f6b0d-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f6b0d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="f6b0d-106">Questa esercitazione illustra come usare ML.NET per creare un [modello di regressione](../resources/glossary.md#regression) per la stima delle tariffe dei taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="f6b0d-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f6b0d-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="f6b0d-108">Understand the problem</span></span>
> * <span data-ttu-id="f6b0d-109">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="f6b0d-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f6b0d-110">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="f6b0d-110">Prepare and understand your data</span></span>
> * <span data-ttu-id="f6b0d-111">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="f6b0d-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="f6b0d-112">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="f6b0d-112">Load and transform your data</span></span>
> * <span data-ttu-id="f6b0d-113">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="f6b0d-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f6b0d-114">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="f6b0d-114">Train the model</span></span>
> * <span data-ttu-id="f6b0d-115">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="f6b0d-115">Evaluate the model</span></span>
> * <span data-ttu-id="f6b0d-116">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="f6b0d-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6b0d-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6b0d-117">Prerequisites</span></span>

* <span data-ttu-id="f6b0d-118">[Visual Studio 2017 15.6 o versione successiva](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-118">[Visual Studio 2017 15.6 or later](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="f6b0d-119">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="f6b0d-119">Understand the problem</span></span>

<span data-ttu-id="f6b0d-120">Questo problema è incentrato sulla **stima della tariffa di un viaggio in taxi a New York**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="f6b0d-121">A prima vista, potrebbe sembrare dipendere semplicemente dalla distanza percorsa.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="f6b0d-122">Tuttavia, le società di taxi di New York applicano un addebito per quantità variabili di altri fattori, come i passeggeri aggiuntivi o il pagamento tramite carta di credito anziché in contanti.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="f6b0d-123">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="f6b0d-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="f6b0d-124">Per stimare le tariffe dei taxi, è innanzitutto necessario selezionare l'attività di apprendimento automatico appropriata.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="f6b0d-125">L'obiettivo è stimare valori reali (un valore double che rappresenta il prezzo) in base ad altri fattori nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="f6b0d-126">Si sceglie un'attività di [ **regressione**](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="f6b0d-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

<span data-ttu-id="f6b0d-127">Il processo di training del modello identifica i fattori nel set di dati più influenti per la stima del prezzo finale.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-127">The process of training the model identifies which factors in the dataset are most influential when predicting the final fare price.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f6b0d-128">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="f6b0d-128">Create a console application</span></span>

1. <span data-ttu-id="f6b0d-129">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="f6b0d-130">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="f6b0d-131">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="f6b0d-132">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f6b0d-133">Nella casella di testo **Nome** digitare "TaxiFarePrediction" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="f6b0d-134">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-134">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="f6b0d-135">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-135">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="f6b0d-136">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-136">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="f6b0d-137">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-137">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="f6b0d-138">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-138">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f6b0d-139">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-139">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f6b0d-140">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-and-understand-your-data"></a><span data-ttu-id="f6b0d-141">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="f6b0d-141">Prepare and understand your data</span></span>

1. <span data-ttu-id="f6b0d-142">Scaricare i set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) e salvarli nella cartella *Data* creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="f6b0d-143">Il set di dati Taxi Trip esegue il training del modello di apprendimento automatico e può essere usato per valutare il livello di accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-143">The Taxi Trip data set trains the machine learning model and can be used to evaluate how accurate your model is.</span></span> <span data-ttu-id="f6b0d-144">Questi set di dati sono originariamente ricavati dal [set di dati NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="f6b0d-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="f6b0d-145">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione csv e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="f6b0d-146">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Sempre**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="f6b0d-147">Aprire il set di dati **taxi-fare-train.csv** nell'editor di codice e controllare le intestazioni di colonna nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-147">Open the **taxi-fare-train.csv** data set in the code editor and look at column headers in the first row.</span></span> <span data-ttu-id="f6b0d-148">Esaminare ognuna delle colonne.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-148">Take a look at each of the columns.</span></span> <span data-ttu-id="f6b0d-149">Comprendere i dati e decidere quali colonne sono **funzionalità** e qual è l'**etichetta**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-149">Understand the data and decide which columns are **features** and which is the **label**.</span></span>

<span data-ttu-id="f6b0d-150">L'**etichetta** è l'identificatore della colonna che si sta tentando di stimare.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-150">The **label** is the identifier of the column you are trying to predict.</span></span> <span data-ttu-id="f6b0d-151">Le **funzionalità** identificate vengono usate per stimare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-151">The identified **features** are used to predict the label.</span></span>

* <span data-ttu-id="f6b0d-152">**vendor_id:** l'ID della società di taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="f6b0d-153">**rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="f6b0d-154">**passenger_count:** il numero di passeggeri è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="f6b0d-155">**trip_time_in_secs:** il tempo impiegato per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f6b0d-156">Non è possibile conoscere la durata del viaggio finché questo non viene completato.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-156">You won't know how long the trip takes until after it is completed.</span></span> <span data-ttu-id="f6b0d-157">Questa colonna viene esclusa dal modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-157">You exclude this column from the model.</span></span>
* <span data-ttu-id="f6b0d-158">**trip_distance:** la distanza del viaggio è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="f6b0d-159">**payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="f6b0d-160">**fare_amount:** la tariffa totale per il viaggio in taxi è l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="f6b0d-161">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="f6b0d-161">Create classes and define paths</span></span>

<span data-ttu-id="f6b0d-162">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-162">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="f6b0d-163">È necessario creare tre variabili globali per contenere i percorsi dei file scaricati di recente e salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-163">You need to create three global variables to hold the paths to the recently downloaded files and to save the model:</span></span>

* <span data-ttu-id="f6b0d-164">`_datapath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-164">`_datapath` has the path to the data set used to train the model.</span></span>
* <span data-ttu-id="f6b0d-165">`_testdatapath` contiene il percorso del set di dati usato per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-165">`_testdatapath` has the path to the data set used to evaluate the model.</span></span>
* <span data-ttu-id="f6b0d-166">`_modelpath` contiene il percorso in cui è archiviato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-166">`_modelpath` has the path where the trained model is stored.</span></span>

<span data-ttu-id="f6b0d-167">Aggiungere il codice seguente nella riga immediatamente sopra `Main` per specificare i file scaricati di recente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-167">Add the following code to the line right above `Main` to specify the recently downloaded files:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="f6b0d-168">Creare quindi le classi per i dati di input e le stime:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-168">Next, create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="f6b0d-169">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-169">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f6b0d-170">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-170">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="f6b0d-171">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-171">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f6b0d-172">Aggiungere al nuovo file le istruzioni `using` seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-172">Add the following `using` statements to the new file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="f6b0d-173">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-173">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="f6b0d-174">`TaxiTrip` è la classe del set di dati di input e contiene le definizioni per ognuna delle colonne del set di dati.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-174">`TaxiTrip` is the input data set class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="f6b0d-175">La classe `TaxiTripFarePrediction` viene usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-175">The `TaxiTripFarePrediction` class is used for prediction after the model has been trained.</span></span> <span data-ttu-id="f6b0d-176">Ha un valore float singolo (`FareAmount`) e un attributo [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) `Score` applicato.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-176">It has a single float (`FareAmount`) and a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span>

<span data-ttu-id="f6b0d-177">Tornare ora al file **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-177">Now go back to the **Program.cs** file.</span></span> <span data-ttu-id="f6b0d-178">In `Main` sostituire `Console.WriteLine("Hello World!")` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-178">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="f6b0d-179">Il metodo `Train` esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-179">The `Train` method trains your model.</span></span> <span data-ttu-id="f6b0d-180">Creare la funzione subito sotto `Main` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-180">Create that function just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="f6b0d-181">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="f6b0d-181">Create a learning pipeline</span></span>

<span data-ttu-id="f6b0d-182">La pipeline di apprendimento carica tutti i dati e gli algoritmi necessari per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-182">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="f6b0d-183">Aggiungere nel metodo `Train()` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-183">Add the following code into the `Train()` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a><span data-ttu-id="f6b0d-184">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="f6b0d-184">Load and transform your data</span></span>

<span data-ttu-id="f6b0d-185">Caricare quindi i dati nella pipeline.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-185">Next, load your data into the pipeline.</span></span> <span data-ttu-id="f6b0d-186">Fare riferimento all'elemento `_datapath` creato inizialmente e specificare il delimitatore del file CSV (,).</span><span class="sxs-lookup"><span data-stu-id="f6b0d-186">Point to the `_datapath` created initially and specify the delimiter of the .csv file (,).</span></span> <span data-ttu-id="f6b0d-187">Aggiungere il codice seguente nel metodo `Train()` sotto l'ultimo passaggio:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-187">Add the following code into the `Train()` method underneath the last step:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

<span data-ttu-id="f6b0d-188">Si farà riferimento alle colonne senza i caratteri di sottolineatura nel codice creato.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-188">You'll refer to the columns without the underscores in the code you're creating.</span></span> <span data-ttu-id="f6b0d-189">Copiare la colonna `FareAmount` in una nuova colonna denominata "Label" usando la funzione `ColumnCopier()`.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-189">Copy the `FareAmount` column into a new column called "Label" using the `ColumnCopier()` function.</span></span> <span data-ttu-id="f6b0d-190">Questa colonna è l'**etichetta**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-190">This column is the **Label**.</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="f6b0d-191">Eseguire alcune attività di **progettazione delle funzionalità** per trasformare i dati in modo da poterli usare in modo efficace per l'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-191">Conduct some **feature engineering** to transform the data so that it can be used effectively for machine learning.</span></span> <span data-ttu-id="f6b0d-192">Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-192">The algorithm that trains the model requires **numeric** features, you transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) into numbers.</span></span> <span data-ttu-id="f6b0d-193">La funzione `CategoricalOneHotVectorizer()` assegna una chiave numerica ai valori in ognuna di queste colonne.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-193">The `CategoricalOneHotVectorizer()` function assigns a numeric key to the values in each of these columns.</span></span> <span data-ttu-id="f6b0d-194">Trasformare i dati aggiungendo il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-194">Transform your data by adding this code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="f6b0d-195">L'ultimo passaggio della preparazione dei dati combina tutte le **funzionalità** in un singolo vettore usando la funzione `ColumnConcatenator()`.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-195">The last step in data preparation combines all of your **features** into one vector using the `ColumnConcatenator()` function.</span></span> <span data-ttu-id="f6b0d-196">Questo passaggio necessario consente all'algoritmo di elaborare facilmente le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-196">This necessary step helps the algorithm easily process your features.</span></span> <span data-ttu-id="f6b0d-197">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-197">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="f6b0d-198">Si noti che la colonna `trip_time_in_secs` non è inclusa.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-198">Notice that the `trip_time_in_secs` column isn't included.</span></span> <span data-ttu-id="f6b0d-199">È già stato determinato che non si tratta di una funzionalità di stima utile.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-199">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="f6b0d-200">Questi passaggi devono essere aggiunti alla pipeline nell'ordine specificato in precedenza per la corretta esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-200">These steps must be added to Pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="f6b0d-201">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="f6b0d-201">Choose a learning algorithm</span></span>

<span data-ttu-id="f6b0d-202">Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, selezionare un **algoritmo di apprendimento**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-202">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="f6b0d-203">L'algoritmo di apprendimento esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-203">The learning algorithm trains the model.</span></span> <span data-ttu-id="f6b0d-204">È stata scelta un'**attività di regressione** per questo problema, pertanto è necessario aggiungere un algoritmo di apprendimento denominato `FastTreeRegressor()` alla pipeline che usa l'**incremento dei gradienti**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-204">You chose a **regression task** for this problem, so you add a learner called `FastTreeRegressor()` to the pipeline that utilizes **gradient boosting**.</span></span>

<span data-ttu-id="f6b0d-205">L'incremento dei gradienti è una tecnica di apprendimento automatico per i problemi di regressione.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-205">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="f6b0d-206">Compila ogni albero di regressione tenendo conto dei singoli passaggi.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-206">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="f6b0d-207">Usa una funzione di perdita predefinita per misurare l'errore in ogni passaggio e correggerlo in quello successivo.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-207">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="f6b0d-208">Il risultato è un modello di stima che è effettivamente un insieme dei modelli di stima più deboli.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-208">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="f6b0d-209">Per altre informazioni sull'incremento dei gradienti, vedere [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regressione dell'albero delle decisioni con incremento).</span><span class="sxs-lookup"><span data-stu-id="f6b0d-209">For more information about gradient boosting, see [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="f6b0d-210">Aggiungere il codice seguente nel metodo `Train()` dopo il codice di elaborazione dei dati aggiunto nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-210">Add the following code into the `Train()` method following the data processing code added in the last step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="f6b0d-211">Tutti i passaggi precedenti sono stati aggiunti alla pipeline come singole istruzioni, ma C# presenta un'utile sintassi di inizializzazione della raccolta che rende più semplice creare e inizializzare la pipeline.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-211">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="f6b0d-212">Sostituire il codice aggiunto finora al metodo `Train()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-212">Replace the code you added so far to the `Train()` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="f6b0d-213">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="f6b0d-213">Train the model</span></span>

<span data-ttu-id="f6b0d-214">Il passaggio finale consiste nel training del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-214">The final step is to train the model.</span></span> <span data-ttu-id="f6b0d-215">Fino a questo punto, non è stato eseguito alcun elemento nella pipeline.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-215">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="f6b0d-216">La funzione `pipeline.Train<T_Input, T_Output>()` accetta il tipo di classe predefinito `TaxiTrip` e restituisce un tipo `TaxiTripFarePrediction`.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-216">The `pipeline.Train<T_Input, T_Output>()` function takes in the pre-defined `TaxiTrip` class type and outputs a `TaxiTripFarePrediction` type.</span></span> <span data-ttu-id="f6b0d-217">Aggiungere questo frammento di codice finale nella funzione `Train()`:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-217">Add this final piece of code into the `Train()` function:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="f6b0d-218">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-218">And that's it!</span></span> <span data-ttu-id="f6b0d-219">È stato eseguito il training di un modello di apprendimento automatico in grado di prevedere le tariffe dei taxi a New York.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-219">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="f6b0d-220">Ora vediamo come comprendere il livello di accuratezza del modello e come usarlo.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-220">Now take a look to understand how accurate your model is and learn how to consume it.</span></span>

## <a name="save-the-model"></a><span data-ttu-id="f6b0d-221">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="f6b0d-221">Save the model</span></span>

<span data-ttu-id="f6b0d-222">Prima di procedere al passaggio successivo, salvare il modello in un file ZIP aggiungendo il codice seguente alla fine della funzione `Train()`:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-222">Before you go onto the next step, save your model to a .zip file by adding the following code at the end of your `Train()` function:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="f6b0d-223">L'aggiunta dell'istruzione `await` per la chiamata `model.WriteAsync()` significa che il metodo `Train()` deve essere cambiato in un metodo asincrono che restituisce un elemento `Task`.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-223">Adding the `await` statement to the `model.WriteAsync()` call means that the `Train()` method must be changed to an async method that returns a `Task`.</span></span> <span data-ttu-id="f6b0d-224">Modificare la firma di `Train` come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-224">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="f6b0d-225">Con la modifica del tipo restituito del metodo `Train`, è necessario aggiungere un `await` al codice che chiama `Train` nel metodo `Main`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-225">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="f6b0d-226">L'aggiunta di un `await` nel metodo `Main` implica che il metodo `Main` deve avere il modificatore `async` e restituire un elemento `Task`:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-226">Adding an `await` in your `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="f6b0d-227">È inoltre necessario aggiungere la seguente istruzione using all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-227">You also need to add the following using statement at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="f6b0d-228">Poiché il metodo `async Main` è una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-228">Because the `async Main` method is a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="f6b0d-229">A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-229">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="f6b0d-230">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-230">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="f6b0d-231">Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="f6b0d-231">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="f6b0d-232">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="f6b0d-232">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="f6b0d-233">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="f6b0d-233">Evaluate the model</span></span>

<span data-ttu-id="f6b0d-234">La valutazione è il processo di verifica del funzionamento del modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-234">Evaluation is the process of checking how well the model works.</span></span> <span data-ttu-id="f6b0d-235">È importante che il modello formuli stime corrette su dati che non sono stati usati quando è stato eseguito il training.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-235">It's important that your model makes good predictions on data that it didn't use when it was trained.</span></span> <span data-ttu-id="f6b0d-236">Un modo per eseguire questa operazione è suddividere i dati in set di dati di training e di test, com'è stato descritto in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-236">One way to do this is by splitting the data into train and test datasets, as you did in this tutorial.</span></span> <span data-ttu-id="f6b0d-237">Ora che è stato eseguito il training del modello sui dati di training, è possibile verificarne le prestazioni sui dati di test.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-237">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="f6b0d-238">Tornare alla funzione `Main` e aggiungere il codice seguente dopo la chiamata al metodo `Train()`:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-238">Go back to your `Main` function and add the following code beneath the call to the `Train()`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="f6b0d-239">La funzione `Evaluate()` valuta il modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-239">The `Evaluate()` function evaluates your model.</span></span> <span data-ttu-id="f6b0d-240">Creare la funzione sotto `Train()`.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-240">Create that function below `Train()`.</span></span> <span data-ttu-id="f6b0d-241">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-241">Add the following code:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="f6b0d-242">Caricare i dati di test usando la funzione `TextLoader()`.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-242">Load the test data using the `TextLoader()` function.</span></span> <span data-ttu-id="f6b0d-243">Aggiungere nel metodo `Evaluate()` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-243">Add the following code into the `Evaluate()` method:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="f6b0d-244">Aggiungere il codice seguente per valutare il modello e produrre le relative metriche:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-244">Add the following code to evaluate the model and produce the metrics for it:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="f6b0d-245">RMS è una metrica per la valutazione dei problemi di regressione.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-245">RMS is one metric for evaluating regression problems.</span></span> <span data-ttu-id="f6b0d-246">Più è basso il valore, migliore è il modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-246">The lower it is, the better your model.</span></span> <span data-ttu-id="f6b0d-247">Aggiungere il codice seguente nella funzione `Evaluate()` per ottenere la metrica RMS per il modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-247">Add the following code into the `Evaluate()` function to print the RMS for your model.</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="f6b0d-248">RSquared è un'altra metrica per la valutazione dei problemi di regressione.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-248">RSquared is another metric for evaluating regression problems.</span></span> <span data-ttu-id="f6b0d-249">RSquared ha un valore compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-249">RSquared will be a value between 0 and 1.</span></span> <span data-ttu-id="f6b0d-250">Più il valore è vicino a 1, migliore è il modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-250">The closer you are to 1, the better your model.</span></span> <span data-ttu-id="f6b0d-251">Aggiungere il codice seguente nella funzione `Evaluate()` per ottenere il valore RSquared per il modello.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-251">Add the following code into the `Evaluate()` function to print the RSquared value for your model.</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="f6b0d-252">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="f6b0d-252">Use the model for predictions</span></span>

<span data-ttu-id="f6b0d-253">È quindi possibile creare una classe per gestire scenari di test che è possibile usare per verificare il corretto funzionamento del modello:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-253">Next, create a class to house test scenarios that you can use to make sure your model is working correctly:</span></span>

1. <span data-ttu-id="f6b0d-254">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-254">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f6b0d-255">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-255">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="f6b0d-256">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-256">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f6b0d-257">Modificare la classe in modo da renderla statica, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-257">Modify the class to be static like in the following example:</span></span>

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="f6b0d-258">In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-258">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="f6b0d-259">Successivamente, è possibile aggiungere altri scenari per sperimentare con questo esempio.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-259">Later you can add other scenarios to experiment with this sample.</span></span> <span data-ttu-id="f6b0d-260">Aggiungere il codice seguente nella classe `TestTrips`:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-260">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="f6b0d-261">La tariffa effettiva di questo viaggio è 29,5, ma usare 0 come segnaposto.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-261">This trip's actual fare is 29.5, but use 0 as a placeholder.</span></span> <span data-ttu-id="f6b0d-262">L'algoritmo di apprendimento automatico stimerà la tariffa.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-262">The machine learning algorithm will predict the fare.</span></span>

<span data-ttu-id="f6b0d-263">Aggiungere il codice seguente nella funzione `Main`.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-263">Add the following code in your `Main` function.</span></span> <span data-ttu-id="f6b0d-264">Esegue il test del modello usando i dati di `TestTrip`:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-264">It tests out your model using the `TestTrip` data:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="f6b0d-265">Eseguire il programma per visualizzare la tariffa del taxi stimata per il test case.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-265">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="f6b0d-266">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-266">Congratulations!</span></span> <span data-ttu-id="f6b0d-267">È stato creato un modello di apprendimento automatico per la stima delle tariffe dei taxi, ne è stata valutata l'accuratezza ed è stato eseguito il testing.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-267">You've now successfully built a machine learning model for predicting taxi fares, evaluated its accuracy, and tested it.</span></span> <span data-ttu-id="f6b0d-268">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="f6b0d-268">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6b0d-269">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6b0d-269">Next steps</span></span>

<span data-ttu-id="f6b0d-270">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="f6b0d-270">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f6b0d-271">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="f6b0d-271">Understand the problem</span></span>
> * <span data-ttu-id="f6b0d-272">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="f6b0d-272">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f6b0d-273">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="f6b0d-273">Prepare and understand your data</span></span>
> * <span data-ttu-id="f6b0d-274">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="f6b0d-274">Create a learning pipeline</span></span>
> * <span data-ttu-id="f6b0d-275">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="f6b0d-275">Load and transform your data</span></span>
> * <span data-ttu-id="f6b0d-276">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="f6b0d-276">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f6b0d-277">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="f6b0d-277">Train the model</span></span>
> * <span data-ttu-id="f6b0d-278">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="f6b0d-278">Evaluate the model</span></span>
> * <span data-ttu-id="f6b0d-279">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="f6b0d-279">Use the model for predictions</span></span>

<span data-ttu-id="f6b0d-280">Visitare il repository GitHub per ottenere altre informazioni ed esempi.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-280">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f6b0d-281">Repository GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="f6b0d-281">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
