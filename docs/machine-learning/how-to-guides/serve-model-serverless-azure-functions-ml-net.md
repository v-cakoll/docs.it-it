---
title: Distribuire un modello in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: c30c1c2e6f00020d22fe32fb3f53cefe88d8bb09
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063507"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="0f9c1-103">Distribuire un modello in Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="0f9c1-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="0f9c1-104">Informazioni su come distribuire un modello di Machine Learning ML.NET con training preliminare per le previsioni su HTTP tramite un ambiente serverless di Funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="0f9c1-105">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f9c1-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0f9c1-106">Prerequisites</span></span>

- <span data-ttu-id="0f9c1-107">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" e "Sviluppo di Azure" installato.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- [<span data-ttu-id="0f9c1-108">Strumenti di Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="0f9c1-108">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="0f9c1-109">PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f9c1-109">Powershell</span></span>
- <span data-ttu-id="0f9c1-110">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-110">Pre-trained model.</span></span> <span data-ttu-id="0f9c1-111">Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="0f9c1-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="0f9c1-112">Creare un progetto Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="0f9c1-112">Create Azure Functions project</span></span>

1. <span data-ttu-id="0f9c1-113">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="0f9c1-114">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-114">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="0f9c1-115">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-115">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="0f9c1-116">Selezionare quindi il modello di progetto **Funzioni di Azure**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-116">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="0f9c1-117">Nella casella di testo **Nome** digitare "SentimentAnalysisFunctionsApp" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-117">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="0f9c1-118">Nella finestra di dialogo **Nuovo progetto** aprire l'elenco a discesa sopra le opzioni del progetto e selezionare **Azure Functions v2 (.NET Core)** (Funzioni di Azure v2 - .NET Core).</span><span class="sxs-lookup"><span data-stu-id="0f9c1-118">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="0f9c1-119">Selezionare quindi il progetto **Trigger HTTP** e infine fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-119">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="0f9c1-120">Creare una directory denominata *MLModels* nel progetto per salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-120">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="0f9c1-121">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-121">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="0f9c1-122">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-122">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="0f9c1-123">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-123">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="0f9c1-124">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-124">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="0f9c1-125">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-125">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="0f9c1-126">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-126">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="0f9c1-127">Installare il **pacchetto Microsoft.Extensions.ML NuGet**:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-127">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="0f9c1-128">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="0f9c1-129">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="0f9c1-130">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="0f9c1-131">Aggiungere il modello con training preliminare al progetto</span><span class="sxs-lookup"><span data-stu-id="0f9c1-131">Add pre-trained model to project</span></span>

1. <span data-ttu-id="0f9c1-132">Copiare il modello predefinito nella cartella *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="0f9c1-133">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="0f9c1-134">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="0f9c1-135">Creare la funzione di Azure per analizzare il sentiment</span><span class="sxs-lookup"><span data-stu-id="0f9c1-135">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="0f9c1-136">Creare una classe per prevedere il sentiment.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="0f9c1-137">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="0f9c1-138">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="0f9c1-139">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Funzione di Azure** e impostare il campo **Nome** su *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="0f9c1-140">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="0f9c1-141">Nella finestra di dialogo **Nuova funzione di Azure** selezionare **Trigger HTTP**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="0f9c1-142">Fare quindi clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="0f9c1-143">Il file *AnalyzeSentiment.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="0f9c1-144">Aggiungere l'istruzione `using` seguente all'inizio di *AnalyzeSentiment.cs*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-144">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="0f9c1-145">Per impostazione predefinita, la classe `AnalyzeSentiment` è `static`.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-145">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="0f9c1-146">Assicurarsi di rimuovere la parola chiave `static` dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-146">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="0f9c1-147">Creare i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="0f9c1-147">Create data models</span></span>

<span data-ttu-id="0f9c1-148">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-148">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="0f9c1-149">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="0f9c1-150">Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati: In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-150">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="0f9c1-151">Digitare "DataModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-151">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="0f9c1-152">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-152">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="0f9c1-153">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="0f9c1-154">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-154">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="0f9c1-155">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-155">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="0f9c1-156">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-156">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="0f9c1-157">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-157">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="0f9c1-158">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-158">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="0f9c1-159">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-159">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="0f9c1-160">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-160">Then, select the **Add** button.</span></span> <span data-ttu-id="0f9c1-161">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-161">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="0f9c1-162">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-162">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="0f9c1-163">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-163">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="0f9c1-164">`SentimentPrediction` eredita da `SentimentData` che consente l'accesso ai dati originali nella proprietà `SentimentText` e all'output generato dal modello.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-164">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="0f9c1-165">Registrare il servizio PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="0f9c1-165">Register PredictionEnginePool service</span></span>

<span data-ttu-id="0f9c1-166">Per effettuare una singola previsione, usare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="0f9c1-166">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="0f9c1-167">Per poter usare la classe [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) nell'applicazione è necessario crearla quando è richiesta.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-167">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="0f9c1-168">In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-168">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="0f9c1-169">Il collegamento seguente fornisce altre informazioni sull'[inserimento delle dipendenze](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="0f9c1-169">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="0f9c1-170">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-170">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="0f9c1-171">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="0f9c1-172">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-172">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="0f9c1-173">Il file *Startup.cs* verrà aperto nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-173">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="0f9c1-174">Aggiungere l'istruzione using seguente all'inizio di *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-174">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="0f9c1-175">Rimuovere il codice esistente sotto le istruzioni using e aggiungere il codice seguente al file *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-175">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

<span data-ttu-id="0f9c1-176">In generale, questo codice inizializza automaticamente gli oggetti e i servizi quando vengono richiesti dall'applicazione invece di doverlo fare manualmente.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-176">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="0f9c1-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="0f9c1-178">Per migliorare le prestazioni e le capacità di thread safety, usare il servizio `PredictionEnginePool` che crea una classe [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti `PredictionEngine` per l'uso da parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-178">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="register-startup-as-an-azure-functions-extension"></a><span data-ttu-id="0f9c1-179">Registrare Startup come estensione di Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="0f9c1-179">Register Startup as an Azure Functions extension</span></span>

<span data-ttu-id="0f9c1-180">Per poter usare `Startup` nell'applicazione è necessario registrarlo come estensione di Funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-180">In order to use `Startup` in your application, you need to register it as an Azure Functions extension.</span></span> <span data-ttu-id="0f9c1-181">Creare un nuovo file denominato *extensions.json* nel progetto, se non ne esiste già uno.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-181">Create a new file called *extensions.json* in your project if one does not already exist.</span></span>

1. <span data-ttu-id="0f9c1-182">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-182">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="0f9c1-183">Nella finestra di dialogo **Nuovo elemento** selezionare il nodo **Visual C#**  seguito dal nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-183">In the **New Item** dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="0f9c1-184">Quindi selezionare l'opzione **File Json**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-184">Then select the **Json File** option.</span></span> <span data-ttu-id="0f9c1-185">Nella casella di testo **Nome** digitare "extensions.json" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-185">In the **Name** text box, type "extensions.json" and then select the **OK** button.</span></span>

    <span data-ttu-id="0f9c1-186">Il file *extensions.json* verrà aperto nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-186">The *extensions.json* file opens in the code editor.</span></span> <span data-ttu-id="0f9c1-187">Aggiungere il contenuto seguente a *extensions.json*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-187">Add the following content to *extensions.json*:</span></span>
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. <span data-ttu-id="0f9c1-188">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file *extensions.json* e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-188">In Solution Explorer, right-click your *extensions.json* file and select **Properties**.</span></span> <span data-ttu-id="0f9c1-189">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="0f9c1-190">Caricare il modello nella funzione</span><span class="sxs-lookup"><span data-stu-id="0f9c1-190">Load the model into the function</span></span>

<span data-ttu-id="0f9c1-191">Inserire il codice seguente all'interno della classe *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-191">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="0f9c1-192">Questo codice assegna `PredictionEnginePool` passandolo al costruttore della funzione ottenuto tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-192">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="0f9c1-193">Usare il modello per effettuare previsioni</span><span class="sxs-lookup"><span data-stu-id="0f9c1-193">Use the model to make predictions</span></span>

<span data-ttu-id="0f9c1-194">Sostituire l'implementazione esistente del metodo *Run* nella classe *AnalyzeSentiment* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-194">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);
    
    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="0f9c1-195">Quando il metodo `Run` viene eseguito, i dati in ingresso dalla richiesta HTTP vengono deserializzati e usati come input per `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-195">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="0f9c1-196">Viene quindi chiamato il metodo `Predict` per generare una previsione e restituire il risultato all'utente.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-196">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="0f9c1-197">Eseguire il test in locale</span><span class="sxs-lookup"><span data-stu-id="0f9c1-197">Test locally</span></span>

<span data-ttu-id="0f9c1-198">Dopo aver completato la configurazione, è possibile testare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-198">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="0f9c1-199">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f9c1-199">Run the application</span></span>
1. <span data-ttu-id="0f9c1-200">Aprire PowerShell e immettere il codice nel prompt, dove PORT è la porta su cui l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-200">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="0f9c1-201">La porta è in genere la 7071.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-201">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="0f9c1-202">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="0f9c1-202">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="0f9c1-203">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-203">Congratulations!</span></span> <span data-ttu-id="0f9c1-204">È stato creato il modello per eseguire previsioni tramite Internet usando una funzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0f9c1-204">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f9c1-205">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0f9c1-205">Next Steps</span></span>

- [<span data-ttu-id="0f9c1-206">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="0f9c1-206">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
