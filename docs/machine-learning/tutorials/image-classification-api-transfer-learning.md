---
title: 'Esercitazione: ispezione visiva automatizzata tramite trasferimento Learning'
description: Questa esercitazione illustra come usare Transfer learning per eseguire il training di un modello di apprendimento approfondito di TensorFlow in ML.NET usando l'API di rilevamento immagini per classificare le immagini di superfici concrete come incrinate o non incrinate.
author: luisquintanilla
ms.author: luquinta
ms.date: 12/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 2915259d7c7031b9e699c7fd0cf65cf723c41680
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144422"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a><span data-ttu-id="953df-103">Esercitazione: ispezione visiva automatizzata tramite il trasferimento dell'apprendimento con l'API di classificazione delle immagini ML.NET</span><span class="sxs-lookup"><span data-stu-id="953df-103">Tutorial: Automated visual inspection using transfer learning with the ML.NET Image Classification API</span></span>

<span data-ttu-id="953df-104">Informazioni su come eseguire il training di un modello di apprendimento avanzato personalizzato usando il servizio di formazione per il trasferimento, un modello TensorFlow pretrainato e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non incrinate</span><span class="sxs-lookup"><span data-stu-id="953df-104">Learn how to train a custom deep learning model using transfer learning, a pretrained TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="953df-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="953df-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="953df-106">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="953df-106">Understand the problem</span></span>
> - <span data-ttu-id="953df-107">Informazioni sull'API di classificazione delle immagini ML.NET</span><span class="sxs-lookup"><span data-stu-id="953df-107">Learn about ML.NET Image Classification API</span></span>
> - <span data-ttu-id="953df-108">Informazioni sul modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="953df-108">Understand the pretrained model</span></span>
> - <span data-ttu-id="953df-109">Usare Transfer learning per eseguire il training di un modello di classificazione immagini TensorFlow personalizzato</span><span class="sxs-lookup"><span data-stu-id="953df-109">Use transfer learning to train a custom TensorFlow image classification model</span></span>
> - <span data-ttu-id="953df-110">Classificare le immagini con il modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="953df-110">Classify images with the custom model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="953df-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="953df-111">Prerequisites</span></span>

- <span data-ttu-id="953df-112">[Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o visual studio 2017 versione 15,6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="953df-112">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="image-classification-transfer-learning-sample-overview"></a><span data-ttu-id="953df-113">Panoramica dell'esempio di apprendimento della classificazione delle immagini Transfer</span><span class="sxs-lookup"><span data-stu-id="953df-113">Image classification transfer learning sample overview</span></span>

<span data-ttu-id="953df-114">Questo esempio è un'applicazione console .NET Core C# che classifica le immagini usando un modello TensorFlow di apprendimento avanzato con training.</span><span class="sxs-lookup"><span data-stu-id="953df-114">This sample is a C# .NET Core console application that classifies images using a pretrained deep learning TensorFlow model.</span></span> <span data-ttu-id="953df-115">Il codice per questo esempio è disponibile nel [repository dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="953df-115">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="953df-116">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="953df-116">Understand the problem</span></span>

<span data-ttu-id="953df-117">La classificazione delle immagini è un problema di visione artificiale.</span><span class="sxs-lookup"><span data-stu-id="953df-117">Image classification is a computer vision problem.</span></span> <span data-ttu-id="953df-118">La classificazione delle immagini acquisisce un'immagine come input e la Categorizza in una classe prescritta.</span><span class="sxs-lookup"><span data-stu-id="953df-118">Image classification takes an image as input and categorizes it into a prescribed class.</span></span> <span data-ttu-id="953df-119">Di seguito sono riportati alcuni scenari in cui è utile la classificazione delle immagini:</span><span class="sxs-lookup"><span data-stu-id="953df-119">Some scenarios where image classification is useful include:</span></span>

- <span data-ttu-id="953df-120">Riconoscimento facciale</span><span class="sxs-lookup"><span data-stu-id="953df-120">Facial recognition</span></span>
- <span data-ttu-id="953df-121">Rilevamento emozioni</span><span class="sxs-lookup"><span data-stu-id="953df-121">Emotion detection</span></span>
- <span data-ttu-id="953df-122">Diagnosi medica</span><span class="sxs-lookup"><span data-stu-id="953df-122">Medical diagnosis</span></span>
- <span data-ttu-id="953df-123">Rilevamento di punti di riferimento</span><span class="sxs-lookup"><span data-stu-id="953df-123">Landmark detection</span></span>

<span data-ttu-id="953df-124">Questa esercitazione esegue il training di un modello di classificazione delle immagini personalizzato per eseguire un'ispezione visiva automatizzata dei deck Bridge per identificare le strutture danneggiate da crepe.</span><span class="sxs-lookup"><span data-stu-id="953df-124">This tutorial trains a custom image classification model to perform automated visual inspection of bridge decks to identify structures that are damaged by cracks.</span></span>

## <a name="mlnet-image-classification-api"></a><span data-ttu-id="953df-125">API di classificazione delle immagini ML.NET</span><span class="sxs-lookup"><span data-stu-id="953df-125">ML.NET Image Classification API</span></span>

<span data-ttu-id="953df-126">ML.NET offre diversi modi per eseguire la classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="953df-126">ML.NET provides various ways of performing image classification.</span></span> <span data-ttu-id="953df-127">Questa esercitazione applica l'apprendimento del trasferimento usando l'API di classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="953df-127">This tutorial applies transfer learning using the Image Classification API.</span></span> <span data-ttu-id="953df-128">L'API di classificazione delle immagini USA [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), una libreria di basso livello che fornisce associazioni C# per l'API C++ TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="953df-128">The Image Classification API makes use of [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), a low-level library that provides C# bindings for the TensorFlow C++ API.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="953df-129">Che cos'è l'apprendimento trasferito?</span><span class="sxs-lookup"><span data-stu-id="953df-129">What is transfer learning?</span></span>

<span data-ttu-id="953df-130">Transfer Learning applica le informazioni ottenute dalla risoluzione di un problema a un altro problema correlato.</span><span class="sxs-lookup"><span data-stu-id="953df-130">Transfer learning applies knowledge gained from solving one problem to another related problem.</span></span>

<span data-ttu-id="953df-131">Per il training di un modello di apprendimento avanzato da zero è necessario impostare diversi parametri, una grande quantità di dati di training con etichette e una grande quantità di risorse di calcolo (centinaia di ore GPU).</span><span class="sxs-lookup"><span data-stu-id="953df-131">Training a deep learning model from scratch requires setting several parameters, a large amount of labeled training data, and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="953df-132">L'uso di un modello pretrainato insieme a transfer Learning consente di abbreviare il processo di training.</span><span class="sxs-lookup"><span data-stu-id="953df-132">Using a pretrained model along with transfer learning allows you to shortcut the training process.</span></span>

## <a name="training-process"></a><span data-ttu-id="953df-133">Processo di training</span><span class="sxs-lookup"><span data-stu-id="953df-133">Training process</span></span>

<span data-ttu-id="953df-134">L'API di classificazione delle immagini avvia il processo di training caricando un modello TensorFlow pre-trainato.</span><span class="sxs-lookup"><span data-stu-id="953df-134">The Image Classification API starts the training process by loading a pretrained TensorFlow model.</span></span> <span data-ttu-id="953df-135">Il processo di training è costituito da due passaggi:</span><span class="sxs-lookup"><span data-stu-id="953df-135">The training process consists of two steps:</span></span>

1. <span data-ttu-id="953df-136">Fase collo di bottiglia</span><span class="sxs-lookup"><span data-stu-id="953df-136">Bottleneck phase</span></span>
2. <span data-ttu-id="953df-137">Fase di training</span><span class="sxs-lookup"><span data-stu-id="953df-137">Training phase</span></span>

![Passaggi di training](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a><span data-ttu-id="953df-139">Fase collo di bottiglia</span><span class="sxs-lookup"><span data-stu-id="953df-139">Bottleneck phase</span></span>

<span data-ttu-id="953df-140">Durante la fase di collo di bottiglia, viene caricato il set di immagini di training e i valori dei pixel vengono usati come input, o funzionalità, per i livelli bloccati del modello con training.</span><span class="sxs-lookup"><span data-stu-id="953df-140">During the bottleneck phase, the set of training images is loaded and the pixel values are used as input, or features, for the frozen layers of the pretrained model.</span></span> <span data-ttu-id="953df-141">I livelli bloccati includono tutti i livelli nella rete neurale fino al penultimo livello, noto in modo informale come livello del collo di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="953df-141">The frozen layers include all of the layers in the neural network up to the penultimate layer, informally known as the bottleneck layer.</span></span> <span data-ttu-id="953df-142">A questi livelli viene fatto riferimento come bloccato perché non si verificherà alcun training su questi livelli e le operazioni sono pass-through.</span><span class="sxs-lookup"><span data-stu-id="953df-142">These layers are referred to as frozen because no training will occur on these layers and operations are pass-through.</span></span> <span data-ttu-id="953df-143">Si trova in questi livelli bloccati in cui vengono calcolati i modelli di livello inferiore che consentono di distinguere un modello tra le diverse classi.</span><span class="sxs-lookup"><span data-stu-id="953df-143">It's at these frozen layers where the lower-level patterns that help a model differentiate between the different classes are computed.</span></span> <span data-ttu-id="953df-144">Maggiore è il numero di livelli, più elevato a livello di calcolo questo passaggio è.</span><span class="sxs-lookup"><span data-stu-id="953df-144">The larger the number of layers, the more computationally intensive this step is.</span></span> <span data-ttu-id="953df-145">Fortunatamente, dal momento che si tratta di un calcolo monouso, i risultati possono essere memorizzati nella cache e usati nelle esecuzioni successive quando si sperimentano parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="953df-145">Fortunately, since this is a one-time calculation, the results can be cached and used in later runs when experimenting with different parameters.</span></span>

### <a name="training-phase"></a><span data-ttu-id="953df-146">Fase di training</span><span class="sxs-lookup"><span data-stu-id="953df-146">Training phase</span></span>

<span data-ttu-id="953df-147">Una volta calcolati i valori di output della fase di collo di bottiglia, essi vengono utilizzati come input per ripetere il training del livello finale del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-147">Once the output values from the bottleneck phase are computed, they are used as input to retrain the final layer of the model.</span></span> <span data-ttu-id="953df-148">Questo processo è iterativo e viene eseguito per il numero di volte specificato dai parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-148">This process is iterative and runs for the number of times specified by model parameters.</span></span> <span data-ttu-id="953df-149">Durante ogni esecuzione, la perdita e l'accuratezza vengono valutate.</span><span class="sxs-lookup"><span data-stu-id="953df-149">During each run, the loss and accuracy are evaluated.</span></span> <span data-ttu-id="953df-150">Quindi, vengono apportate le regolazioni appropriate per migliorare il modello con l'obiettivo di ridurre al minimo la perdita e massimizzare la precisione.</span><span class="sxs-lookup"><span data-stu-id="953df-150">Then, the appropriate adjustments are made to improve the model with the goal of minimizing the loss and maximizing the accuracy.</span></span> <span data-ttu-id="953df-151">Al termine del training, vengono restituiti due formati di modello.</span><span class="sxs-lookup"><span data-stu-id="953df-151">Once training is finished, two model formats are output.</span></span> <span data-ttu-id="953df-152">Una di esse è la `.pb` versione del modello e l'altra è la `.zip` versione serializzata ml.NET del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-152">One of them is the `.pb` version of the model and the other is the `.zip` ML.NET serialized version of the model.</span></span> <span data-ttu-id="953df-153">Quando si lavora in ambienti supportati da ML.NET, è consigliabile usare la `.zip` versione del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-153">When working in environments supported by ML.NET, it is recommended to use the `.zip` version of the model.</span></span> <span data-ttu-id="953df-154">Tuttavia, negli ambienti in cui ML.NET non è supportato, è possibile usare la `.pb` versione.</span><span class="sxs-lookup"><span data-stu-id="953df-154">However, in environments where ML.NET is not supported, you have the option of using the `.pb` version.</span></span>

## <a name="understand-the-pretrained-model"></a><span data-ttu-id="953df-155">Informazioni sul modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="953df-155">Understand the pretrained model</span></span>

<span data-ttu-id="953df-156">Il modello con training pretrain usato in questa esercitazione è la variante a 101 livelli del modello di rete residua (ResNet) v2.</span><span class="sxs-lookup"><span data-stu-id="953df-156">The pretrained model used in this tutorial is the 101-layer variant of the Residual Network (ResNet) v2 model.</span></span> <span data-ttu-id="953df-157">Il modello originale viene sottoposto a training per classificare le immagini in un centinaio di categorie.</span><span class="sxs-lookup"><span data-stu-id="953df-157">The original model is trained to classify images into a thousand categories.</span></span> <span data-ttu-id="953df-158">Il modello accetta come input un'immagine di dimensione 224 x 224 e restituisce le probabilità della classe per ogni classe su cui è stato eseguito il training.</span><span class="sxs-lookup"><span data-stu-id="953df-158">The model takes as input an image of size 224 x 224 and outputs the class probabilities for each of the classes it's trained on.</span></span> <span data-ttu-id="953df-159">Parte di questo modello viene utilizzata per eseguire il training di un nuovo modello utilizzando immagini personalizzate per eseguire stime tra due classi.</span><span class="sxs-lookup"><span data-stu-id="953df-159">Part of this model is used to train a new model using custom images to make predictions between two classes.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="953df-160">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="953df-160">Create console application</span></span>

<span data-ttu-id="953df-161">Ora che si dispone di una conoscenza generale del trasferimento dell'apprendimento e dell'API di classificazione delle immagini, è il momento di compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="953df-161">Now that you have a general understanding of transfer learning and the Image Classification API, it's time to build the application.</span></span>

1. <span data-ttu-id="953df-162">Creare un' **applicazione console C# .NET Core** denominata "DeepLearning_ImageClassification_Binary".</span><span class="sxs-lookup"><span data-stu-id="953df-162">Create a **C# .NET Core Console Application** called "DeepLearning_ImageClassification_Binary".</span></span>
1. <span data-ttu-id="953df-163">Installare il pacchetto NuGet **Microsoft.ml** versione **1.4.0** :</span><span class="sxs-lookup"><span data-stu-id="953df-163">Install the **Microsoft.ML** version **1.4.0** NuGet Package:</span></span>
    1. <span data-ttu-id="953df-164">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="953df-164">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="953df-165">Scegliere "nuget.org" come origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="953df-165">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="953df-166">Selezionare la scheda **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="953df-166">Select the **Browse** tab.</span></span>
    1. <span data-ttu-id="953df-167">Selezionare la casella di controllo **Includi versione preliminare** .</span><span class="sxs-lookup"><span data-stu-id="953df-167">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="953df-168">Cercare **Microsoft.ml**.</span><span class="sxs-lookup"><span data-stu-id="953df-168">Search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="953df-169">Selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="953df-169">Select the **Install** button.</span></span>
    1. <span data-ttu-id="953df-170">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="953df-170">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="953df-171">Ripetere questi passaggi per i pacchetti NuGet **Microsoft. ml. Vision** versione **1.4.0**, **SciSharp. TensorFlow. Redist** Version **1.15.0**e **Microsoft. ml. ImageAnalytics** Version **1.4.0** .</span><span class="sxs-lookup"><span data-stu-id="953df-171">Repeat these steps for the **Microsoft.ML.Vision** version **1.4.0**, **SciSharp.TensorFlow.Redist** version **1.15.0**, and **Microsoft.ML.ImageAnalytics** version **1.4.0** NuGet packages.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="953df-172">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="953df-172">Prepare and understand the data</span></span>

> [!NOTE]
> <span data-ttu-id="953df-173">I set di impostazioni per questa esercitazione sono di Maguire, Marc; Dorafshan, Sattar; e Thomas, Robert J., "SDNET2018: un set di dati concreti per le immagini per le applicazioni di Machine Learning" (2018).</span><span class="sxs-lookup"><span data-stu-id="953df-173">The datasets for this tutorial are from Maguire, Marc; Dorafshan, Sattar; and Thomas, Robert J., "SDNET2018: A concrete crack image dataset for machine learning applications" (2018).</span></span> <span data-ttu-id="953df-174">Esplorare tutti i set di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="953df-174">Browse all Datasets.</span></span> <span data-ttu-id="953df-175">Carta 48.</span><span class="sxs-lookup"><span data-stu-id="953df-175">Paper 48.</span></span> <https://digitalcommons.usu.edu/all_datasets/48>

<span data-ttu-id="953df-176">SDNET2018 è un set di dati di immagini che contiene annotazioni per le strutture concrete incrinate e non incrinate (Bridge, muri e pavimentazione).</span><span class="sxs-lookup"><span data-stu-id="953df-176">SDNET2018 is an image dataset that contains annotations for cracked and non-cracked concrete structures (bridge decks, walls, and pavement).</span></span>

![Esempi di Deck Bridge per set di dati SDNET2018](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

<span data-ttu-id="953df-178">I dati sono organizzati in tre sottodirectory:</span><span class="sxs-lookup"><span data-stu-id="953df-178">The data is organized in three subdirectories:</span></span>

- <span data-ttu-id="953df-179">D contiene immagini del deck Bridge</span><span class="sxs-lookup"><span data-stu-id="953df-179">D contains bridge deck images</span></span>
- <span data-ttu-id="953df-180">P contiene immagini pavimentali</span><span class="sxs-lookup"><span data-stu-id="953df-180">P contains pavement images</span></span>
- <span data-ttu-id="953df-181">W contiene immagini a parete</span><span class="sxs-lookup"><span data-stu-id="953df-181">W contains wall images</span></span>

<span data-ttu-id="953df-182">Ognuna di queste sottodirectory contiene due sottodirectory con prefisso aggiuntivo:</span><span class="sxs-lookup"><span data-stu-id="953df-182">Each of these subdirectories contains two additional prefixed subdirectories:</span></span>

- <span data-ttu-id="953df-183">C è il prefisso usato per le superfici incrinate</span><span class="sxs-lookup"><span data-stu-id="953df-183">C is the prefix used for cracked surfaces</span></span>
- <span data-ttu-id="953df-184">U è il prefisso usato per le superfici non incrinate</span><span class="sxs-lookup"><span data-stu-id="953df-184">U is the prefix used for uncracked surfaces</span></span>

<span data-ttu-id="953df-185">In questa esercitazione vengono usate solo le immagini del deck Bridge.</span><span class="sxs-lookup"><span data-stu-id="953df-185">In this tutorial, only bridge deck images are used.</span></span>

1. <span data-ttu-id="953df-186">Scaricare il [set di dati](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) e decomprimere.</span><span class="sxs-lookup"><span data-stu-id="953df-186">Download the [dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) and unzip.</span></span>
1. <span data-ttu-id="953df-187">Creare una directory denominata "assets" nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="953df-187">Create a directory named "assets" in your project to save your dataset files.</span></span>
1. <span data-ttu-id="953df-188">Copiare le sottodirectory *CD* e *UD* dalla directory decomprimeta di recente alla directory *assets* .</span><span class="sxs-lookup"><span data-stu-id="953df-188">Copy the *CD* and *UD* subdirectories from the recently unzipped directory to the *assets* directory.</span></span>

### <a name="create-input-and-output-classes"></a><span data-ttu-id="953df-189">Creare classi di input e output</span><span class="sxs-lookup"><span data-stu-id="953df-189">Create input and output classes</span></span>

1. <span data-ttu-id="953df-190">Aprire il file *Program.cs* e sostituire le `using` istruzioni esistenti all'inizio del file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="953df-190">Open the *Program.cs* file and replace the existing `using` statements at the top of the file with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. <span data-ttu-id="953df-191">Sotto la `Program` classe in *Program.cs*creare una classe denominata `ImageData` .</span><span class="sxs-lookup"><span data-stu-id="953df-191">Below the `Program` class in *Program.cs*, create a class called `ImageData`.</span></span> <span data-ttu-id="953df-192">Questa classe viene utilizzata per rappresentare i dati caricati inizialmente.</span><span class="sxs-lookup"><span data-stu-id="953df-192">This class is used to represent the initially loaded data.</span></span>

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L137-L142)]

    <span data-ttu-id="953df-193">`ImageData`contiene le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="953df-193">`ImageData` contains the following properties:</span></span>

    - <span data-ttu-id="953df-194">`ImagePath`è il percorso completo in cui è archiviata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-194">`ImagePath` is the fully qualified path where the image is stored.</span></span>
    - <span data-ttu-id="953df-195">`Label`categoria a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-195">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="953df-196">Si tratta del valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="953df-196">This is the value to predict.</span></span>

1. <span data-ttu-id="953df-197">Creare classi per i dati di input e di output</span><span class="sxs-lookup"><span data-stu-id="953df-197">Create classes for your input and output data</span></span>

    1. <span data-ttu-id="953df-198">Sotto la `ImageData` classe definire lo schema dei dati di input in una nuova classe denominata `ModelInput` .</span><span class="sxs-lookup"><span data-stu-id="953df-198">Below the `ImageData` class, define the schema of your input data in a new class called `ModelInput`.</span></span>

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L144-L153)]

        <span data-ttu-id="953df-199">`ModelInput`contiene le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="953df-199">`ModelInput` contains the following properties:</span></span>

        - <span data-ttu-id="953df-200">`Image``byte[]`rappresentazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-200">`Image` is the `byte[]` representation of the image.</span></span> <span data-ttu-id="953df-201">Il modello prevede che i dati dell'immagine siano di questo tipo per il training.</span><span class="sxs-lookup"><span data-stu-id="953df-201">The model expects image data to be of this type for training.</span></span>
        - <span data-ttu-id="953df-202">`LabelAsKey`rappresentazione numerica dell'oggetto `Label` .</span><span class="sxs-lookup"><span data-stu-id="953df-202">`LabelAsKey` is the numerical representation of the `Label`.</span></span>
        - <span data-ttu-id="953df-203">`ImagePath`è il percorso completo in cui è archiviata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-203">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="953df-204">`Label`categoria a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-204">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="953df-205">Si tratta del valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="953df-205">This is the value to predict.</span></span>

        <span data-ttu-id="953df-206">Solo `Image` e `LabelAsKey` vengono utilizzati per eseguire il training del modello ed eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="953df-206">Only `Image` and `LabelAsKey` are used to train the model and make predictions.</span></span> <span data-ttu-id="953df-207">Le `ImagePath` `Label` proprietà e vengono conservate per praticità per accedere al nome del file di immagine originale e alla categoria.</span><span class="sxs-lookup"><span data-stu-id="953df-207">The `ImagePath` and `Label` properties are kept for convenience to access the original image file name and category.</span></span>

    1. <span data-ttu-id="953df-208">Quindi, sotto la `ModelInput` classe, definire lo schema dei dati di output in una nuova classe denominata `ModelOutput` .</span><span class="sxs-lookup"><span data-stu-id="953df-208">Then, below the `ModelInput` class, define the schema of your output data in a new class called `ModelOutput`.</span></span>

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L155-L162)]

        <span data-ttu-id="953df-209">`ModelOutput`contiene le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="953df-209">`ModelOutput` contains the following properties:</span></span>

        - <span data-ttu-id="953df-210">`ImagePath`è il percorso completo in cui è archiviata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-210">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="953df-211">`Label`è la categoria originale a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-211">`Label` is the original category the image belongs to.</span></span> <span data-ttu-id="953df-212">Si tratta del valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="953df-212">This is the value to predict.</span></span>
        - <span data-ttu-id="953df-213">`PredictedLabel`valore stimato dal modello.</span><span class="sxs-lookup"><span data-stu-id="953df-213">`PredictedLabel` is the value predicted by the model.</span></span>

        <span data-ttu-id="953df-214">Analogamente a `ModelInput` , `PredictedLabel` è necessario solo per eseguire stime poiché contiene la stima effettuata dal modello.</span><span class="sxs-lookup"><span data-stu-id="953df-214">Similar to `ModelInput`, only the `PredictedLabel` is required to make predictions since it contains the prediction made by the model.</span></span> <span data-ttu-id="953df-215">Le `ImagePath` `Label` proprietà e vengono conservate per praticità per accedere al nome del file di immagine originale e alla categoria.</span><span class="sxs-lookup"><span data-stu-id="953df-215">The `ImagePath` and `Label` properties are retained for convenience to access the original image file name and category.</span></span>

### <a name="create-workspace-directory"></a><span data-ttu-id="953df-216">Crea directory dell'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="953df-216">Create workspace directory</span></span>

<span data-ttu-id="953df-217">Quando i dati di training e convalida non cambiano spesso, è consigliabile memorizzare nella cache i valori del collo di bottiglia calcolati per altre esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="953df-217">When training and validation data do not change often, it is good practice to cache the computed bottleneck values for further runs.</span></span>

1. <span data-ttu-id="953df-218">Nel progetto creare una nuova directory denominata *Workspace* per archiviare i valori del collo di bottiglia calcolati e la `.pb` versione del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-218">In your project, create a new directory called *workspace* to store the computed bottleneck values and `.pb` version of the model.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="953df-219">Definire i percorsi e inizializzare le variabili</span><span class="sxs-lookup"><span data-stu-id="953df-219">Define paths and initialize variables</span></span>

1. <span data-ttu-id="953df-220">All'interno del `Main` metodo, definire la posizione degli asset, i valori del collo di bottiglia calcolati e la `.pb` versione del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-220">Inside the `Main` method, define the location of your assets, computed bottleneck values and `.pb` version of the model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L17)]

1. <span data-ttu-id="953df-221">Inizializzare la `mlContext` variabile con una nuova istanza di [MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="953df-221">Initialize the `mlContext` variable with a new instance of [MLContext](xref:Microsoft.ML.MLContext).</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L19)]

    <span data-ttu-id="953df-222">La classe [MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni di ml.NET e l'inizializzazione di MLContext crea un nuovo ambiente ml.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-222">The [MLContext](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="953df-223">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="953df-223">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="953df-224">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="953df-224">Load the data</span></span>

### <a name="create-data-loading-utility-method"></a><span data-ttu-id="953df-225">Metodo di creazione dell'utilità di caricamento dati</span><span class="sxs-lookup"><span data-stu-id="953df-225">Create data loading utility method</span></span>

<span data-ttu-id="953df-226">Le immagini vengono archiviate in due sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="953df-226">The images are stored in two subdirectories.</span></span> <span data-ttu-id="953df-227">Prima di caricare i dati, è necessario formattarli in un elenco di `ImageData` oggetti.</span><span class="sxs-lookup"><span data-stu-id="953df-227">Before loading the data, it needs to be formatted into a list of `ImageData` objects.</span></span> <span data-ttu-id="953df-228">A tale scopo, creare il `LoadImagesFromDirectory` Metodo sotto il `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="953df-228">To do so, create the `LoadImagesFromDirectory` method below the `Main` method.</span></span>

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. <span data-ttu-id="953df-229">All'interno `LoadImagesDirectory` di aggiungere il codice seguente per ottenere tutti i percorsi di file dalle sottodirectory:</span><span class="sxs-lookup"><span data-stu-id="953df-229">Inside the `LoadImagesDirectory` add the following code to get all of the file paths from the subdirectories:</span></span>

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L104-L105)]

1. <span data-ttu-id="953df-230">Scorrere quindi ogni file usando un' `foreach` istruzione.</span><span class="sxs-lookup"><span data-stu-id="953df-230">Then, iterate through each of the files using a `foreach` statement.</span></span>

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. <span data-ttu-id="953df-231">All'interno dell' `foreach` istruzione, verificare che le estensioni di file siano supportate.</span><span class="sxs-lookup"><span data-stu-id="953df-231">Inside the `foreach` statement, check that the file extensions are supported.</span></span> <span data-ttu-id="953df-232">L'API di classificazione delle immagini supporta i formati JPEG e PNG.</span><span class="sxs-lookup"><span data-stu-id="953df-232">The Image Classification API supports JPEG and PNG formats.</span></span>

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L109-L110)]

1. <span data-ttu-id="953df-233">Ottenere quindi l'etichetta per il file.</span><span class="sxs-lookup"><span data-stu-id="953df-233">Then, get the label for the file.</span></span> <span data-ttu-id="953df-234">Se il `useFolderNameAsLabel` parametro è impostato su `true` , viene usata come etichetta la directory padre in cui viene salvato il file.</span><span class="sxs-lookup"><span data-stu-id="953df-234">If the `useFolderNameAsLabel` parameter is set to `true`, then the parent directory where the file is saved is used as the label.</span></span> <span data-ttu-id="953df-235">In caso contrario, prevede che l'etichetta sia un prefisso del nome file o il nome del file stesso.</span><span class="sxs-lookup"><span data-stu-id="953df-235">Otherwise, it expects the label to be a prefix of the file name or the file name itself.</span></span>

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L112-L126)]

1. <span data-ttu-id="953df-236">Infine, creare una nuova istanza di `ModelInput` .</span><span class="sxs-lookup"><span data-stu-id="953df-236">Finally, create a new instance of `ModelInput`.</span></span>

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L128-L132)]

### <a name="prepare-the-data"></a><span data-ttu-id="953df-237">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="953df-237">Prepare the data</span></span>

1. <span data-ttu-id="953df-238">Tornando al `Main` metodo, utilizzare il `LoadFromDirectory` Metodo Utility per ottenere l'elenco delle immagini utilizzate per il training.</span><span class="sxs-lookup"><span data-stu-id="953df-238">Back in the `Main` method, use the `LoadFromDirectory` utility method to get the list of images used for training.</span></span>

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L21)]

1. <span data-ttu-id="953df-239">Quindi, caricare le immagini in un oggetto [`IDataView`](xref:Microsoft.ML.IDataView) usando il [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) metodo.</span><span class="sxs-lookup"><span data-stu-id="953df-239">Then, load the images into an [`IDataView`](xref:Microsoft.ML.IDataView) using the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method.</span></span>

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L23)]

1. <span data-ttu-id="953df-240">I dati vengono caricati nell'ordine in cui sono stati letti dalle directory.</span><span class="sxs-lookup"><span data-stu-id="953df-240">The data is loaded in the order it was read from the directories.</span></span> <span data-ttu-id="953df-241">Per bilanciare i dati, eseguire il shuffle usando il [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) metodo.</span><span class="sxs-lookup"><span data-stu-id="953df-241">To balance the data, shuffle it using the [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) method.</span></span>

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L25)]

1. <span data-ttu-id="953df-242">Per i modelli di apprendimento automatico si prevede che l'input sia in formato numerico.</span><span class="sxs-lookup"><span data-stu-id="953df-242">Machine learning models expect input to be in numerical format.</span></span> <span data-ttu-id="953df-243">Pertanto, è necessario eseguire alcune operazioni di pre-elaborazione sui dati prima di eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="953df-243">Therefore, some preprocessing needs to be done on the data prior to training.</span></span> <span data-ttu-id="953df-244">Creare un oggetto [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) costituito da [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) `LoadRawImageBytes` trasformazioni e.</span><span class="sxs-lookup"><span data-stu-id="953df-244">Create an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) made up of the [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) and `LoadRawImageBytes` transforms.</span></span> <span data-ttu-id="953df-245">La `MapValueToKey` trasformazione acquisisce il valore categorico nella `Label` colonna, lo converte in un `KeyType` valore numerico e lo archivia in una nuova colonna denominata `LabelAsKey` .</span><span class="sxs-lookup"><span data-stu-id="953df-245">The `MapValueToKey` transform takes the categorical value in the `Label` column, converts it to a numerical `KeyType` value and stores it in a new column called `LabelAsKey`.</span></span> <span data-ttu-id="953df-246">`LoadImages`Accetta i valori dalla `ImagePath` colonna insieme al `imageFolder` parametro per caricare le immagini per il training.</span><span class="sxs-lookup"><span data-stu-id="953df-246">The `LoadImages` takes the values from the `ImagePath` column along with the `imageFolder` parameter to load images for training.</span></span>

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L27-L33)]

1. <span data-ttu-id="953df-247">Usare il [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) metodo per applicare i dati a `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) seguito dal [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) metodo, che restituisce un oggetto [`IDataView`](xref:Microsoft.ML.IDataView) contenente i dati pre-elaborati.</span><span class="sxs-lookup"><span data-stu-id="953df-247">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to apply the data to the `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) followed by the [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) method, which returns an [`IDataView`](xref:Microsoft.ML.IDataView) containing the pre-processed data.</span></span>

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. <span data-ttu-id="953df-248">Per eseguire il training di un modello, è importante avere un set di dati di training e un set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="953df-248">To train a model, it's important to have a training dataset as well as a validation dataset.</span></span> <span data-ttu-id="953df-249">Viene eseguito il training del modello nel training set.</span><span class="sxs-lookup"><span data-stu-id="953df-249">The model is trained on the training set.</span></span> <span data-ttu-id="953df-250">Il modo in cui esegue le stime sui dati non visualizzati viene misurato in base alle prestazioni rispetto al set di convalida.</span><span class="sxs-lookup"><span data-stu-id="953df-250">How well it makes predictions on unseen data is measured by the performance against the validation set.</span></span> <span data-ttu-id="953df-251">In base ai risultati di tali prestazioni, il modello apporta modifiche a quanto appreso nel tentativo di migliorare.</span><span class="sxs-lookup"><span data-stu-id="953df-251">Based on the results of that performance, the model makes adjustments to what it has learned in an effort to improve.</span></span> <span data-ttu-id="953df-252">Il set di convalida può derivare dalla suddivisione del set di dati originale o da un'altra origine che è già stata riservata a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="953df-252">The validation set can come from either splitting your original dataset or from another source that has already been set aside for this purpose.</span></span> <span data-ttu-id="953df-253">In questo caso, il set di dati pre-elaborato viene suddiviso in set di training, convalida e test.</span><span class="sxs-lookup"><span data-stu-id="953df-253">In this case, the pre-processed dataset is split into training, validation and test sets.</span></span>

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    <span data-ttu-id="953df-254">L'esempio di codice precedente esegue due divisioni.</span><span class="sxs-lookup"><span data-stu-id="953df-254">The code sample above performs two splits.</span></span> <span data-ttu-id="953df-255">In primo luogo, i dati pre-elaborati sono divisi e il 70% viene usato per il training, mentre il 30% rimanente viene usato per la convalida.</span><span class="sxs-lookup"><span data-stu-id="953df-255">First, the pre-processed data is split and 70% is used for training while the remaining 30% is used for validation.</span></span> <span data-ttu-id="953df-256">Il set di convalida del 30% viene quindi suddiviso ulteriormente nei set di convalida e di test, in cui il 90% viene usato per la convalida e il 10% viene usato per il test.</span><span class="sxs-lookup"><span data-stu-id="953df-256">Then, the 30% validation set is further split into validation and test sets where 90% is used for validation and 10% is used for testing.</span></span>

    <span data-ttu-id="953df-257">Un modo per considerare lo scopo di queste partizioni di dati consiste nell'esame.</span><span class="sxs-lookup"><span data-stu-id="953df-257">A way to think about the purpose of these data partitions is taking an exam.</span></span> <span data-ttu-id="953df-258">Quando si studia un esame, si esaminano le note, i libri o altre risorse per approfondire i concetti relativi all'esame.</span><span class="sxs-lookup"><span data-stu-id="953df-258">When studying for an exam, you review your notes, books, or other resources to get a grasp on the concepts that are on the exam.</span></span> <span data-ttu-id="953df-259">Questo è il set di training.</span><span class="sxs-lookup"><span data-stu-id="953df-259">This is what the train set is for.</span></span> <span data-ttu-id="953df-260">Quindi, è possibile eseguire un esame fittizio per convalidare le proprie conoscenze.</span><span class="sxs-lookup"><span data-stu-id="953df-260">Then, you might take a mock exam to validate your knowledge.</span></span> <span data-ttu-id="953df-261">Questo è il punto in cui il set di convalida risulta utile.</span><span class="sxs-lookup"><span data-stu-id="953df-261">This is where the validation set comes in handy.</span></span> <span data-ttu-id="953df-262">Si desidera controllare se si dispone di una conoscenza adeguata dei concetti prima di intraprendere l'esame effettivo.</span><span class="sxs-lookup"><span data-stu-id="953df-262">You want to check whether you have a good grasp of the concepts before taking the actual exam.</span></span> <span data-ttu-id="953df-263">In base a questi risultati, si prende nota di quanto si è verificato un errore o non si è capito bene e si inseriscono le modifiche durante la revisione del vero esame.</span><span class="sxs-lookup"><span data-stu-id="953df-263">Based on those results, you take note of what you got wrong or didn't understand well and incorporate your changes as you review for the real exam.</span></span> <span data-ttu-id="953df-264">Infine, si prenderà in esame.</span><span class="sxs-lookup"><span data-stu-id="953df-264">Finally, you take the exam.</span></span> <span data-ttu-id="953df-265">Per questa operazione viene usato il set di test.</span><span class="sxs-lookup"><span data-stu-id="953df-265">This is what the test set is used for.</span></span> <span data-ttu-id="953df-266">Non hai mai visto le domande che sono in fase di esame e ora usi quanto appreso dalla formazione e dalla convalida per applicare le tue conoscenze all'attività.</span><span class="sxs-lookup"><span data-stu-id="953df-266">You've never seen the questions that are on the exam and now use what you learned from training and validation to apply your knowledge to the task at hand.</span></span>

1. <span data-ttu-id="953df-267">Assegnare alle partizioni i rispettivi valori per i dati di training, convalida e test.</span><span class="sxs-lookup"><span data-stu-id="953df-267">Assign the partitions their respective values for the train, validation and test data.</span></span>

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a><span data-ttu-id="953df-268">Definire la pipeline di training</span><span class="sxs-lookup"><span data-stu-id="953df-268">Define the training pipeline</span></span>

<span data-ttu-id="953df-269">Il training del modello è costituito da un paio di passaggi.</span><span class="sxs-lookup"><span data-stu-id="953df-269">Model training consists of a couple of steps.</span></span> <span data-ttu-id="953df-270">Per prima cosa, viene utilizzata l'API di classificazione delle immagini per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-270">First, Image Classification API is used to train the model.</span></span> <span data-ttu-id="953df-271">Quindi, le etichette codificate nella `PredictedLabel` colonna vengono riconvertite nel valore categorico originale usando la `MapKeyToValue` trasformazione.</span><span class="sxs-lookup"><span data-stu-id="953df-271">Then, the encoded labels in the `PredictedLabel` column are converted back to their original categorical value using the `MapKeyToValue` transform.</span></span>

1. <span data-ttu-id="953df-272">Creare una nuova variabile per archiviare un set di parametri obbligatori e facoltativi per un oggetto `ImageClassificationTrainer` .</span><span class="sxs-lookup"><span data-stu-id="953df-272">Create a new variable to store a set of required and optional parameters for an `ImageClassificationTrainer`.</span></span>

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L57)]

    <span data-ttu-id="953df-273">Un `ImageClassificationTrainer` accetta diversi parametri facoltativi:</span><span class="sxs-lookup"><span data-stu-id="953df-273">An `ImageClassificationTrainer` takes several optional parameters:</span></span>

    - <span data-ttu-id="953df-274">`FeatureColumnName`colonna utilizzata come input per il modello.</span><span class="sxs-lookup"><span data-stu-id="953df-274">`FeatureColumnName` is the column that is used as input for the model.</span></span>
    - <span data-ttu-id="953df-275">`LabelColumnName`colonna per il valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="953df-275">`LabelColumnName` is the column for the value to predict.</span></span>
    - <span data-ttu-id="953df-276">`ValidationSet`oggetto [`IDataView`](xref:Microsoft.ML.IDataView) che contiene i dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="953df-276">`ValidationSet` is the [`IDataView`](xref:Microsoft.ML.IDataView) containing the validation data.</span></span>
    - <span data-ttu-id="953df-277">`Arch`definisce quale delle architetture del modello con training.</span><span class="sxs-lookup"><span data-stu-id="953df-277">`Arch` defines which of the pretrained model architectures to use.</span></span> <span data-ttu-id="953df-278">Questa esercitazione usa la variante a 101 livelli del modello ResNetv2.</span><span class="sxs-lookup"><span data-stu-id="953df-278">This tutorial uses the 101-layer variant of the ResNetv2 model.</span></span>
    - <span data-ttu-id="953df-279">`MetricsCallback`associa una funzione per tenere traccia dello stato di avanzamento durante il training.</span><span class="sxs-lookup"><span data-stu-id="953df-279">`MetricsCallback` binds a function to track the progress during training.</span></span>
    - <span data-ttu-id="953df-280">`TestOnTrainSet`indica al modello di misurare le prestazioni rispetto al set di training quando non è presente alcun set di convalida.</span><span class="sxs-lookup"><span data-stu-id="953df-280">`TestOnTrainSet` tells the model to measure performance against the training set when no validation set is present.</span></span>
    - <span data-ttu-id="953df-281">`ReuseTrainSetBottleneckCachedValues`indica al modello se utilizzare i valori memorizzati nella cache della fase di collo di bottiglia nelle esecuzioni successive.</span><span class="sxs-lookup"><span data-stu-id="953df-281">`ReuseTrainSetBottleneckCachedValues` tells the model whether to use the cached values from the bottleneck phase in subsequent runs.</span></span> <span data-ttu-id="953df-282">La fase di collo di bottiglia è un calcolo pass-through monouso che richiede un utilizzo intensivo di calcolo alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="953df-282">The bottleneck phase is a one-time pass-through computation that is computationally intensive the first time it is performed.</span></span> <span data-ttu-id="953df-283">Se i dati di training non cambiano e si vuole provare a usare un numero diverso di epoche o dimensioni del batch, l'uso dei valori memorizzati nella cache riduce significativamente la quantità di tempo necessaria per eseguire il training di un modello.</span><span class="sxs-lookup"><span data-stu-id="953df-283">If the training data does not change and you want to experiment using a different number of epochs or batch size, using the cached values significantly reduces the amount of time required to train a model.</span></span>
    - <span data-ttu-id="953df-284">`ReuseValidationSetBottleneckCachedValues`è simile `ReuseTrainSetBottleneckCachedValues` solo a quello che in questo caso è per il set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="953df-284">`ReuseValidationSetBottleneckCachedValues` is similar to `ReuseTrainSetBottleneckCachedValues` only that in this case it's for the validation dataset.</span></span>
    - <span data-ttu-id="953df-285">`WorkspacePath`definisce la directory in cui archiviare i valori del collo di bottiglia calcolati e la `.pb` versione del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-285">`WorkspacePath` defines the directory where to store the computed bottleneck values and `.pb` version of the model.</span></span>

1. <span data-ttu-id="953df-286">Definire la [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) pipeline di training costituita sia da che da `mapLabelEstimator` `ImageClassificationTrainer` .</span><span class="sxs-lookup"><span data-stu-id="953df-286">Define the [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) training pipeline that consists of both the `mapLabelEstimator` and the `ImageClassificationTrainer`.</span></span>

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L59-L60)]

1. <span data-ttu-id="953df-287">Utilizzare il [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) metodo per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-287">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to train your model.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

## <a name="use-the-model"></a><span data-ttu-id="953df-288">Usare il modello</span><span class="sxs-lookup"><span data-stu-id="953df-288">Use the model</span></span>

<span data-ttu-id="953df-289">A questo punto, dopo aver eseguito il training del modello, è possibile usarlo per classificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="953df-289">Now that you have trained your model, it's time to use it to classify images.</span></span>

<span data-ttu-id="953df-290">Sotto il `Main` metodo, creare un nuovo metodo di utilità denominato `OutputPrediction` per visualizzare le informazioni di stima nella console di.</span><span class="sxs-lookup"><span data-stu-id="953df-290">Below the `Main` method, create a new utility method called `OutputPrediction` to display prediction information in the console.</span></span>

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L96-L100)]

### <a name="classify-a-single-image"></a><span data-ttu-id="953df-291">Classificare una singola immagine</span><span class="sxs-lookup"><span data-stu-id="953df-291">Classify a single image</span></span>

1. <span data-ttu-id="953df-292">Aggiungere un nuovo metodo denominato `ClassifySingleImage` sotto il `Main` metodo per creare e restituire una singola stima di immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-292">Add a new method called `ClassifySingleImage` below the `Main` method to make and output a single image prediction.</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="953df-293">Creare un oggetto [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) all'interno del `ClassifySingleImage` metodo.</span><span class="sxs-lookup"><span data-stu-id="953df-293">Create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) inside the `ClassifySingleImage` method.</span></span> <span data-ttu-id="953df-294">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)È un'API utile che consente di passare ed eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="953df-294">The [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. <span data-ttu-id="953df-295">Per accedere a una singola `ModelInput` istanza, convertire `data` [`IDataView`](xref:Microsoft.ML.IDataView) in un oggetto [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) usando il [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) metodo e quindi ottenere la prima osservazione.</span><span class="sxs-lookup"><span data-stu-id="953df-295">To access a single `ModelInput` instance, convert the `data` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first observation.</span></span>

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. <span data-ttu-id="953df-296">Usare il [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) metodo per classificare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-296">Use the [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) method to classify the image.</span></span>

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77)]

1. <span data-ttu-id="953df-297">Restituire la stima alla console con il `OutputPrediction` metodo.</span><span class="sxs-lookup"><span data-stu-id="953df-297">Output the prediction to the console with the `OutputPrediction` method.</span></span>

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L79-L80)]

1. <span data-ttu-id="953df-298">All'interno del `Main` metodo chiamare `ClassifySingleImage` usando il set di immagini di test.</span><span class="sxs-lookup"><span data-stu-id="953df-298">Inside the `Main` method, call `ClassifySingleImage` using the test set of images.</span></span>

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

### <a name="classify-multiple-images"></a><span data-ttu-id="953df-299">Classificare più immagini</span><span class="sxs-lookup"><span data-stu-id="953df-299">Classify multiple images</span></span>

1. <span data-ttu-id="953df-300">Aggiungere un nuovo metodo denominato `ClassifyImages` sotto il `ClassifySingleImage` metodo per creare e restituire più stime di immagine.</span><span class="sxs-lookup"><span data-stu-id="953df-300">Add a new method called `ClassifyImages` below the `ClassifySingleImage` method to make and output multiple image predictions.</span></span>

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="953df-301">Creare un oggetto [`IDataView`](xref:Microsoft.ML.IDataView) contenente le stime tramite il [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) metodo.</span><span class="sxs-lookup"><span data-stu-id="953df-301">Create an [`IDataView`](xref:Microsoft.ML.IDataView) containing the predictions by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method.</span></span> <span data-ttu-id="953df-302">Aggiungere il codice seguente all'interno del metodo `ClassifyImages`.</span><span class="sxs-lookup"><span data-stu-id="953df-302">Add the following code inside the `ClassifyImages` method.</span></span>

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. <span data-ttu-id="953df-303">Per eseguire l'iterazione delle stime, convertire `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) in un oggetto [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) usando il [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) metodo e quindi ottenere le prime 10 osservazioni.</span><span class="sxs-lookup"><span data-stu-id="953df-303">In order to iterate over the predictions, convert the `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first 10 observations.</span></span>

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87)]

1. <span data-ttu-id="953df-304">Eseguire l'iterazione e restituire le etichette originali e stimate per le stime.</span><span class="sxs-lookup"><span data-stu-id="953df-304">Iterate and output the original and predicted labels for the predictions.</span></span>

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L89-L93)]

1. <span data-ttu-id="953df-305">Infine, all'interno del `Main` metodo, chiamare `ClassifyImages` utilizzando il set di immagini di test.</span><span class="sxs-lookup"><span data-stu-id="953df-305">Finally, inside the `Main` method, call `ClassifyImages` using the test set of images.</span></span>

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L66)]

## <a name="run-the-application"></a><span data-ttu-id="953df-306">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="953df-306">Run the application</span></span>

<span data-ttu-id="953df-307">Eseguire l'app console.</span><span class="sxs-lookup"><span data-stu-id="953df-307">Run your console app.</span></span> <span data-ttu-id="953df-308">L'output dovrebbe essere simile a quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="953df-308">The output should be similar to that below.</span></span> <span data-ttu-id="953df-309">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="953df-309">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span> <span data-ttu-id="953df-310">Per brevità, l'output è stato condensato.</span><span class="sxs-lookup"><span data-stu-id="953df-310">For brevity, the output has been condensed.</span></span>

<span data-ttu-id="953df-311">**Fase collo di bottiglia**</span><span class="sxs-lookup"><span data-stu-id="953df-311">**Bottleneck phase**</span></span>

<span data-ttu-id="953df-312">Non viene stampato alcun valore per il nome dell'immagine perché le immagini vengono caricate come un oggetto, `byte[]` di conseguenza non è presente alcun nome di immagine da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="953df-312">No value is printed for the image name because the images are loaded as a `byte[]` therefore there is no image name to display.</span></span>

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

<span data-ttu-id="953df-313">**Fase di training**</span><span class="sxs-lookup"><span data-stu-id="953df-313">**Training phase**</span></span>

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

<span data-ttu-id="953df-314">**Classifica output immagini**</span><span class="sxs-lookup"><span data-stu-id="953df-314">**Classify images output**</span></span>

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

<span data-ttu-id="953df-315">Quando si verifica l'immagine *7001 -220. jpg* , è possibile notare che in realtà non è incrinato.</span><span class="sxs-lookup"><span data-stu-id="953df-315">Upon inspection of the *7001-220.jpg* image, you can see that it in fact is not cracked.</span></span>

![Immagine del set di dati SDNET2018 utilizzata per la stima](./media/image-classification-api-transfer-learning/predictedimage.jpg)

<span data-ttu-id="953df-317">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="953df-317">Congratulations!</span></span> <span data-ttu-id="953df-318">A questo punto è stato creato un modello di apprendimento avanzato per la classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="953df-318">You've now successfully built a deep learning model for classifying images.</span></span>

### <a name="improve-the-model"></a><span data-ttu-id="953df-319">Migliorare il modello</span><span class="sxs-lookup"><span data-stu-id="953df-319">Improve the model</span></span>

<span data-ttu-id="953df-320">Se non si è soddisfatti dei risultati del modello, è possibile provare a migliorarne le prestazioni provando alcuni degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="953df-320">If you're not satisfied with the results of your model, you can try to improve its performance by trying some of the following approaches:</span></span>

- <span data-ttu-id="953df-321">**Altri dati**: maggiore è il numero di esempi apportati da un modello, migliori saranno le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="953df-321">**More Data**: The more examples a model learns from, the better it performs.</span></span> <span data-ttu-id="953df-322">Scaricare il [set di dati SDNET2018](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) completo e usarlo per il training.</span><span class="sxs-lookup"><span data-stu-id="953df-322">Download the full [SDNET2018 dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) and use it to train.</span></span>
- <span data-ttu-id="953df-323">**Migliorare i dati**: una tecnica comune per aggiungere varietà ai dati consiste nell'aumentare i dati mediante l'acquisizione di un'immagine e l'applicazione di trasformazioni diverse (ruotare, capovolgere, spostare o ritagliare).</span><span class="sxs-lookup"><span data-stu-id="953df-323">**Augment the data**: A common technique to add variety to the data is to augment the data by taking an image and applying different transforms (rotate, flip, shift, crop).</span></span> <span data-ttu-id="953df-324">In questo modo vengono aggiunti esempi più diversi per il modello da cui apprendere.</span><span class="sxs-lookup"><span data-stu-id="953df-324">This adds more varied examples for the model to learn from.</span></span>
- <span data-ttu-id="953df-325">Eseguire il **training per un periodo di tempo più lungo**: maggiore sarà il training del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-325">**Train for a longer time**: The longer you train, the more tuned the model will be.</span></span> <span data-ttu-id="953df-326">L'aumento del numero di epoche può migliorare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="953df-326">Increasing the number of epochs may improve the performance of your model.</span></span>
- <span data-ttu-id="953df-327">**Esperimento con i parametri ipertestuali**: oltre ai parametri usati in questa esercitazione, è possibile ottimizzare altri parametri per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="953df-327">**Experiment with the hyper-parameters**: In addition to the parameters used in this tutorial, other parameters can be tuned to potentially improve performance.</span></span> <span data-ttu-id="953df-328">Modifica della velocità di apprendimento, che determina la grandezza degli aggiornamenti apportati al modello dopo che ogni Epoch può migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="953df-328">Changing the learning rate, which determines the magnitude of updates made to the model after each epoch may improve performance.</span></span>
- <span data-ttu-id="953df-329">**Usare un'architettura del modello diversa**: a seconda dell'aspetto dei dati, il modello che può apprendere meglio le sue funzionalità può essere diverso.</span><span class="sxs-lookup"><span data-stu-id="953df-329">**Use a different model architecture**: Depending on what your data looks like, the model that can best learn its features may differ.</span></span> <span data-ttu-id="953df-330">Se non si è soddisfatti delle prestazioni del modello, provare a modificare l'architettura.</span><span class="sxs-lookup"><span data-stu-id="953df-330">If you're not satisfied with the performance of your model, try changing the architecture.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="953df-331">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="953df-331">Additional Resources</span></span>

- <span data-ttu-id="953df-332">[Visual Studio e Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="953df-332">[Deep Learning vs Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span></span>

## <a name="next-steps"></a><span data-ttu-id="953df-333">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="953df-333">Next steps</span></span>

<span data-ttu-id="953df-334">In questa esercitazione si è appreso come creare un modello di apprendimento avanzato personalizzato usando Transfer Learning, un modello di classificazione di immagini con training TensorFlow e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non incrinate.</span><span class="sxs-lookup"><span data-stu-id="953df-334">In this tutorial, you learned how to build a custom deep learning model using transfer learning, a pretrained image classification TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="953df-335">Passare all'esercitazione successiva per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="953df-335">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="953df-336">Rilevamento oggetti</span><span class="sxs-lookup"><span data-stu-id="953df-336">Object Detection</span></span>](object-detection-onnx.md)
