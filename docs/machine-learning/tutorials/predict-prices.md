---
title: 'Esercitazione: stimare i prezzi tramite regressione'
description: Questa esercitazione illustra come compilare un modello di regressione usando ML.NET per stimare i prezzi, in particolare le tariffe dei taxi di New York.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, seodec18, title-hack-0516
ms.openlocfilehash: 500eef32f569acfe3a28adbd63b1465c8153d5ba
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344981"
---
# <a name="tutorial-predict-prices-using-regression-with-mlnet"></a><span data-ttu-id="2a361-103">Esercitazione: stimare i prezzi usando la regressione con ML.NET</span><span class="sxs-lookup"><span data-stu-id="2a361-103">Tutorial: Predict prices using regression with ML.NET</span></span>

<span data-ttu-id="2a361-104">Questa esercitazione illustra come creare un [modello di regressione](../resources/glossary.md#regression) usando ML.NET per stimare i prezzi, in particolare le tariffe dei taxi di New York.</span><span class="sxs-lookup"><span data-stu-id="2a361-104">This tutorial illustrates how to build a [regression model](../resources/glossary.md#regression) using ML.NET to predict prices, specifically, New York City taxi fares.</span></span>

<span data-ttu-id="2a361-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="2a361-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="2a361-106">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="2a361-106">Prepare and understand the data</span></span>
> * <span data-ttu-id="2a361-107">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="2a361-107">Load and transform the data</span></span>
> * <span data-ttu-id="2a361-108">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="2a361-108">Choose a learning algorithm</span></span>
> * <span data-ttu-id="2a361-109">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2a361-109">Train the model</span></span>
> * <span data-ttu-id="2a361-110">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="2a361-110">Evaluate the model</span></span>
> * <span data-ttu-id="2a361-111">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="2a361-111">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a361-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2a361-112">Prerequisites</span></span>

* <span data-ttu-id="2a361-113">[Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="2a361-113">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="2a361-114">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="2a361-114">Create a console application</span></span>

1. <span data-ttu-id="2a361-115">Creare un'**applicazione console di .NET Core** con nome "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="2a361-115">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="2a361-116">Creare una directory *Data* nel progetto per archiviare il set di dati e i file di modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-116">Create a directory named *Data* in your project to store the data set and model files.</span></span>

1. <span data-ttu-id="2a361-117">Installare il pacchetto NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="2a361-117">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="2a361-118">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2a361-118">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2a361-119">Scegliere "nuget.org" come Origine del pacchetto, selezionare la scheda **Sfoglia**, trovare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="2a361-119">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="2a361-120">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="2a361-120">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="2a361-121">Eseguire la stessa operazione per il pacchetto NuGet **Microsoft.ML.FastTree**.</span><span class="sxs-lookup"><span data-stu-id="2a361-121">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="2a361-122">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="2a361-122">Prepare and understand the data</span></span>

1. <span data-ttu-id="2a361-123">Scaricare i set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) e salvarli nella cartella *Data* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="2a361-123">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="2a361-124">Questi set di dati vengono usati per eseguire il training del modello di machine learning e quindi valutarne l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="2a361-124">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="2a361-125">Questi set di dati sono originariamente ricavati dal [set di dati NYC TLC Taxi Trip](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).</span><span class="sxs-lookup"><span data-stu-id="2a361-125">These data sets are originally from the [NYC TLC Taxi Trip data set](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).</span></span>

1. <span data-ttu-id="2a361-126">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su ognuno dei file \*.csv e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2a361-126">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="2a361-127">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="2a361-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="2a361-128">Aprire il set di dati **taxi-fare-train.csv** e controllare le intestazioni di colonna nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="2a361-128">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="2a361-129">Esaminare ognuna delle colonne.</span><span class="sxs-lookup"><span data-stu-id="2a361-129">Take a look at each of the columns.</span></span> <span data-ttu-id="2a361-130">Identificare i dati e decidere quali colonne sono **funzionalità** e qual è l'**etichetta**.</span><span class="sxs-lookup"><span data-stu-id="2a361-130">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="2a361-131">`label` è la colonna sulla quale eseguire le stime.</span><span class="sxs-lookup"><span data-stu-id="2a361-131">The `label` is the column you want to predict.</span></span> <span data-ttu-id="2a361-132">Gli elementi `Features` identificati sono gli input assegnati al modello per la stima di `Label`.</span><span class="sxs-lookup"><span data-stu-id="2a361-132">The identified `Features`are the inputs you give the model to predict the `Label`.</span></span>

<span data-ttu-id="2a361-133">Il set di dati fornito contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a361-133">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="2a361-134">**vendor_id:** l'ID della società di taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a361-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="2a361-135">**rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a361-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="2a361-136">**passenger_count:** il numero di passeggeri è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a361-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="2a361-137">**trip_time_in_secs:** il tempo impiegato per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="2a361-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="2a361-138">Si vuole stimare la tariffa del viaggio prima del termine.</span><span class="sxs-lookup"><span data-stu-id="2a361-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="2a361-139">A questo punto, non si sa quanto tempo è necessario per il viaggio.</span><span class="sxs-lookup"><span data-stu-id="2a361-139">At that moment, you don't know how long the trip would take.</span></span> <span data-ttu-id="2a361-140">Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="2a361-141">**trip_distance:** la distanza del viaggio è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a361-141">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="2a361-142">**payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a361-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="2a361-143">**fare_amount:** la tariffa totale per il viaggio in taxi è l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="2a361-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="2a361-144">Creare classi di dati</span><span class="sxs-lookup"><span data-stu-id="2a361-144">Create data classes</span></span>

<span data-ttu-id="2a361-145">Creare le classi per i dati di input e le stime:</span><span class="sxs-lookup"><span data-stu-id="2a361-145">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="2a361-146">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2a361-146">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="2a361-147">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="2a361-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="2a361-148">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2a361-148">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="2a361-149">Aggiungere le direttive `using` seguenti al nuovo file:</span><span class="sxs-lookup"><span data-stu-id="2a361-149">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="2a361-150">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="2a361-150">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="2a361-151">`TaxiTrip` è la classe dei dati di input e contiene le definizioni per ognuna delle colonne del set di dati.</span><span class="sxs-lookup"><span data-stu-id="2a361-151">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="2a361-152">Usare l'attributo <xref:Microsoft.ML.Data.LoadColumnAttribute> per specificare gli indici delle colonne di origine nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="2a361-152">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="2a361-153">La classe `TaxiTripFarePrediction` rappresenta i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="2a361-153">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="2a361-154">Dispone di un singolo campo float, `FareAmount`, con un attributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> applicato.</span><span class="sxs-lookup"><span data-stu-id="2a361-154">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="2a361-155">Nel caso dell'attività di regressione, la colonna **Score** contiene i valori delle etichette stimate.</span><span class="sxs-lookup"><span data-stu-id="2a361-155">In case of the regression task, the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="2a361-156">Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.</span><span class="sxs-lookup"><span data-stu-id="2a361-156">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

### <a name="define-data-and-model-paths"></a><span data-ttu-id="2a361-157">Definire i percorsi dei dati e del modello</span><span class="sxs-lookup"><span data-stu-id="2a361-157">Define data and model paths</span></span>

<span data-ttu-id="2a361-158">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="2a361-158">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="2a361-159">È necessario creare tre campi per i percorsi dei file con i set di dati e del file per il salvataggio del modello:</span><span class="sxs-lookup"><span data-stu-id="2a361-159">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="2a361-160">`_trainDataPath` contiene il percorso del file con il set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-160">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="2a361-161">`_testDataPath` contiene il percorso del file con il set di dati usato per la valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-161">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="2a361-162">`_modelPath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="2a361-162">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="2a361-163">Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi e per la variabile `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="2a361-163">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="2a361-164">Tutte le operazioni di ML.NET iniziano nella [classe MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="2a361-164">All ML.NET operations start in the [MLContext class](xref:Microsoft.ML.MLContext).</span></span> <span data-ttu-id="2a361-165">L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-165">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="2a361-166">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2a361-166">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="2a361-167">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="2a361-167">Initialize variables in Main</span></span>

<span data-ttu-id="2a361-168">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="2a361-168">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="2a361-169">Aggiungere il codice seguente come riga successiva nel metodo `Main` per chiamare il metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="2a361-169">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="2a361-170">Il metodo `Train()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a361-170">The `Train()` method executes the following tasks:</span></span>

* <span data-ttu-id="2a361-171">Carica i dati.</span><span class="sxs-lookup"><span data-stu-id="2a361-171">Loads the data.</span></span>
* <span data-ttu-id="2a361-172">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="2a361-172">Extracts and transforms the data.</span></span>
* <span data-ttu-id="2a361-173">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-173">Trains the model.</span></span>
* <span data-ttu-id="2a361-174">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-174">Returns the model.</span></span>

<span data-ttu-id="2a361-175">Il metodo `Train` esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-175">The `Train` method trains the model.</span></span> <span data-ttu-id="2a361-176">Creare il metodo subito sotto `Main` usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-176">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

## <a name="load-and-transform-data"></a><span data-ttu-id="2a361-177">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="2a361-177">Load and transform data</span></span>

<span data-ttu-id="2a361-178">ML.NET usa la [classe IDataView](xref:Microsoft.ML.IDataView) come un modo efficiente e flessibile per descrivere i dati tabulari numerici o di testo.</span><span class="sxs-lookup"><span data-stu-id="2a361-178">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="2a361-179">`IDataView` può caricare file testo o in tempo reale (ad esempio, file di database SQL o di log).</span><span class="sxs-lookup"><span data-stu-id="2a361-179">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span> <span data-ttu-id="2a361-180">Aggiungere il codice seguente come prima riga del metodo `Train()`:</span><span class="sxs-lookup"><span data-stu-id="2a361-180">Add the following code as the first line of the `Train()` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="2a361-181">Per stimare la tariffa per le corse dei taxi, il `FareAmount` colonna è il `Label` che verrà stimato (l'output del modello).</span><span class="sxs-lookup"><span data-stu-id="2a361-181">As you want to predict the taxi trip fare, the `FareAmount` column is the `Label` that you will predict (the output of the model).</span></span> <span data-ttu-id="2a361-182">Usare la classe Transformation `CopyColumnsEstimator` per copiare `FareAmount`e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-182">Use the `CopyColumnsEstimator` transformation class to copy `FareAmount`, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="2a361-183">Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri (`VendorIdEncoded`, `RateCodeEncoded` e `PaymentTypeEncoded`).</span><span class="sxs-lookup"><span data-stu-id="2a361-183">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="2a361-184">Per fare ciò usare la classe di trasformazione [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer), che assegna valori chiave numerica diversi ai differenti valori in ognuna delle colonne e quindi aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-184">To do that, use the [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer) transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="2a361-185">L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione `mlContext.Transforms.Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="2a361-185">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="2a361-186">Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**.</span><span class="sxs-lookup"><span data-stu-id="2a361-186">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="2a361-187">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-187">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="2a361-188">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="2a361-188">Choose a learning algorithm</span></span>

<span data-ttu-id="2a361-189">Questo problema riguarda la stima del costo di una corsa in taxi nella città di New York.</span><span class="sxs-lookup"><span data-stu-id="2a361-189">This problem is about predicting a taxi trip fare in New York City.</span></span> <span data-ttu-id="2a361-190">A prima vista, potrebbe sembrare dipendere semplicemente dalla distanza percorsa.</span><span class="sxs-lookup"><span data-stu-id="2a361-190">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="2a361-191">Tuttavia, le società di taxi di New York applicano un addebito per quantità variabili di altri fattori, come i passeggeri aggiuntivi o il pagamento tramite carta di credito anziché in contanti.</span><span class="sxs-lookup"><span data-stu-id="2a361-191">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span> <span data-ttu-id="2a361-192">Si vuole stimare il valore del prezzo, ovvero un valore reale, in base ad altri fattori nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="2a361-192">You want to predict the price value, which is a real value, based on the other factors in the dataset.</span></span> <span data-ttu-id="2a361-193">Per fare ciò, scegliere un'attività di apprendimento automatico di tipo [regressione](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="2a361-193">To do that, you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

<span data-ttu-id="2a361-194">Aggiungere l'attività di apprendimento automatico [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) alle definizioni di trasformazione dei dati aggiungendo il codice seguente come riga successiva in `Train()`:</span><span class="sxs-lookup"><span data-stu-id="2a361-194">Append the [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) machine learning task to the data transformation definitions by adding the following as the next line of code in `Train()`:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="2a361-195">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2a361-195">Train the model</span></span>

<span data-ttu-id="2a361-196">Adattare il modello all'elemento di training `dataview` e restituire il modello sottoposto a training aggiungendo la seguente riga di codice al metodo `Train()`:</span><span class="sxs-lookup"><span data-stu-id="2a361-196">Fit the model to the training `dataview` and return the trained model by adding the following line of code in the `Train()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

<span data-ttu-id="2a361-197">Il metodo [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) esegue il training del modello trasformando il set di dati e applicando il training.</span><span class="sxs-lookup"><span data-stu-id="2a361-197">The [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="2a361-198">Restituire il modello di cui è stato eseguito il training con la riga di codice seguente nel metodo `Train()`:</span><span class="sxs-lookup"><span data-stu-id="2a361-198">Return the trained model with the following line of code in the `Train()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="2a361-199">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="2a361-199">Evaluate the model</span></span>

<span data-ttu-id="2a361-200">In seguito valutare le prestazioni del modello con i dati di test, per la convalida e il controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="2a361-200">Next, evaluate your model performance with your test data for quality assurance and validation.</span></span> <span data-ttu-id="2a361-201">Creare il metodo `Evaluate()` subito dopo `Train()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-201">Create the `Evaluate()` method, just after `Train()`, with the following code:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="2a361-202">Il metodo `Evaluate` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a361-202">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="2a361-203">Carica il set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="2a361-203">Loads the test dataset.</span></span>
* <span data-ttu-id="2a361-204">Crea l'analizzatore della regressione.</span><span class="sxs-lookup"><span data-stu-id="2a361-204">Creates the regression evaluator.</span></span>
* <span data-ttu-id="2a361-205">Valuta il modello e crea le metriche.</span><span class="sxs-lookup"><span data-stu-id="2a361-205">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="2a361-206">Visualizza le metriche.</span><span class="sxs-lookup"><span data-stu-id="2a361-206">Displays the metrics.</span></span>

<span data-ttu-id="2a361-207">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-207">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="2a361-208">Caricare il set di dati di test usando il metodo [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A).</span><span class="sxs-lookup"><span data-stu-id="2a361-208">Load the test dataset using the [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method.</span></span> <span data-ttu-id="2a361-209">Valutare il modello usando il set di dati come controllo di qualità tramite l'aggiunta del codice seguente nel metodo `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="2a361-209">Evaluate the model using this dataset as a quality check by adding the following code in the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="2a361-210">Quindi trasformare i dati `Test` aggiungendo il codice seguente a `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="2a361-210">Next, transform the `Test` data by adding the following code to `Evaluate()`:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="2a361-211">Il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) esegue stime per le righe di input della serie di dati di test.</span><span class="sxs-lookup"><span data-stu-id="2a361-211">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for the test dataset input rows.</span></span>

<span data-ttu-id="2a361-212">Il metodo `RegressionContext.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="2a361-212">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="2a361-213">Restituisce un oggetto <xref:Microsoft.ML.Data.RegressionMetrics> che contiene le metriche complessive calcolate dagli analizzatori della regressione.</span><span class="sxs-lookup"><span data-stu-id="2a361-213">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span>

<span data-ttu-id="2a361-214">Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche.</span><span class="sxs-lookup"><span data-stu-id="2a361-214">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="2a361-215">Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="2a361-215">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="2a361-216">Dopo aver impostato la previsione, il metodo [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) valuta il modello confrontando i valori stimati con gli oggetti `Labels` effettivi presenti nel set di dati di test e restituisce le metriche relative alle prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-216">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="2a361-217">Aggiungere il codice seguente per valutare il modello e produrre le metriche di valutazione:</span><span class="sxs-lookup"><span data-stu-id="2a361-217">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="2a361-218">[RSquared](../resources/glossary.md#coefficient-of-determination) è un'altra metrica di valutazione dei modelli di regressione.</span><span class="sxs-lookup"><span data-stu-id="2a361-218">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="2a361-219">Accetta valori compresi tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="2a361-219">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="2a361-220">I valori più vicini a 1 producono modelli migliori.</span><span class="sxs-lookup"><span data-stu-id="2a361-220">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="2a361-221">Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RSquared:</span><span class="sxs-lookup"><span data-stu-id="2a361-221">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="2a361-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) è una delle metriche di valutazione del modello di regressione.</span><span class="sxs-lookup"><span data-stu-id="2a361-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="2a361-223">Più basso è il valore, migliore è il modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-223">The lower it is, the better the model is.</span></span> <span data-ttu-id="2a361-224">Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RMS:</span><span class="sxs-lookup"><span data-stu-id="2a361-224">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="2a361-225">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="2a361-225">Use the model for predictions</span></span>

<span data-ttu-id="2a361-226">Creare il metodo `TestSinglePrediction` subito dopo il metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-226">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="2a361-227">Il metodo `TestSinglePrediction` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a361-227">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="2a361-228">Crea un singolo commento di dati di test.</span><span class="sxs-lookup"><span data-stu-id="2a361-228">Creates a single comment of test data.</span></span>
* <span data-ttu-id="2a361-229">Esegue la stima dell'importo della tariffa in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="2a361-229">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="2a361-230">Combina i dati di test e le stime per i report.</span><span class="sxs-lookup"><span data-stu-id="2a361-230">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="2a361-231">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="2a361-231">Displays the predicted results.</span></span>

<span data-ttu-id="2a361-232">Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2a361-232">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="2a361-233">Usare `PredictionEngine` per stimare l'importo della tariffa aggiungendo il codice seguente a `TestSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="2a361-233">Use the `PredictionEngine` to predict the fare by adding the following code to `TestSinglePrediction()`:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]

<span data-ttu-id="2a361-234">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="2a361-234">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="2a361-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="2a361-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="2a361-236">È accettabile usare in ambienti a thread singolo o prototipi.</span><span class="sxs-lookup"><span data-stu-id="2a361-236">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="2a361-237">Per migliorare le prestazioni e thread safety negli ambienti di produzione, usare il servizio `PredictionEnginePool`, che consente di creare un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da usare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a361-237">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="2a361-238">Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="2a361-238">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="2a361-239">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="2a361-239">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="2a361-240">In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe.</span><span class="sxs-lookup"><span data-stu-id="2a361-240">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="2a361-241">Successivamente, è possibile aggiungere altri scenari da sperimentare con il modello.</span><span class="sxs-lookup"><span data-stu-id="2a361-241">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="2a361-242">Aggiungere una corsa per testare la stima dei costi del modello sottoposto a training nel metodo `TestSinglePrediction()` creando un'istanza di `TaxiTrip`:</span><span class="sxs-lookup"><span data-stu-id="2a361-242">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction()` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

<span data-ttu-id="2a361-243">Successivamente eseguire la stima della tariffa in base a una singola istanza dei dati relativi al viaggio in taxi e passarla a `PredictionEngine` aggiungendo il codice seguente come righe successive di codice nel metodo `TestSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="2a361-243">Next, predict the fare based on a single instance of the taxi trip data and pass it to the `PredictionEngine` by adding the following as the next lines of code in the `TestSinglePrediction()` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="2a361-244">La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="2a361-244">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single instance of data.</span></span>

<span data-ttu-id="2a361-245">Per visualizzare la tariffa stimata della corsa specificata, aggiungere il codice seguente nel metodo `TestSinglePrediction`:</span><span class="sxs-lookup"><span data-stu-id="2a361-245">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="2a361-246">Eseguire il programma per visualizzare la tariffa del taxi stimata per il test case.</span><span class="sxs-lookup"><span data-stu-id="2a361-246">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="2a361-247">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="2a361-247">Congratulations!</span></span> <span data-ttu-id="2a361-248">È stato creato un modello di machine learning per la stima delle tariffe delle corse in taxi e ne è stata valutata l'accuratezza, quindi il modello è stato usato per produrre stime.</span><span class="sxs-lookup"><span data-stu-id="2a361-248">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="2a361-249">È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="2a361-249">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2a361-250">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2a361-250">Next steps</span></span>

<span data-ttu-id="2a361-251">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="2a361-251">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="2a361-252">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="2a361-252">Prepare and understand the data</span></span>
> * <span data-ttu-id="2a361-253">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="2a361-253">Create a learning pipeline</span></span>
> * <span data-ttu-id="2a361-254">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="2a361-254">Load and transform the data</span></span>
> * <span data-ttu-id="2a361-255">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="2a361-255">Choose a learning algorithm</span></span>
> * <span data-ttu-id="2a361-256">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2a361-256">Train the model</span></span>
> * <span data-ttu-id="2a361-257">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="2a361-257">Evaluate the model</span></span>
> * <span data-ttu-id="2a361-258">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="2a361-258">Use the model for predictions</span></span>

<span data-ttu-id="2a361-259">Passare all'esercitazione successiva per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="2a361-259">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2a361-260">Clustering Iris</span><span class="sxs-lookup"><span data-stu-id="2a361-260">Iris clustering</span></span>](iris-clustering.md)
