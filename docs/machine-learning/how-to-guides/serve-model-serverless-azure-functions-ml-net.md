---
title: Distribuire il modello ML.NET in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: db29e37660665b02ab93a07b37418f0c4c20a608
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2019
ms.locfileid: "57788641"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="76cc6-103">Procedura: Usare il modello ML.NET in Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="76cc6-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="76cc6-104">Questa procedura illustra come si possono eseguire singole previsioni usando un modello di Machine Learning ML.NET predefinito tramite Internet in un ambiente serverless come Funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="76cc6-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="76cc6-105">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="76cc6-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="76cc6-106">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="76cc6-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="76cc6-107">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="76cc6-108">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="76cc6-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="76cc6-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="76cc6-109">Prerequisites</span></span>

- <span data-ttu-id="76cc6-110">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" e "Sviluppo di Azure" installato.</span><span class="sxs-lookup"><span data-stu-id="76cc6-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="76cc6-111">Strumenti di Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="76cc6-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="76cc6-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="76cc6-112">Powershell</span></span>
- <span data-ttu-id="76cc6-113">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="76cc6-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="76cc6-114">Usare l'[esercitazione sull'analisi del sentiment con ML.NET](../tutorials/sentiment-analysis.md) per creare il proprio modello.</span><span class="sxs-lookup"><span data-stu-id="76cc6-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="76cc6-115">Scaricare questo [modello di Machine Learning per l'analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="76cc6-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="76cc6-116">Creare il progetto di Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="76cc6-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="76cc6-117">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="76cc6-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="76cc6-118">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="76cc6-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="76cc6-119">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="76cc6-120">Selezionare quindi il modello di progetto **Funzioni di Azure**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="76cc6-121">Nella casella di testo **Nome** digitare "SentimentAnalysisFunctionsApp" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="76cc6-122">Nella finestra di dialogo **Nuovo progetto** aprire l'elenco a discesa sopra le opzioni del progetto e selezionare **Azure Functions v2 (.NET Core)** (Funzioni di Azure v2 - .NET Core).</span><span class="sxs-lookup"><span data-stu-id="76cc6-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="76cc6-123">Selezionare quindi il progetto **Trigger HTTP** e infine fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="76cc6-124">Creare una directory denominata *MLModels* nel progetto per salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="76cc6-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="76cc6-125">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="76cc6-126">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="76cc6-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="76cc6-127">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="76cc6-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="76cc6-128">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="76cc6-129">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="76cc6-130">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="76cc6-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="76cc6-131">Aggiungere il modello predefinito al progetto</span><span class="sxs-lookup"><span data-stu-id="76cc6-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="76cc6-132">Copiare il modello predefinito nella cartella *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="76cc6-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="76cc6-133">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="76cc6-134">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="76cc6-135">Creare la funzione per analizzare il sentiment</span><span class="sxs-lookup"><span data-stu-id="76cc6-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="76cc6-136">Creare una classe per prevedere il sentiment.</span><span class="sxs-lookup"><span data-stu-id="76cc6-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="76cc6-137">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="76cc6-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="76cc6-138">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="76cc6-139">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Funzione di Azure** e impostare il campo **Nome** su *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="76cc6-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="76cc6-140">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="76cc6-141">Nella finestra di dialogo **Nuova funzione di Azure** selezionare **Trigger HTTP**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="76cc6-142">Fare quindi clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="76cc6-143">Il file *AnalyzeSentiment.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="76cc6-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="76cc6-144">Aggiungere l'istruzione `using` seguente all'inizio del file *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="76cc6-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Azure.WebJobs;
using Microsoft.Azure.WebJobs.Extensions.Http;
using Microsoft.AspNetCore.Http;
using Microsoft.Extensions.Logging;
using Newtonsoft.Json;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="76cc6-145">Creare i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="76cc6-145">Create Data Models</span></span>

<span data-ttu-id="76cc6-146">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="76cc6-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="76cc6-147">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="76cc6-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="76cc6-148">Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati: In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="76cc6-149">Digitare "DataModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="76cc6-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="76cc6-150">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="76cc6-151">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="76cc6-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="76cc6-152">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-152">Then, select the **Add** button.</span></span> <span data-ttu-id="76cc6-153">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="76cc6-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="76cc6-154">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="76cc6-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="76cc6-155">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file SentimentData.cs:</span><span class="sxs-lookup"><span data-stu-id="76cc6-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="76cc6-156">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="76cc6-157">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="76cc6-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="76cc6-158">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-158">Then, select the **Add** button.</span></span> <span data-ttu-id="76cc6-159">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="76cc6-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="76cc6-160">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="76cc6-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="76cc6-161">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="76cc6-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="76cc6-162">Aggiungere la log della previsione</span><span class="sxs-lookup"><span data-stu-id="76cc6-162">Add Prediction Logic</span></span>

<span data-ttu-id="76cc6-163">Sostituire l'implementazione esistente del metodo *Run* nella classe *AnalyzeSentiment* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="76cc6-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="76cc6-164">Eseguire il test in locale</span><span class="sxs-lookup"><span data-stu-id="76cc6-164">Test Locally</span></span>

<span data-ttu-id="76cc6-165">Dopo aver completato la configurazione, è possibile testare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="76cc6-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="76cc6-166">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="76cc6-166">Run the application</span></span>
1. <span data-ttu-id="76cc6-167">Aprire PowerShell e immettere il codice nel prompt, dove PORT è la porta su cui l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="76cc6-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="76cc6-168">La porta è in genere la 7071.</span><span class="sxs-lookup"><span data-stu-id="76cc6-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="76cc6-169">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="76cc6-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="76cc6-170">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="76cc6-170">Congratulations!</span></span> <span data-ttu-id="76cc6-171">È stato creato il modello per eseguire previsioni tramite Internet usando una funzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="76cc6-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="76cc6-172">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="76cc6-172">Next Steps</span></span>

- [<span data-ttu-id="76cc6-173">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="76cc6-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)