---
title: 'Esercitazione: previsione della richiesta di noleggio biciclette'
description: Questa esercitazione illustra come prevedere la domanda per un servizio di noleggio di biciclette usando l'analisi della serie temporale univariata e ML.NET.
ms.date: 11/07/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 026421d7b1b2a0e39118ae712780ca7fc8f6e444
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921248"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a><span data-ttu-id="d1d62-103">Esercitazione: prevedere la richiesta del servizio di noleggio biciclette con l'analisi delle serie temporali e ML.NET</span><span class="sxs-lookup"><span data-stu-id="d1d62-103">Tutorial: Forecast bike rental service demand with time series analysis and ML.NET</span></span>

<span data-ttu-id="d1d62-104">Informazioni su come prevedere la domanda per un servizio di noleggio di biciclette usando l'analisi della serie temporale univariata nei dati archiviati in un database di SQL Server con ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d1d62-104">Learn how to forecast demand for a bike rental service using univariate time series analysis on data stored in a SQL Server database with ML.NET.</span></span>

<span data-ttu-id="d1d62-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="d1d62-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="d1d62-106">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="d1d62-106">Understand the problem</span></span>
> * <span data-ttu-id="d1d62-107">Caricare dati da un database</span><span class="sxs-lookup"><span data-stu-id="d1d62-107">Load data from a database</span></span>
> * <span data-ttu-id="d1d62-108">Creare un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="d1d62-108">Create a forecasting model</span></span>
> * <span data-ttu-id="d1d62-109">Valutare il modello di previsione</span><span class="sxs-lookup"><span data-stu-id="d1d62-109">Evaluate forecasting model</span></span>
> * <span data-ttu-id="d1d62-110">Salvare un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="d1d62-110">Save a forecasting model</span></span>
> * <span data-ttu-id="d1d62-111">Usare un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="d1d62-111">Use a forecasting model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1d62-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d1d62-112">Prerequisites</span></span>

- <span data-ttu-id="d1d62-113">[Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="d1d62-113">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="time-series-forecasting-sample-overview"></a><span data-ttu-id="d1d62-114">Panoramica dell'esempio di previsione delle serie temporali</span><span class="sxs-lookup"><span data-stu-id="d1d62-114">Time series forecasting sample overview</span></span>

<span data-ttu-id="d1d62-115">Questo esempio è un'  **C# applicazione console .NET Core** che prevede la richiesta di noleggi di biciclette usando un algoritmo di analisi della serie temporale univariato noto come analisi a spettro singolo.</span><span class="sxs-lookup"><span data-stu-id="d1d62-115">This sample is a **C# .NET Core console application** that forecasts demand for bike rentals using a univariate time series analysis algorithm known as Single Spectrum Analysis.</span></span> <span data-ttu-id="d1d62-116">Il codice per questo esempio è disponibile nel repository [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="d1d62-116">The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="d1d62-117">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="d1d62-117">Understand the problem</span></span>

<span data-ttu-id="d1d62-118">Per eseguire un'operazione efficiente, gestione inventario gioca un ruolo fondamentale.</span><span class="sxs-lookup"><span data-stu-id="d1d62-118">In order to run an efficient operation, inventory management plays a key role.</span></span> <span data-ttu-id="d1d62-119">La presenza di una quantità eccessiva di prodotti in magazzino significa che i prodotti non venduti seduti sugli scaffali non generano ricavi.</span><span class="sxs-lookup"><span data-stu-id="d1d62-119">Having too much of a product in stock means unsold products sitting on the shelves not generating any revenue.</span></span> <span data-ttu-id="d1d62-120">Il fatto di avere un prodotto troppo piccolo porta a perdere le vendite e i clienti che acquistano da concorrenti.</span><span class="sxs-lookup"><span data-stu-id="d1d62-120">Having too little product leads to lost sales and customers purchasing from competitors.</span></span> <span data-ttu-id="d1d62-121">Quindi, la domanda costante è, qual è la quantità ottimale di inventario da usare?</span><span class="sxs-lookup"><span data-stu-id="d1d62-121">Therefore, the constant question is, what is the optimal amount of inventory to keep on hand?</span></span> <span data-ttu-id="d1d62-122">L'analisi delle serie temporali consente di fornire una risposta a queste domande osservando i dati cronologici, identificando i modelli e usando queste informazioni per prevedere i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="d1d62-122">Time-series analysis helps provide an answer to these questions by looking at historical data, identifying patterns, and using this information to forecast values some time in the future.</span></span>

<span data-ttu-id="d1d62-123">La tecnica per analizzare i dati usati in questa esercitazione è l'analisi della serie temporale univariata.</span><span class="sxs-lookup"><span data-stu-id="d1d62-123">The technique for analyzing data used in this tutorial is univariate time-series analysis.</span></span> <span data-ttu-id="d1d62-124">L'analisi della serie temporale univariata esamina un'unica osservazione numerica in un periodo di tempo a intervalli specifici, ad esempio le vendite mensili.</span><span class="sxs-lookup"><span data-stu-id="d1d62-124">Univariate time-series analysis takes a look at a single numerical observation over a period of time at specific intervals such as monthly sales.</span></span>

<span data-ttu-id="d1d62-125">L'algoritmo usato in questa esercitazione è [Single Spectrum Analysis (SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span><span class="sxs-lookup"><span data-stu-id="d1d62-125">The algorithm used in this tutorial is [Single Spectrum Analysis(SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span></span> <span data-ttu-id="d1d62-126">La funzione SSA scompone una serie temporale in un set di componenti principali.</span><span class="sxs-lookup"><span data-stu-id="d1d62-126">SSA works by decomposing a time-series into a set of principal components.</span></span> <span data-ttu-id="d1d62-127">Questi componenti possono essere interpretati come parti di un segnale che corrispondono a tendenze, rumore, stagionalità e molti altri fattori.</span><span class="sxs-lookup"><span data-stu-id="d1d62-127">These components can be interpreted as the parts of a signal that correspond to trends, noise, seasonality, and many other factors.</span></span> <span data-ttu-id="d1d62-128">Quindi, questi componenti vengono ricostruiti e usati per prevedere i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="d1d62-128">Then, these components are reconstructed and used to forecast values some time in the future.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="d1d62-129">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="d1d62-129">Create console application</span></span>

1. <span data-ttu-id="d1d62-130">Creare una nuova  **C# applicazione console .NET Core** denominata "BikeDemandForecasting".</span><span class="sxs-lookup"><span data-stu-id="d1d62-130">Create a new **C# .NET Core console application** called "BikeDemandForecasting".</span></span>
1. <span data-ttu-id="d1d62-131">Installare il pacchetto NuGet **Microsoft.ml** Version **1.4.0**</span><span class="sxs-lookup"><span data-stu-id="d1d62-131">Install **Microsoft.ML** version **1.4.0** NuGet package</span></span>
    1. <span data-ttu-id="d1d62-132">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="d1d62-132">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="d1d62-133">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda **Sfoglia** , cercare **Microsoft.ml**.</span><span class="sxs-lookup"><span data-stu-id="d1d62-133">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="d1d62-134">Selezionare la casella di controllo **Includi versione preliminare** .</span><span class="sxs-lookup"><span data-stu-id="d1d62-134">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="d1d62-135">Selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="d1d62-135">Select the **Install** button.</span></span>
    1. <span data-ttu-id="d1d62-136">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="d1d62-136">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="d1d62-137">Ripetere questi passaggi per **System. Data. SqlClient** versione **4.7.0** e **Microsoft. ml. TimeSeries** versione **1.4.0**.</span><span class="sxs-lookup"><span data-stu-id="d1d62-137">Repeat these steps for **System.Data.SqlClient** version **4.7.0** and **Microsoft.ML.TimeSeries** version **1.4.0**.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="d1d62-138">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="d1d62-138">Prepare and understand the data</span></span>

1. <span data-ttu-id="d1d62-139">Creare una directory denominata *Data*.</span><span class="sxs-lookup"><span data-stu-id="d1d62-139">Create a directory called *Data*.</span></span>
1. <span data-ttu-id="d1d62-140">Scaricare il [file di database *DailyDemand. MDF* ](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) e salvarlo nella directory *dei dati* .</span><span class="sxs-lookup"><span data-stu-id="d1d62-140">Download the [*DailyDemand.mdf* database file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) and save it to the *Data* directory.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d62-141">I dati usati in questa esercitazione provengono dal set di dati [UCI bike sharing](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span><span class="sxs-lookup"><span data-stu-id="d1d62-141">The data used in this tutorial comes from the [UCI Bike Sharing Dataset](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span></span> <span data-ttu-id="d1d62-142">Federico-T, Hadi e Gama, Joao,' Event Labeling combining Ensemble Detectors and background Knowledge ', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [collegamento Web](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span><span class="sxs-lookup"><span data-stu-id="d1d62-142">Fanaee-T, Hadi, and Gama, Joao, 'Event labeling combining ensemble detectors and background knowledge', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [Web Link](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span></span>

<span data-ttu-id="d1d62-143">Il set di dati originale contiene diverse colonne che corrispondono a stagionalità e meteo.</span><span class="sxs-lookup"><span data-stu-id="d1d62-143">The original dataset contains several columns corresponding to seasonality and weather.</span></span> <span data-ttu-id="d1d62-144">Per brevità e perché l'algoritmo usato in questa esercitazione richiede solo i valori di una singola colonna numerica, il set di dati originale è stato condensato in modo da includere solo le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1d62-144">For brevity and because the algorithm used in this tutorial only requires the values from a single numerical column, the original dataset has been condensed to include only the following columns:</span></span>

- <span data-ttu-id="d1d62-145">**dteday**: data dell'osservazione.</span><span class="sxs-lookup"><span data-stu-id="d1d62-145">**dteday**: The date of the observation.</span></span>
- <span data-ttu-id="d1d62-146">**year**: anno codificato dell'osservazione (0 = 2011, 1 = 2012).</span><span class="sxs-lookup"><span data-stu-id="d1d62-146">**year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
- <span data-ttu-id="d1d62-147">**CNT**: numero totale di noleggi di biciclette per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="d1d62-147">**cnt**: The total number of bike rentals for that day.</span></span>

<span data-ttu-id="d1d62-148">Il set di dati originale viene mappato a una tabella di database con lo schema seguente in un database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1d62-148">The original dataset is mapped to a database table with the following schema in a SQL Server database.</span></span>

```SQL
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

<span data-ttu-id="d1d62-149">Di seguito è riportato un esempio dei dati:</span><span class="sxs-lookup"><span data-stu-id="d1d62-149">The following is a sample of the data:</span></span>

| <span data-ttu-id="d1d62-150">RentalDate</span><span class="sxs-lookup"><span data-stu-id="d1d62-150">RentalDate</span></span> | <span data-ttu-id="d1d62-151">Anno</span><span class="sxs-lookup"><span data-stu-id="d1d62-151">Year</span></span> | <span data-ttu-id="d1d62-152">TotalRentals</span><span class="sxs-lookup"><span data-stu-id="d1d62-152">TotalRentals</span></span> |
| --- | --- | --- |
|<span data-ttu-id="d1d62-153">1/1/2011</span><span class="sxs-lookup"><span data-stu-id="d1d62-153">1/1/2011</span></span>|<span data-ttu-id="d1d62-154">0</span><span class="sxs-lookup"><span data-stu-id="d1d62-154">0</span></span>|<span data-ttu-id="d1d62-155">985</span><span class="sxs-lookup"><span data-stu-id="d1d62-155">985</span></span>|
|<span data-ttu-id="d1d62-156">1/2/2011</span><span class="sxs-lookup"><span data-stu-id="d1d62-156">1/2/2011</span></span>|<span data-ttu-id="d1d62-157">0</span><span class="sxs-lookup"><span data-stu-id="d1d62-157">0</span></span>|<span data-ttu-id="d1d62-158">801</span><span class="sxs-lookup"><span data-stu-id="d1d62-158">801</span></span>|
|<span data-ttu-id="d1d62-159">1/3/2011</span><span class="sxs-lookup"><span data-stu-id="d1d62-159">1/3/2011</span></span>|<span data-ttu-id="d1d62-160">0</span><span class="sxs-lookup"><span data-stu-id="d1d62-160">0</span></span>|<span data-ttu-id="d1d62-161">1349</span><span class="sxs-lookup"><span data-stu-id="d1d62-161">1349</span></span>|

### <a name="create-input-and-output-classes"></a><span data-ttu-id="d1d62-162">Creare classi di input e output</span><span class="sxs-lookup"><span data-stu-id="d1d62-162">Create input and output classes</span></span>

1. <span data-ttu-id="d1d62-163">Aprire il file *Program.cs* e sostituire le istruzioni `using` esistenti con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d1d62-163">Open *Program.cs* file and replace the existing `using` statements with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. <span data-ttu-id="d1d62-164">Creare `ModelInput` classe.</span><span class="sxs-lookup"><span data-stu-id="d1d62-164">Create `ModelInput` class.</span></span> <span data-ttu-id="d1d62-165">Sotto la classe `Program` aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d1d62-165">Below the `Program` class, add the following code.</span></span>

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    <span data-ttu-id="d1d62-166">La classe `ModelInput` contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1d62-166">The `ModelInput` class contains the following columns:</span></span>

    - <span data-ttu-id="d1d62-167">**RentalDate**: data dell'osservazione.</span><span class="sxs-lookup"><span data-stu-id="d1d62-167">**RentalDate**: The date of the observation.</span></span>
    - <span data-ttu-id="d1d62-168">**Year**: anno codificato dell'osservazione (0 = 2011, 1 = 2012).</span><span class="sxs-lookup"><span data-stu-id="d1d62-168">**Year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
    - <span data-ttu-id="d1d62-169">**TotalRentals**: numero totale di noleggi di biciclette per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="d1d62-169">**TotalRentals**: The total number of bike rentals for that day.</span></span>

1. <span data-ttu-id="d1d62-170">Creare `ModelOutput` classe al di sotto della `ModelInput` classe appena creata.</span><span class="sxs-lookup"><span data-stu-id="d1d62-170">Create `ModelOutput` class below the newly created `ModelInput` class.</span></span>

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    <span data-ttu-id="d1d62-171">La classe `ModelOutput` contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1d62-171">The `ModelOutput` class contains the following columns:</span></span>

    - <span data-ttu-id="d1d62-172">**ForecastedRentals**: i valori stimati per il periodo previsto.</span><span class="sxs-lookup"><span data-stu-id="d1d62-172">**ForecastedRentals**: The predicted values for the forecasted period.</span></span>
    - <span data-ttu-id="d1d62-173">**LowerBoundRentals**: valori minimi stimati per il periodo previsto.</span><span class="sxs-lookup"><span data-stu-id="d1d62-173">**LowerBoundRentals**: The predicted minimum values for the forecasted period.</span></span>
    - <span data-ttu-id="d1d62-174">**UpperBoundRentals**: valori massimi stimati per il periodo previsto.</span><span class="sxs-lookup"><span data-stu-id="d1d62-174">**UpperBoundRentals**: The predicted maximum values for the forecasted period.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="d1d62-175">Definire i percorsi e inizializzare le variabili</span><span class="sxs-lookup"><span data-stu-id="d1d62-175">Define paths and initialize variables</span></span>

1. <span data-ttu-id="d1d62-176">All'interno del metodo `Main` definire le variabili per archiviare il percorso dei dati, la stringa di connessione e il percorso in cui salvare il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="d1d62-176">Inside the `Main` method, define variables to store the location of your data, connection string, and where to save the trained model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. <span data-ttu-id="d1d62-177">Inizializzare la variabile `mlContext` con una nuova istanza di [`MLContext`](xref:Microsoft.ML.MLContext) aggiungendo la riga seguente al metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-177">Initialize the `mlContext` variable with a new instance of [`MLContext`](xref:Microsoft.ML.MLContext) by adding the following line to the `Main` method.</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    <span data-ttu-id="d1d62-178">La classe [`MLContext`](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ml.NET e l'inizializzazione di mlContext crea un nuovo ambiente ml.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="d1d62-178">The [`MLContext`](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="d1d62-179">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d1d62-179">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="d1d62-180">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="d1d62-180">Load the data</span></span>

1. <span data-ttu-id="d1d62-181">Creare `DatabaseLoader` che carica i record di tipo `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-181">Create `DatabaseLoader` that loads records of type `ModelInput`.</span></span>

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. <span data-ttu-id="d1d62-182">Definire la query per caricare i dati dal database.</span><span class="sxs-lookup"><span data-stu-id="d1d62-182">Define the query to load the data from the database.</span></span>

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    <span data-ttu-id="d1d62-183">Gli algoritmi ML.NET prevedono che i dati siano di tipo [`Single`](xref:System.Single).</span><span class="sxs-lookup"><span data-stu-id="d1d62-183">ML.NET algorithms expect data to be of type [`Single`](xref:System.Single).</span></span> <span data-ttu-id="d1d62-184">Pertanto, i valori numerici provenienti dal database che non sono di tipo [`Real`](xref:System.Data.SqlDbType), un valore a virgola mobile e precisione singola, devono essere convertiti in [`Real`](xref:System.Data.SqlDbType).</span><span class="sxs-lookup"><span data-stu-id="d1d62-184">Therefore, numerical values coming from the database that are not of type [`Real`](xref:System.Data.SqlDbType), a single-precision floating-point value, have to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span>

    <span data-ttu-id="d1d62-185">Le colonne `Year` e `TotalRental` sono entrambi tipi integer nel database.</span><span class="sxs-lookup"><span data-stu-id="d1d62-185">The `Year` and `TotalRental` columns are both integer types in the database.</span></span> <span data-ttu-id="d1d62-186">Utilizzando la `CAST` funzione predefinita, viene eseguito il cast a `Real`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-186">Using the `CAST` built-in function, they are both cast to `Real`.</span></span>

1. <span data-ttu-id="d1d62-187">Creare una `DatabaseSource` per connettersi al database ed eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="d1d62-187">Create a `DatabaseSource` to connect to the database and execute the query.</span></span>

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. <span data-ttu-id="d1d62-188">Caricare i dati in un `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-188">Load the data into an `IDataView`.</span></span>

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. <span data-ttu-id="d1d62-189">Il set di dati contiene due anni di dati.</span><span class="sxs-lookup"><span data-stu-id="d1d62-189">The dataset contains two years worth of data.</span></span> <span data-ttu-id="d1d62-190">Solo i dati del primo anno vengono utilizzati per il training, il secondo anno viene considerato per confrontare i valori effettivi rispetto alla previsione prodotta dal modello.</span><span class="sxs-lookup"><span data-stu-id="d1d62-190">Only data from the first year is used for training, the second year is held out to compare the actual values against the forecast produced by the model.</span></span> <span data-ttu-id="d1d62-191">Filtrare i dati utilizzando la trasformazione [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) .</span><span class="sxs-lookup"><span data-stu-id="d1d62-191">Filter the data using the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) transform.</span></span>

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    <span data-ttu-id="d1d62-192">Per il primo anno, solo i valori della colonna `Year` inferiore a 1 vengono selezionati impostando il parametro `upperBound` su 1.</span><span class="sxs-lookup"><span data-stu-id="d1d62-192">For the first year, only the values in the `Year` column less than 1 are selected by setting the `upperBound` parameter to 1.</span></span> <span data-ttu-id="d1d62-193">Viceversa, per il secondo anno vengono selezionati i valori maggiori o uguali a 1 impostando il parametro `lowerBound` su 1.</span><span class="sxs-lookup"><span data-stu-id="d1d62-193">Conversely, for the second year, values greater than or equal to 1 are selected by setting the `lowerBound` parameter to 1.</span></span>

## <a name="define-time-series-analysis-pipeline"></a><span data-ttu-id="d1d62-194">Definire la pipeline di analisi della serie temporale</span><span class="sxs-lookup"><span data-stu-id="d1d62-194">Define time series analysis pipeline</span></span>

1. <span data-ttu-id="d1d62-195">Definire una pipeline che usa [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) per prevedere i valori in un set di dati di serie temporali.</span><span class="sxs-lookup"><span data-stu-id="d1d62-195">Define a pipeline that uses the [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) to forecast values in a time-series dataset.</span></span>

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    <span data-ttu-id="d1d62-196">Il `forecastingPipeline` accetta 365 punti dati per il primo anno ed esempi oppure suddivide il set di dati di serie temporali in intervalli di 30 giorni (mensili) come specificato dal parametro `seriesLength`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-196">The `forecastingPipeline` takes 365 data points for the first year and samples or splits the time-series dataset into 30-day (monthly) intervals as specified by the `seriesLength` parameter.</span></span> <span data-ttu-id="d1d62-197">Ognuno di questi esempi viene analizzato tramite una finestra settimanale o di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="d1d62-197">Each of these samples is analyzed through weekly or a 7-day window.</span></span> <span data-ttu-id="d1d62-198">Quando si determina il valore previsto per il periodo di tempo successivo, vengono utilizzati i valori dei sette giorni precedenti per eseguire una stima.</span><span class="sxs-lookup"><span data-stu-id="d1d62-198">When determining what the forecasted value for the next period(s) is, the values from previous seven days are used to make a prediction.</span></span> <span data-ttu-id="d1d62-199">Il modello è impostato in modo da prevedere sette periodi nel futuro in base a quanto definito dal parametro `horizon`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-199">The model is set to forecast seven periods into the future as defined by the `horizon` parameter.</span></span> <span data-ttu-id="d1d62-200">Poiché una previsione è un'ipotesi informata, non è sempre accurata al 100%.</span><span class="sxs-lookup"><span data-stu-id="d1d62-200">Because a forecast is an informed guess, it's not always 100% accurate.</span></span> <span data-ttu-id="d1d62-201">È quindi opportuno conoscere l'intervallo di valori negli scenari migliori e peggiori in base a quanto definito dai limiti superiore e inferiore.</span><span class="sxs-lookup"><span data-stu-id="d1d62-201">Therefore, it's good to know the range of values in the best and worst-case scenarios as defined by the upper and lower bounds.</span></span> <span data-ttu-id="d1d62-202">In questo caso, il livello di confidenza per i limiti inferiore e superiore è impostato su 95%.</span><span class="sxs-lookup"><span data-stu-id="d1d62-202">In this case, the level of confidence for the lower and upper bounds is set to 95%.</span></span> <span data-ttu-id="d1d62-203">Il livello di confidenza può essere aumentato o diminuito di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="d1d62-203">The confidence level can be increased or decreased accordingly.</span></span> <span data-ttu-id="d1d62-204">Maggiore è il valore, più ampio è l'intervallo tra i limiti superiore e inferiore per raggiungere il livello di confidenza desiderato.</span><span class="sxs-lookup"><span data-stu-id="d1d62-204">The higher the value, the wider the range is between the upper and lower bounds to achieve the desired level of confidence.</span></span>

1. <span data-ttu-id="d1d62-205">Utilizzare il metodo [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) per eseguire il training del modello e adattare i dati al `forecastingPipeline`definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d1d62-205">Use the [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) method to train the model and fit the data to the previously defined `forecastingPipeline`.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a><span data-ttu-id="d1d62-206">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="d1d62-206">Evaluate the model</span></span>

<span data-ttu-id="d1d62-207">Valutare le prestazioni del modello tramite la previsione dei dati dell'anno successivo e il confronto con i valori effettivi.</span><span class="sxs-lookup"><span data-stu-id="d1d62-207">Evaluate how well the model performs by forecasting next year's data and comparing it against the actual values.</span></span>

1. <span data-ttu-id="d1d62-208">Sotto il metodo `Main` creare un nuovo metodo di utilità denominato `Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-208">Below the `Main` method, create a new utility method called `Evaluate`.</span></span>

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="d1d62-209">All'interno del `Evaluate` metodo, prevedere i dati del secondo anno utilizzando il metodo [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) con il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="d1d62-209">Inside the `Evaluate` method, forecast the second year's data by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method with the trained model.</span></span>

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. <span data-ttu-id="d1d62-210">Ottenere i valori effettivi dai dati tramite il metodo [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) .</span><span class="sxs-lookup"><span data-stu-id="d1d62-210">Get the actual values from the data by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. <span data-ttu-id="d1d62-211">Ottenere i valori di previsione usando il metodo [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) .</span><span class="sxs-lookup"><span data-stu-id="d1d62-211">Get the forecast values by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. <span data-ttu-id="d1d62-212">Calcolare la differenza tra i valori effettivi e quelli previsti, comunemente indicati come errori.</span><span class="sxs-lookup"><span data-stu-id="d1d62-212">Calculate the difference between the actual and forecast values, commonly referred to as the error.</span></span>

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. <span data-ttu-id="d1d62-213">Misurare le prestazioni calcolando i valori di errore assoluto medio e radice media di errore quadratico.</span><span class="sxs-lookup"><span data-stu-id="d1d62-213">Measure performance by computing the Mean Absolute Error and Root Mean Squared Error values.</span></span>

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    <span data-ttu-id="d1d62-214">Per valutare le prestazioni, vengono usate le metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1d62-214">To evaluate performance, the following metrics are used:</span></span>

    - <span data-ttu-id="d1d62-215">**Errore assoluto medio**: misura il modo in cui le stime di chiusura corrispondono al valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="d1d62-215">**Mean Absolute Error**: Measures how close predictions are to the actual value.</span></span> <span data-ttu-id="d1d62-216">Questo valore è compreso tra 0 e infinito.</span><span class="sxs-lookup"><span data-stu-id="d1d62-216">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="d1d62-217">Più vicino a 0, più è alta la qualità del modello.</span><span class="sxs-lookup"><span data-stu-id="d1d62-217">The closer to 0, the better the quality of the model.</span></span>
    - <span data-ttu-id="d1d62-218">**Radice errore quadratico medio**: riepiloga l'errore nel modello.</span><span class="sxs-lookup"><span data-stu-id="d1d62-218">**Root Mean Squared Error**: Summarizes the error in the model.</span></span> <span data-ttu-id="d1d62-219">Questo valore è compreso tra 0 e infinito.</span><span class="sxs-lookup"><span data-stu-id="d1d62-219">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="d1d62-220">Più vicino a 0, più è alta la qualità del modello.</span><span class="sxs-lookup"><span data-stu-id="d1d62-220">The closer to 0, the better the quality of the model.</span></span>

1. <span data-ttu-id="d1d62-221">Inviare le metriche alla console.</span><span class="sxs-lookup"><span data-stu-id="d1d62-221">Output the metrics to the console.</span></span>

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. <span data-ttu-id="d1d62-222">Usare il metodo `Evaluate` all'interno del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-222">Use the `Evaluate` method inside the `Main` method.</span></span>

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a><span data-ttu-id="d1d62-223">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="d1d62-223">Save the model</span></span>

<span data-ttu-id="d1d62-224">Se si è soddisfatti del modello, salvarlo per usarlo in seguito in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d1d62-224">If you're satisfied with your model, save it for later use in other applications.</span></span>

1. <span data-ttu-id="d1d62-225">Nel metodo `Main` creare una [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="d1d62-225">In the `Main` method, create a [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span></span> <span data-ttu-id="d1d62-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) è un metodo pratico per eseguire stime singole.</span><span class="sxs-lookup"><span data-stu-id="d1d62-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) is a convenience method to make single predictions.</span></span>

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. <span data-ttu-id="d1d62-227">Salvare il modello in un file denominato `MLModel.zip` come specificato dalla variabile `modelPath` definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d1d62-227">Save the model to a file called `MLModel.zip` as specified by the previously defined `modelPath` variable.</span></span> <span data-ttu-id="d1d62-228">Utilizzare il metodo [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) per salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="d1d62-228">Use the [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) method to save the model.</span></span>

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a><span data-ttu-id="d1d62-229">Usare il modello per prevedere la domanda</span><span class="sxs-lookup"><span data-stu-id="d1d62-229">Use the model to forecast demand</span></span>

1. <span data-ttu-id="d1d62-230">Sotto il metodo `Evaluate` creare un nuovo metodo di utilità denominato `Forecast`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-230">Below the `Evaluate` method, create a new utility method called `Forecast`.</span></span>

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="d1d62-231">All'interno del metodo `Forecast` usare il metodo [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) per prevedere i noleggi per i sette giorni successivi.</span><span class="sxs-lookup"><span data-stu-id="d1d62-231">Inside the `Forecast` method, use the [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) method to forecast rentals for the next seven days.</span></span>

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. <span data-ttu-id="d1d62-232">Allinea i valori effettivi e di previsione per sette punti.</span><span class="sxs-lookup"><span data-stu-id="d1d62-232">Align the actual and forecast values for seven periods.</span></span>

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. <span data-ttu-id="d1d62-233">Scorrere l'output di previsione e visualizzarlo nella console.</span><span class="sxs-lookup"><span data-stu-id="d1d62-233">Iterate through the forecast output and display it on the console.</span></span>

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a><span data-ttu-id="d1d62-234">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d1d62-234">Run the application</span></span>

1. <span data-ttu-id="d1d62-235">All'interno del metodo `Main`, chiamare il metodo `Forecast`.</span><span class="sxs-lookup"><span data-stu-id="d1d62-235">Inside the `Main` method, call the `Forecast` method.</span></span>

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. <span data-ttu-id="d1d62-236">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d1d62-236">Run the application.</span></span> <span data-ttu-id="d1d62-237">Viene visualizzato un output simile al seguente nella console.</span><span class="sxs-lookup"><span data-stu-id="d1d62-237">Output similar to that below should appear on the console.</span></span> <span data-ttu-id="d1d62-238">Per brevità, l'output è stato condensato.</span><span class="sxs-lookup"><span data-stu-id="d1d62-238">For brevity, the output has been condensed.</span></span>

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

<span data-ttu-id="d1d62-239">L'ispezione dei valori effettivi e previsti Mostra le relazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1d62-239">Inspection of the actual and forecasted values shows the following relationships:</span></span>

![Confronto tra previsioni effettive di Visual Studio](./media/time-series-demand-forecasting/forecast.png)

<span data-ttu-id="d1d62-241">Sebbene i valori previsti non prevedano il numero esatto di affitti, forniscono un intervallo più limitato di valori che consentono a un'operazione di ottimizzare l'uso delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d1d62-241">While the forecasted values are not predicting the exact number of rentals, they provide a more narrow range of values that allows an operation to optimize their use of resources.</span></span>

<span data-ttu-id="d1d62-242">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="d1d62-242">Congratulations!</span></span> <span data-ttu-id="d1d62-243">A questo punto è stato creato un modello di Machine Learning di serie temporali per prevedere la richiesta di noleggio di biciclette.</span><span class="sxs-lookup"><span data-stu-id="d1d62-243">You've now successfully built a time series machine learning model to forecast bike rental demand.</span></span>

<span data-ttu-id="d1d62-244">Il codice sorgente per questa esercitazione è reperibile nel repository [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) .</span><span class="sxs-lookup"><span data-stu-id="d1d62-244">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1d62-245">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d1d62-245">Next steps</span></span>

- [<span data-ttu-id="d1d62-246">Attività di Machine Learning in ML.NET</span><span class="sxs-lookup"><span data-stu-id="d1d62-246">Machine learning tasks in ML.NET</span></span>](../resources/tasks.md)
- [<span data-ttu-id="d1d62-247">Migliorare l'accuratezza del modello</span><span class="sxs-lookup"><span data-stu-id="d1d62-247">Improve model accuracy</span></span>](../resources/improve-machine-learning-model-ml-net.md)
