---
title: Fornire il modello di Machine Learning nell'API Web ASP.NET Core
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET tramite Internet usando l'API Web ASP.NET Core
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 0cc13ec22b3a8805ec4aa17bf10560b2564ccd63
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2019
ms.locfileid: "58307915"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="a85c0-103">Procedura: Fornire il modello di Machine Learning tramite l'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a85c0-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="a85c0-104">Questa procedura illustra come fornire un modello di Machine Learning ML.NET predefinito nel Web usando un'API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a85c0-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="a85c0-105">In questo modo, gli utenti possono accedere all'API a scopo di previsione tramite i metodi HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="a85c0-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="a85c0-106">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="a85c0-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="a85c0-107">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a85c0-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="a85c0-108">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="a85c0-109">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="a85c0-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a85c0-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a85c0-110">Prerequisites</span></span>

- <span data-ttu-id="a85c0-111">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="a85c0-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="a85c0-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a85c0-112">Powershell.</span></span>
- <span data-ttu-id="a85c0-113">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="a85c0-113">Pre-trained model.</span></span>
    - <span data-ttu-id="a85c0-114">Usare l'[esercitazione sull'analisi del sentiment con ML.NET](../tutorials/sentiment-analysis.md) per creare il proprio modello.</span><span class="sxs-lookup"><span data-stu-id="a85c0-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="a85c0-115">Scaricare questo [modello di Machine Learning per l'analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="a85c0-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="a85c0-116">Creare il progetto per l'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a85c0-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="a85c0-117">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a85c0-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="a85c0-118">Dalla barra dei menu scegliere **File > Nuovo > Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="a85c0-119">Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="a85c0-120">Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="a85c0-121">Nella casella di testo **Nome** digitare "SentimentAnalysisWebAPI" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="a85c0-122">Nella finestra in cui sono visualizzati i diversi tipi di progetti ASP.NET Core selezionare **API** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="a85c0-123">Nel progetto creare una directory denominata *MLModels* in cui salvare i file dei modelli di Machine Learning predefiniti:</span><span class="sxs-lookup"><span data-stu-id="a85c0-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="a85c0-124">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="a85c0-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="a85c0-125">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a85c0-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="a85c0-126">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="a85c0-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a85c0-127">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a85c0-128">Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante Installa.</span><span class="sxs-lookup"><span data-stu-id="a85c0-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="a85c0-129">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="a85c0-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="a85c0-130">Aggiungere il modello al progetto per l'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a85c0-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="a85c0-131">Copiare il modello predefinito nella directory *MLModels*</span><span class="sxs-lookup"><span data-stu-id="a85c0-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="a85c0-132">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file ZIP del modello e scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a85c0-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="a85c0-133">In Avanzate impostare il valore di Copia nella directory di output su Copia se più recente.</span><span class="sxs-lookup"><span data-stu-id="a85c0-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="a85c0-134">Creare modelli di dati</span><span class="sxs-lookup"><span data-stu-id="a85c0-134">Build Data Models</span></span>

<span data-ttu-id="a85c0-135">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="a85c0-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="a85c0-136">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="a85c0-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="a85c0-137">Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati:</span><span class="sxs-lookup"><span data-stu-id="a85c0-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="a85c0-138">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="a85c0-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="a85c0-139">Digitare "DataModels" e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="a85c0-140">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere Aggiungi > Nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="a85c0-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="a85c0-141">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="a85c0-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="a85c0-142">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-142">Then, select the **Add** button.</span></span> <span data-ttu-id="a85c0-143">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="a85c0-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a85c0-144">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="a85c0-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="a85c0-145">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file **SentimentData.cs**:</span><span class="sxs-lookup"><span data-stu-id="a85c0-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="a85c0-146">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="a85c0-147">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="a85c0-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="a85c0-148">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a85c0-148">Then, select the Add button.</span></span> <span data-ttu-id="a85c0-149">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="a85c0-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="a85c0-150">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="a85c0-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="a85c0-151">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="a85c0-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="register-predictionengine-for-use-in-application"></a><span data-ttu-id="a85c0-152">Registrare PredictionEngine per usarlo nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a85c0-152">Register PredictionEngine for Use in Application</span></span>

<span data-ttu-id="a85c0-153">Per eseguire una sola stima, è possibile usare `PredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="a85c0-153">To make a single prediction, you can use `PredictionEngine`.</span></span> <span data-ttu-id="a85c0-154">Per usare `PredictionEngine` nell'applicazione, è necessario crearlo ogni volta che è necessario.</span><span class="sxs-lookup"><span data-stu-id="a85c0-154">In order to use `PredictionEngine` in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="a85c0-155">In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a85c0-155">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="a85c0-156">Il collegamento seguente fornisce altre informazioni sull'[inserimento delle dipendenze](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="a85c0-156">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="a85c0-157">Aprire la classe *Startup.cs* e aggiungere l'istruzione using seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="a85c0-157">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

2. <span data-ttu-id="a85c0-158">Aggiungere le righe di codice seguenti al metodo *ConfigureServices*:</span><span class="sxs-lookup"><span data-stu-id="a85c0-158">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddScoped<MLContext>();
    services.AddScoped<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
}
```

> [!WARNING]
> <span data-ttu-id="a85c0-159">`PredictionEngine` non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="a85c0-159">`PredictionEngine` is not thread-safe.</span></span> <span data-ttu-id="a85c0-160">Per limitare il costo della creazione dell'oggetto, la durata del servizio deve essere di tipo *Con ambito*.</span><span class="sxs-lookup"><span data-stu-id="a85c0-160">A way that you can limit the cost of creating the object is by making its service lifetime *Scoped*.</span></span> <span data-ttu-id="a85c0-161">Gli oggetti *con ambito* sono gli stessi all'interno di una richiesta, ma variano nelle diverse richieste.</span><span class="sxs-lookup"><span data-stu-id="a85c0-161">*Scoped* objects are the same within a request but different across requests.</span></span> <span data-ttu-id="a85c0-162">Visitare il collegamento seguente per altre informazioni sulle [durate dei servizi](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes).</span><span class="sxs-lookup"><span data-stu-id="a85c0-162">Visit the following link to learn more about [service lifetimes](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes).</span></span>

<span data-ttu-id="a85c0-163">In generale, questo codice inizializza automaticamente gli oggetti e i servizi quando vengono richiesti dall'applicazione invece di doverlo fare manualmente.</span><span class="sxs-lookup"><span data-stu-id="a85c0-163">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="a85c0-164">Creare il controller per le previsioni</span><span class="sxs-lookup"><span data-stu-id="a85c0-164">Create Predict Controller</span></span>

<span data-ttu-id="a85c0-165">Per elaborare le richieste HTTP in ingresso, è necessario creare un controller.</span><span class="sxs-lookup"><span data-stu-id="a85c0-165">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="a85c0-166">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Controllers* e quindi scegliere **Aggiungi > Controller**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-166">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="a85c0-167">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Controller API - Vuoto** e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a85c0-167">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="a85c0-168">Nel prompt impostare il campo **Nome controller** su *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="a85c0-168">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="a85c0-169">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a85c0-169">Then, select the Add button.</span></span> <span data-ttu-id="a85c0-170">Il file *PredictController.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="a85c0-170">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="a85c0-171">Aggiungere l'istruzione using seguente all'inizio del file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="a85c0-171">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using System;
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using Microsoft.ML;
```

<span data-ttu-id="a85c0-172">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="a85c0-172">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{
    
    private readonly PredictionEngine<SentimentData,SentimentPrediction> _predictionEngine;

    public PredictController(PredictionEngine<SentimentData, SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine; //Define prediction engine
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }

        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return Ok(isToxic);
    }
    
}
```

<span data-ttu-id="a85c0-173">`PredictionEngine` viene quindi assegnato passandolo al costruttore del controller ottenuto tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="a85c0-173">This is assigning the `PredictionEngine` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="a85c0-174">Nel metodo POST di questo controller `PredictionEngine` viene poi usato per eseguire previsioni e restituire i risultati all'utente in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a85c0-174">Then, in the POST method of this controller the `PredictionEngine` is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="a85c0-175">Testare l'API Web in locale</span><span class="sxs-lookup"><span data-stu-id="a85c0-175">Test Web API Locally</span></span>

<span data-ttu-id="a85c0-176">Dopo aver completato la configurazione, è possibile testare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a85c0-176">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="a85c0-177">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a85c0-177">Run the application.</span></span>
1. <span data-ttu-id="a85c0-178">Aprire PowerShell e immettere il codice seguente, dove PORT è la porta su cui l'applicazione è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="a85c0-178">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="a85c0-179">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="a85c0-179">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="a85c0-180">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a85c0-180">Congratulations!</span></span> <span data-ttu-id="a85c0-181">È stato creato il modello per eseguire previsioni tramite Internet usando un'API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a85c0-181">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a85c0-182">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a85c0-182">Next Steps</span></span>

- [<span data-ttu-id="a85c0-183">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="a85c0-183">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)