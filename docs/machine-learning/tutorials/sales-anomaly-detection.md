---
title: 'Esercitazione: Rilevare le anomalie nelle vendite dei prodottiTutorial: Detect anomalies in product sales'
description: Informazioni su come creare un'applicazione di rilevamento delle anomalie per i dati di vendita dei prodotti. Questa esercitazione crea un'applicazione console .NET Core usando C# in Visual Studio 2019.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: c3fd4aa715a64a20f1eff9b789f6a87eaa749163
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78239989"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a><span data-ttu-id="24f81-104">Esercitazione: Rilevare le anomalie nelle vendite di prodotti con ML.NET</span><span class="sxs-lookup"><span data-stu-id="24f81-104">Tutorial: Detect anomalies in product sales with ML.NET</span></span>

<span data-ttu-id="24f81-105">Informazioni su come creare un'applicazione di rilevamento delle anomalie per i dati di vendita dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="24f81-105">Learn how to build an anomaly detection application for product sales data.</span></span> <span data-ttu-id="24f81-106">Questa esercitazione crea un'applicazione console .NET Core usando C# in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="24f81-106">This tutorial creates a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="24f81-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="24f81-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="24f81-108">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="24f81-108">Load the data</span></span>
> * <span data-ttu-id="24f81-109">Creare una trasformazione per il rilevamento di anomalie dei picchi</span><span class="sxs-lookup"><span data-stu-id="24f81-109">Create a transform for spike anomaly detection</span></span>
> * <span data-ttu-id="24f81-110">Rilevare le anomalie dei picchi con la trasformazione</span><span class="sxs-lookup"><span data-stu-id="24f81-110">Detect spike anomalies with the transform</span></span>
> * <span data-ttu-id="24f81-111">Creare una trasformazione per il rilevamento di anomalie dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="24f81-111">Create a transform for change point anomaly detection</span></span>
> * <span data-ttu-id="24f81-112">Rilevare le anomalie dei punti di modifica con la trasformazione</span><span class="sxs-lookup"><span data-stu-id="24f81-112">Detect change point anomalies with the transform</span></span>

<span data-ttu-id="24f81-113">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="24f81-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24f81-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="24f81-114">Prerequisites</span></span>

* <span data-ttu-id="24f81-115">[Visual Studio 2017 versione 15.6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro ".NET Core cross-platform development" installato.</span><span class="sxs-lookup"><span data-stu-id="24f81-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="24f81-116">Set di dati product-sales.csv</span><span class="sxs-lookup"><span data-stu-id="24f81-116">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="24f81-117">Il formato di dati usato in `product-sales.csv` è basato sul set di dati "Vendite di shampoo in un arco di tre anni" ricavato originariamente da DataMarket e fornito da Time Series Data Library (TSDL), di Rob Hyndman.</span><span class="sxs-lookup"><span data-stu-id="24f81-117">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span>
> <span data-ttu-id="24f81-118">Set di dati "Vendite di shampoo in un arco di tre anni" concesso in licenza nell'ambito della licenza aperta predefinita DataMarket.</span><span class="sxs-lookup"><span data-stu-id="24f81-118">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="24f81-119">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="24f81-119">Create a console application</span></span>

1. <span data-ttu-id="24f81-120">Creare un'**applicazione Console .NET Core** denominata "ProductSalesAnomalyDetection".</span><span class="sxs-lookup"><span data-stu-id="24f81-120">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="24f81-121">Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="24f81-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="24f81-122">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="24f81-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="24f81-123">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="24f81-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="24f81-124">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML** e selezionare il pulsante **Installa.**</span><span class="sxs-lookup"><span data-stu-id="24f81-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="24f81-125">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="24f81-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="24f81-126">Ripetere questi passaggi per **Microsoft.ML.TimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="24f81-126">Repeat these steps for **Microsoft.ML.TimeSeries**.</span></span>

4. <span data-ttu-id="24f81-127">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="24f81-127">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="24f81-128">Scaricare i dati</span><span class="sxs-lookup"><span data-stu-id="24f81-128">Download your data</span></span>

1. <span data-ttu-id="24f81-129">Scaricare il set di dati e salvarlo nella cartella *Dati* precedentemente creata:</span><span class="sxs-lookup"><span data-stu-id="24f81-129">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="24f81-130">Fare clic con il pulsante destro del mouse su [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."</span><span class="sxs-lookup"><span data-stu-id="24f81-130">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="24f81-131">Assicurarsi di salvare i file \*.csv nella cartella *Dati* oppure, dopo averli salvati in un altro percorso, spostare i file \*.csv nella cartella *Dati*.</span><span class="sxs-lookup"><span data-stu-id="24f81-131">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="24f81-132">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file \*.csv e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="24f81-132">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="24f81-133">In **Avanzate**, modificare il valore di **Copia nella directory** di output in Copia se **più recente**.</span><span class="sxs-lookup"><span data-stu-id="24f81-133">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="24f81-134">Nella tabella seguente è riportata un'anteprima dei dati del file \*.csv:</span><span class="sxs-lookup"><span data-stu-id="24f81-134">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="24f81-135">Month</span><span class="sxs-lookup"><span data-stu-id="24f81-135">Month</span></span>  |<span data-ttu-id="24f81-136">VenditeProdotto</span><span class="sxs-lookup"><span data-stu-id="24f81-136">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="24f81-137">1 - gen</span><span class="sxs-lookup"><span data-stu-id="24f81-137">1-Jan</span></span>  |    <span data-ttu-id="24f81-138">271</span><span class="sxs-lookup"><span data-stu-id="24f81-138">271</span></span>      |
|<span data-ttu-id="24f81-139">2 - gen</span><span class="sxs-lookup"><span data-stu-id="24f81-139">2-Jan</span></span>  |    <span data-ttu-id="24f81-140">150.9</span><span class="sxs-lookup"><span data-stu-id="24f81-140">150.9</span></span>    |
|<span data-ttu-id="24f81-141">.....</span><span class="sxs-lookup"><span data-stu-id="24f81-141">.....</span></span>  |    <span data-ttu-id="24f81-142">.....</span><span class="sxs-lookup"><span data-stu-id="24f81-142">.....</span></span>    |
|<span data-ttu-id="24f81-143">1-feb</span><span class="sxs-lookup"><span data-stu-id="24f81-143">1-Feb</span></span>  |    <span data-ttu-id="24f81-144">199.3</span><span class="sxs-lookup"><span data-stu-id="24f81-144">199.3</span></span>    |
|<span data-ttu-id="24f81-145">.....</span><span class="sxs-lookup"><span data-stu-id="24f81-145">.....</span></span>  |    <span data-ttu-id="24f81-146">.....</span><span class="sxs-lookup"><span data-stu-id="24f81-146">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="24f81-147">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="24f81-147">Create classes and define paths</span></span>

<span data-ttu-id="24f81-148">Successivamente, definire le strutture dei dati delle classi di input e stima.</span><span class="sxs-lookup"><span data-stu-id="24f81-148">Next, define your input and prediction class data structures.</span></span>

<span data-ttu-id="24f81-149">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="24f81-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="24f81-150">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24f81-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="24f81-151">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ProductSalesData.cs*.</span><span class="sxs-lookup"><span data-stu-id="24f81-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="24f81-152">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="24f81-152">Then, select the **Add** button.</span></span>

   <span data-ttu-id="24f81-153">Il file *ProductSalesData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="24f81-153">The *ProductSalesData.cs* file opens in the code editor.</span></span>

3. <span data-ttu-id="24f81-154">Aggiungere l'istruzione `using` seguente all'inizio di *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="24f81-154">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

   ```csharp
   using Microsoft.ML.Data;
   ```

4. <span data-ttu-id="24f81-155">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `ProductSalesData` e `ProductSalesPrediction`, al file *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="24f81-155">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/ProductSalesData.cs#DeclareTypes "Declare data record types")]

    <span data-ttu-id="24f81-156">`ProductSalesData` specifica una classe di dati di input.</span><span class="sxs-lookup"><span data-stu-id="24f81-156">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="24f81-157">L'attributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) specifica quali colonne (in base all'indice delle colonne) nel set di dati è necessario caricare.</span><span class="sxs-lookup"><span data-stu-id="24f81-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span>

    <span data-ttu-id="24f81-158">`ProductSalesPrediction` specifica la classe di dati di stima.</span><span class="sxs-lookup"><span data-stu-id="24f81-158">`ProductSalesPrediction` specifies the prediction data class.</span></span> <span data-ttu-id="24f81-159">Per il rilevamento delle anomalie, la stima consiste in un avviso per indicare l'eventuale presenza di un'anomalia, un punteggio non elaborato e un valore p.</span><span class="sxs-lookup"><span data-stu-id="24f81-159">For anomaly detection, the prediction consists of an alert to indicate whether there is an anomaly, a raw score, and p-value.</span></span> <span data-ttu-id="24f81-160">Quanto più vicino a 0 è il valore p, tanto maggiore è la probabilità che si sia verificata un'anomalia.</span><span class="sxs-lookup"><span data-stu-id="24f81-160">The closer the p-value is to 0, the more likely an anomaly has occurred.</span></span>

5. <span data-ttu-id="24f81-161">Creare due campi globali per contenere il percorso del file del set di dati scaricato di recente e il percorso del file del modello salvato:</span><span class="sxs-lookup"><span data-stu-id="24f81-161">Create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

    * <span data-ttu-id="24f81-162">`_dataPath` contiene il percorso del set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="24f81-162">`_dataPath` has the path to the dataset used to train the model.</span></span>
    * <span data-ttu-id="24f81-163">`_docsize` contiene il numero di record presenti nel file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="24f81-163">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="24f81-164">Si userà `_docSize` per calcolare `pvalueHistoryLength`.</span><span class="sxs-lookup"><span data-stu-id="24f81-164">You'll use `_docSize` to calculate `pvalueHistoryLength`.</span></span>

6. <span data-ttu-id="24f81-165">Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:</span><span class="sxs-lookup"><span data-stu-id="24f81-165">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a><span data-ttu-id="24f81-166">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="24f81-166">Initialize variables in Main</span></span>

1. <span data-ttu-id="24f81-167">Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="24f81-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    <span data-ttu-id="24f81-168">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="24f81-168">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="24f81-169">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="24f81-169">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="load-the-data"></a><span data-ttu-id="24f81-170">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="24f81-170">Load the data</span></span>

<span data-ttu-id="24f81-171">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="24f81-171">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="24f81-172">`IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="24f81-172">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="24f81-173">È possibile caricare dati da un file di testo o da altre origini, ad esempio un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="24f81-173">Data can be loaded from a text file or from other sources (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="24f81-174">Aggiungere il codice seguente al metodo `Main()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="24f81-174">Add the following code as the next line of the `Main()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="24f81-175">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="24f81-175">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="24f81-176">Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="24f81-176">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="time-series-anomaly-detection"></a><span data-ttu-id="24f81-177">Rilevamento delle anomalie delle serie temporali</span><span class="sxs-lookup"><span data-stu-id="24f81-177">Time series anomaly detection</span></span>

<span data-ttu-id="24f81-178">Il rilevamento delle anomalie segnala eventi o comportamenti imprevisti o insoliti.</span><span class="sxs-lookup"><span data-stu-id="24f81-178">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="24f81-179">Fornisce indizi su dove cercare i problemi e consente di rispondere alla domanda "È strano?".</span><span class="sxs-lookup"><span data-stu-id="24f81-179">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![Esempio di rilevamento di anomalie "È così strano".](./media/sales-anomaly-detection/time-series-anomaly-detection.png)

<span data-ttu-id="24f81-181">Il rilevamento delle anomalie è il processo di rilevamento degli outlier dati delle serie temporali; indica una determinata serie temporale di input in cui il comportamento non è quello previsto o è "strano".</span><span class="sxs-lookup"><span data-stu-id="24f81-181">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="24f81-182">Il rilevamento delle anomalie può essere utile in molte situazioni.</span><span class="sxs-lookup"><span data-stu-id="24f81-182">Anomaly detection can be useful in lots of ways.</span></span> <span data-ttu-id="24f81-183">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="24f81-183">For instance:</span></span>

<span data-ttu-id="24f81-184">Se si dispone di una macchina, si potrebbe desiderare di sapere: Questo indicatore di olio di lettura normale, o ho una perdita?</span><span class="sxs-lookup"><span data-stu-id="24f81-184">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="24f81-185">Se si monitora il consumo di energia, è necessario sapere: Si è verificato un'interruzione?</span><span class="sxs-lookup"><span data-stu-id="24f81-185">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="24f81-186">Esistono due tipi di anomalie di serie temporali che possono essere rilevati:</span><span class="sxs-lookup"><span data-stu-id="24f81-186">There are two types of time series anomalies that can be detected:</span></span>

* <span data-ttu-id="24f81-187">**I picchi** indicano accessi temporanei di comportamenti anomali nel sistema.</span><span class="sxs-lookup"><span data-stu-id="24f81-187">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span>

* <span data-ttu-id="24f81-188">**I punti di modifica** indicano l'inizio di modifiche persistenti nel corso del tempo nel sistema.</span><span class="sxs-lookup"><span data-stu-id="24f81-188">**Change points** indicate the beginning of persistent changes over time in the system.</span></span>

<span data-ttu-id="24f81-189">In ML.NET, gli algoritmi IID Spike Detection o IID Change point Detection sono adatti ai [set di dati indipendenti e distribuiti in modo identico](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span><span class="sxs-lookup"><span data-stu-id="24f81-189">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span>

<span data-ttu-id="24f81-190">A differenza dei modelli nelle altre esercitazioni, le trasformazioni di rilevamento delle anomalie nelle serie temporali vengono applicate direttamente ai dati di input.</span><span class="sxs-lookup"><span data-stu-id="24f81-190">Unlike the models in the other tutorials, the time series anomaly detector transforms operate directly on input data.</span></span> <span data-ttu-id="24f81-191">Il metodo `IEstimator.Fit()` non necessita dei dati di training per generare la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="24f81-191">The `IEstimator.Fit()` method does not need training data to produce the transform.</span></span> <span data-ttu-id="24f81-192">Ha tuttavia bisogno dello schema dei dati, fornito da una visualizzazione dati generata da un elenco vuoto di `ProductSalesData`.</span><span class="sxs-lookup"><span data-stu-id="24f81-192">It does need the data schema though, which is provided by a data view generated from an empty list of `ProductSalesData`.</span></span>

<span data-ttu-id="24f81-193">Analizzare gli stessi dati di vendita del prodotto per rilevare i picchi e i punti di modifica.</span><span class="sxs-lookup"><span data-stu-id="24f81-193">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="24f81-194">Il processo del modello di compilazione e di training è lo stesso per il rilevamento dei picchi e dei punti di modifica; la differenza principale è l'algoritmo di rilevamento specifico usato.</span><span class="sxs-lookup"><span data-stu-id="24f81-194">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="24f81-195">Rilevamento dei picchi</span><span class="sxs-lookup"><span data-stu-id="24f81-195">Spike detection</span></span>

<span data-ttu-id="24f81-196">Lo scopo del rilevamento dei picchi consiste nell'identificare i picchi improvvisi ma temporanei che differiscono notevolmente dalla maggior parte dei valori dei dati delle serie temporali.</span><span class="sxs-lookup"><span data-stu-id="24f81-196">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="24f81-197">È importante rilevare questi elementi, osservazioni o eventi rari sospetti in modo tempestivo per fare in modo che abbiano un impatto minimo.</span><span class="sxs-lookup"><span data-stu-id="24f81-197">It's important to detect these suspicious rare items, events, or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="24f81-198">L'approccio seguente può essere usato per rilevare un'ampia gamma di anomalie, quali: interruzioni del servizio, attacchi informatici o contenuto web virale.</span><span class="sxs-lookup"><span data-stu-id="24f81-198">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="24f81-199">L'immagine seguente riporta un esempio di picchi in un set di dati relativo a una serie temporale:</span><span class="sxs-lookup"><span data-stu-id="24f81-199">The following image is an example of spikes in a time series dataset:</span></span>

![Screenshot che mostra due rilevamenti di picchi.](./media/sales-anomaly-detection/two-spike-detections.png)

### <a name="add-the-createemptydataview-method"></a><span data-ttu-id="24f81-201">Aggiungere il metodo CreateEmptyDataView()</span><span class="sxs-lookup"><span data-stu-id="24f81-201">Add the CreateEmptyDataView() method</span></span>

<span data-ttu-id="24f81-202">Aggiungere il metodo seguente a `Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="24f81-202">Add the following method to `Program.cs`:</span></span>

[!code-csharp[CreateEmptyDataView](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEmptyDataView)]

<span data-ttu-id="24f81-203">Il metodo `CreateEmptyDataView()` genera un oggetto visualizzazione dati vuoto con lo schema corretto, da usare come input per il metodo `IEstimator.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="24f81-203">The `CreateEmptyDataView()` produces an empty data view object with the correct schema to be used as input to the `IEstimator.Fit()` method.</span></span>

### <a name="create-the-detectspike-method"></a><span data-ttu-id="24f81-204">Creare il metodo DetectSpike()</span><span class="sxs-lookup"><span data-stu-id="24f81-204">Create the DetectSpike() method</span></span>

<span data-ttu-id="24f81-205">Il metodo `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="24f81-205">The `DetectSpike()` method:</span></span>

* <span data-ttu-id="24f81-206">Crea la trasformazione dallo strumento di stima.</span><span class="sxs-lookup"><span data-stu-id="24f81-206">Creates the transform from the estimator.</span></span>
* <span data-ttu-id="24f81-207">Rileva picchi in base ai dati cronologici di vendita.</span><span class="sxs-lookup"><span data-stu-id="24f81-207">Detects spikes based on historical sales data.</span></span>
* <span data-ttu-id="24f81-208">Visualizza i risultati.</span><span class="sxs-lookup"><span data-stu-id="24f81-208">Displays the results.</span></span>

1. <span data-ttu-id="24f81-209">Creare il metodo `DetectSpike()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-209">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. <span data-ttu-id="24f81-210">Usare [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) per eseguire il training del modello per il rilevamento dei picchi.</span><span class="sxs-lookup"><span data-stu-id="24f81-210">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="24f81-211">Aggiungerlo al metodo `DetectSpike()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-211">Add it to the `DetectSpike()` method with the following code:</span></span>

    [!code-csharp[AddSpikeTrainer](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddSpikeTrainer)]

1. <span data-ttu-id="24f81-212">Creare la trasformazione di rilevamento dei picchi aggiungendo il codice seguente come riga successiva nel metodo `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="24f81-212">Create the spike detection transform by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

    [!code-csharp[TrainModel1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TrainModel1)]

1. <span data-ttu-id="24f81-213">Aggiungere la seguente riga di codice per trasformare i dati `productSales` nella riga successiva nel metodo `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="24f81-213">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

    [!code-csharp[TransformData1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TransformData1)]

    <span data-ttu-id="24f81-214">Il codice precedente usa il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) per effettuare stime per più righe di input di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="24f81-214">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple input rows of a dataset.</span></span>

1. <span data-ttu-id="24f81-215">Convertire `transformedData` in un oggetto `IEnumerable` fortemente tipizzato per una visualizzazione più semplice tramite il metodo [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-215">Convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

    [!code-csharp[CreateEnumerable1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEnumerable1)]

1. <span data-ttu-id="24f81-216">Creare una linea dell'intestazione di visualizzazione usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-216">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

    [!code-csharp[DisplayHeader1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayHeader1)]

    <span data-ttu-id="24f81-217">Nei risultati relativi al rilevamento di picchi saranno visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24f81-217">You'll display the following information in your spike detection results:</span></span>

    * <span data-ttu-id="24f81-218">`Alert` indica un avviso di picco per un punto dati specificato.</span><span class="sxs-lookup"><span data-stu-id="24f81-218">`Alert` indicates a spike alert for a given data point.</span></span>
    * <span data-ttu-id="24f81-219">`Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="24f81-219">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
    * <span data-ttu-id="24f81-220">`P-Value` "P" è l'acronimo di probabilità.</span><span class="sxs-lookup"><span data-stu-id="24f81-220">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="24f81-221">Quanto più vicino a 0 è il valore p, tanto maggiore è la probabilità che il punto dati costituisca un'anomalia.</span><span class="sxs-lookup"><span data-stu-id="24f81-221">The closer the p-value is to 0, the more likely the data point is an anomaly.</span></span>

1. <span data-ttu-id="24f81-222">Utilizzare il codice seguente `predictions` `IEnumerable` per scorrere e visualizzare i risultati:</span><span class="sxs-lookup"><span data-stu-id="24f81-222">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

    [!code-csharp[DisplayResults1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayResults1)]

1. <span data-ttu-id="24f81-223">Aggiungere la chiamata al metodo `DetectSpike()` nel metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="24f81-223">Add the call to the `DetectSpike()`method in the `Main()` method:</span></span>

    [!code-csharp[CallDetectSpike](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CallDetectSpike)]

## <a name="spike-detection-results"></a><span data-ttu-id="24f81-224">Risultati del rilevamento di picchi</span><span class="sxs-lookup"><span data-stu-id="24f81-224">Spike detection results</span></span>

<span data-ttu-id="24f81-225">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="24f81-225">Your results should be similar to the following.</span></span> <span data-ttu-id="24f81-226">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="24f81-226">During processing, messages are displayed.</span></span> <span data-ttu-id="24f81-227">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="24f81-227">You may see warnings, or processing messages.</span></span> <span data-ttu-id="24f81-228">Per maggiore chiarezza, dai risultati seguenti sono stati rimossi alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="24f81-228">Some of the messages have been removed from the following results for clarity.</span></span>

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

## <a name="change-point-detection"></a><span data-ttu-id="24f81-229">Rilevamento dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="24f81-229">Change point detection</span></span>

<span data-ttu-id="24f81-230">`Change points` sono modifiche permanenti in una serie temporale di un flusso di distribuzione di valori, come le modifiche di livello e le tendenze.</span><span class="sxs-lookup"><span data-stu-id="24f81-230">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="24f81-231">Queste modifiche persistenti durano molto più tempo rispetto ai `spikes` e potrebbero indicare uno o più eventi catastrofici.</span><span class="sxs-lookup"><span data-stu-id="24f81-231">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="24f81-232">I `Change points` non sono in genere visibili a occhio nudo, ma possono essere rilevati nei dati usando alcuni approcci, come nel metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="24f81-232">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="24f81-233">L'immagine seguente rappresenta un esempio di rilevamento di un punto di modifica:</span><span class="sxs-lookup"><span data-stu-id="24f81-233">The following image is an example of a change point detection:</span></span>

![Screenshot che mostra il rilevamento di un punto di modifica.](./media/sales-anomaly-detection/change-point-detection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="24f81-235">Creare il metodo DetectChangepoint()</span><span class="sxs-lookup"><span data-stu-id="24f81-235">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="24f81-236">Il metodo `DetectChangepoint()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="24f81-236">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="24f81-237">Crea la trasformazione dallo strumento di stima.</span><span class="sxs-lookup"><span data-stu-id="24f81-237">Creates the transform from the estimator.</span></span>
* <span data-ttu-id="24f81-238">Rileva punti di modifica in base ai dati cronologici di vendita.</span><span class="sxs-lookup"><span data-stu-id="24f81-238">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="24f81-239">Visualizza i risultati.</span><span class="sxs-lookup"><span data-stu-id="24f81-239">Displays the results.</span></span>

1. <span data-ttu-id="24f81-240">Creare il metodo `DetectChangepoint()` subito dopo il metodo `Main()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-240">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. <span data-ttu-id="24f81-241">Creare l'oggetto [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) nel metodo `DetectChangepoint()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-241">Create the [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) in the `DetectChangepoint()` method with the following code:</span></span>

    [!code-csharp[AddChangepointTrainer](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddChangepointTrainer)]

1. <span data-ttu-id="24f81-242">Come già fatto in precedenza, creare la trasformazione dallo strumento di stima aggiungendo la riga di codice seguente nel metodo `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="24f81-242">As you did previously, create the transform from the estimator by adding the following line of code in the `DetectChangePoint()` method:</span></span>

    [!code-csharp[TrainModel2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TrainModel2)]

1. <span data-ttu-id="24f81-243">Usare il metodo `Transform()` per trasformare i dati aggiungendo il codice seguente a `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="24f81-243">Use the `Transform()` method to transform the data by adding the following code to `DetectChangePoint()`:</span></span>

    [!code-csharp[TransformData2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TransformData2)]

1. <span data-ttu-id="24f81-244">Come già fatto in precedenza, convertire `transformedData` in un oggetto `IEnumerable` fortemente tipizzato per una visualizzazione più semplice tramite il metodo `CreateEnumerable()` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-244">As you did previously, convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

    [!code-csharp[CreateEnumerable2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEnumerable2)]

1. <span data-ttu-id="24f81-245">Creare un'intestazione di visualizzazione con il codice seguente al metodo `DetectChangePoint()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="24f81-245">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

    [!code-csharp[DisplayHeader2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayHeader2)]

    <span data-ttu-id="24f81-246">Nei risultati del rilevamento di punti di modifica saranno visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24f81-246">You'll display the following information in your change point detection results:</span></span>

    * <span data-ttu-id="24f81-247">`Alert` indica un avviso di punto di modifica per un punto dati specificato.</span><span class="sxs-lookup"><span data-stu-id="24f81-247">`Alert` indicates a change point alert for a given data point.</span></span>
    * <span data-ttu-id="24f81-248">`Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="24f81-248">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
    * <span data-ttu-id="24f81-249">`P-Value` "P" è l'acronimo di probabilità.</span><span class="sxs-lookup"><span data-stu-id="24f81-249">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="24f81-250">Quanto più vicino a 0 è il valore P, tanto maggiore è la probabilità che il punto dati costituisca un'anomalia.</span><span class="sxs-lookup"><span data-stu-id="24f81-250">The closer the P-value is to 0, the more likely the data point is an anomaly.</span></span>
    * <span data-ttu-id="24f81-251">`Martingale value` viene usato per identificare il livello di "anomalia" del punto dati, in base alla sequenza di valori di P.</span><span class="sxs-lookup"><span data-stu-id="24f81-251">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>

1. <span data-ttu-id="24f81-252">Scorrere e `predictions` `IEnumerable` visualizzare i risultati con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24f81-252">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

    [!code-csharp[DisplayResults2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayResults2)]

1. <span data-ttu-id="24f81-253">Aggiungere la chiamata seguente al metodo `DetectChangepoint()` nel metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="24f81-253">Add the following call to the `DetectChangepoint()`method in the `Main()` method:</span></span>

    [!code-csharp[CallDetectChangepoint](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CallDetectChangepoint)]

## <a name="change-point-detection-results"></a><span data-ttu-id="24f81-254">Risultati del rilevamento dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="24f81-254">Change point detection results</span></span>

<span data-ttu-id="24f81-255">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="24f81-255">Your results should be similar to the following.</span></span> <span data-ttu-id="24f81-256">Durante l'elaborazione, vengono visualizzati alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="24f81-256">During processing, messages are displayed.</span></span> <span data-ttu-id="24f81-257">Possono essere mostrati avvisi o messaggi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="24f81-257">You may see warnings, or processing messages.</span></span> <span data-ttu-id="24f81-258">Per maggiore chiarezza, dai risultati seguenti sono stati rimossi alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="24f81-258">Some messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="24f81-259">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="24f81-259">Congratulations!</span></span> <span data-ttu-id="24f81-260">Sono stati compilati modelli di machine learning per il rilevamento di anomalie quali picchi e punti di modifica nei dati di vendita.</span><span class="sxs-lookup"><span data-stu-id="24f81-260">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="24f81-261">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="24f81-261">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="24f81-262">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="24f81-262">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="24f81-263">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="24f81-263">Load the data</span></span>
> * <span data-ttu-id="24f81-264">Eseguire il training del modello per il rilevamento anomalie dei picchi</span><span class="sxs-lookup"><span data-stu-id="24f81-264">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="24f81-265">Rilevare le anomalie dei picchi con il modello con training</span><span class="sxs-lookup"><span data-stu-id="24f81-265">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="24f81-266">Eseguire il training del modello per il rilevamento anomalie dei punti di modifica</span><span class="sxs-lookup"><span data-stu-id="24f81-266">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="24f81-267">Rilevare le anomalie del punto di modifica con il modello con training</span><span class="sxs-lookup"><span data-stu-id="24f81-267">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="24f81-268">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="24f81-268">Next steps</span></span>

<span data-ttu-id="24f81-269">Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di rilevamento di anomalie di consumo energetico.</span><span class="sxs-lookup"><span data-stu-id="24f81-269">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="24f81-270">Repository GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="24f81-270">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
