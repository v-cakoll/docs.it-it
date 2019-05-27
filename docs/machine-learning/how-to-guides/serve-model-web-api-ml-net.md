---
title: Distribuire un modello in un'API Web ASP.NET Core
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET tramite Internet usando l'API Web ASP.NET Core
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: f8b8f74f752aeb243d4a2987929bd28ddc5f7d5a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641088"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="c030e-103">Distribuire un modello in un'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c030e-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="c030e-104">Informazioni su come rendere disponibile un modello di Machine Learning ML.NET con training preliminare sul Web usando un'API Web ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c030e-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="c030e-105">La disponibilità di un modello su un'API Web consente previsioni tramite metodi HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="c030e-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="c030e-106">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="c030e-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c030e-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c030e-107">Prerequisites</span></span>

- <span data-ttu-id="c030e-108">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="c030e-108">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="c030e-109">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c030e-109">Powershell.</span></span>
- <span data-ttu-id="c030e-110">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="c030e-110">Pre-trained model.</span></span> <span data-ttu-id="c030e-111">Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="c030e-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="c030e-112">Creare un progetto API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c030e-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="c030e-113">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c030e-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="c030e-114">Dalla barra dei menu scegliere **File > Nuovo > Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c030e-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="c030e-115">Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="c030e-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="c030e-116">Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c030e-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="c030e-117">Nella casella di testo **Nome** digitare "SentimentAnalysisWebAPI" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="c030e-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="c030e-118">Nella finestra in cui sono visualizzati i diversi tipi di progetti ASP.NET Core selezionare **API** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c030e-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="c030e-119">Nel progetto creare una directory denominata *MLModels* in cui salvare i file dei modelli di Machine Learning predefiniti:</span><span class="sxs-lookup"><span data-stu-id="c030e-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="c030e-120">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="c030e-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="c030e-121">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="c030e-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="c030e-122">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="c030e-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="c030e-123">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c030e-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c030e-124">Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante Installa.</span><span class="sxs-lookup"><span data-stu-id="c030e-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="c030e-125">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="c030e-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="c030e-126">Installare il **pacchetto Nuget Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="c030e-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="c030e-127">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c030e-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c030e-128">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante Installa.</span><span class="sxs-lookup"><span data-stu-id="c030e-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="c030e-129">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="c030e-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="c030e-130">Aggiungere il modello al progetto API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c030e-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="c030e-131">Copiare il modello predefinito nella directory *MLModels*</span><span class="sxs-lookup"><span data-stu-id="c030e-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="c030e-132">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file ZIP del modello e scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="c030e-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="c030e-133">In Avanzate impostare il valore di Copia nella directory di output su Copia se più recente.</span><span class="sxs-lookup"><span data-stu-id="c030e-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="c030e-134">Creare i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="c030e-134">Create data models</span></span>

<span data-ttu-id="c030e-135">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="c030e-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="c030e-136">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="c030e-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="c030e-137">Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati:</span><span class="sxs-lookup"><span data-stu-id="c030e-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="c030e-138">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="c030e-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="c030e-139">Digitare "DataModels" e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="c030e-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="c030e-140">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere Aggiungi > Nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="c030e-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="c030e-141">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="c030e-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="c030e-142">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c030e-142">Then, select the **Add** button.</span></span> <span data-ttu-id="c030e-143">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="c030e-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="c030e-144">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="c030e-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="c030e-145">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file **SentimentData.cs**:</span><span class="sxs-lookup"><span data-stu-id="c030e-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>
    
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

4. <span data-ttu-id="c030e-146">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="c030e-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="c030e-147">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="c030e-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="c030e-148">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c030e-148">Then, select the Add button.</span></span> <span data-ttu-id="c030e-149">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="c030e-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="c030e-150">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="c030e-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="c030e-151">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="c030e-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="c030e-152">`SentimentPrediction` eredita da `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="c030e-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="c030e-153">Ciò semplifica la visualizzazione dei dati originali nella proprietà `SentimentText` insieme all'output generato dal modello.</span><span class="sxs-lookup"><span data-stu-id="c030e-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span> 

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="c030e-154">Registrare PredictionEnginePool per l'uso nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="c030e-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="c030e-155">Per effettuare una singola previsione, usare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="c030e-155">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="c030e-156">Per poter usare la classe [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) nell'applicazione è necessario crearla quando è richiesta.</span><span class="sxs-lookup"><span data-stu-id="c030e-156">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="c030e-157">In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c030e-157">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="c030e-158">Per altre informazioni su questo argomento, vedere [Inserimento delle dipendenze in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="c030e-158">The following link provides more information if you want to learn about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="c030e-159">Aprire la classe *Startup.cs* e aggiungere l'istruzione using seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="c030e-159">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="c030e-160">Aggiungere il codice seguente al metodo *ConfigureServices*:</span><span class="sxs-lookup"><span data-stu-id="c030e-160">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

<span data-ttu-id="c030e-161">In generale, questo codice inizializza automaticamente gli oggetti e i servizi quando vengono richiesti dall'applicazione invece di doverlo fare manualmente.</span><span class="sxs-lookup"><span data-stu-id="c030e-161">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="c030e-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="c030e-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="c030e-163">Per migliorare le prestazioni e le capacità di thread safety, usare il servizio `PredictionEnginePool` che crea una classe [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti `PredictionEngine` per l'uso da parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c030e-163">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="c030e-164">Leggere il post di blog seguente per altre informazioni su come [creare e usare pool di oggetti `PredictionEngine` in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="c030e-164">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>  

## <a name="create-predict-controller"></a><span data-ttu-id="c030e-165">Creare il controller Predict</span><span class="sxs-lookup"><span data-stu-id="c030e-165">Create Predict controller</span></span>

<span data-ttu-id="c030e-166">Per elaborare le richieste HTTP in ingresso, creare un controller.</span><span class="sxs-lookup"><span data-stu-id="c030e-166">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="c030e-167">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Controllers* e quindi scegliere **Aggiungi > Controller**.</span><span class="sxs-lookup"><span data-stu-id="c030e-167">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="c030e-168">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Controller API - Vuoto** e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c030e-168">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="c030e-169">Nel prompt impostare il campo **Nome controller** su *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="c030e-169">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="c030e-170">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c030e-170">Then, select the Add button.</span></span> <span data-ttu-id="c030e-171">Il file *PredictController.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="c030e-171">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="c030e-172">Aggiungere l'istruzione using seguente all'inizio del file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="c030e-172">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="c030e-173">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="c030e-173">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>
    
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

            SentimentPrediction prediction = _predictionEnginePool.Predict(input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="c030e-174">Questo codice assegna `PredictionEnginePool` passandolo al costruttore del controller ottenuto tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c030e-174">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="c030e-175">Quindi, il metodo `Post` del controller `Predict` usa `PredictionEnginePool` per effettuare previsioni e restituire i risultati all'utente in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c030e-175">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="c030e-176">Testare l'API Web in locale</span><span class="sxs-lookup"><span data-stu-id="c030e-176">Test web API locally</span></span>

<span data-ttu-id="c030e-177">Dopo aver completato la configurazione, è possibile testare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c030e-177">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="c030e-178">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c030e-178">Run the application.</span></span>
1. <span data-ttu-id="c030e-179">Aprire PowerShell e immettere il codice seguente, dove PORT è la porta su cui l'applicazione è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="c030e-179">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="c030e-180">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="c030e-180">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="c030e-181">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c030e-181">Congratulations!</span></span> <span data-ttu-id="c030e-182">Il modello per effettuare previsioni in Internet usando un'API Web ASP.NET Core è stato reso disponibile.</span><span class="sxs-lookup"><span data-stu-id="c030e-182">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c030e-183">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c030e-183">Next Steps</span></span>

- [<span data-ttu-id="c030e-184">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="c030e-184">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
