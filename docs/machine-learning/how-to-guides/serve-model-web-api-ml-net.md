---
title: Fornire il modello di Machine Learning nell'API Web ASP.NET Core
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET tramite Internet usando l'API Web ASP.NET Core
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856703"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="00cda-103">Procedura: Fornire il modello di Machine Learning tramite l'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="00cda-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="00cda-104">Questa procedura illustra come fornire un modello di Machine Learning ML.NET predefinito nel Web usando un'API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="00cda-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="00cda-105">In questo modo, gli utenti possono accedere all'API a scopo di previsione tramite i metodi HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="00cda-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="00cda-106">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="00cda-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="00cda-107">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="00cda-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="00cda-108">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="00cda-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="00cda-109">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="00cda-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00cda-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="00cda-110">Prerequisites</span></span>

- <span data-ttu-id="00cda-111">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="00cda-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="00cda-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00cda-112">Powershell.</span></span>
- <span data-ttu-id="00cda-113">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="00cda-113">Pre-trained model.</span></span>
    - <span data-ttu-id="00cda-114">Usare l'[esercitazione sull'analisi del sentiment con ML.NET](../tutorials/sentiment-analysis.md) per creare il proprio modello.</span><span class="sxs-lookup"><span data-stu-id="00cda-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="00cda-115">Scaricare questo [modello di Machine Learning per l'analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="00cda-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="00cda-116">Creare il progetto per l'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="00cda-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="00cda-117">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="00cda-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="00cda-118">Dalla barra dei menu scegliere **File > Nuovo > Progetto**.</span><span class="sxs-lookup"><span data-stu-id="00cda-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="00cda-119">Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="00cda-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="00cda-120">Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="00cda-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="00cda-121">Nella casella di testo **Nome** digitare "SentimentAnalysisWebAPI" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="00cda-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="00cda-122">Nella finestra in cui sono visualizzati i diversi tipi di progetti ASP.NET Core selezionare **API** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="00cda-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="00cda-123">Nel progetto creare una directory denominata *MLModels* in cui salvare i file dei modelli di Machine Learning predefiniti:</span><span class="sxs-lookup"><span data-stu-id="00cda-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="00cda-124">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="00cda-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="00cda-125">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="00cda-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="00cda-126">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="00cda-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="00cda-127">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="00cda-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="00cda-128">Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante Installa.</span><span class="sxs-lookup"><span data-stu-id="00cda-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="00cda-129">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="00cda-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="00cda-130">Aggiungere il modello al progetto per l'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="00cda-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="00cda-131">Copiare il modello predefinito nella directory *MLModels*</span><span class="sxs-lookup"><span data-stu-id="00cda-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="00cda-132">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file ZIP del modello e scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="00cda-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="00cda-133">In Avanzate impostare il valore di Copia nella directory di output su Copia se più recente.</span><span class="sxs-lookup"><span data-stu-id="00cda-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="00cda-134">Creare modelli di dati</span><span class="sxs-lookup"><span data-stu-id="00cda-134">Build Data Models</span></span>

<span data-ttu-id="00cda-135">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="00cda-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="00cda-136">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="00cda-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="00cda-137">Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati:</span><span class="sxs-lookup"><span data-stu-id="00cda-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="00cda-138">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="00cda-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="00cda-139">Digitare "DataModels" e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="00cda-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="00cda-140">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere Aggiungi > Nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="00cda-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="00cda-141">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="00cda-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="00cda-142">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="00cda-142">Then, select the **Add** button.</span></span> <span data-ttu-id="00cda-143">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="00cda-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="00cda-144">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="00cda-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="00cda-145">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file **SentimentData.cs**:</span><span class="sxs-lookup"><span data-stu-id="00cda-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="00cda-146">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="00cda-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="00cda-147">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="00cda-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="00cda-148">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="00cda-148">Then, select the Add button.</span></span> <span data-ttu-id="00cda-149">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="00cda-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="00cda-150">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="00cda-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="00cda-151">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="00cda-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="create-prediction-service"></a><span data-ttu-id="00cda-152">Creare il servizio di previsione</span><span class="sxs-lookup"><span data-stu-id="00cda-152">Create Prediction Service</span></span>

<span data-ttu-id="00cda-153">Per organizzare e riutilizzare la logica di previsione nell'intera applicazione, creare un servizio di previsione.</span><span class="sxs-lookup"><span data-stu-id="00cda-153">To organize and re-use the prediction logic throughout the entire application, create a prediction service.</span></span>

1. <span data-ttu-id="00cda-154">Nel progetto creare una directory denominata *Services* in cui archiviare i servizi usati dall'applicazione:</span><span class="sxs-lookup"><span data-stu-id="00cda-154">Create a directory named *Services* in your project to hold services to be used by the application:</span></span>

    <span data-ttu-id="00cda-155">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="00cda-155">In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="00cda-156">Digitare "Services" e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="00cda-156">Type "Services" and hit **Enter**.</span></span>

1. <span data-ttu-id="00cda-157">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Services* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="00cda-157">In Solution Explorer, right-click the *Services* directory, and then select **Add > New Item**.</span></span>
1. <span data-ttu-id="00cda-158">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** impostando *PredictionService.cs*.</span><span class="sxs-lookup"><span data-stu-id="00cda-158">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *PredictionService.cs*.</span></span> <span data-ttu-id="00cda-159">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="00cda-159">Then, select the **Add** button.</span></span> <span data-ttu-id="00cda-160">Il file *PredictionService.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="00cda-160">The *PredictionService.cs* file opens in the code editor.</span></span> <span data-ttu-id="00cda-161">Aggiungere l'istruzione using seguente all'inizio del file *PredictionService.cs*:</span><span class="sxs-lookup"><span data-stu-id="00cda-161">Add the following using statement to the top of *PredictionService.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

<span data-ttu-id="00cda-162">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictionService.cs*:</span><span class="sxs-lookup"><span data-stu-id="00cda-162">Remove the existing class definition and add the following code to the *PredictionService.cs* file:</span></span>

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a><span data-ttu-id="00cda-163">Registrare il servizio di previsione per usarlo nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="00cda-163">Register Predictions Service for Use in Application</span></span>

<span data-ttu-id="00cda-164">Per usare il servizio di previsione nell'applicazione, lo si dovrà creare ogni volta che sarà necessario.</span><span class="sxs-lookup"><span data-stu-id="00cda-164">To use the prediction service in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="00cda-165">In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="00cda-165">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="00cda-166">Il collegamento seguente fornisce altre informazioni sull'[inserimento delle dipendenze](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="00cda-166">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="00cda-167">Aprire la classe *Startup.cs* e aggiungere l'istruzione using seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="00cda-167">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

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
using SentimentAnalysisWebAPI.Services;
```

1. <span data-ttu-id="00cda-168">Aggiungere le righe di codice seguenti al metodo *ConfigureServices*:</span><span class="sxs-lookup"><span data-stu-id="00cda-168">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
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
    services.AddSingleton<PredictionService>();
}
```

<span data-ttu-id="00cda-169">In generale, questo codice inizializza automaticamente gli oggetti e i servizi quando vengono richiesti dall'applicazione invece di doverlo fare manualmente.</span><span class="sxs-lookup"><span data-stu-id="00cda-169">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="00cda-170">Creare il controller per le previsioni</span><span class="sxs-lookup"><span data-stu-id="00cda-170">Create Predict Controller</span></span>

<span data-ttu-id="00cda-171">Per elaborare le richieste HTTP in ingresso, è necessario creare un controller.</span><span class="sxs-lookup"><span data-stu-id="00cda-171">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="00cda-172">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Controllers* e quindi scegliere **Aggiungi > Controller**.</span><span class="sxs-lookup"><span data-stu-id="00cda-172">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="00cda-173">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Controller API - Vuoto** e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="00cda-173">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="00cda-174">Nel prompt impostare il campo **Nome controller** su *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="00cda-174">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="00cda-175">Selezionare quindi il pulsante Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="00cda-175">Then, select the Add button.</span></span> <span data-ttu-id="00cda-176">Il file *PredictController.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="00cda-176">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="00cda-177">Aggiungere l'istruzione using seguente all'inizio del file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="00cda-177">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

<span data-ttu-id="00cda-178">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="00cda-178">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

<span data-ttu-id="00cda-179">Il servizio di previsione viene quindi assegnato passandolo al costruttore del controller ottenuto tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="00cda-179">This is assigning the Prediction service by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="00cda-180">Nel metodo POST di questo controller il servizio di previsione viene poi usato per eseguire previsioni e restituire i risultati all'utente in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="00cda-180">Then, in the POST method of this controller the Prediction service is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="00cda-181">Testare l'API Web in locale</span><span class="sxs-lookup"><span data-stu-id="00cda-181">Test Web API Locally</span></span>

<span data-ttu-id="00cda-182">Dopo aver completato la configurazione, è possibile testare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="00cda-182">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="00cda-183">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="00cda-183">Run the application.</span></span>
1. <span data-ttu-id="00cda-184">Aprire PowerShell e immettere il codice seguente, dove PORT è la porta su cui l'applicazione è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="00cda-184">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="00cda-185">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="00cda-185">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="00cda-186">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="00cda-186">Congratulations!</span></span> <span data-ttu-id="00cda-187">È stato creato il modello per eseguire previsioni tramite Internet usando un'API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="00cda-187">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="00cda-188">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="00cda-188">Next Steps</span></span>

- [<span data-ttu-id="00cda-189">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="00cda-189">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)