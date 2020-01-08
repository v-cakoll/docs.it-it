---
title: 'Esercitazione: ispezione visiva automatizzata tramite trasferimento Learning'
description: Questa esercitazione illustra come usare Transfer learning per eseguire il training di un modello di apprendimento approfondito di TensorFlow in ML.NET usando l'API di rilevamento immagini per classificare le immagini di superfici concrete come incrinate o non incrinate.
author: luisquintanilla
ms.author: luquinta
ms.date: 12/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4781e39a0c8827adb6ab0155d5215645242208a5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348171"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a><span data-ttu-id="3ef42-103">Esercitazione: ispezione visiva automatizzata tramite il trasferimento dell'apprendimento con l'API di classificazione delle immagini ML.NET</span><span class="sxs-lookup"><span data-stu-id="3ef42-103">Tutorial: Automated visual inspection using transfer learning with the ML.NET Image Classification API</span></span>

<span data-ttu-id="3ef42-104">Informazioni su come eseguire il training di un modello di apprendimento avanzato personalizzato usando il servizio di formazione per il trasferimento, un modello TensorFlow pretrainato e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non incrinate</span><span class="sxs-lookup"><span data-stu-id="3ef42-104">Learn how to train a custom deep learning model using transfer learning, a pretrained TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="3ef42-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="3ef42-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="3ef42-106">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="3ef42-106">Understand the problem</span></span>
> - <span data-ttu-id="3ef42-107">Informazioni sull'API di classificazione delle immagini ML.NET</span><span class="sxs-lookup"><span data-stu-id="3ef42-107">Learn about ML.NET Image Classification API</span></span>
> - <span data-ttu-id="3ef42-108">Informazioni sul modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="3ef42-108">Understand the pretrained model</span></span>
> - <span data-ttu-id="3ef42-109">Usare Transfer learning per eseguire il training di un modello di classificazione immagini TensorFlow personalizzato</span><span class="sxs-lookup"><span data-stu-id="3ef42-109">Use transfer learning to train a custom TensorFlow image classification model</span></span>
> - <span data-ttu-id="3ef42-110">Classificare le immagini con il modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="3ef42-110">Classify images with the custom model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ef42-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3ef42-111">Prerequisites</span></span>

- <span data-ttu-id="3ef42-112">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="3ef42-112">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="image-classification-transfer-learning-sample-overview"></a><span data-ttu-id="3ef42-113">Panoramica dell'esempio di apprendimento della classificazione delle immagini Transfer</span><span class="sxs-lookup"><span data-stu-id="3ef42-113">Image classification transfer learning sample overview</span></span>

<span data-ttu-id="3ef42-114">Questo esempio è un' C# applicazione console .NET Core che classifica le immagini usando un modello TensorFlow di apprendimento avanzato pretrainato.</span><span class="sxs-lookup"><span data-stu-id="3ef42-114">This sample is a C# .NET Core console application that classifies images using a pretrained deep learning TensorFlow model.</span></span> <span data-ttu-id="3ef42-115">Il codice per questo esempio è disponibile nel [repository dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="3ef42-115">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="3ef42-116">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="3ef42-116">Understand the problem</span></span>

<span data-ttu-id="3ef42-117">La classificazione delle immagini è un problema di visione artificiale.</span><span class="sxs-lookup"><span data-stu-id="3ef42-117">Image classification is a computer vision problem.</span></span> <span data-ttu-id="3ef42-118">La classificazione delle immagini acquisisce un'immagine come input e la Categorizza in una classe prescritta.</span><span class="sxs-lookup"><span data-stu-id="3ef42-118">Image classification takes an image as input and categorizes it into a prescribed class.</span></span> <span data-ttu-id="3ef42-119">Di seguito sono riportati alcuni scenari in cui è utile la classificazione delle immagini:</span><span class="sxs-lookup"><span data-stu-id="3ef42-119">Some scenarios where image classification is useful include:</span></span>

- <span data-ttu-id="3ef42-120">Riconoscimento facciale</span><span class="sxs-lookup"><span data-stu-id="3ef42-120">Facial recognition</span></span>
- <span data-ttu-id="3ef42-121">Rilevamento emozioni</span><span class="sxs-lookup"><span data-stu-id="3ef42-121">Emotion detection</span></span>
- <span data-ttu-id="3ef42-122">Diagnosi medica</span><span class="sxs-lookup"><span data-stu-id="3ef42-122">Medical diagnosis</span></span>
- <span data-ttu-id="3ef42-123">Rilevamento di punti di riferimento</span><span class="sxs-lookup"><span data-stu-id="3ef42-123">Landmark detection</span></span>

<span data-ttu-id="3ef42-124">Questa esercitazione esegue il training di un modello di classificazione delle immagini personalizzato per eseguire un'ispezione visiva automatizzata dei deck Bridge per identificare le strutture danneggiate da crepe.</span><span class="sxs-lookup"><span data-stu-id="3ef42-124">This tutorial trains a custom image classification model to perform automated visual inspection of bridge decks to identify structures that are damaged by cracks.</span></span>

## <a name="mlnet-image-classification-api"></a><span data-ttu-id="3ef42-125">API di classificazione delle immagini ML.NET</span><span class="sxs-lookup"><span data-stu-id="3ef42-125">ML.NET Image Classification API</span></span>

<span data-ttu-id="3ef42-126">ML.NET offre diversi modi per eseguire la classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="3ef42-126">ML.NET provides various ways of performing image classification.</span></span> <span data-ttu-id="3ef42-127">Questa esercitazione applica l'apprendimento del trasferimento usando l'API di classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="3ef42-127">This tutorial applies transfer learning using the Image Classification API.</span></span> <span data-ttu-id="3ef42-128">L'API di classificazione delle immagini USA [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), una libreria di basso livello che fornisce C# binding per l'API TensorFlow C++ .</span><span class="sxs-lookup"><span data-stu-id="3ef42-128">The Image Classification API makes use of [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), a low-level library that provides C# bindings for the TensorFlow C++ API.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="3ef42-129">Che cos'è l'apprendimento trasferito?</span><span class="sxs-lookup"><span data-stu-id="3ef42-129">What is transfer learning?</span></span>

<span data-ttu-id="3ef42-130">Transfer Learning applica le informazioni ottenute dalla risoluzione di un problema a un altro problema correlato.</span><span class="sxs-lookup"><span data-stu-id="3ef42-130">Transfer learning applies knowledge gained from solving one problem to another related problem.</span></span>

<span data-ttu-id="3ef42-131">Per il training di un modello di apprendimento avanzato da zero è necessario impostare diversi parametri, una grande quantità di dati di training con etichette e una grande quantità di risorse di calcolo (centinaia di ore GPU).</span><span class="sxs-lookup"><span data-stu-id="3ef42-131">Training a deep learning model from scratch requires setting several parameters, a large amount of labeled training data, and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="3ef42-132">L'uso di un modello pretrainato insieme a transfer Learning consente di abbreviare il processo di training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-132">Using a pretrained model along with transfer learning allows you to shortcut the training process.</span></span>

## <a name="training-process"></a><span data-ttu-id="3ef42-133">Processo di training</span><span class="sxs-lookup"><span data-stu-id="3ef42-133">Training process</span></span>

<span data-ttu-id="3ef42-134">L'API di classificazione delle immagini avvia il processo di training caricando un modello TensorFlow pre-trainato.</span><span class="sxs-lookup"><span data-stu-id="3ef42-134">The Image Classification API starts the training process by loading a pretrained TensorFlow model.</span></span> <span data-ttu-id="3ef42-135">Il processo di training è costituito da due passaggi:</span><span class="sxs-lookup"><span data-stu-id="3ef42-135">The training process consists of two steps:</span></span>

1. <span data-ttu-id="3ef42-136">Fase collo di bottiglia</span><span class="sxs-lookup"><span data-stu-id="3ef42-136">Bottleneck phase</span></span>
2. <span data-ttu-id="3ef42-137">Fase di training</span><span class="sxs-lookup"><span data-stu-id="3ef42-137">Training phase</span></span>

![Passaggi di training](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a><span data-ttu-id="3ef42-139">Fase collo di bottiglia</span><span class="sxs-lookup"><span data-stu-id="3ef42-139">Bottleneck phase</span></span>

<span data-ttu-id="3ef42-140">Durante la fase di collo di bottiglia, viene caricato il set di immagini di training e i valori dei pixel vengono usati come input, o funzionalità, per i livelli bloccati del modello con training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-140">During the bottleneck phase, the set of training images is loaded and the pixel values are used as input, or features, for the frozen layers of the pretrained model.</span></span> <span data-ttu-id="3ef42-141">I livelli bloccati includono tutti i livelli nella rete neurale fino al penultimo livello, noto in modo informale come livello del collo di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="3ef42-141">The frozen layers include all of the layers in the neural network up to the penultimate layer, informally known as the bottleneck layer.</span></span> <span data-ttu-id="3ef42-142">A questi livelli viene fatto riferimento come bloccato perché non si verificherà alcun training su questi livelli e le operazioni sono pass-through.</span><span class="sxs-lookup"><span data-stu-id="3ef42-142">These layers are referred to as frozen because no training will occur on these layers and operations are pass-through.</span></span> <span data-ttu-id="3ef42-143">Si trova in questi livelli bloccati in cui vengono calcolati i modelli di livello inferiore che consentono di distinguere un modello tra le diverse classi.</span><span class="sxs-lookup"><span data-stu-id="3ef42-143">It's at these frozen layers where the lower-level patterns that help a model differentiate between the different classes are computed.</span></span> <span data-ttu-id="3ef42-144">Maggiore è il numero di livelli, più elevato a livello di calcolo questo passaggio è.</span><span class="sxs-lookup"><span data-stu-id="3ef42-144">The larger the number of layers, the more computationally intensive this step is.</span></span> <span data-ttu-id="3ef42-145">Fortunatamente, dal momento che si tratta di un calcolo monouso, i risultati possono essere memorizzati nella cache e usati nelle esecuzioni successive quando si sperimentano parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="3ef42-145">Fortunately, since this is a one-time calculation, the results can be cached and used in later runs when experimenting with different parameters.</span></span>

### <a name="training-phase"></a><span data-ttu-id="3ef42-146">Fase di training</span><span class="sxs-lookup"><span data-stu-id="3ef42-146">Training phase</span></span>

<span data-ttu-id="3ef42-147">Una volta calcolati i valori di output della fase di collo di bottiglia, essi vengono utilizzati come input per ripetere il training del livello finale del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-147">Once the output values from the bottleneck phase are computed, they are used as input to retrain the final layer of the model.</span></span> <span data-ttu-id="3ef42-148">Questo processo è iterativo e viene eseguito per il numero di volte specificato dai parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-148">This process is iterative and runs for the number of times specified by model parameters.</span></span> <span data-ttu-id="3ef42-149">Durante ogni esecuzione, la perdita e l'accuratezza vengono valutate.</span><span class="sxs-lookup"><span data-stu-id="3ef42-149">During each run, the loss and accuracy are evaluated.</span></span> <span data-ttu-id="3ef42-150">Quindi, vengono apportate le regolazioni appropriate per migliorare il modello con l'obiettivo di ridurre al minimo la perdita e massimizzare la precisione.</span><span class="sxs-lookup"><span data-stu-id="3ef42-150">Then, the appropriate adjustments are made to improve the model with the goal of minimizing the loss and maximizing the accuracy.</span></span> <span data-ttu-id="3ef42-151">Al termine del training, vengono restituiti due formati di modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-151">Once training is finished, two model formats are output.</span></span> <span data-ttu-id="3ef42-152">Uno di essi è la versione `.pb` del modello e l'altro è la versione serializzata `.zip` ML.NET del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-152">One of them is the `.pb` version of the model and the other is the `.zip` ML.NET serialized version of the model.</span></span> <span data-ttu-id="3ef42-153">Quando si lavora in ambienti supportati da ML.NET, è consigliabile usare la versione `.zip` del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-153">When working in environments supported by ML.NET, it is recommended to use the `.zip` version of the model.</span></span> <span data-ttu-id="3ef42-154">Tuttavia, negli ambienti in cui ML.NET non è supportato, è possibile usare la versione `.pb`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-154">However, in environments where ML.NET is not supported, you have the option of using the `.pb` version.</span></span>

## <a name="understand-the-pretrained-model"></a><span data-ttu-id="3ef42-155">Informazioni sul modello sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="3ef42-155">Understand the pretrained model</span></span>

<span data-ttu-id="3ef42-156">Il modello con training pretrain usato in questa esercitazione è la variante a 101 livelli del modello di rete residua (ResNet) v2.</span><span class="sxs-lookup"><span data-stu-id="3ef42-156">The pretrained model used in this tutorial is the 101-layer variant of the Residual Network (ResNet) v2 model.</span></span> <span data-ttu-id="3ef42-157">Il modello originale viene sottoposto a training per classificare le immagini in un centinaio di categorie.</span><span class="sxs-lookup"><span data-stu-id="3ef42-157">The original model is trained to classify images into a thousand categories.</span></span> <span data-ttu-id="3ef42-158">Il modello accetta come input un'immagine di dimensione 224 x 224 e restituisce le probabilità della classe per ogni classe su cui è stato eseguito il training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-158">The model takes as input an image of size 224 x 224 and outputs the class probabilities for each of the classes it's trained on.</span></span> <span data-ttu-id="3ef42-159">Parte di questo modello viene utilizzata per eseguire il training di un nuovo modello utilizzando immagini personalizzate per eseguire stime tra due classi.</span><span class="sxs-lookup"><span data-stu-id="3ef42-159">Part of this model is used to train a new model using custom images to make predictions between two classes.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="3ef42-160">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="3ef42-160">Create console application</span></span>

<span data-ttu-id="3ef42-161">Ora che si dispone di una conoscenza generale del trasferimento dell'apprendimento e dell'API di classificazione delle immagini, è il momento di compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ef42-161">Now that you have a general understanding of transfer learning and the Image Classification API, it's time to build the application.</span></span>

1. <span data-ttu-id="3ef42-162">Creare un'  **C# applicazione console .NET Core** denominata "DeepLearning_ImageClassification_Binary".</span><span class="sxs-lookup"><span data-stu-id="3ef42-162">Create a **C# .NET Core Console Application** called "DeepLearning_ImageClassification_Binary".</span></span>
1. <span data-ttu-id="3ef42-163">Installare il pacchetto NuGet **Microsoft.ml** versione **1.4.0** :</span><span class="sxs-lookup"><span data-stu-id="3ef42-163">Install the **Microsoft.ML** version **1.4.0** NuGet Package:</span></span>
    1. <span data-ttu-id="3ef42-164">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-164">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="3ef42-165">Scegliere "nuget.org" come origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3ef42-165">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="3ef42-166">Selezionare la scheda **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-166">Select the **Browse** tab.</span></span>
    1. <span data-ttu-id="3ef42-167">Selezionare la casella di controllo **Includi versione preliminare** .</span><span class="sxs-lookup"><span data-stu-id="3ef42-167">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="3ef42-168">Cercare **Microsoft.ml**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-168">Search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="3ef42-169">Selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-169">Select the **Install** button.</span></span>
    1. <span data-ttu-id="3ef42-170">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="3ef42-170">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="3ef42-171">Ripetere questi passaggi per i pacchetti NuGet **Microsoft. ml. Vision** versione **1.4.0**, **SciSharp. TensorFlow. Redist** Version **1.15.0**e **Microsoft. ml. ImageAnalytics** Version **1.4.0** .</span><span class="sxs-lookup"><span data-stu-id="3ef42-171">Repeat these steps for the **Microsoft.ML.Vision** version **1.4.0**, **SciSharp.TensorFlow.Redist** version **1.15.0**, and **Microsoft.ML.ImageAnalytics** version **1.4.0** NuGet packages.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="3ef42-172">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="3ef42-172">Prepare and understand the data</span></span>

> [!NOTE]
> <span data-ttu-id="3ef42-173">I set di impostazioni per questa esercitazione sono di Maguire, Marc; Dorafshan, Sattar; e Thomas, Robert J., "SDNET2018: un set di dati concreti per le immagini per le applicazioni di Machine Learning" (2018).</span><span class="sxs-lookup"><span data-stu-id="3ef42-173">The datasets for this tutorial are from Maguire, Marc; Dorafshan, Sattar; and Thomas, Robert J., "SDNET2018: A concrete crack image dataset for machine learning applications" (2018).</span></span> <span data-ttu-id="3ef42-174">Esplorare tutti i set di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-174">Browse all Datasets.</span></span> <span data-ttu-id="3ef42-175">Carta 48.</span><span class="sxs-lookup"><span data-stu-id="3ef42-175">Paper 48.</span></span> <span data-ttu-id="3ef42-176">https://digitalcommons.usu.edu/all_datasets/48</span><span class="sxs-lookup"><span data-stu-id="3ef42-176">https://digitalcommons.usu.edu/all_datasets/48</span></span>

<span data-ttu-id="3ef42-177">SDNET2018 è un set di dati di immagini che contiene annotazioni per le strutture concrete incrinate e non incrinate (Bridge, muri e pavimentazione).</span><span class="sxs-lookup"><span data-stu-id="3ef42-177">SDNET2018 is an image dataset that contains annotations for cracked and non-cracked concrete structures (bridge decks, walls, and pavement).</span></span>

![Esempi di Deck Bridge per set di dati SDNET2018](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

<span data-ttu-id="3ef42-179">I dati sono organizzati in tre sottodirectory:</span><span class="sxs-lookup"><span data-stu-id="3ef42-179">The data is organized in three subdirectories:</span></span>

- <span data-ttu-id="3ef42-180">D contiene immagini del deck Bridge</span><span class="sxs-lookup"><span data-stu-id="3ef42-180">D contains bridge deck images</span></span>
- <span data-ttu-id="3ef42-181">P contiene immagini pavimentali</span><span class="sxs-lookup"><span data-stu-id="3ef42-181">P contains pavement images</span></span>
- <span data-ttu-id="3ef42-182">W contiene immagini a parete</span><span class="sxs-lookup"><span data-stu-id="3ef42-182">W contains wall images</span></span>

<span data-ttu-id="3ef42-183">Ognuna di queste sottodirectory contiene due sottodirectory con prefisso aggiuntivo:</span><span class="sxs-lookup"><span data-stu-id="3ef42-183">Each of these subdirectories contains two additional prefixed subdirectories:</span></span>

- <span data-ttu-id="3ef42-184">C è il prefisso usato per le superfici incrinate</span><span class="sxs-lookup"><span data-stu-id="3ef42-184">C is the prefix used for cracked surfaces</span></span>
- <span data-ttu-id="3ef42-185">U è il prefisso usato per le superfici non incrinate</span><span class="sxs-lookup"><span data-stu-id="3ef42-185">U is the prefix used for uncracked surfaces</span></span>

<span data-ttu-id="3ef42-186">In questa esercitazione vengono usate solo le immagini del deck Bridge.</span><span class="sxs-lookup"><span data-stu-id="3ef42-186">In this tutorial, only bridge deck images are used.</span></span>

1. <span data-ttu-id="3ef42-187">Scaricare il [set di dati](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) e decomprimere.</span><span class="sxs-lookup"><span data-stu-id="3ef42-187">Download the [dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) and unzip.</span></span>
1. <span data-ttu-id="3ef42-188">Creare una directory denominata "assets" nel progetto per salvare i file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="3ef42-188">Create a directory named "assets" in your project to save your dataset files.</span></span>
1. <span data-ttu-id="3ef42-189">Copiare le sottodirectory *CD* e *UD* dalla directory decomprimeta di recente alla directory *assets* .</span><span class="sxs-lookup"><span data-stu-id="3ef42-189">Copy the *CD* and *UD* subdirectories from the recently unzipped directory to the *assets* directory.</span></span>

### <a name="create-input-and-output-classes"></a><span data-ttu-id="3ef42-190">Creare classi di input e output</span><span class="sxs-lookup"><span data-stu-id="3ef42-190">Create input and output classes</span></span>

1. <span data-ttu-id="3ef42-191">Aprire il file *Program.cs* e sostituire le istruzioni `using` esistenti all'inizio del file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-191">Open the *Program.cs* file and replace the existing `using` statements at the top of the file with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. <span data-ttu-id="3ef42-192">Sotto la classe `Program` in *Program.cs*creare una classe denominata `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-192">Below the `Program` class in *Program.cs*, create a class called `ImageData`.</span></span> <span data-ttu-id="3ef42-193">Questa classe viene utilizzata per rappresentare i dati caricati inizialmente.</span><span class="sxs-lookup"><span data-stu-id="3ef42-193">This class is used to represent the initially loaded data.</span></span>

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L137-L142)]

    <span data-ttu-id="3ef42-194">`ImageData` contiene le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ef42-194">`ImageData` contains the following properties:</span></span>

    - <span data-ttu-id="3ef42-195">`ImagePath` è il percorso completo in cui è archiviata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-195">`ImagePath` is the fully qualified path where the image is stored.</span></span>
    - <span data-ttu-id="3ef42-196">`Label` è la categoria a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-196">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="3ef42-197">Si tratta del valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="3ef42-197">This is the value to predict.</span></span>

1. <span data-ttu-id="3ef42-198">Creare classi per i dati di input e di output</span><span class="sxs-lookup"><span data-stu-id="3ef42-198">Create classes for your input and output data</span></span>

    1. <span data-ttu-id="3ef42-199">Sotto la classe `ImageData` definire lo schema dei dati di input in una nuova classe denominata `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-199">Below the `ImageData` class, define the schema of your input data in a new class called `ModelInput`.</span></span>

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L144-L153)]

        <span data-ttu-id="3ef42-200">`ModelInput` contiene le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ef42-200">`ModelInput` contains the following properties:</span></span>

        - <span data-ttu-id="3ef42-201">`ImagePath` è il percorso completo in cui è archiviata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-201">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="3ef42-202">`Label` è la categoria a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-202">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="3ef42-203">Si tratta del valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="3ef42-203">This is the value to predict.</span></span>
        - <span data-ttu-id="3ef42-204">`Image` è la rappresentazione `byte[]` dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-204">`Image` is the `byte[]` representation of the image.</span></span> <span data-ttu-id="3ef42-205">Il modello prevede che i dati dell'immagine siano di questo tipo per il training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-205">The model expects image data to be of this type for training.</span></span>
        - <span data-ttu-id="3ef42-206">`LabelAsKey` è la rappresentazione numerica del `Label`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-206">`LabelAsKey` is the numerical representation of the `Label`.</span></span>

        <span data-ttu-id="3ef42-207">Per eseguire il training del modello e eseguire stime, vengono utilizzati solo `Image` e `LabelAsKey`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-207">Only `Image` and `LabelAsKey` are used to train the model and make predictions.</span></span> <span data-ttu-id="3ef42-208">Le proprietà `ImagePath` e `Label` sono conservate per praticità per accedere al nome del file di immagine originale e alla categoria.</span><span class="sxs-lookup"><span data-stu-id="3ef42-208">The `ImagePath` and `Label` properties are kept for convenience to access the original image file name and category.</span></span>

    1. <span data-ttu-id="3ef42-209">Quindi, sotto la classe `ModelInput`, definire lo schema dei dati di output in una nuova classe denominata `ModelOutput`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-209">Then, below the `ModelInput` class, define the schema of your output data in a new class called `ModelOutput`.</span></span>

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L155-L162)]

        <span data-ttu-id="3ef42-210">`ModelOutput` contiene le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ef42-210">`ModelOutput` contains the following properties:</span></span>

        - <span data-ttu-id="3ef42-211">`ImagePath` è il percorso completo in cui è archiviata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-211">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="3ef42-212">`Label` è la categoria originale a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-212">`Label` is the original category the image belongs to.</span></span> <span data-ttu-id="3ef42-213">Si tratta del valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="3ef42-213">This is the value to predict.</span></span>
        - <span data-ttu-id="3ef42-214">`PredictedLabel` è il valore stimato dal modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-214">`PredictedLabel` is the value predicted by the model.</span></span>

        <span data-ttu-id="3ef42-215">Analogamente a `ModelInput`, per eseguire stime è necessario solo il `PredictedLabel` perché contiene la stima effettuata dal modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-215">Similar to `ModelInput`, only the `PredictedLabel` is required to make predictions since it contains the prediction made by the model.</span></span> <span data-ttu-id="3ef42-216">Le proprietà `ImagePath` e `Label` vengono conservate per praticità per accedere al nome del file di immagine originale e alla categoria.</span><span class="sxs-lookup"><span data-stu-id="3ef42-216">The `ImagePath` and `Label` properties are retained for convenience to access the original image file name and category.</span></span>

### <a name="create-workspace-directory"></a><span data-ttu-id="3ef42-217">Crea directory dell'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="3ef42-217">Create workspace directory</span></span>

<span data-ttu-id="3ef42-218">Quando i dati di training e convalida non cambiano spesso, è consigliabile memorizzare nella cache i valori del collo di bottiglia calcolati per altre esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-218">When training and validation data do not change often, it is good practice to cache the computed bottleneck values for further runs.</span></span>

1. <span data-ttu-id="3ef42-219">Nel progetto creare una nuova directory denominata *Workspace* per archiviare i valori del collo di bottiglia calcolati e la versione `.pb` del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-219">In your project, create a new directory called *workspace* to store the computed bottleneck values and `.pb` version of the model.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="3ef42-220">Definire i percorsi e inizializzare le variabili</span><span class="sxs-lookup"><span data-stu-id="3ef42-220">Define paths and initialize variables</span></span>

1. <span data-ttu-id="3ef42-221">All'interno del `Main` metodo, definire la posizione degli asset, i valori del collo di bottiglia calcolati e la versione `.pb` del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-221">Inside the `Main` method, define the location of your assets, computed bottleneck values and `.pb` version of the model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L17)]

1. <span data-ttu-id="3ef42-222">Quindi, inizializzare la variabile `mlContext` con una nuova istanza di [MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="3ef42-222">Then, initialize the `mlContext` variable with a new instance of [MLContext](xref:Microsoft.ML.MLContext).</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L19)]

    <span data-ttu-id="3ef42-223">La classe [MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni di ml.NET e l'inizializzazione di MLContext crea un nuovo ambiente ml.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-223">The [MLContext](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="3ef42-224">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="3ef42-224">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="3ef42-225">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="3ef42-225">Load the data</span></span>

### <a name="create-data-loading-utility-method"></a><span data-ttu-id="3ef42-226">Metodo di creazione dell'utilità di caricamento dati</span><span class="sxs-lookup"><span data-stu-id="3ef42-226">Create data loading utility method</span></span>

<span data-ttu-id="3ef42-227">Le immagini vengono archiviate in due sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="3ef42-227">The images are stored in two subdirectories.</span></span> <span data-ttu-id="3ef42-228">Prima di caricare i dati, è necessario formattarli in un elenco di oggetti `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-228">Before loading the data, it needs to be formatted into a list of `ImageData` objects.</span></span> <span data-ttu-id="3ef42-229">A tale scopo, creare il metodo `LoadImagesFromDirectory` al di sotto del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-229">To do so, create the `LoadImagesFromDirectory` method below the `Main` method.</span></span>

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. <span data-ttu-id="3ef42-230">All'interno del `LoadImagesDirectory` aggiungere il codice seguente per ottenere tutti i percorsi di file dalle sottodirectory:</span><span class="sxs-lookup"><span data-stu-id="3ef42-230">Inside the `LoadImagesDirectory` add the following code to get all of the file paths from the subdirectories:</span></span>

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L104-L105)]

1. <span data-ttu-id="3ef42-231">Eseguire quindi l'iterazione di ogni file usando un'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-231">Then, iterate through each of the files using a `foreach` statement.</span></span>

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. <span data-ttu-id="3ef42-232">All'interno dell'istruzione `foreach` verificare che le estensioni di file siano supportate.</span><span class="sxs-lookup"><span data-stu-id="3ef42-232">Inside the `foreach` statement, check that the file extensions are supported.</span></span> <span data-ttu-id="3ef42-233">L'API di classificazione delle immagini supporta i formati JPEG e PNG.</span><span class="sxs-lookup"><span data-stu-id="3ef42-233">The Image Classification API supports JPEG and PNG formats.</span></span>

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L109-L110)]

1. <span data-ttu-id="3ef42-234">Ottenere quindi l'etichetta per il file.</span><span class="sxs-lookup"><span data-stu-id="3ef42-234">Then, get the label for the file.</span></span> <span data-ttu-id="3ef42-235">Se il parametro `useFolderNameAsLabel` è impostato su `true`, viene usata come etichetta la directory padre in cui viene salvato il file.</span><span class="sxs-lookup"><span data-stu-id="3ef42-235">If the `useFolderNameAsLabel` parameter is set to `true`, then the parent directory where the file is saved is used as the label.</span></span> <span data-ttu-id="3ef42-236">In caso contrario, prevede che l'etichetta sia un prefisso del nome file o il nome del file stesso.</span><span class="sxs-lookup"><span data-stu-id="3ef42-236">Otherwise, it expects the label to be a prefix of the file name or the file name itself.</span></span>

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L112-L126)]

1. <span data-ttu-id="3ef42-237">Infine, creare una nuova istanza di `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-237">Finally, create a new instance of `ModelInput`.</span></span>

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L128-L132)]

### <a name="prepare-the-data"></a><span data-ttu-id="3ef42-238">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="3ef42-238">Prepare the data</span></span>

1. <span data-ttu-id="3ef42-239">Tornando al metodo `Main`, usare il metodo di utilità `LoadFromDirectory` per ottenere l'elenco delle immagini usate per il training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-239">Back in the `Main` method, use the `LoadFromDirectory` utility method to get the list of images used for training.</span></span>

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L21)]

1. <span data-ttu-id="3ef42-240">Quindi, caricare le immagini in una [`IDataView`](xref:Microsoft.ML.IDataView) usando il metodo [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) .</span><span class="sxs-lookup"><span data-stu-id="3ef42-240">Then, load the images into an [`IDataView`](xref:Microsoft.ML.IDataView) using the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method.</span></span>

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L23)]

1. <span data-ttu-id="3ef42-241">I dati vengono caricati nell'ordine in cui sono stati letti dalle directory.</span><span class="sxs-lookup"><span data-stu-id="3ef42-241">The data is loaded in the order it was read from the directories.</span></span> <span data-ttu-id="3ef42-242">Per bilanciare i dati, eseguire il shuffle usando il metodo [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) .</span><span class="sxs-lookup"><span data-stu-id="3ef42-242">To balance the data, shuffle it using the [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) method.</span></span>

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L25)]

1. <span data-ttu-id="3ef42-243">Per i modelli di apprendimento automatico si prevede che l'input sia in formato numerico.</span><span class="sxs-lookup"><span data-stu-id="3ef42-243">Machine learning models expect input to be in numerical format.</span></span> <span data-ttu-id="3ef42-244">Pertanto, è necessario eseguire alcune operazioni di pre-elaborazione sui dati prima di eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-244">Therefore, some preprocessing needs to be done on the data prior to training.</span></span> <span data-ttu-id="3ef42-245">Creare un [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) costituito dalle trasformazioni [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) e `LoadRawImageBytes`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-245">Create an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) made up of the [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) and `LoadRawImageBytes` transforms.</span></span> <span data-ttu-id="3ef42-246">La trasformazione `MapValueToKey` accetta il valore categorico nella colonna `Label`, lo converte in un valore numerico `KeyType` e lo archivia in una nuova colonna denominata `LabelAsKey`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-246">The `MapValueToKey` transform takes the categorical value in the `Label` column, converts it to a numerical `KeyType` value and stores it in a new column called `LabelAsKey`.</span></span> <span data-ttu-id="3ef42-247">Il `LoadImages` accetta i valori della colonna `ImagePath` insieme al parametro `imageFolder` per caricare le immagini per il training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-247">The `LoadImages` takes the values from the `ImagePath` column along with the `imageFolder` parameter to load images for training.</span></span>

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L27-L33)]

1. <span data-ttu-id="3ef42-248">Usare il metodo [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) per applicare i dati al `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) seguito dal metodo [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) , che restituisce un [`IDataView`](xref:Microsoft.ML.IDataView) contenente i dati pre-elaborati.</span><span class="sxs-lookup"><span data-stu-id="3ef42-248">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to apply the data to the `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) followed by the [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) method, which returns an [`IDataView`](xref:Microsoft.ML.IDataView) containing the pre-processed data.</span></span>

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. <span data-ttu-id="3ef42-249">Per eseguire il training di un modello, è importante avere un set di dati di training e un set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="3ef42-249">To train a model, it's important to have a training dataset as well as a validation dataset.</span></span> <span data-ttu-id="3ef42-250">Viene eseguito il training del modello nel training set.</span><span class="sxs-lookup"><span data-stu-id="3ef42-250">The model is trained on the training set.</span></span> <span data-ttu-id="3ef42-251">Il modo in cui esegue le stime sui dati non visualizzati viene misurato in base alle prestazioni rispetto al set di convalida.</span><span class="sxs-lookup"><span data-stu-id="3ef42-251">How well it makes predictions on unseen data is measured by the performance against the validation set.</span></span> <span data-ttu-id="3ef42-252">In base ai risultati di tali prestazioni, il modello apporta modifiche a quanto appreso nel tentativo di migliorare.</span><span class="sxs-lookup"><span data-stu-id="3ef42-252">Based on the results of that performance, the model makes adjustments to what it has learned in an effort to improve.</span></span> <span data-ttu-id="3ef42-253">Il set di convalida può derivare dalla suddivisione del set di dati originale o da un'altra origine che è già stata riservata a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-253">The validation set can come from either splitting your original dataset or from another source that has already been set aside for this purpose.</span></span> <span data-ttu-id="3ef42-254">In questo caso, il set di dati pre-elaborato viene suddiviso in set di training, convalida e test.</span><span class="sxs-lookup"><span data-stu-id="3ef42-254">In this case, the pre-processed dataset is split into training, validation and test sets.</span></span>

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    <span data-ttu-id="3ef42-255">L'esempio di codice precedente esegue due divisioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-255">The code sample above performs two splits.</span></span> <span data-ttu-id="3ef42-256">In primo luogo, i dati pre-elaborati sono divisi e il 70% viene usato per il training, mentre il 30% rimanente viene usato per la convalida.</span><span class="sxs-lookup"><span data-stu-id="3ef42-256">First, the pre-processed data is split and 70% is used for training while the remaining 30% is used for validation.</span></span> <span data-ttu-id="3ef42-257">Il set di convalida del 30% viene quindi suddiviso ulteriormente nei set di convalida e di test, in cui il 90% viene usato per la convalida e il 10% viene usato per il test.</span><span class="sxs-lookup"><span data-stu-id="3ef42-257">Then, the 30% validation set is further split into validation and test sets where 90% is used for validation and 10% is used for testing.</span></span>

    <span data-ttu-id="3ef42-258">Un modo per considerare lo scopo di queste partizioni di dati consiste nell'esame.</span><span class="sxs-lookup"><span data-stu-id="3ef42-258">A way to think about the purpose of these data partitions is taking an exam.</span></span> <span data-ttu-id="3ef42-259">Quando si studia un esame, si esaminano le note, i libri o altre risorse per approfondire i concetti relativi all'esame.</span><span class="sxs-lookup"><span data-stu-id="3ef42-259">When studying for an exam, you review your notes, books, or other resources to get a grasp on the concepts that are on the exam.</span></span> <span data-ttu-id="3ef42-260">Questo è il set di training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-260">This is what the train set is for.</span></span> <span data-ttu-id="3ef42-261">Quindi, è possibile eseguire un esame fittizio per convalidare le proprie conoscenze.</span><span class="sxs-lookup"><span data-stu-id="3ef42-261">Then, you might take a mock exam to validate your knowledge.</span></span> <span data-ttu-id="3ef42-262">Questo è il punto in cui il set di convalida risulta utile.</span><span class="sxs-lookup"><span data-stu-id="3ef42-262">This is where the validation set comes in handy.</span></span> <span data-ttu-id="3ef42-263">Si desidera controllare se si dispone di una conoscenza adeguata dei concetti prima di intraprendere l'esame effettivo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-263">You want to check whether you have a good grasp of the concepts before taking the actual exam.</span></span> <span data-ttu-id="3ef42-264">In base a questi risultati, si prende nota di quanto si è verificato un errore o non si è capito bene e si inseriscono le modifiche durante la revisione del vero esame.</span><span class="sxs-lookup"><span data-stu-id="3ef42-264">Based on those results, you take note of what you got wrong or didn't understand well and incorporate your changes as you review for the real exam.</span></span> <span data-ttu-id="3ef42-265">Infine, si prenderà in esame.</span><span class="sxs-lookup"><span data-stu-id="3ef42-265">Finally, you take the exam.</span></span> <span data-ttu-id="3ef42-266">Per questa operazione viene usato il set di test.</span><span class="sxs-lookup"><span data-stu-id="3ef42-266">This is what the test set is used for.</span></span> <span data-ttu-id="3ef42-267">Non hai mai visto le domande che sono in fase di esame e ora usi quanto appreso dalla formazione e dalla convalida per applicare le tue conoscenze all'attività.</span><span class="sxs-lookup"><span data-stu-id="3ef42-267">You've never seen the questions that are on the exam and now use what you learned from training and validation to apply your knowledge to the task at hand.</span></span>

1. <span data-ttu-id="3ef42-268">Assegnare alle partizioni i rispettivi valori per i dati di training, convalida e test.</span><span class="sxs-lookup"><span data-stu-id="3ef42-268">Assign the partitions their respective values for the train, validation and test data.</span></span>

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a><span data-ttu-id="3ef42-269">Definire la pipeline di training</span><span class="sxs-lookup"><span data-stu-id="3ef42-269">Define the training pipeline</span></span>

<span data-ttu-id="3ef42-270">Il training del modello è costituito da un paio di passaggi.</span><span class="sxs-lookup"><span data-stu-id="3ef42-270">Model training consists of a couple of steps.</span></span> <span data-ttu-id="3ef42-271">Per prima cosa, viene utilizzata l'API di classificazione delle immagini per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-271">First, Image Classification API is used to train the model.</span></span> <span data-ttu-id="3ef42-272">Quindi, le etichette codificate nella colonna `PredictedLabel` vengono riconvertite nel valore categorico originale utilizzando la trasformazione `MapKeyToValue`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-272">Then, the encoded labels in the `PredictedLabel` column are converted back to their original categorical value using the `MapKeyToValue` transform.</span></span>

1. <span data-ttu-id="3ef42-273">Creare una nuova variabile per archiviare un set di parametri obbligatori e facoltativi per un `ImageClassificationTrainer`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-273">Create a new variable to store a set of required and optional parameters for an `ImageClassificationTrainer`.</span></span> 

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L57)]

    <span data-ttu-id="3ef42-274">Un `ImageClassificationTrainer` accetta diversi parametri facoltativi:</span><span class="sxs-lookup"><span data-stu-id="3ef42-274">An `ImageClassificationTrainer` takes several optional parameters:</span></span>

    - <span data-ttu-id="3ef42-275">`FeatureColumnName` è la colonna utilizzata come input per il modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-275">`FeatureColumnName` is the column that is used as input for the model.</span></span>
    - <span data-ttu-id="3ef42-276">`LabelColumnName` è la colonna per il valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="3ef42-276">`LabelColumnName` is the column for the value to predict.</span></span>
    - <span data-ttu-id="3ef42-277">`ValidationSet` è l' [`IDataView`](xref:Microsoft.ML.IDataView) contenente i dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="3ef42-277">`ValidationSet` is the [`IDataView`](xref:Microsoft.ML.IDataView) containing the validation data.</span></span>
    - <span data-ttu-id="3ef42-278">`Arch` definisce quali architetture del modello con training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-278">`Arch` defines which of the pretrained model architectures to use.</span></span> <span data-ttu-id="3ef42-279">Questa esercitazione usa la variante a 101 livelli del modello ResNetv2.</span><span class="sxs-lookup"><span data-stu-id="3ef42-279">This tutorial uses the 101-layer variant of the ResNetv2 model.</span></span>
    - <span data-ttu-id="3ef42-280">`MetricsCallback` associa una funzione per tenere traccia dello stato di avanzamento durante il training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-280">`MetricsCallback` binds a function to track the progress during training.</span></span>
    - <span data-ttu-id="3ef42-281">`TestOnTrainSet` indica al modello di misurare le prestazioni rispetto al set di training quando non è presente alcun set di convalida.</span><span class="sxs-lookup"><span data-stu-id="3ef42-281">`TestOnTrainSet` tells the model to measure performance against the training set when no validation set is present.</span></span>
    - <span data-ttu-id="3ef42-282">`ReuseTrainSetBottleneckCachedValues` indica al modello se utilizzare i valori memorizzati nella cache della fase di collo di bottiglia nelle esecuzioni successive.</span><span class="sxs-lookup"><span data-stu-id="3ef42-282">`ReuseTrainSetBottleneckCachedValues` tells the model whether to use the cached values from the bottleneck phase in subsequent runs.</span></span> <span data-ttu-id="3ef42-283">La fase di collo di bottiglia è un calcolo pass-through monouso che richiede un utilizzo intensivo di calcolo alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3ef42-283">The bottleneck phase is a one-time pass-through computation that is computationally intensive the first time it is performed.</span></span> <span data-ttu-id="3ef42-284">Se i dati di training non cambiano e si vuole provare a usare un numero diverso di epoche o dimensioni del batch, l'uso dei valori memorizzati nella cache riduce significativamente la quantità di tempo necessaria per eseguire il training di un modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-284">If the training data does not change and you want to experiment using a different number of epochs or batch size, using the cached values significantly reduces the amount of time required to train a model.</span></span>
    - <span data-ttu-id="3ef42-285">`ReuseValidationSetBottleneckCachedValues` è simile `ReuseTrainSetBottleneckCachedValues` solo che in questo caso è per il set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="3ef42-285">`ReuseValidationSetBottleneckCachedValues` is similar to `ReuseTrainSetBottleneckCachedValues` only that in this case it's for the validation dataset.</span></span>
    - <span data-ttu-id="3ef42-286">`WorkspacePath` definisce la directory in cui archiviare i valori del collo di bottiglia calcolati e la versione `.pb` del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-286">`WorkspacePath` defines the directory where to store the computed bottleneck values and `.pb` version of the model.</span></span>

1. <span data-ttu-id="3ef42-287">Definire la pipeline di training [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) costituita sia dal `mapLabelEstimator` che dal `ImageClassificationTrainer`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-287">Define the [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) training pipeline that consists of both the `mapLabelEstimator` and the `ImageClassificationTrainer`.</span></span>

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L59-L60)]

1. <span data-ttu-id="3ef42-288">Usare il metodo [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-288">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to train your model.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

## <a name="use-the-model"></a><span data-ttu-id="3ef42-289">Usare il modello</span><span class="sxs-lookup"><span data-stu-id="3ef42-289">Use the model</span></span>

<span data-ttu-id="3ef42-290">A questo punto, dopo aver eseguito il training del modello, è possibile usarlo per classificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="3ef42-290">Now that you have trained your model, it's time to use it to classify images.</span></span>

<span data-ttu-id="3ef42-291">Sotto il metodo `Main` creare un nuovo metodo di utilità denominato `OutputPrediction` per visualizzare le informazioni di stima nella console di.</span><span class="sxs-lookup"><span data-stu-id="3ef42-291">Below the `Main` method, create a new utility method called `OutputPrediction` to display prediction information in the console.</span></span>

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L96-L100)]

### <a name="classify-a-single-image"></a><span data-ttu-id="3ef42-292">Classificare una singola immagine</span><span class="sxs-lookup"><span data-stu-id="3ef42-292">Classify a single image</span></span>

1. <span data-ttu-id="3ef42-293">Aggiungere un nuovo metodo denominato `ClassifySingleImage` sotto il metodo `Main` per creare e restituire una singola stima di immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-293">Add a new method called `ClassifySingleImage` below the `Main` method to make and output a single image prediction.</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="3ef42-294">Creare un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) all'interno del metodo `ClassifySingleImage`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-294">Create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) inside the `ClassifySingleImage` method.</span></span> <span data-ttu-id="3ef42-295">Il [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) è una praticità API, che consente di passare ed eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="3ef42-295">The [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. <span data-ttu-id="3ef42-296">Per accedere a una singola istanza di `ModelInput`, convertire il [`IDataView`](xref:Microsoft.ML.IDataView) di `data` in un [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) usando il metodo [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) e quindi ottenere la prima osservazione.</span><span class="sxs-lookup"><span data-stu-id="3ef42-296">To access a single `ModelInput` instance, convert the `data` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first observation.</span></span>

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. <span data-ttu-id="3ef42-297">Usare il metodo [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) per classificare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-297">Use the [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) method to classify the image.</span></span>

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77)]

1. <span data-ttu-id="3ef42-298">Restituire la stima alla console con il metodo `OutputPrediction`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-298">Output the prediction to the console with the `OutputPrediction` method.</span></span>

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L79-L80)]

1. <span data-ttu-id="3ef42-299">All'interno del metodo `Main` chiamare `ClassifySingleImage` utilizzando il set di immagini di test.</span><span class="sxs-lookup"><span data-stu-id="3ef42-299">Inside the `Main` method, call `ClassifySingleImage` using the test set of images.</span></span>

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

### <a name="classify-multiple-images"></a><span data-ttu-id="3ef42-300">Classificare più immagini</span><span class="sxs-lookup"><span data-stu-id="3ef42-300">Classify multiple images</span></span>

1. <span data-ttu-id="3ef42-301">Aggiungere un nuovo metodo denominato `ClassifyImages` sotto il metodo `ClassifySingleImage` per creare e restituire più stime di immagine.</span><span class="sxs-lookup"><span data-stu-id="3ef42-301">Add a new method called `ClassifyImages` below the `ClassifySingleImage` method to make and output multiple image predictions.</span></span>

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="3ef42-302">Creare un [`IDataView`](xref:Microsoft.ML.IDataView) contenente le stime utilizzando il metodo [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) .</span><span class="sxs-lookup"><span data-stu-id="3ef42-302">Create an [`IDataView`](xref:Microsoft.ML.IDataView) containing the predictions by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method.</span></span> <span data-ttu-id="3ef42-303">Aggiungere il codice seguente all'interno del metodo `ClassifyImages`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-303">Add the following code inside the `ClassifyImages` method.</span></span>

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. <span data-ttu-id="3ef42-304">Per eseguire l'iterazione delle stime, convertire il `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) in un [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) usando il metodo [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) e quindi ottenere le prime 10 osservazioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-304">In order to iterate over the predictions, convert the `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first 10 observations.</span></span>

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87)]

1. <span data-ttu-id="3ef42-305">Eseguire l'iterazione e restituire le etichette originali e stimate per le stime.</span><span class="sxs-lookup"><span data-stu-id="3ef42-305">Iterate and output the original and predicted labels for the predictions.</span></span>

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L89-L93)]

1. <span data-ttu-id="3ef42-306">Infine, all'interno del metodo `Main`, chiamare `ClassifyImages` utilizzando il set di immagini di test.</span><span class="sxs-lookup"><span data-stu-id="3ef42-306">Finally, inside the `Main` method, call `ClassifyImages` using the test set of images.</span></span>

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L66)]

## <a name="run-the-application"></a><span data-ttu-id="3ef42-307">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3ef42-307">Run the application</span></span>

<span data-ttu-id="3ef42-308">Eseguire l'app console.</span><span class="sxs-lookup"><span data-stu-id="3ef42-308">Run your console app.</span></span> <span data-ttu-id="3ef42-309">L'output dovrebbe essere simile a quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3ef42-309">The output should be similar to that below.</span></span> <span data-ttu-id="3ef42-310">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="3ef42-310">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span> <span data-ttu-id="3ef42-311">Per brevità, l'output è stato condensato.</span><span class="sxs-lookup"><span data-stu-id="3ef42-311">For brevity, the output has been condensed.</span></span>

<span data-ttu-id="3ef42-312">**Fase collo di bottiglia**</span><span class="sxs-lookup"><span data-stu-id="3ef42-312">**Bottleneck phase**</span></span>

<span data-ttu-id="3ef42-313">Non viene stampato alcun valore per il nome dell'immagine perché le immagini vengono caricate come `byte[]` pertanto non è presente alcun nome immagine da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="3ef42-313">No value is printed for the image name because the images are loaded as a `byte[]` therefore there is no image name to display.</span></span>

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

<span data-ttu-id="3ef42-314">**Fase di training**</span><span class="sxs-lookup"><span data-stu-id="3ef42-314">**Training phase**</span></span>

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

<span data-ttu-id="3ef42-315">**Classifica output immagini**</span><span class="sxs-lookup"><span data-stu-id="3ef42-315">**Classify images output**</span></span>

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

<span data-ttu-id="3ef42-316">Quando si verifica l'immagine *7001 -220. jpg* , è possibile notare che in realtà non è incrinato.</span><span class="sxs-lookup"><span data-stu-id="3ef42-316">Upon inspection of the *7001-220.jpg* image, you can see that it in fact is not cracked.</span></span>

![Immagine del set di dati SDNET2018 utilizzata per la stima](./media/image-classification-api-transfer-learning/predictedimage.jpg)

<span data-ttu-id="3ef42-318">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="3ef42-318">Congratulations!</span></span> <span data-ttu-id="3ef42-319">A questo punto è stato creato un modello di apprendimento avanzato per la classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="3ef42-319">You've now successfully built a deep learning model for classifying images.</span></span>

### <a name="improve-the-model"></a><span data-ttu-id="3ef42-320">Migliorare il modello</span><span class="sxs-lookup"><span data-stu-id="3ef42-320">Improve the model</span></span>

<span data-ttu-id="3ef42-321">Se non si è soddisfatti dei risultati del modello, è possibile provare a migliorarne le prestazioni provando alcuni degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ef42-321">If you're not satisfied with the results of your model, you can try to improve its performance by trying some of the following approaches:</span></span>

- <span data-ttu-id="3ef42-322">**Altri dati**: maggiore è il numero di esempi apportati da un modello, migliori saranno le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-322">**More Data**: The more examples a model learns from, the better it performs.</span></span> <span data-ttu-id="3ef42-323">Scaricare il [set di dati SDNET2018](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) completo e usarlo per il training.</span><span class="sxs-lookup"><span data-stu-id="3ef42-323">Download the full [SDNET2018 dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) and use it to train.</span></span>
- <span data-ttu-id="3ef42-324">**Migliorare i dati**: una tecnica comune per aggiungere varietà ai dati consiste nell'aumentare i dati mediante l'acquisizione di un'immagine e l'applicazione di trasformazioni diverse (ruotare, capovolgere, spostare o ritagliare).</span><span class="sxs-lookup"><span data-stu-id="3ef42-324">**Augment the data**: A common technique to add variety to the data is to augment the data by taking an image and applying different transforms (rotate, flip, shift, crop).</span></span> <span data-ttu-id="3ef42-325">In questo modo vengono aggiunti esempi più diversi per il modello da cui apprendere.</span><span class="sxs-lookup"><span data-stu-id="3ef42-325">This adds more varied examples for the model to learn from.</span></span>
- <span data-ttu-id="3ef42-326">Eseguire il **training per un periodo di tempo più lungo**: maggiore sarà il training del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-326">**Train for a longer time**: The longer you train, the more tuned the model will be.</span></span> <span data-ttu-id="3ef42-327">L'aumento del numero di epoche può migliorare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="3ef42-327">Increasing the number of epochs may improve the performance of your model.</span></span>
- <span data-ttu-id="3ef42-328">**Esperimento con i parametri ipertestuali**: oltre ai parametri usati in questa esercitazione, è possibile ottimizzare altri parametri per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-328">**Experiment with the hyper-parameters**: In addition to the parameters used in this tutorial, other parameters can be tuned to potentially improve performance.</span></span> <span data-ttu-id="3ef42-329">Modifica della velocità di apprendimento, che determina la grandezza degli aggiornamenti apportati al modello dopo che ogni Epoch può migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-329">Changing the learning rate, which determines the magnitude of updates made to the model after each epoch may improve performance.</span></span>
- <span data-ttu-id="3ef42-330">**Usare un'architettura del modello diversa**: a seconda dell'aspetto dei dati, il modello che può apprendere meglio le sue funzionalità può essere diverso.</span><span class="sxs-lookup"><span data-stu-id="3ef42-330">**Use a different model architecture**: Depending on what your data looks like, the model that can best learn its features may differ.</span></span> <span data-ttu-id="3ef42-331">Se non si è soddisfatti delle prestazioni del modello, provare a modificare l'architettura.</span><span class="sxs-lookup"><span data-stu-id="3ef42-331">If you're not satisfied with the performance of your model, try changing the architecture.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3ef42-332">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3ef42-332">Additional Resources</span></span>

- <span data-ttu-id="3ef42-333">[Visual Studio e Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="3ef42-333">[Deep Learning vs Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ef42-334">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3ef42-334">Next steps</span></span>

<span data-ttu-id="3ef42-335">In questa esercitazione si è appreso come creare un modello di apprendimento avanzato personalizzato usando Transfer Learning, un modello di classificazione di immagini con training TensorFlow e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non incrinate.</span><span class="sxs-lookup"><span data-stu-id="3ef42-335">In this tutorial, you learned how to build a custom deep learning model using transfer learning, a pretrained image classification TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="3ef42-336">Passare all'esercitazione successiva per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="3ef42-336">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3ef42-337">Rilevamento oggetti</span><span class="sxs-lookup"><span data-stu-id="3ef42-337">Object Detection</span></span>](object-detection-onnx.md)
