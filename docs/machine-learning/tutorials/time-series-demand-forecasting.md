---
title: 'Tutorial: Prevedere la domanda di noleggio biciclette - serie di tempo'
description: Questa esercitazione illustra come prevedere la domanda per un servizio di noleggio biciclette utilizzando l'analisi di serie temporali univariate e ML.NET.
ms.date: 11/07/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: bceb32f4ea22ade6d3b49b3a99d7ec48a7ba168d
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607402"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a><span data-ttu-id="a338e-103">Tutorial: Prevedere la domanda di servizio di noleggio biciclette con analisi di serie temporali e ML.NET</span><span class="sxs-lookup"><span data-stu-id="a338e-103">Tutorial: Forecast bike rental service demand with time series analysis and ML.NET</span></span>

<span data-ttu-id="a338e-104">Informazioni su come prevedere la domanda di un servizio di noleggio biciclette utilizzando l'analisi di serie temporali univariate sui dati archiviati in un database di SQL Server con ML.NET.</span><span class="sxs-lookup"><span data-stu-id="a338e-104">Learn how to forecast demand for a bike rental service using univariate time series analysis on data stored in a SQL Server database with ML.NET.</span></span>

<span data-ttu-id="a338e-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="a338e-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="a338e-106">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="a338e-106">Understand the problem</span></span>
> * <span data-ttu-id="a338e-107">Caricare dati da un databaseLoad data from a database</span><span class="sxs-lookup"><span data-stu-id="a338e-107">Load data from a database</span></span>
> * <span data-ttu-id="a338e-108">Creare un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="a338e-108">Create a forecasting model</span></span>
> * <span data-ttu-id="a338e-109">Valutare il modello di previsione</span><span class="sxs-lookup"><span data-stu-id="a338e-109">Evaluate forecasting model</span></span>
> * <span data-ttu-id="a338e-110">Salvare un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="a338e-110">Save a forecasting model</span></span>
> * <span data-ttu-id="a338e-111">Utilizzare un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="a338e-111">Use a forecasting model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a338e-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a338e-112">Prerequisites</span></span>

- <span data-ttu-id="a338e-113">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o Visual Studio 2017 versione 15.6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="a338e-113">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="time-series-forecasting-sample-overview"></a><span data-ttu-id="a338e-114">Panoramica dell'esempio di previsione di serie temporali</span><span class="sxs-lookup"><span data-stu-id="a338e-114">Time series forecasting sample overview</span></span>

<span data-ttu-id="a338e-115">Questo esempio è **un'applicazione console .NET Core di C.NET** che prevede la domanda di noleggi di biciclette utilizzando un algoritmo di analisi di serie temporali univariato noto come Single Spectrum Analysis.</span><span class="sxs-lookup"><span data-stu-id="a338e-115">This sample is a **C# .NET Core console application** that forecasts demand for bike rentals using a univariate time series analysis algorithm known as Single Spectrum Analysis.</span></span> <span data-ttu-id="a338e-116">Il codice per questo esempio è disponibile nel repository dotnet/machinelearning-samples in GitHub.The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository on GitHub.</span><span class="sxs-lookup"><span data-stu-id="a338e-116">The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="a338e-117">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="a338e-117">Understand the problem</span></span>

<span data-ttu-id="a338e-118">Per eseguire un'operazione efficiente, la gestione dell'inventario svolge un ruolo chiave.</span><span class="sxs-lookup"><span data-stu-id="a338e-118">In order to run an efficient operation, inventory management plays a key role.</span></span> <span data-ttu-id="a338e-119">Avere troppo di un prodotto in magazzino significa prodotti invenduti seduti sugli scaffali senza generare alcun reddito.</span><span class="sxs-lookup"><span data-stu-id="a338e-119">Having too much of a product in stock means unsold products sitting on the shelves not generating any revenue.</span></span> <span data-ttu-id="a338e-120">Avere troppo poco prodotto porta a perdere vendite e clienti l'acquisto da concorrenti.</span><span class="sxs-lookup"><span data-stu-id="a338e-120">Having too little product leads to lost sales and customers purchasing from competitors.</span></span> <span data-ttu-id="a338e-121">Pertanto, la domanda costante è, qual è la quantità ottimale di inventario da tenere a portata di mano?</span><span class="sxs-lookup"><span data-stu-id="a338e-121">Therefore, the constant question is, what is the optimal amount of inventory to keep on hand?</span></span> <span data-ttu-id="a338e-122">L'analisi delle serie temporali consente di fornire una risposta a queste domande esaminando i dati cronologici, identificando i modelli e utilizzando queste informazioni per prevedere i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="a338e-122">Time-series analysis helps provide an answer to these questions by looking at historical data, identifying patterns, and using this information to forecast values some time in the future.</span></span>

<span data-ttu-id="a338e-123">La tecnica per l'analisi dei dati utilizzata in questa esercitazione è l'analisi univariate di serie temporali.</span><span class="sxs-lookup"><span data-stu-id="a338e-123">The technique for analyzing data used in this tutorial is univariate time-series analysis.</span></span> <span data-ttu-id="a338e-124">L'analisi univariate di serie temporali dà un'occhiata a una singola osservazione numerica in un periodo di tempo a intervalli specifici come le vendite mensili.</span><span class="sxs-lookup"><span data-stu-id="a338e-124">Univariate time-series analysis takes a look at a single numerical observation over a period of time at specific intervals such as monthly sales.</span></span>

<span data-ttu-id="a338e-125">L'algoritmo utilizzato in questa esercitazione è [Single Spectrum Analysis(SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span><span class="sxs-lookup"><span data-stu-id="a338e-125">The algorithm used in this tutorial is [Single Spectrum Analysis(SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span></span> <span data-ttu-id="a338e-126">SSA funziona scomponendo una serie temporale in un insieme di componenti principali.</span><span class="sxs-lookup"><span data-stu-id="a338e-126">SSA works by decomposing a time-series into a set of principal components.</span></span> <span data-ttu-id="a338e-127">Questi componenti possono essere interpretati come le parti di un segnale che corrispondono a tendenze, rumore, stagionalità e molti altri fattori.</span><span class="sxs-lookup"><span data-stu-id="a338e-127">These components can be interpreted as the parts of a signal that correspond to trends, noise, seasonality, and many other factors.</span></span> <span data-ttu-id="a338e-128">Quindi, questi componenti vengono ricostruiti e utilizzati per prevedere i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="a338e-128">Then, these components are reconstructed and used to forecast values some time in the future.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="a338e-129">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="a338e-129">Create console application</span></span>

1. <span data-ttu-id="a338e-130">Creare una nuova **applicazione console di .NET Core** di C, denominata "BikeDemandForecasting".</span><span class="sxs-lookup"><span data-stu-id="a338e-130">Create a new **C# .NET Core console application** called "BikeDemandForecasting".</span></span>
1. <span data-ttu-id="a338e-131">Installare **Microsoft.ML** pacchetto NuGet versione **1.4.0Install a version 1.4.0** NuGet package</span><span class="sxs-lookup"><span data-stu-id="a338e-131">Install **Microsoft.ML** version **1.4.0** NuGet package</span></span>
    1. <span data-ttu-id="a338e-132">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a338e-132">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="a338e-133">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda **Sfoglia,** cercare **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="a338e-133">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="a338e-134">Selezionare la casella di **controllo Includi versione non definitiva.**</span><span class="sxs-lookup"><span data-stu-id="a338e-134">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="a338e-135">Selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a338e-135">Select the **Install** button.</span></span>
    1. <span data-ttu-id="a338e-136">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="a338e-136">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="a338e-137">Ripetere questi passaggi per **System.Data.SqlClient** versione **4.7.0** e **Microsoft.ML.TimeSeries** versione **1.4.0**.</span><span class="sxs-lookup"><span data-stu-id="a338e-137">Repeat these steps for **System.Data.SqlClient** version **4.7.0** and **Microsoft.ML.TimeSeries** version **1.4.0**.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="a338e-138">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="a338e-138">Prepare and understand the data</span></span>

1. <span data-ttu-id="a338e-139">Creare una directory denominata *Data*.</span><span class="sxs-lookup"><span data-stu-id="a338e-139">Create a directory called *Data*.</span></span>
1. <span data-ttu-id="a338e-140">Scaricare il file di database [ *DailyDemand.mdf* ](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) e salvarlo nella directory *Data.*</span><span class="sxs-lookup"><span data-stu-id="a338e-140">Download the [*DailyDemand.mdf* database file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) and save it to the *Data* directory.</span></span>

> [!NOTE]
> <span data-ttu-id="a338e-141">I dati utilizzati in questa esercitazione provengono dal set di dati [UCI Bike Sharing](http://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span><span class="sxs-lookup"><span data-stu-id="a338e-141">The data used in this tutorial comes from the [UCI Bike Sharing Dataset](http://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span></span> <span data-ttu-id="a338e-142">Fanaee-T, Hadi e Gama, Joao, "Etichettatura degli eventi che combinano rilevatori di ensemble e conoscenze di base", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [Web Link](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span><span class="sxs-lookup"><span data-stu-id="a338e-142">Fanaee-T, Hadi, and Gama, Joao, 'Event labeling combining ensemble detectors and background knowledge', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [Web Link](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span></span>

<span data-ttu-id="a338e-143">Il set di dati originale contiene diverse colonne corrispondenti alla stagionalità e al tempo.</span><span class="sxs-lookup"><span data-stu-id="a338e-143">The original dataset contains several columns corresponding to seasonality and weather.</span></span> <span data-ttu-id="a338e-144">Per brevità e poiché l'algoritmo usato in questa esercitazione richiede solo i valori di una singola colonna numerica, il set di dati originale è stato condensato per includere solo le colonne seguenti:For brevity and because the algorithm used in this tutorial only requires the values from a single numerical column, the original dataset has been condensed to include only the following columns:</span><span class="sxs-lookup"><span data-stu-id="a338e-144">For brevity and because the algorithm used in this tutorial only requires the values from a single numerical column, the original dataset has been condensed to include only the following columns:</span></span>

- <span data-ttu-id="a338e-145">**dteday**: La data dell'osservazione.</span><span class="sxs-lookup"><span data-stu-id="a338e-145">**dteday**: The date of the observation.</span></span>
- <span data-ttu-id="a338e-146">**anno**: L'anno codificato dell'osservazione (0-2011, 1-2012).</span><span class="sxs-lookup"><span data-stu-id="a338e-146">**year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
- <span data-ttu-id="a338e-147">**cnt**: Il numero totale di noleggi di biciclette per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="a338e-147">**cnt**: The total number of bike rentals for that day.</span></span>

<span data-ttu-id="a338e-148">Il set di dati originale viene mappato a una tabella di database con lo schema seguente in un database di SQL Server.The original dataset is mapped to a database table with the following schema in a SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="a338e-148">The original dataset is mapped to a database table with the following schema in a SQL Server database.</span></span>

```SQL
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

<span data-ttu-id="a338e-149">Di seguito è riportato un esempio di dati:</span><span class="sxs-lookup"><span data-stu-id="a338e-149">The following is a sample of the data:</span></span>

| <span data-ttu-id="a338e-150">RentalDate</span><span class="sxs-lookup"><span data-stu-id="a338e-150">RentalDate</span></span> | <span data-ttu-id="a338e-151">Year</span><span class="sxs-lookup"><span data-stu-id="a338e-151">Year</span></span> | <span data-ttu-id="a338e-152">TotaleNoRentals</span><span class="sxs-lookup"><span data-stu-id="a338e-152">TotalRentals</span></span> |
| --- | --- | --- |
|<span data-ttu-id="a338e-153">1/1/2011</span><span class="sxs-lookup"><span data-stu-id="a338e-153">1/1/2011</span></span>|<span data-ttu-id="a338e-154">0</span><span class="sxs-lookup"><span data-stu-id="a338e-154">0</span></span>|<span data-ttu-id="a338e-155">985</span><span class="sxs-lookup"><span data-stu-id="a338e-155">985</span></span>|
|<span data-ttu-id="a338e-156">1/2/2011</span><span class="sxs-lookup"><span data-stu-id="a338e-156">1/2/2011</span></span>|<span data-ttu-id="a338e-157">0</span><span class="sxs-lookup"><span data-stu-id="a338e-157">0</span></span>|<span data-ttu-id="a338e-158">801</span><span class="sxs-lookup"><span data-stu-id="a338e-158">801</span></span>|
|<span data-ttu-id="a338e-159">1/3/2011</span><span class="sxs-lookup"><span data-stu-id="a338e-159">1/3/2011</span></span>|<span data-ttu-id="a338e-160">0</span><span class="sxs-lookup"><span data-stu-id="a338e-160">0</span></span>|<span data-ttu-id="a338e-161">1349</span><span class="sxs-lookup"><span data-stu-id="a338e-161">1349</span></span>|

### <a name="create-input-and-output-classes"></a><span data-ttu-id="a338e-162">Creare classi di input e outputCreate input and output classes</span><span class="sxs-lookup"><span data-stu-id="a338e-162">Create input and output classes</span></span>

1. <span data-ttu-id="a338e-163">Aprire *Program.cs* file e `using` sostituire le istruzioni esistenti con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a338e-163">Open *Program.cs* file and replace the existing `using` statements with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. <span data-ttu-id="a338e-164">Creare la classe `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="a338e-164">Create `ModelInput` class.</span></span> <span data-ttu-id="a338e-165">Sotto `Program` la classe, aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a338e-165">Below the `Program` class, add the following code.</span></span>

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    <span data-ttu-id="a338e-166">La `ModelInput` classe contiene le seguenti colonne:</span><span class="sxs-lookup"><span data-stu-id="a338e-166">The `ModelInput` class contains the following columns:</span></span>

    - <span data-ttu-id="a338e-167">**RentalDate**: La data dell'osservazione.</span><span class="sxs-lookup"><span data-stu-id="a338e-167">**RentalDate**: The date of the observation.</span></span>
    - <span data-ttu-id="a338e-168">**Anno**: L'anno codificato dell'osservazione (0-2011, 1-2012).</span><span class="sxs-lookup"><span data-stu-id="a338e-168">**Year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
    - <span data-ttu-id="a338e-169">**TotalRentals**: Il numero totale di noleggi di biciclette per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="a338e-169">**TotalRentals**: The total number of bike rentals for that day.</span></span>

1. <span data-ttu-id="a338e-170">Creare `ModelOutput` la classe `ModelInput` sotto la classe appena creata.</span><span class="sxs-lookup"><span data-stu-id="a338e-170">Create `ModelOutput` class below the newly created `ModelInput` class.</span></span>

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    <span data-ttu-id="a338e-171">La `ModelOutput` classe contiene le seguenti colonne:</span><span class="sxs-lookup"><span data-stu-id="a338e-171">The `ModelOutput` class contains the following columns:</span></span>

    - <span data-ttu-id="a338e-172">**ForecastedRentals**: I valori previsti per il periodo previsto.</span><span class="sxs-lookup"><span data-stu-id="a338e-172">**ForecastedRentals**: The predicted values for the forecasted period.</span></span>
    - <span data-ttu-id="a338e-173">**LowerBoundRentals:** valori minimi previsti per il periodo previsto.</span><span class="sxs-lookup"><span data-stu-id="a338e-173">**LowerBoundRentals**: The predicted minimum values for the forecasted period.</span></span>
    - <span data-ttu-id="a338e-174">**UpperBoundRentals: valori massimi previsti**per il periodo previsto.</span><span class="sxs-lookup"><span data-stu-id="a338e-174">**UpperBoundRentals**: The predicted maximum values for the forecasted period.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="a338e-175">Definire percorsi e inizializzare le variabiliDefine paths and initialize variables</span><span class="sxs-lookup"><span data-stu-id="a338e-175">Define paths and initialize variables</span></span>

1. <span data-ttu-id="a338e-176">All'interno del `Main` metodo, definire le variabili per archiviare la posizione dei dati, la stringa di connessione e dove salvare il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="a338e-176">Inside the `Main` method, define variables to store the location of your data, connection string, and where to save the trained model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. <span data-ttu-id="a338e-177">Inizializzare `mlContext` la variabile con [`MLContext`](xref:Microsoft.ML.MLContext) una nuova istanza `Main` di aggiungendo la riga seguente al metodo.</span><span class="sxs-lookup"><span data-stu-id="a338e-177">Initialize the `mlContext` variable with a new instance of [`MLContext`](xref:Microsoft.ML.MLContext) by adding the following line to the `Main` method.</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    <span data-ttu-id="a338e-178">La [`MLContext`](xref:Microsoft.ML.MLContext) classe è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di mlContext crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="a338e-178">The [`MLContext`](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="a338e-179">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="a338e-179">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="a338e-180">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="a338e-180">Load the data</span></span>

1. <span data-ttu-id="a338e-181">Creare `DatabaseLoader` che carica `ModelInput`i record di tipo .</span><span class="sxs-lookup"><span data-stu-id="a338e-181">Create `DatabaseLoader` that loads records of type `ModelInput`.</span></span>

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. <span data-ttu-id="a338e-182">Definire la query per caricare i dati dal database.</span><span class="sxs-lookup"><span data-stu-id="a338e-182">Define the query to load the data from the database.</span></span>

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    <span data-ttu-id="a338e-183">ML.NET algoritmi prevedono che [`Single`](xref:System.Single)i dati siano di tipo .</span><span class="sxs-lookup"><span data-stu-id="a338e-183">ML.NET algorithms expect data to be of type [`Single`](xref:System.Single).</span></span> <span data-ttu-id="a338e-184">Pertanto, i valori numerici provenienti [`Real`](xref:System.Data.SqlDbType)dal database che non sono di tipo , [`Real`](xref:System.Data.SqlDbType)un valore a virgola mobile a precisione singola, devono essere convertiti in .</span><span class="sxs-lookup"><span data-stu-id="a338e-184">Therefore, numerical values coming from the database that are not of type [`Real`](xref:System.Data.SqlDbType), a single-precision floating-point value, have to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span>

    <span data-ttu-id="a338e-185">Le `Year` `TotalRental` colonne e sono entrambi tipi integer nel database.</span><span class="sxs-lookup"><span data-stu-id="a338e-185">The `Year` and `TotalRental` columns are both integer types in the database.</span></span> <span data-ttu-id="a338e-186">Utilizzando `CAST` la funzione incorporata, è `Real`stato eseguito il cast in .</span><span class="sxs-lookup"><span data-stu-id="a338e-186">Using the `CAST` built-in function, they are both cast to `Real`.</span></span>

1. <span data-ttu-id="a338e-187">Creare `DatabaseSource` un per connettersi al database ed eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="a338e-187">Create a `DatabaseSource` to connect to the database and execute the query.</span></span>

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. <span data-ttu-id="a338e-188">Caricare i dati in un'interfaccia `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="a338e-188">Load the data into an `IDataView`.</span></span>

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. <span data-ttu-id="a338e-189">Il set di dati contiene due anni di dati.</span><span class="sxs-lookup"><span data-stu-id="a338e-189">The dataset contains two years worth of data.</span></span> <span data-ttu-id="a338e-190">Per il training vengono utilizzati solo i dati del primo anno, il secondo anno viene bloccato per confrontare i valori effettivi con quelli prodotti dal modello.</span><span class="sxs-lookup"><span data-stu-id="a338e-190">Only data from the first year is used for training, the second year is held out to compare the actual values against the forecast produced by the model.</span></span> <span data-ttu-id="a338e-191">Filtrare i [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) dati utilizzando la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="a338e-191">Filter the data using the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) transform.</span></span>

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    <span data-ttu-id="a338e-192">Per il primo anno, solo `Year` i valori nella colonna `upperBound` minore di 1 vengono selezionati impostando il parametro su 1.</span><span class="sxs-lookup"><span data-stu-id="a338e-192">For the first year, only the values in the `Year` column less than 1 are selected by setting the `upperBound` parameter to 1.</span></span> <span data-ttu-id="a338e-193">Al contrario, per il secondo anno, i valori maggiori `lowerBound` o uguali a 1 vengono selezionati impostando il parametro su 1.</span><span class="sxs-lookup"><span data-stu-id="a338e-193">Conversely, for the second year, values greater than or equal to 1 are selected by setting the `lowerBound` parameter to 1.</span></span>

## <a name="define-time-series-analysis-pipeline"></a><span data-ttu-id="a338e-194">Definire la pipeline di analisi delle serie temporaliDefine time series analysis pipeline</span><span class="sxs-lookup"><span data-stu-id="a338e-194">Define time series analysis pipeline</span></span>

1. <span data-ttu-id="a338e-195">Definire una pipeline che usa [ssaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) per prevedere i valori in un set di dati di serie temporali.</span><span class="sxs-lookup"><span data-stu-id="a338e-195">Define a pipeline that uses the [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) to forecast values in a time-series dataset.</span></span>

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    <span data-ttu-id="a338e-196">Prende `forecastingPipeline` 365 punti dati per il primo anno e campiona o divide il set di dati `seriesLength` della serie temporale in intervalli di 30 giorni (mensili) come specificato dal parametro.</span><span class="sxs-lookup"><span data-stu-id="a338e-196">The `forecastingPipeline` takes 365 data points for the first year and samples or splits the time-series dataset into 30-day (monthly) intervals as specified by the `seriesLength` parameter.</span></span> <span data-ttu-id="a338e-197">Ognuno di questi campioni viene analizzato attraverso una finestra settimanale o di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="a338e-197">Each of these samples is analyzed through weekly or a 7-day window.</span></span> <span data-ttu-id="a338e-198">Quando si determina il valore previsto per i periodi successivi, i valori dei sette giorni precedenti vengono utilizzati per eseguire una stima.</span><span class="sxs-lookup"><span data-stu-id="a338e-198">When determining what the forecasted value for the next period(s) is, the values from previous seven days are used to make a prediction.</span></span> <span data-ttu-id="a338e-199">Il modello è impostato per prevedere sette periodi `horizon` nel futuro come definito dal parametro.</span><span class="sxs-lookup"><span data-stu-id="a338e-199">The model is set to forecast seven periods into the future as defined by the `horizon` parameter.</span></span> <span data-ttu-id="a338e-200">Poiché una previsione è un'ipotesi informata, non è sempre accurata al 100%.</span><span class="sxs-lookup"><span data-stu-id="a338e-200">Because a forecast is an informed guess, it's not always 100% accurate.</span></span> <span data-ttu-id="a338e-201">Pertanto, è bene conoscere l'intervallo di valori negli scenari migliori e peggiori definiti dai limiti superiore e inferiore.</span><span class="sxs-lookup"><span data-stu-id="a338e-201">Therefore, it's good to know the range of values in the best and worst-case scenarios as defined by the upper and lower bounds.</span></span> <span data-ttu-id="a338e-202">In questo caso, il livello di attendibilità per i limiti inferiore e superiore è impostato su 95%.</span><span class="sxs-lookup"><span data-stu-id="a338e-202">In this case, the level of confidence for the lower and upper bounds is set to 95%.</span></span> <span data-ttu-id="a338e-203">Il livello di confidenza può essere aumentato o diminuito di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a338e-203">The confidence level can be increased or decreased accordingly.</span></span> <span data-ttu-id="a338e-204">Più alto è il valore, più ampio è l'intervallo tra i limiti superiore e inferiore per raggiungere il livello di confidenza desiderato.</span><span class="sxs-lookup"><span data-stu-id="a338e-204">The higher the value, the wider the range is between the upper and lower bounds to achieve the desired level of confidence.</span></span>

1. <span data-ttu-id="a338e-205">Utilizzare [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) il metodo per eseguire il training del `forecastingPipeline`modello e adattare i dati all'oggetto definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a338e-205">Use the [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) method to train the model and fit the data to the previously defined `forecastingPipeline`.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a><span data-ttu-id="a338e-206">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="a338e-206">Evaluate the model</span></span>

<span data-ttu-id="a338e-207">Valutare le prestazioni del modello prevedendo i dati dell'anno prossimo e confrontandoli con i valori effettivi.</span><span class="sxs-lookup"><span data-stu-id="a338e-207">Evaluate how well the model performs by forecasting next year's data and comparing it against the actual values.</span></span>

1. <span data-ttu-id="a338e-208">Sotto `Main` il metodo, creare un `Evaluate`nuovo metodo di utilità denominato .</span><span class="sxs-lookup"><span data-stu-id="a338e-208">Below the `Main` method, create a new utility method called `Evaluate`.</span></span>

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="a338e-209">All'interno del `Evaluate` metodo, prevedere i dati [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) del secondo anno utilizzando il metodo con il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="a338e-209">Inside the `Evaluate` method, forecast the second year's data by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method with the trained model.</span></span>

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. <span data-ttu-id="a338e-210">Ottenere i valori effettivi dai [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) dati utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="a338e-210">Get the actual values from the data by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. <span data-ttu-id="a338e-211">Ottenere i valori di [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) previsione utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="a338e-211">Get the forecast values by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. <span data-ttu-id="a338e-212">Calcolare la differenza tra i valori effettivi e quelli di previsione, comunemente indicati come errore.</span><span class="sxs-lookup"><span data-stu-id="a338e-212">Calculate the difference between the actual and forecast values, commonly referred to as the error.</span></span>

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. <span data-ttu-id="a338e-213">Misurare le prestazioni calcolando i valori Di errore assoluto medio e Errore al quadrato radice.</span><span class="sxs-lookup"><span data-stu-id="a338e-213">Measure performance by computing the Mean Absolute Error and Root Mean Squared Error values.</span></span>

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    <span data-ttu-id="a338e-214">Per valutare le prestazioni, vengono utilizzate le metriche seguenti:To evaluate performance, the following metrics are used:</span><span class="sxs-lookup"><span data-stu-id="a338e-214">To evaluate performance, the following metrics are used:</span></span>

    - <span data-ttu-id="a338e-215">**Errore assoluto medio**: misura il grado di stima ravvicinata al valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="a338e-215">**Mean Absolute Error**: Measures how close predictions are to the actual value.</span></span> <span data-ttu-id="a338e-216">Questo valore è compreso tra 0 e infinito.</span><span class="sxs-lookup"><span data-stu-id="a338e-216">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="a338e-217">Più vicino a 0, migliore è la qualità del modello.</span><span class="sxs-lookup"><span data-stu-id="a338e-217">The closer to 0, the better the quality of the model.</span></span>
    - <span data-ttu-id="a338e-218">**Root Mean Squared Error**: Riepiloga l'errore nel modello.</span><span class="sxs-lookup"><span data-stu-id="a338e-218">**Root Mean Squared Error**: Summarizes the error in the model.</span></span> <span data-ttu-id="a338e-219">Questo valore è compreso tra 0 e infinito.</span><span class="sxs-lookup"><span data-stu-id="a338e-219">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="a338e-220">Più vicino a 0, migliore è la qualità del modello.</span><span class="sxs-lookup"><span data-stu-id="a338e-220">The closer to 0, the better the quality of the model.</span></span>

1. <span data-ttu-id="a338e-221">Eseguire l'output delle metriche nella console.</span><span class="sxs-lookup"><span data-stu-id="a338e-221">Output the metrics to the console.</span></span>

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. <span data-ttu-id="a338e-222">Utilizzare `Evaluate` il metodo `Main` all'interno del metodo .</span><span class="sxs-lookup"><span data-stu-id="a338e-222">Use the `Evaluate` method inside the `Main` method.</span></span>

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a><span data-ttu-id="a338e-223">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="a338e-223">Save the model</span></span>

<span data-ttu-id="a338e-224">Se si è soddisfatti del modello, salvarlo per un utilizzo successivo in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a338e-224">If you're satisfied with your model, save it for later use in other applications.</span></span>

1. <span data-ttu-id="a338e-225">Nel `Main` metodo creare [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602)un file .</span><span class="sxs-lookup"><span data-stu-id="a338e-225">In the `Main` method, create a [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span></span> <span data-ttu-id="a338e-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602)è un metodo pratico per fare singole previsioni.</span><span class="sxs-lookup"><span data-stu-id="a338e-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) is a convenience method to make single predictions.</span></span>

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. <span data-ttu-id="a338e-227">Salvare il modello in `MLModel.zip` un file denominato `modelPath` come specificato dalla variabile definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a338e-227">Save the model to a file called `MLModel.zip` as specified by the previously defined `modelPath` variable.</span></span> <span data-ttu-id="a338e-228">Utilizzare [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) il metodo per salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="a338e-228">Use the [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) method to save the model.</span></span>

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a><span data-ttu-id="a338e-229">Utilizzare il modello per prevedere la domanda</span><span class="sxs-lookup"><span data-stu-id="a338e-229">Use the model to forecast demand</span></span>

1. <span data-ttu-id="a338e-230">Sotto `Evaluate` il metodo, creare un `Forecast`nuovo metodo di utilità denominato .</span><span class="sxs-lookup"><span data-stu-id="a338e-230">Below the `Evaluate` method, create a new utility method called `Forecast`.</span></span>

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="a338e-231">All'interno del `Forecast` [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) metodo, utilizzare il metodo per prevedere gli affitti per i prossimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="a338e-231">Inside the `Forecast` method, use the [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) method to forecast rentals for the next seven days.</span></span>

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. <span data-ttu-id="a338e-232">Allineare i valori effettivi e di previsione per sette periodi.</span><span class="sxs-lookup"><span data-stu-id="a338e-232">Align the actual and forecast values for seven periods.</span></span>

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. <span data-ttu-id="a338e-233">Scorrere l'output di previsione e visualizzarlo nella console.</span><span class="sxs-lookup"><span data-stu-id="a338e-233">Iterate through the forecast output and display it on the console.</span></span>

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a><span data-ttu-id="a338e-234">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="a338e-234">Run the application</span></span>

1. <span data-ttu-id="a338e-235">All'interno del `Main` `Forecast` metodo, chiamare il metodo .</span><span class="sxs-lookup"><span data-stu-id="a338e-235">Inside the `Main` method, call the `Forecast` method.</span></span>

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. <span data-ttu-id="a338e-236">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a338e-236">Run the application.</span></span> <span data-ttu-id="a338e-237">L'output simile a quello riportato di seguito dovrebbe essere visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="a338e-237">Output similar to that below should appear on the console.</span></span> <span data-ttu-id="a338e-238">Per brevità, l'output è stato condensato.</span><span class="sxs-lookup"><span data-stu-id="a338e-238">For brevity, the output has been condensed.</span></span>

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

<span data-ttu-id="a338e-239">L'ispezione dei valori effettivi e previsti mostra le seguenti relazioni:</span><span class="sxs-lookup"><span data-stu-id="a338e-239">Inspection of the actual and forecasted values shows the following relationships:</span></span>

![Confronto effettivo rispetto a previsione](./media/time-series-demand-forecasting/forecast.png)

<span data-ttu-id="a338e-241">Mentre i valori previsti non prevedono il numero esatto di noleggi, forniscono una gamma più ristretta di valori che consente a un'operazione di ottimizzare l'uso delle risorse.</span><span class="sxs-lookup"><span data-stu-id="a338e-241">While the forecasted values are not predicting the exact number of rentals, they provide a more narrow range of values that allows an operation to optimize their use of resources.</span></span>

<span data-ttu-id="a338e-242">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="a338e-242">Congratulations!</span></span> <span data-ttu-id="a338e-243">Ora hai creato con successo un modello di apprendimento automatico di serie temporali per prevedere la domanda di noleggio biciclette.</span><span class="sxs-lookup"><span data-stu-id="a338e-243">You've now successfully built a time series machine learning model to forecast bike rental demand.</span></span>

<span data-ttu-id="a338e-244">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/machinelearning-samples.You](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) can find the source code for this tutorial at the dotnet/machinelearning-samples repository.</span><span class="sxs-lookup"><span data-stu-id="a338e-244">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a338e-245">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a338e-245">Next steps</span></span>

- [<span data-ttu-id="a338e-246">Attività di apprendimento automatico in ML.NET</span><span class="sxs-lookup"><span data-stu-id="a338e-246">Machine learning tasks in ML.NET</span></span>](../resources/tasks.md)
- [<span data-ttu-id="a338e-247">Migliorare l'accuratezza del modello</span><span class="sxs-lookup"><span data-stu-id="a338e-247">Improve model accuracy</span></span>](../resources/improve-machine-learning-model-ml-net.md)
