---
title: Distribuire un modello in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 06/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 7df7a6f9fcc5a4702171e1aac4b6b67e0c343748
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025983"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="8cbc1-103">Distribuire un modello in Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="8cbc1-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="8cbc1-104">Informazioni su come distribuire un modello di Machine Learning ML.NET con training preliminare per le previsioni su HTTP tramite un ambiente serverless di Funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="8cbc1-105">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cbc1-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8cbc1-106">Prerequisites</span></span>

- <span data-ttu-id="8cbc1-107">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" e "Sviluppo di Azure" installato.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="8cbc1-108">Pacchetto NuGet Microsoft.NET.Sdk.Functions versione 1.0.28+.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- [<span data-ttu-id="8cbc1-109">Strumenti di Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="8cbc1-109">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="8cbc1-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cbc1-110">Powershell</span></span>
- <span data-ttu-id="8cbc1-111">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-111">Pre-trained model.</span></span> <span data-ttu-id="8cbc1-112">Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="8cbc1-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="8cbc1-113">Creare un progetto Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="8cbc1-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="8cbc1-114">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="8cbc1-115">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="8cbc1-116">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="8cbc1-117">Selezionare quindi il modello di progetto **Funzioni di Azure**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="8cbc1-118">Nella casella di testo **Nome** digitare "SentimentAnalysisFunctionsApp" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="8cbc1-119">Nella finestra di dialogo **Nuovo progetto** aprire l'elenco a discesa sopra le opzioni del progetto e selezionare **Azure Functions v2 (.NET Core)** (Funzioni di Azure v2 - .NET Core).</span><span class="sxs-lookup"><span data-stu-id="8cbc1-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="8cbc1-120">Selezionare quindi il progetto **Trigger HTTP** e infine fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="8cbc1-121">Creare una directory denominata *MLModels* nel progetto per salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="8cbc1-122">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="8cbc1-123">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="8cbc1-124">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="8cbc1-125">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8cbc1-126">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="8cbc1-127">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="8cbc1-128">Installare il **pacchetto NuGet Microsoft.Azure.Functions.Extensions**:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="8cbc1-129">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8cbc1-130">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Azure.Functions.Extensions**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="8cbc1-131">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="8cbc1-132">Installare il **pacchetto Microsoft.Extensions.ML NuGet**:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="8cbc1-133">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8cbc1-134">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="8cbc1-135">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="8cbc1-136">Aggiornare il **pacchetto NuGet Microsoft.NET.Sdk.Functions** alla versione 1.0.28:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28:</span></span>

    <span data-ttu-id="8cbc1-137">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8cbc1-138">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Installati, cercare **Microsoft.NET.Sdk.Functions**, selezionare il pacchetto nell'elenco, selezionare 1.0.28 o versione successiva nell'elenco a discesa Versione e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="8cbc1-139">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="8cbc1-140">Aggiungere il modello con training preliminare al progetto</span><span class="sxs-lookup"><span data-stu-id="8cbc1-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="8cbc1-141">Copiare il modello predefinito nella cartella *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="8cbc1-142">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="8cbc1-143">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="8cbc1-144">Creare la funzione di Azure per analizzare il sentiment</span><span class="sxs-lookup"><span data-stu-id="8cbc1-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="8cbc1-145">Creare una classe per prevedere il sentiment.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="8cbc1-146">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="8cbc1-147">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="8cbc1-148">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Funzione di Azure** e impostare il campo **Nome** su *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="8cbc1-149">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="8cbc1-150">Nella finestra di dialogo **Nuova funzione di Azure** selezionare **Trigger HTTP**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="8cbc1-151">Fare quindi clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="8cbc1-152">Il file *AnalyzeSentiment.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="8cbc1-153">Aggiungere l'istruzione `using` seguente all'inizio di *AnalyzeSentiment.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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

    <span data-ttu-id="8cbc1-154">Per impostazione predefinita, la classe `AnalyzeSentiment` è `static`.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="8cbc1-155">Assicurarsi di rimuovere la parola chiave `static` dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="8cbc1-156">Creare i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="8cbc1-156">Create data models</span></span>

<span data-ttu-id="8cbc1-157">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="8cbc1-158">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="8cbc1-159">Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati: In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="8cbc1-160">Digitare "DataModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="8cbc1-161">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="8cbc1-162">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="8cbc1-163">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-163">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="8cbc1-164">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="8cbc1-165">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="8cbc1-166">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="8cbc1-167">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="8cbc1-168">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="8cbc1-169">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-169">Then, select the **Add** button.</span></span> <span data-ttu-id="8cbc1-170">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="8cbc1-171">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="8cbc1-172">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="8cbc1-173">`SentimentPrediction` eredita da `SentimentData` che consente l'accesso ai dati originali nella proprietà `SentimentText` e all'output generato dal modello.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="8cbc1-174">Registrare il servizio PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="8cbc1-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="8cbc1-175">Per effettuare una singola previsione, usare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="8cbc1-175">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="8cbc1-176">Per poter usare la classe [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) nell'applicazione è necessario crearla quando è richiesta.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-176">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="8cbc1-177">In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-177">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="8cbc1-178">Il collegamento seguente fornisce altre informazioni sull'[inserimento delle dipendenze](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="8cbc1-178">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="8cbc1-179">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-179">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="8cbc1-180">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-180">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="8cbc1-181">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-181">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="8cbc1-182">Il file *Startup.cs* verrà aperto nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-182">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="8cbc1-183">Aggiungere l'istruzione using seguente all'inizio di *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-183">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="8cbc1-184">Rimuovere il codice esistente sotto le istruzioni using e aggiungere il codice seguente al file *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-184">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

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

<span data-ttu-id="8cbc1-185">In generale, questo codice inizializza automaticamente gli oggetti e i servizi quando vengono richiesti dall'applicazione invece di doverlo fare manualmente.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-185">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="8cbc1-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="8cbc1-187">Per migliorare le prestazioni e le capacità di thread safety, usare il servizio `PredictionEnginePool` che crea una classe [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti `PredictionEngine` per l'uso da parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-187">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="8cbc1-188">Caricare il modello nella funzione</span><span class="sxs-lookup"><span data-stu-id="8cbc1-188">Load the model into the function</span></span>

<span data-ttu-id="8cbc1-189">Inserire il codice seguente all'interno della classe *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-189">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="8cbc1-190">Questo codice assegna `PredictionEnginePool` passandolo al costruttore della funzione ottenuto tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-190">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="8cbc1-191">Usare il modello per effettuare previsioni</span><span class="sxs-lookup"><span data-stu-id="8cbc1-191">Use the model to make predictions</span></span>

<span data-ttu-id="8cbc1-192">Sostituire l'implementazione esistente del metodo *Run* nella classe *AnalyzeSentiment* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-192">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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

<span data-ttu-id="8cbc1-193">Quando il metodo `Run` viene eseguito, i dati in ingresso dalla richiesta HTTP vengono deserializzati e usati come input per `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-193">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="8cbc1-194">Viene quindi chiamato il metodo `Predict` per generare una previsione e restituire il risultato all'utente.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-194">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="8cbc1-195">Eseguire il test in locale</span><span class="sxs-lookup"><span data-stu-id="8cbc1-195">Test locally</span></span>

<span data-ttu-id="8cbc1-196">Dopo aver completato la configurazione, è possibile testare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-196">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="8cbc1-197">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8cbc1-197">Run the application</span></span>
1. <span data-ttu-id="8cbc1-198">Aprire PowerShell e immettere il codice nel prompt, dove PORT è la porta su cui l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-198">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="8cbc1-199">La porta è in genere la 7071.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-199">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="8cbc1-200">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="8cbc1-200">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="8cbc1-201">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-201">Congratulations!</span></span> <span data-ttu-id="8cbc1-202">È stato creato il modello per eseguire previsioni tramite Internet usando una funzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="8cbc1-202">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8cbc1-203">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8cbc1-203">Next Steps</span></span>

- [<span data-ttu-id="8cbc1-204">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="8cbc1-204">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
