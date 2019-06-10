---
title: Usare ML.NET in uno scenario di rilevamento anomalie di vendita
description: Informazioni su come usare ML.NET in uno scenario di rilevamento anomalie di vendita dei prodotti per comprendere come analizzare i dati per fare in modo di adottare azioni appropriate per le anomalie dei picchi e dei punti di modifica.
ms.date: 05/29/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e092aea66ca9f439cf97c1ebee83097def0f520b
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758804"
---
# <a name="tutorial-use-mlnet-for-product-sales-anomaly-detection"></a><span data-ttu-id="25acb-103">Esercitazione: Usare ML.NET per il rilevamento anomalie di vendita dei prodotti</span><span class="sxs-lookup"><span data-stu-id="25acb-103">Tutorial: Use ML.NET for product sales anomaly detection</span></span> 

<span data-ttu-id="25acb-104">In questa esercitazione di esempio viene illustrato l'utilizzo di ML.NET per rilevare le anomalie nei dati di vendita dei prodotti allo scopo di eseguire l'azione appropriata tramite un'applicazione console .NET Core con C# in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="25acb-104">This sample tutorial illustrates using ML.NET to detect anomalies in product sales data to take the appropriate action via a .NET Core console application using C# in Visual Studio 2019.</span></span> 

<span data-ttu-id="25acb-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="25acb-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="25acb-106">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="25acb-106">Load the data</span></span>
> * <span data-ttu-id="25acb-107">Eseguire il training del modello per il rilevamento anomalie dei picchi</span><span class="sxs-lookup"><span data-stu-id="25acb-107">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="25acb-108">Rilevare le anomalie dei picchi con il modello con training</span><span class="sxs-lookup"><span data-stu-id="25acb-108">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="25acb-109">Eseguire il training del modello per il rilevamento anomalie dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="25acb-109">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="25acb-110">Rilevare le anomalie dei punti di modifica con il modello con training</span><span class="sxs-lookup"><span data-stu-id="25acb-110">Detect change point anomalies with the trained model</span></span>

<span data-ttu-id="25acb-111">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="25acb-111">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25acb-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="25acb-112">Prerequisites</span></span>

* <span data-ttu-id="25acb-113">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="25acb-113">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="25acb-114">Set di dati product-sales.csv</span><span class="sxs-lookup"><span data-stu-id="25acb-114">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="25acb-115">Il formato di dati usato in `product-sales.csv` è basato sul set di dati "Vendite di shampoo in un arco di tre anni" ricavato originariamente da DataMarket e fornito da Time Series Data Library (TSDL), di Rob Hyndman.</span><span class="sxs-lookup"><span data-stu-id="25acb-115">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span> <span data-ttu-id="25acb-116">Set di dati "Vendite di shampoo in un arco di tre anni" concesso in licenza nell'ambito della licenza aperta predefinita DataMarket.</span><span class="sxs-lookup"><span data-stu-id="25acb-116">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="25acb-117">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="25acb-117">Create a console application</span></span>

1. <span data-ttu-id="25acb-118">Creare un'**applicazione Console .NET Core** denominata "ProductSalesAnomalyDetection".</span><span class="sxs-lookup"><span data-stu-id="25acb-118">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="25acb-119">Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="25acb-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="25acb-120">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="25acb-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="25acb-121">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="25acb-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="25acb-122">Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto **v1.0.0** nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="25acb-122">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="25acb-123">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="25acb-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="25acb-124">Ripetere questi passaggi per **Microsoft.ML.TimeSeries v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="25acb-124">Repeat these steps for **Microsoft.ML.TimeSeries v0.12.0**.</span></span>

4. <span data-ttu-id="25acb-125">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="25acb-125">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="25acb-126">Scaricare i dati</span><span class="sxs-lookup"><span data-stu-id="25acb-126">Download your data</span></span>

1. <span data-ttu-id="25acb-127">Scaricare il set di dati e salvarlo nella cartella *Dati* precedentemente creata:</span><span class="sxs-lookup"><span data-stu-id="25acb-127">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="25acb-128">Fare clic con il pulsante destro del mouse su [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."</span><span class="sxs-lookup"><span data-stu-id="25acb-128">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="25acb-129">Assicurarsi di salvare i file \*.csv nella cartella *Dati* oppure, dopo averli salvati in un altro percorso, spostare i file \*.csv nella cartella *Dati*.</span><span class="sxs-lookup"><span data-stu-id="25acb-129">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="25acb-130">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file \*.csv e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="25acb-130">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="25acb-131">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="25acb-131">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="25acb-132">Nella tabella seguente è riportata un'anteprima dei dati del file \*.csv:</span><span class="sxs-lookup"><span data-stu-id="25acb-132">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="25acb-133">Mese</span><span class="sxs-lookup"><span data-stu-id="25acb-133">Month</span></span>  |<span data-ttu-id="25acb-134">VenditeProdotto</span><span class="sxs-lookup"><span data-stu-id="25acb-134">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="25acb-135">1 - gen</span><span class="sxs-lookup"><span data-stu-id="25acb-135">1-Jan</span></span>  |    <span data-ttu-id="25acb-136">271</span><span class="sxs-lookup"><span data-stu-id="25acb-136">271</span></span>      |
|<span data-ttu-id="25acb-137">2 - gen</span><span class="sxs-lookup"><span data-stu-id="25acb-137">2-Jan</span></span>  |    <span data-ttu-id="25acb-138">150.9</span><span class="sxs-lookup"><span data-stu-id="25acb-138">150.9</span></span>    |
|<span data-ttu-id="25acb-139">.....</span><span class="sxs-lookup"><span data-stu-id="25acb-139">.....</span></span>  |    <span data-ttu-id="25acb-140">.....</span><span class="sxs-lookup"><span data-stu-id="25acb-140">.....</span></span>    |
|<span data-ttu-id="25acb-141">1-feb</span><span class="sxs-lookup"><span data-stu-id="25acb-141">1-Feb</span></span>  |    <span data-ttu-id="25acb-142">199.3</span><span class="sxs-lookup"><span data-stu-id="25acb-142">199.3</span></span>    |
|<span data-ttu-id="25acb-143">.....</span><span class="sxs-lookup"><span data-stu-id="25acb-143">.....</span></span>  |    <span data-ttu-id="25acb-144">.....</span><span class="sxs-lookup"><span data-stu-id="25acb-144">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="25acb-145">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="25acb-145">Create classes and define paths</span></span>

<span data-ttu-id="25acb-146">Successivamente, definire la struttura dei dati della classe di input.</span><span class="sxs-lookup"><span data-stu-id="25acb-146">Next, define your input class data structure.</span></span>

<span data-ttu-id="25acb-147">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="25acb-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="25acb-148">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="25acb-148">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="25acb-149">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ProductSalesData.cs*.</span><span class="sxs-lookup"><span data-stu-id="25acb-149">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="25acb-150">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="25acb-150">Then, select the **Add** button.</span></span>

<span data-ttu-id="25acb-151">Il file *ProductSalesData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="25acb-151">The *ProductSalesData.cs* file opens in the code editor.</span></span> <span data-ttu-id="25acb-152">Aggiungere l'istruzione `using` seguente all'inizio di *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="25acb-152">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="25acb-153">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `ProductSalesData` e `ProductSalesPrediction`, al file *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="25acb-153">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="25acb-154">`ProductSalesData` specifica una classe di dati di input.</span><span class="sxs-lookup"><span data-stu-id="25acb-154">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="25acb-155">L'attributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) specifica quali colonne (in base all'indice delle colonne) nel set di dati è necessario caricare.</span><span class="sxs-lookup"><span data-stu-id="25acb-155">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> 

<span data-ttu-id="25acb-156">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="25acb-156">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="25acb-157">È necessario creare due campi globali per contenere il percorso del file del set di dati scaricato di recente e il percorso del file modello salvato:</span><span class="sxs-lookup"><span data-stu-id="25acb-157">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="25acb-158">`_dataPath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="25acb-158">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="25acb-159">`_docsize` contiene il numero di record presenti nel file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="25acb-159">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="25acb-160">Verrà usato per calcolare `pvalueHistoryLength`.</span><span class="sxs-lookup"><span data-stu-id="25acb-160">You'll use this to calculate `pvalueHistoryLength`.</span></span>

<span data-ttu-id="25acb-161">Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:</span><span class="sxs-lookup"><span data-stu-id="25acb-161">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="25acb-162">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="25acb-162">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="25acb-163">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="25acb-163">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="25acb-164">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="25acb-164">Initialize variables in Main</span></span>

<span data-ttu-id="25acb-165">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="25acb-165">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a><span data-ttu-id="25acb-166">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="25acb-166">Load the data</span></span>

<span data-ttu-id="25acb-167">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="25acb-167">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="25acb-168">`IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="25acb-168">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="25acb-169">È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="25acb-169">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span> <span data-ttu-id="25acb-170">Aggiungere il codice seguente al metodo `Main()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="25acb-170">Add the following code as the next line of the `Main()` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

<span data-ttu-id="25acb-171">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="25acb-171">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="25acb-172">Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="25acb-172">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="ml-task---time-series-anomaly-detection"></a><span data-ttu-id="25acb-173">Attività di Machine Learning - rilevamento delle anomalie delle serie temporali</span><span class="sxs-lookup"><span data-stu-id="25acb-173">ML task - time series anomaly detection</span></span> 

<span data-ttu-id="25acb-174">Il rilevamento delle anomalie segnala eventi o comportamenti inattesi o insoliti.</span><span class="sxs-lookup"><span data-stu-id="25acb-174">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="25acb-175">Fornisce indizi su dove cercare i problemi e consente di rispondere alla domanda "È strano?".</span><span class="sxs-lookup"><span data-stu-id="25acb-175">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![È strano](./media/sales-anomaly-detection/anomalydetection.png)

<span data-ttu-id="25acb-177">Il rilevamento delle anomalie è il processo di rilevamento degli outlier dati delle serie temporali; indica una determinata serie temporale di input in cui il comportamento non è quello previsto o è "strano".</span><span class="sxs-lookup"><span data-stu-id="25acb-177">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="25acb-178">Ciò può essere utile in molti modi.</span><span class="sxs-lookup"><span data-stu-id="25acb-178">This can be useful in lots of ways.</span></span> <span data-ttu-id="25acb-179">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="25acb-179">For instance:</span></span>

<span data-ttu-id="25acb-180">Se si dispone di un'automobile, si potrebbe voler sapere se: La lettura del manometro dell'olio è normale o è presente una perdita?</span><span class="sxs-lookup"><span data-stu-id="25acb-180">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="25acb-181">Se si sta monitorando il consumo di energia elettrica, si desidera sapere: se vi è un'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="25acb-181">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="25acb-182">Esistono due tipi di anomalie di serie temporali che possono essere rilevati:</span><span class="sxs-lookup"><span data-stu-id="25acb-182">There are two types of time series anomalies that can be detected:</span></span> 

* <span data-ttu-id="25acb-183">**I picchi** indicano accessi temporanei di comportamenti anomali nel sistema.</span><span class="sxs-lookup"><span data-stu-id="25acb-183">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span> 

* <span data-ttu-id="25acb-184">**I punti di modifica** indicano l'inizio di modifiche persistenti nel corso del tempo nel sistema.</span><span class="sxs-lookup"><span data-stu-id="25acb-184">**Change points** indicate the beginning of persistent changes over time in the system.</span></span> 

<span data-ttu-id="25acb-185">In ML.NET, gli algoritmi IID Spike Detection o IID Change point Detection sono adatti ai [set di dati indipendenti e distribuiti in modo identico](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span><span class="sxs-lookup"><span data-stu-id="25acb-185">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span> 

<span data-ttu-id="25acb-186">Analizzare gli stessi dati di vendita del prodotto per rilevare i picchi e i punti di modifica.</span><span class="sxs-lookup"><span data-stu-id="25acb-186">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="25acb-187">Il processo del modello di compilazione e di training è lo stesso per il rilevamento dei picchi e dei punti di modifica; la differenza principale è l'algoritmo di rilevamento specifico usato.</span><span class="sxs-lookup"><span data-stu-id="25acb-187">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="25acb-188">Rilevamento dei picchi</span><span class="sxs-lookup"><span data-stu-id="25acb-188">Spike detection</span></span> 

<span data-ttu-id="25acb-189">Lo scopo del rilevamento dei picchi consiste nell'identificare i picchi improvvisi ma temporanei che differiscono notevolmente dalla maggior parte dei valori dei dati delle serie temporali.</span><span class="sxs-lookup"><span data-stu-id="25acb-189">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="25acb-190">È importante rilevare questi elementi, eventi oppure osservazioni rari sospetti in modo tempestivo per fare in modo che abbiano un impatto minimo.</span><span class="sxs-lookup"><span data-stu-id="25acb-190">It's important to detect these suspicious rare items, events or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="25acb-191">L'approccio seguente può essere usato per rilevare un'ampia gamma di anomalie, quali: interruzioni del servizio, attacchi informatici o contenuto web virale.</span><span class="sxs-lookup"><span data-stu-id="25acb-191">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="25acb-192">L'immagine seguente riporta un esempio di picchi in un set di dati relativo a una serie temporale:</span><span class="sxs-lookup"><span data-stu-id="25acb-192">The following image is an example of spikes in a time series dataset:</span></span>

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a><span data-ttu-id="25acb-194">Creare il metodo DetectSpike()</span><span class="sxs-lookup"><span data-stu-id="25acb-194">Create the DetectSpike() method</span></span>

<span data-ttu-id="25acb-195">Aggiungere la seguente chiamata al metodo `DetectSpike()` come riga successiva nel metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="25acb-195">Add the following call to the `DetectSpike()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

<span data-ttu-id="25acb-196">Il metodo `DetectSpike()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="25acb-196">The `DetectSpike()` method executes the following tasks:</span></span>

* <span data-ttu-id="25acb-197">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="25acb-197">Trains the model.</span></span>
* <span data-ttu-id="25acb-198">Rileva picchi in base ai dati cronologici di vendita.</span><span class="sxs-lookup"><span data-stu-id="25acb-198">Detects spikes based on on historical sales data.</span></span>
* <span data-ttu-id="25acb-199">Visualizza i risultati.</span><span class="sxs-lookup"><span data-stu-id="25acb-199">Displays the results.</span></span>

<span data-ttu-id="25acb-200">Creare il metodo `DetectSpike()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-200">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="25acb-201">Usare [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) per eseguire il training del modello per il rilevamento dei picchi.</span><span class="sxs-lookup"><span data-stu-id="25acb-201">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="25acb-202">Aggiungerlo al metodo `DetectChangepoint()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-202">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

<span data-ttu-id="25acb-203">Adattare il modello ai dati di `productSales` aggiungendo il codice seguente come riga successiva nel metodo `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="25acb-203">Fit the model to the `productSales` data by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

<span data-ttu-id="25acb-204">Il metodo [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) esegue il training del modello trasformando il set di dati e applicando il training.</span><span class="sxs-lookup"><span data-stu-id="25acb-204">The [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="25acb-205">Aggiungere la seguente riga di codice per trasformare i dati `productSales` nella riga successiva nel metodo `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="25acb-205">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

<span data-ttu-id="25acb-206">Il codice precedente usa il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) per effettuare previsioni per più righe di input specificate di un set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="25acb-206">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="25acb-207">Convertire `transformedData` in un oggetto `IEnumerable` fortemente tipizzato per una visualizzazione più semplice tramite il metodo [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-207">Convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

<span data-ttu-id="25acb-208">Creare una linea dell'intestazione di visualizzazione usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-208">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

<span data-ttu-id="25acb-209">Nei risultati relativi al rilevamento di picchi saranno visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25acb-209">You'll display the following information in your spike detection results:</span></span>

* <span data-ttu-id="25acb-210">`Alert` indica un avviso di picco per un punto dati specificato.</span><span class="sxs-lookup"><span data-stu-id="25acb-210">`Alert` indicates a spike alert for a given data point.</span></span>

* <span data-ttu-id="25acb-211">`Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="25acb-211">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>

* <span data-ttu-id="25acb-212">`P-Value` "P" è l'acronimo di probabilità.</span><span class="sxs-lookup"><span data-stu-id="25acb-212">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="25acb-213">Indica con che probabilità il punto dati è un'anomalia.</span><span class="sxs-lookup"><span data-stu-id="25acb-213">This indicates how likely this data point is an anomaly.</span></span> 

<span data-ttu-id="25acb-214">Usare il codice seguente per eseguire l'iterazione attraverso `predictions` `IEnumerable` e visualizzare i risultati:</span><span class="sxs-lookup"><span data-stu-id="25acb-214">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a><span data-ttu-id="25acb-215">Risultati del rilevamento di picchi</span><span class="sxs-lookup"><span data-stu-id="25acb-215">Spike detection results</span></span>

<span data-ttu-id="25acb-216">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="25acb-216">Your results should be similar to the following.</span></span> <span data-ttu-id="25acb-217">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="25acb-217">During processing, messages are displayed.</span></span> <span data-ttu-id="25acb-218">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="25acb-218">You may see warnings, or processing messages.</span></span> <span data-ttu-id="25acb-219">Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="25acb-219">These have been removed from the following results for clarity.</span></span>

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a><span data-ttu-id="25acb-220">Rilevamento dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="25acb-220">Change point detection</span></span>

<span data-ttu-id="25acb-221">`Change points` sono modifiche permanenti in una serie temporale di un flusso di distribuzione di valori, come le modifiche di livello e le tendenze.</span><span class="sxs-lookup"><span data-stu-id="25acb-221">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="25acb-222">Queste modifiche persistenti durano molto più tempo rispetto ai `spikes` e potrebbero indicare uno o più eventi catastrofici.</span><span class="sxs-lookup"><span data-stu-id="25acb-222">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="25acb-223">I `Change points` non sono in genere visibili a occhio nudo, ma possono essere rilevati nei dati usando alcuni approcci, come nel metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="25acb-223">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="25acb-224">L'immagine seguente rappresenta un esempio di rilevamento di un punto di modifica:</span><span class="sxs-lookup"><span data-stu-id="25acb-224">The following image is an example of a change point detection:</span></span>

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="25acb-226">Creare il metodo DetectChangepoint()</span><span class="sxs-lookup"><span data-stu-id="25acb-226">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="25acb-227">Aggiungere la seguente chiamata al metodo `DetectChangepoint()` come riga successiva nel metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="25acb-227">Add the following call to the `DetectChangepoint()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

<span data-ttu-id="25acb-228">Il metodo `DetectChangepoint()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="25acb-228">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="25acb-229">Esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="25acb-229">Trains the model.</span></span>
* <span data-ttu-id="25acb-230">Rileva punti di modifica in base ai dati cronologici di vendita.</span><span class="sxs-lookup"><span data-stu-id="25acb-230">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="25acb-231">Visualizza i risultati.</span><span class="sxs-lookup"><span data-stu-id="25acb-231">Displays the results.</span></span>

<span data-ttu-id="25acb-232">Creare il metodo `DetectChangepoint()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-232">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="25acb-233">[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) viene usato per il training del modello per il rilevamento dei punti di modifica.</span><span class="sxs-lookup"><span data-stu-id="25acb-233">The [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) is used to train the model for change point detection.</span></span> <span data-ttu-id="25acb-234">Aggiungerlo al metodo `DetectChangepoint()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-234">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

<span data-ttu-id="25acb-235">Come in precedenza, adattare il modello ai dati di `productSales` aggiungendo il codice seguente come riga successiva nel metodo `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="25acb-235">As you did previously, fit the model to the `productSales` data by adding the following as the next line of code in the `DetectChangePoint()` method:</span></span>

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

<span data-ttu-id="25acb-236">Usare il metodo `Transform()` per trasformare i dati `Training` aggiungendo il codice seguente a `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="25acb-236">Use the `Transform()` method to transform the `Training` data by adding the following code to `DetectChangePoint()`:</span></span>

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

<span data-ttu-id="25acb-237">Come già fatto in precedenza, convertire `transformedData` in un oggetto `IEnumerable` fortemente tipizzato per una visualizzazione più semplice tramite il metodo `CreateEnumerable()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-237">As you did previously, convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

<span data-ttu-id="25acb-238">Creare un'intestazione di visualizzazione con il codice seguente al metodo `DetectChangePoint()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="25acb-238">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

<span data-ttu-id="25acb-239">Nei risultati del rilevamento di punti di modifica saranno visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25acb-239">You'll display the following information in your change point detection results:</span></span>

* <span data-ttu-id="25acb-240">`Alert` indica un avviso di punto di modifica per un punto dati specificato.</span><span class="sxs-lookup"><span data-stu-id="25acb-240">`Alert` indicates a change point alert for a given data point.</span></span>
* <span data-ttu-id="25acb-241">`Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="25acb-241">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
* <span data-ttu-id="25acb-242">`P-Value` "P" è l'acronimo di probabilità.</span><span class="sxs-lookup"><span data-stu-id="25acb-242">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="25acb-243">Indica con che probabilità il punto dati è un'anomalia.</span><span class="sxs-lookup"><span data-stu-id="25acb-243">This indicates how likely this data point is an anomaly.</span></span> 
* <span data-ttu-id="25acb-244">`Martingale value` viene usato per identificare il livello di "anomalia" del punto dati, in base alla sequenza di valori di P.</span><span class="sxs-lookup"><span data-stu-id="25acb-244">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>  

<span data-ttu-id="25acb-245">Eseguire l'iterazione attraverso `predictions` `IEnumerable` e visualizzare i risultati con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="25acb-245">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a><span data-ttu-id="25acb-246">Risultati del rilevamento dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="25acb-246">Change point detection results</span></span>

<span data-ttu-id="25acb-247">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="25acb-247">Your results should be similar to the following.</span></span> <span data-ttu-id="25acb-248">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="25acb-248">During processing, messages are displayed.</span></span> <span data-ttu-id="25acb-249">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="25acb-249">You may see warnings, or processing messages.</span></span> <span data-ttu-id="25acb-250">Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="25acb-250">These have been removed from the following results for clarity.</span></span>

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

<span data-ttu-id="25acb-251">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="25acb-251">Congratulations!</span></span> <span data-ttu-id="25acb-252">Sono stati compilati modelli di machine learning per il rilevamento di anomalie quali picchi e punti di modifica nei dati di vendita.</span><span class="sxs-lookup"><span data-stu-id="25acb-252">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="25acb-253">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="25acb-253">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="25acb-254">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="25acb-254">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="25acb-255">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="25acb-255">Load the data</span></span>
> * <span data-ttu-id="25acb-256">Eseguire il training del modello per il rilevamento anomalie dei picchi</span><span class="sxs-lookup"><span data-stu-id="25acb-256">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="25acb-257">Rilevare le anomalie dei picchi con il modello con training</span><span class="sxs-lookup"><span data-stu-id="25acb-257">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="25acb-258">Eseguire il training del modello per il rilevamento anomalie dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="25acb-258">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="25acb-259">Rilevare le anomalie del punto di modifica con il modello con training</span><span class="sxs-lookup"><span data-stu-id="25acb-259">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="25acb-260">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="25acb-260">Next steps</span></span>

<span data-ttu-id="25acb-261">Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di rilevamento di anomalie di consumo energetico.</span><span class="sxs-lookup"><span data-stu-id="25acb-261">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="25acb-262">Repository GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="25acb-262">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
