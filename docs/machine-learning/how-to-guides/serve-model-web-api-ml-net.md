---
title: Distribuire un modello in un'API Web ASP.NET Core
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET tramite Internet usando l'API Web ASP.NET Core
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: b6801b7de5a17257be706f77a7a67aa87df96524
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398930"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="146d8-103">Distribuire un modello in un'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="146d8-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="146d8-104">Informazioni su come rendere disponibile un modello di Machine Learning ML.NET con training preliminare sul Web usando un'API Web ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="146d8-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="146d8-105">La disponibilità di un modello su un'API Web consente previsioni tramite metodi HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="146d8-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="146d8-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="146d8-106">Prerequisites</span></span>

- <span data-ttu-id="146d8-107">[Visual Studio 2017 versione 15.6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro ".NET Core cross-platform development" installato.</span><span class="sxs-lookup"><span data-stu-id="146d8-107">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="146d8-108">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="146d8-108">Powershell.</span></span>
- <span data-ttu-id="146d8-109">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="146d8-109">Pre-trained model.</span></span> <span data-ttu-id="146d8-110">Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="146d8-110">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="146d8-111">Creare un progetto API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="146d8-111">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="146d8-112">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="146d8-112">Open Visual Studio 2017.</span></span> <span data-ttu-id="146d8-113">Dalla barra dei menu scegliere **File > Nuovo > Progetto**.</span><span class="sxs-lookup"><span data-stu-id="146d8-113">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="146d8-114">Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="146d8-114">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="146d8-115">Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="146d8-115">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="146d8-116">Nella casella di testo **Nome** digitare "SentimentAnalysisWebAPI" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="146d8-116">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="146d8-117">Nella finestra in cui sono visualizzati i diversi tipi di progetti ASP.NET Core selezionare **API** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="146d8-117">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="146d8-118">Nel progetto creare una directory denominata *MLModels* in cui salvare i file dei modelli di Machine Learning predefiniti:</span><span class="sxs-lookup"><span data-stu-id="146d8-118">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="146d8-119">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="146d8-119">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="146d8-120">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="146d8-120">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="146d8-121">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="146d8-121">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="146d8-122">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="146d8-122">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="146d8-123">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante Installa.</span><span class="sxs-lookup"><span data-stu-id="146d8-123">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="146d8-124">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="146d8-124">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="146d8-125">Installare il **pacchetto Nuget Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="146d8-125">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="146d8-126">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="146d8-126">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="146d8-127">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante Installa.</span><span class="sxs-lookup"><span data-stu-id="146d8-127">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="146d8-128">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="146d8-128">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="146d8-129">Aggiungere il modello al progetto API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="146d8-129">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="146d8-130">Copiare il modello predefinito nella directory *MLModels*</span><span class="sxs-lookup"><span data-stu-id="146d8-130">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="146d8-131">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file ZIP del modello e scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="146d8-131">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="146d8-132">In Avanzate impostare il valore di Copia nella directory di output su Copia se più recente.</span><span class="sxs-lookup"><span data-stu-id="146d8-132">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="146d8-133">Creare i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="146d8-133">Create data models</span></span>

<span data-ttu-id="146d8-134">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="146d8-134">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="146d8-135">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="146d8-135">Add a new class to your project:</span></span>

1. <span data-ttu-id="146d8-136">Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati:</span><span class="sxs-lookup"><span data-stu-id="146d8-136">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="146d8-137">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="146d8-137">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="146d8-138">Digitare "DataModels" e premere **Invio**.</span><span class="sxs-lookup"><span data-stu-id="146d8-138">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="146d8-139">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere Aggiungi > Nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="146d8-139">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="146d8-140">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="146d8-140">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="146d8-141">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="146d8-141">Then, select the **Add** button.</span></span> <span data-ttu-id="146d8-142">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="146d8-142">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="146d8-143">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="146d8-143">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="146d8-144">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file **di SentimentData.cs:**</span><span class="sxs-lookup"><span data-stu-id="146d8-144">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. <span data-ttu-id="146d8-145">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* , quindi **scegliere Aggiungi > nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="146d8-145">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="146d8-146">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="146d8-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="146d8-147">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="146d8-147">Then, select the Add button.</span></span> <span data-ttu-id="146d8-148">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="146d8-148">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="146d8-149">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="146d8-149">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="146d8-150">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="146d8-150">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="146d8-151">`SentimentPrediction` eredita da `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="146d8-151">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="146d8-152">Ciò semplifica la visualizzazione dei dati originali nella proprietà `SentimentText` insieme all'output generato dal modello.</span><span class="sxs-lookup"><span data-stu-id="146d8-152">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span>

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="146d8-153">Registrare PredictionEnginePool per l'uso nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="146d8-153">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="146d8-154">Per eseguire una singola stima, [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)è necessario creare un file .</span><span class="sxs-lookup"><span data-stu-id="146d8-154">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="146d8-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="146d8-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="146d8-156">Inoltre, è necessario creare un'istanza di esso ovunque sia necessario all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-156">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="146d8-157">Man mano che l'applicazione cresce, questo processo può diventare ingestibile.</span><span class="sxs-lookup"><span data-stu-id="146d8-157">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="146d8-158">Per migliorare le prestazioni e la thread safety, `PredictionEnginePool` usare una [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) combinazione [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) di inserimento delle dipendenze e il servizio, che crea un oggetto da utilizzare in tutta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-158">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="146d8-159">Il collegamento seguente fornisce ulteriori informazioni se si desidera ottenere ulteriori informazioni sull'inserimento di [dipendenze in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="146d8-159">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="146d8-160">Aprire la classe *Startup.cs* e aggiungere l'istruzione using seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="146d8-160">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="146d8-161">Aggiungere il codice seguente al metodo *ConfigureServices*:</span><span class="sxs-lookup"><span data-stu-id="146d8-161">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
        .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    ```

<span data-ttu-id="146d8-162">A livello generale, questo codice inizializza automaticamente gli oggetti e i servizi per un utilizzo successivo quando richiesto dall'applicazione anziché dover eseguire manualmente.</span><span class="sxs-lookup"><span data-stu-id="146d8-162">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="146d8-163">I modelli di apprendimento automatico non sono statici.</span><span class="sxs-lookup"><span data-stu-id="146d8-163">Machine learning models are not static.</span></span> <span data-ttu-id="146d8-164">Man mano che i nuovi dati di training diventano disponibili, il modello viene riaddestrato e ridistribuito.</span><span class="sxs-lookup"><span data-stu-id="146d8-164">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="146d8-165">Un modo per ottenere la versione più recente del modello nell'applicazione consiste nel ridistribuire l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-165">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="146d8-166">Tuttavia, questo introduce i tempi di inattività dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-166">However, this introduces application downtime.</span></span> <span data-ttu-id="146d8-167">Il `PredictionEnginePool` servizio fornisce un meccanismo per ricaricare un modello aggiornato senza arrestare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-167">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="146d8-168">Impostare `watchForChanges` il `true`parametro `PredictionEnginePool` su [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) e gli avvii che ascoltano le notifiche di modifica del file system e generano eventi quando viene apportata una modifica al file.</span><span class="sxs-lookup"><span data-stu-id="146d8-168">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="146d8-169">In questo `PredictionEnginePool` modo viene richiesto di ricaricare automaticamente il modello.</span><span class="sxs-lookup"><span data-stu-id="146d8-169">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="146d8-170">Il modello è `modelName` identificato dal parametro in modo che più di un modello per applicazione possa essere ricaricato al momento della modifica.</span><span class="sxs-lookup"><span data-stu-id="146d8-170">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="146d8-171">In alternativa, è `FromUri` possibile utilizzare il metodo quando si lavora con modelli memorizzati in remoto.</span><span class="sxs-lookup"><span data-stu-id="146d8-171">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="146d8-172">Anziché controllare gli eventi `FromUri` di modifica dei file, esegue il polling della posizione remota per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="146d8-172">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="146d8-173">Il valore predefinito dell'intervallo di polling è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="146d8-173">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="146d8-174">È possibile aumentare o ridurre l'intervallo di polling in base ai requisiti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-174">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="146d8-175">Nell'esempio di codice `PredictionEnginePool` riportato di seguito, il modello esegue il polling del modello archiviato nell'URI specificato ogni minuto.</span><span class="sxs-lookup"><span data-stu-id="146d8-175">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a><span data-ttu-id="146d8-176">Creare il controller Predict</span><span class="sxs-lookup"><span data-stu-id="146d8-176">Create Predict controller</span></span>

<span data-ttu-id="146d8-177">Per elaborare le richieste HTTP in ingresso, creare un controller.</span><span class="sxs-lookup"><span data-stu-id="146d8-177">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="146d8-178">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Controllers* e quindi scegliere **Aggiungi > Controller**.</span><span class="sxs-lookup"><span data-stu-id="146d8-178">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="146d8-179">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Controller API - Vuoto** e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="146d8-179">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="146d8-180">Nel prompt impostare il campo **Nome controller** su *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="146d8-180">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="146d8-181">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="146d8-181">Then, select the Add button.</span></span> <span data-ttu-id="146d8-182">Il file *PredictController.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="146d8-182">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="146d8-183">Aggiungere l'istruzione using seguente all'inizio del file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="146d8-183">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="146d8-184">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="146d8-184">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="146d8-185">Questo codice assegna `PredictionEnginePool` passandolo al costruttore del controller ottenuto tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="146d8-185">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="146d8-186">Quindi, `Predict` il metodo `Post` del `PredictionEnginePool` controller utilizza il `SentimentAnalysisModel` per eseguire `Startup` stime utilizzando il registrato nella classe e restituisce i risultati all'utente se ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="146d8-186">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="146d8-187">Testare l'API Web in locale</span><span class="sxs-lookup"><span data-stu-id="146d8-187">Test web API locally</span></span>

<span data-ttu-id="146d8-188">Dopo aver completato la configurazione, è possibile testare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-188">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="146d8-189">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="146d8-189">Run the application.</span></span>
1. <span data-ttu-id="146d8-190">Aprire PowerShell e immettere il codice seguente, dove PORT è la porta su cui l'applicazione è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="146d8-190">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="146d8-191">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="146d8-191">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="146d8-192">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="146d8-192">Congratulations!</span></span> <span data-ttu-id="146d8-193">Il modello per effettuare previsioni in Internet usando un'API Web ASP.NET Core è stato reso disponibile.</span><span class="sxs-lookup"><span data-stu-id="146d8-193">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="146d8-194">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="146d8-194">Next Steps</span></span>

- [<span data-ttu-id="146d8-195">Distribuire in AzureDeploy to Azure</span><span class="sxs-lookup"><span data-stu-id="146d8-195">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)
