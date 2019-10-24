---
title: Distribuire un modello in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 09/12/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 4f805c638df9e60160c27fa08995ce393e59d007
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774533"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="cc3c6-103">Distribuire un modello in Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="cc3c6-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="cc3c6-104">Informazioni su come distribuire un modello di Machine Learning ML.NET con training preliminare per le previsioni su HTTP tramite un ambiente serverless di Funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="cc3c6-105">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc3c6-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="cc3c6-106">Prerequisites</span></span>

- <span data-ttu-id="cc3c6-107">[Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "sviluppo multipiattaforma .NET Core" e "sviluppo Azure" installato.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-107">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="cc3c6-108">Pacchetto NuGet Microsoft.NET.Sdk.Functions versione 1.0.28+.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- [<span data-ttu-id="cc3c6-109">Strumenti di Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="cc3c6-109">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="cc3c6-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc3c6-110">Powershell</span></span>
- <span data-ttu-id="cc3c6-111">Modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-111">Pre-trained model.</span></span> <span data-ttu-id="cc3c6-112">Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="cc3c6-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="cc3c6-113">Creare un progetto Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="cc3c6-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="cc3c6-114">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="cc3c6-115">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="cc3c6-116">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="cc3c6-117">Selezionare quindi il modello di progetto **Funzioni di Azure**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="cc3c6-118">Nella casella di testo **Nome** digitare "SentimentAnalysisFunctionsApp" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="cc3c6-119">Nella finestra di dialogo **Nuovo progetto** aprire l'elenco a discesa sopra le opzioni del progetto e selezionare **Azure Functions v2 (.NET Core)** (Funzioni di Azure v2 - .NET Core).</span><span class="sxs-lookup"><span data-stu-id="cc3c6-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="cc3c6-120">Selezionare quindi il progetto **Trigger HTTP** e infine fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="cc3c6-121">Creare una directory denominata *MLModels* nel progetto per salvare il modello:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="cc3c6-122">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="cc3c6-123">Digitare "MLModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="cc3c6-124">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="cc3c6-125">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="cc3c6-126">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="cc3c6-127">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="cc3c6-128">Installare il **pacchetto NuGet Microsoft.Azure.Functions.Extensions**:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="cc3c6-129">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="cc3c6-130">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Azure.Functions.Extensions**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="cc3c6-131">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="cc3c6-132">Installare il **pacchetto Microsoft.Extensions.ML NuGet**:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="cc3c6-133">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="cc3c6-134">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="cc3c6-135">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="cc3c6-136">Aggiornare il **pacchetto NuGet Microsoft.NET.Sdk.Functions** alla versione 1.0.28+:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28+:</span></span>

    <span data-ttu-id="cc3c6-137">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="cc3c6-138">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Installati, cercare **Microsoft.NET.Sdk.Functions**, selezionare il pacchetto nell'elenco, selezionare 1.0.28 o versione successiva nell'elenco a discesa Versione e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="cc3c6-139">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="cc3c6-140">Aggiungere il modello con training preliminare al progetto</span><span class="sxs-lookup"><span data-stu-id="cc3c6-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="cc3c6-141">Copiare il modello predefinito nella cartella *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="cc3c6-142">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="cc3c6-143">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="cc3c6-144">Creare la funzione di Azure per analizzare il sentiment</span><span class="sxs-lookup"><span data-stu-id="cc3c6-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="cc3c6-145">Creare una classe per prevedere il sentiment.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="cc3c6-146">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="cc3c6-147">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="cc3c6-148">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Funzione di Azure** e impostare il campo **Nome** su *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="cc3c6-149">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="cc3c6-150">Nella finestra di dialogo **Nuova funzione di Azure** selezionare **Trigger HTTP**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="cc3c6-151">Fare quindi clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="cc3c6-152">Il file *AnalyzeSentiment.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="cc3c6-153">Aggiungere l'istruzione `using` seguente all'inizio di *AnalyzeSentiment.cs*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

    [!code-csharp [AnalyzeUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L1-L11)]

    <span data-ttu-id="cc3c6-154">Per impostazione predefinita, la classe `AnalyzeSentiment` è `static`.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="cc3c6-155">Assicurarsi di rimuovere la parola chiave `static` dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {

    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="cc3c6-156">Creare modelli di dati</span><span class="sxs-lookup"><span data-stu-id="cc3c6-156">Create data models</span></span>

<span data-ttu-id="cc3c6-157">È necessario creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="cc3c6-158">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="cc3c6-159">Creare una directory denominata *Datamodes* nel progetto per salvare i modelli di dati: in Esplora soluzioni, fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="cc3c6-160">Digitare "DataModels" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="cc3c6-161">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="cc3c6-162">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="cc3c6-163">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-163">Then, select the **Add** button.</span></span>

    <span data-ttu-id="cc3c6-164">Il file *SentimentData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="cc3c6-165">Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    <span data-ttu-id="cc3c6-166">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. <span data-ttu-id="cc3c6-167">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="cc3c6-168">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="cc3c6-169">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-169">Then, select the **Add** button.</span></span> <span data-ttu-id="cc3c6-170">Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="cc3c6-171">Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    <span data-ttu-id="cc3c6-172">Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    <span data-ttu-id="cc3c6-173">`SentimentPrediction` eredita da `SentimentData` che consente l'accesso ai dati originali nella proprietà `SentimentText` e all'output generato dal modello.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="cc3c6-174">Registrare il servizio PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="cc3c6-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="cc3c6-175">Per eseguire una singola stima, è necessario creare un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="cc3c6-175">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="cc3c6-176">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-176">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="cc3c6-177">Inoltre, è necessario crearne un'istanza ovunque sia necessario all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-177">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="cc3c6-178">Con la crescita dell'applicazione, questo processo può diventare non gestibile.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-178">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="cc3c6-179">Per migliorare le prestazioni e thread safety, utilizzare una combinazione di inserimento delle dipendenze e il servizio `PredictionEnginePool`, che consente di creare un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) per l'utilizzo nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-179">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="cc3c6-180">Il collegamento seguente fornisce ulteriori informazioni se si desidera ottenere ulteriori informazioni sull' [inserimento delle dipendenze](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="cc3c6-180">The following link provides more information if you want to learn more about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="cc3c6-181">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-181">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="cc3c6-182">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-182">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="cc3c6-183">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-183">Then, select the **Add** button.</span></span>

    <span data-ttu-id="cc3c6-184">Il file *Startup.cs* verrà aperto nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-184">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="cc3c6-185">Aggiungere l'istruzione using seguente all'inizio di *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-185">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.Functions.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="cc3c6-186">Rimuovere il codice esistente sotto le istruzioni using e aggiungere il codice seguente al file *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-186">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {
            public override void Configure(IFunctionsHostBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
            }
        }
    }
    ```

<span data-ttu-id="cc3c6-187">A un livello elevato, questo codice inizializza automaticamente gli oggetti e i servizi per un uso successivo quando richiesto dall'applicazione anziché eseguire manualmente questa operazione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-187">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="cc3c6-188">I modelli di apprendimento automatico non sono statici.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-188">Machine learning models are not static.</span></span> <span data-ttu-id="cc3c6-189">Al momento della disponibilità dei nuovi dati di training, il modello viene nuovamente sottoposto a training e ridistribuito.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-189">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="cc3c6-190">Un modo per ottenere la versione più recente del modello nell'applicazione consiste nel ridistribuire l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-190">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="cc3c6-191">Questa operazione introduce tuttavia i tempi di inattività dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-191">However, this introduces application downtime.</span></span> <span data-ttu-id="cc3c6-192">Il servizio `PredictionEnginePool` fornisce un meccanismo per ricaricare un modello aggiornato senza interrompere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-192">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="cc3c6-193">Impostare il parametro `watchForChanges` su `true` e il `PredictionEnginePool` avvia un [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) in ascolto delle notifiche di modifica file System e genera eventi quando viene apportata una modifica al file.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-193">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="cc3c6-194">In questo modo viene richiesto all'`PredictionEnginePool` di ricaricare automaticamente il modello.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-194">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="cc3c6-195">Il modello è identificato dal parametro `modelName` in modo che sia possibile ricaricare più di un modello per applicazione al momento della modifica.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-195">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="cc3c6-196">In alternativa, è possibile utilizzare il metodo `FromUri` quando si utilizzano i modelli archiviati in remoto.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-196">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="cc3c6-197">Invece di controllare gli eventi di modifica dei file, `FromUri` esegue il polling della posizione remota per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-197">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="cc3c6-198">Per impostazione predefinita, l'intervallo di polling è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-198">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="cc3c6-199">È possibile aumentare o diminuire l'intervallo di polling in base ai requisiti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-199">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="cc3c6-200">Nell'esempio di codice riportato di seguito, il `PredictionEnginePool` esegue il polling del modello archiviato nell'URI specificato ogni minuto.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-200">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="cc3c6-201">Caricare il modello nella funzione</span><span class="sxs-lookup"><span data-stu-id="cc3c6-201">Load the model into the function</span></span>

<span data-ttu-id="cc3c6-202">Inserire il codice seguente all'interno della classe *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-202">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

[!code-csharp [AnalyzeCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L18-L24)]

<span data-ttu-id="cc3c6-203">Questo codice assegna `PredictionEnginePool` passandolo al costruttore della funzione ottenuto tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-203">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="cc3c6-204">Usare il modello per effettuare previsioni</span><span class="sxs-lookup"><span data-stu-id="cc3c6-204">Use the model to make predictions</span></span>

<span data-ttu-id="cc3c6-205">Sostituire l'implementazione esistente del metodo *Run* nella classe *AnalyzeSentiment* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-205">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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
    SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="cc3c6-206">Quando il metodo `Run` viene eseguito, i dati in ingresso dalla richiesta HTTP vengono deserializzati e usati come input per `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-206">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="cc3c6-207">Viene quindi chiamato il metodo `Predict` per eseguire stime utilizzando l'`SentimentAnalysisModel` registrato nella classe `Startup` e i risultati vengono restituiti all'utente in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-207">The `Predict` method is then called to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-locally"></a><span data-ttu-id="cc3c6-208">Eseguire il test in locale</span><span class="sxs-lookup"><span data-stu-id="cc3c6-208">Test locally</span></span>

<span data-ttu-id="cc3c6-209">Dopo aver completato la configurazione, è possibile testare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-209">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="cc3c6-210">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="cc3c6-210">Run the application</span></span>
1. <span data-ttu-id="cc3c6-211">Aprire PowerShell e immettere il codice nel prompt, dove PORT è la porta su cui l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-211">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="cc3c6-212">La porta è in genere la 7071.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-212">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="cc3c6-213">In caso di esito positivo, l'output sarà simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="cc3c6-213">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="cc3c6-214">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-214">Congratulations!</span></span> <span data-ttu-id="cc3c6-215">È stato creato il modello per eseguire previsioni tramite Internet usando una funzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-215">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cc3c6-216">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cc3c6-216">Next Steps</span></span>

- [<span data-ttu-id="cc3c6-217">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="cc3c6-217">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
