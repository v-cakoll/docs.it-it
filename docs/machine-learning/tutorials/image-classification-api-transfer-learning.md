---
title: "Esercitazione: Ispezione visiva automatizzata tramite l'apprendimento dei trasferimentiTutorial: Automated visual inspection using transfer learning"
description: Questa esercitazione illustra come usare l'apprendimento tramite trasferimento per eseguire il training di un modello di deep learning TensorFlow in ML.NET usando l'API di rilevamento delle immagini per classificare le immagini di superfici in calcestruzzo come incrinate o non incrinate.
author: luisquintanilla
ms.author: luquinta
ms.date: 12/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a050d7673f7ef00cf11d959d04e709222cb2be8f
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607558"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a><span data-ttu-id="ca90b-103">Esercitazione: Ispezione visiva automatizzata tramite l'apprendimento del trasferimento con l'API di classificazione delle immagini ML.NETTutorial: Automated visual inspection using transfer learning with the ML.NET Image Classification API</span><span class="sxs-lookup"><span data-stu-id="ca90b-103">Tutorial: Automated visual inspection using transfer learning with the ML.NET Image Classification API</span></span>

<span data-ttu-id="ca90b-104">Informazioni su come eseguire il training di un modello di deep learning personalizzato usando l'apprendimento tramite trasferimento, un modello TensorFlow preaddestrato e l'API ML.NET image Classification per classificare le immagini di superfici concrete come incrinate o non superate.</span><span class="sxs-lookup"><span data-stu-id="ca90b-104">Learn how to train a custom deep learning model using transfer learning, a pretrained TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="ca90b-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="ca90b-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ca90b-106">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ca90b-106">Understand the problem</span></span>
> - <span data-ttu-id="ca90b-107">Informazioni su ML.NETAPI di classificazione delle immagini</span><span class="sxs-lookup"><span data-stu-id="ca90b-107">Learn about ML.NET Image Classification API</span></span>
> - <span data-ttu-id="ca90b-108">Comprendere il modello preformato</span><span class="sxs-lookup"><span data-stu-id="ca90b-108">Understand the pretrained model</span></span>
> - <span data-ttu-id="ca90b-109">Usare l'apprendimento di trasferimento per eseguire il training di un modello di classificazione delle immagini TensorFlow personalizzatoUse transfer learning to train a custom TensorFlow image classification model</span><span class="sxs-lookup"><span data-stu-id="ca90b-109">Use transfer learning to train a custom TensorFlow image classification model</span></span>
> - <span data-ttu-id="ca90b-110">Classificare le immagini con il modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="ca90b-110">Classify images with the custom model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca90b-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ca90b-111">Prerequisites</span></span>

- <span data-ttu-id="ca90b-112">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o Visual Studio 2017 versione 15.6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="ca90b-112">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="image-classification-transfer-learning-sample-overview"></a><span data-ttu-id="ca90b-113">Panoramica dell'esempio di apprendimento sul trasferimento della classificazione delle immagini</span><span class="sxs-lookup"><span data-stu-id="ca90b-113">Image classification transfer learning sample overview</span></span>

<span data-ttu-id="ca90b-114">Questo esempio è un'applicazione console .NET Core di C.NET che classifica le immagini usando un modello TensorFlow di deep learning con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-114">This sample is a C# .NET Core console application that classifies images using a pretrained deep learning TensorFlow model.</span></span> <span data-ttu-id="ca90b-115">Il codice per questo esempio è disponibile nel [repository dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="ca90b-115">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="ca90b-116">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ca90b-116">Understand the problem</span></span>

<span data-ttu-id="ca90b-117">La classificazione delle immagini è un problema di visione artificiale.</span><span class="sxs-lookup"><span data-stu-id="ca90b-117">Image classification is a computer vision problem.</span></span> <span data-ttu-id="ca90b-118">La classificazione delle immagini accetta un'immagine come input e la classifica in una classe prescritta.</span><span class="sxs-lookup"><span data-stu-id="ca90b-118">Image classification takes an image as input and categorizes it into a prescribed class.</span></span> <span data-ttu-id="ca90b-119">Alcuni scenari in cui la classificazione delle immagini è utile includono:Some scenarios where image classification is useful include:</span><span class="sxs-lookup"><span data-stu-id="ca90b-119">Some scenarios where image classification is useful include:</span></span>

- <span data-ttu-id="ca90b-120">Riconoscimento facciale</span><span class="sxs-lookup"><span data-stu-id="ca90b-120">Facial recognition</span></span>
- <span data-ttu-id="ca90b-121">Rilevamento emozioni</span><span class="sxs-lookup"><span data-stu-id="ca90b-121">Emotion detection</span></span>
- <span data-ttu-id="ca90b-122">Diagnosi medica</span><span class="sxs-lookup"><span data-stu-id="ca90b-122">Medical diagnosis</span></span>
- <span data-ttu-id="ca90b-123">Rilevamento dei punti di riferimento</span><span class="sxs-lookup"><span data-stu-id="ca90b-123">Landmark detection</span></span>

<span data-ttu-id="ca90b-124">Questa esercitazione esegue il training di un modello di classificazione delle immagini personalizzato per eseguire l'ispezione visiva automatica dei ponti per identificare le strutture danneggiate dalle fessure.</span><span class="sxs-lookup"><span data-stu-id="ca90b-124">This tutorial trains a custom image classification model to perform automated visual inspection of bridge decks to identify structures that are damaged by cracks.</span></span>

## <a name="mlnet-image-classification-api"></a><span data-ttu-id="ca90b-125">ML.NET Image Classification API</span><span class="sxs-lookup"><span data-stu-id="ca90b-125">ML.NET Image Classification API</span></span>

<span data-ttu-id="ca90b-126">ML.NET fornisce vari modi per eseguire la classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="ca90b-126">ML.NET provides various ways of performing image classification.</span></span> <span data-ttu-id="ca90b-127">Questa esercitazione applica l'apprendimento di trasferimento usando l'API di classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="ca90b-127">This tutorial applies transfer learning using the Image Classification API.</span></span> <span data-ttu-id="ca90b-128">L'API di classificazione delle immagini utilizza [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), una libreria di basso livello che fornisce le associazioni di C, per l'API TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="ca90b-128">The Image Classification API makes use of [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), a low-level library that provides C# bindings for the TensorFlow C++ API.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="ca90b-129">Che cos'è l'apprendimento trasferito?</span><span class="sxs-lookup"><span data-stu-id="ca90b-129">What is transfer learning?</span></span>

<span data-ttu-id="ca90b-130">L'apprendimento del trasferimento applica le conoscenze acquisite risolvendo un problema a un altro problema correlato.</span><span class="sxs-lookup"><span data-stu-id="ca90b-130">Transfer learning applies knowledge gained from solving one problem to another related problem.</span></span>

<span data-ttu-id="ca90b-131">Il training di un modello di deep learning da zero richiede l'impostazione di diversi parametri, una grande quantità di dati di training con etichetta e una grande quantità di risorse di calcolo (centinaia di ore GPU).</span><span class="sxs-lookup"><span data-stu-id="ca90b-131">Training a deep learning model from scratch requires setting several parameters, a large amount of labeled training data, and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="ca90b-132">L'utilizzo di un modello con training preliminare e l'apprendimento di trasferimento consente di eseguire il collegamento del processo di training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-132">Using a pretrained model along with transfer learning allows you to shortcut the training process.</span></span>

## <a name="training-process"></a><span data-ttu-id="ca90b-133">Processo di formazione</span><span class="sxs-lookup"><span data-stu-id="ca90b-133">Training process</span></span>

<span data-ttu-id="ca90b-134">L'API di classificazione delle immagini avvia il processo di training caricando un modello TensorFlow con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-134">The Image Classification API starts the training process by loading a pretrained TensorFlow model.</span></span> <span data-ttu-id="ca90b-135">Il processo di formazione si articola in due fasi:</span><span class="sxs-lookup"><span data-stu-id="ca90b-135">The training process consists of two steps:</span></span>

1. <span data-ttu-id="ca90b-136">Fase collo di bottiglia</span><span class="sxs-lookup"><span data-stu-id="ca90b-136">Bottleneck phase</span></span>
2. <span data-ttu-id="ca90b-137">Fase di formazione</span><span class="sxs-lookup"><span data-stu-id="ca90b-137">Training phase</span></span>

![Passaggi di formazione](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a><span data-ttu-id="ca90b-139">Fase collo di bottiglia</span><span class="sxs-lookup"><span data-stu-id="ca90b-139">Bottleneck phase</span></span>

<span data-ttu-id="ca90b-140">Durante la fase di collo di bottiglia, viene caricato il set di immagini di training e i valori dei pixel vengono utilizzati come input, o funzionalità, per i livelli congelati del modello con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-140">During the bottleneck phase, the set of training images is loaded and the pixel values are used as input, or features, for the frozen layers of the pretrained model.</span></span> <span data-ttu-id="ca90b-141">I livelli congelati includono tutti i livelli della rete neurale fino al penultimo strato, informalmente noto come strato di collo di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="ca90b-141">The frozen layers include all of the layers in the neural network up to the penultimate layer, informally known as the bottleneck layer.</span></span> <span data-ttu-id="ca90b-142">Questi layer vengono definiti congelati perché non verrà eseguito alcun addestramento su questi layer e le operazioni sono pass-through.</span><span class="sxs-lookup"><span data-stu-id="ca90b-142">These layers are referred to as frozen because no training will occur on these layers and operations are pass-through.</span></span> <span data-ttu-id="ca90b-143">Si trova a questi strati congelati dove vengono calcolati i modelli di livello inferiore che aiutano un modello a distinguere tra le diverse classi.</span><span class="sxs-lookup"><span data-stu-id="ca90b-143">It's at these frozen layers where the lower-level patterns that help a model differentiate between the different classes are computed.</span></span> <span data-ttu-id="ca90b-144">Maggiore è il numero di strati, più intenso è il calcolo di questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="ca90b-144">The larger the number of layers, the more computationally intensive this step is.</span></span> <span data-ttu-id="ca90b-145">Fortunatamente, poiché si tratta di un calcolo una tantera, i risultati possono essere memorizzati nella cache e utilizzati nelle esecuzioni successive durante la sperimentazione con parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="ca90b-145">Fortunately, since this is a one-time calculation, the results can be cached and used in later runs when experimenting with different parameters.</span></span>

### <a name="training-phase"></a><span data-ttu-id="ca90b-146">Fase di formazione</span><span class="sxs-lookup"><span data-stu-id="ca90b-146">Training phase</span></span>

<span data-ttu-id="ca90b-147">Una volta calcolati, i valori di output della fase di collo di bottiglia vengono utilizzati come input per riqualificare il livello finale del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-147">Once the output values from the bottleneck phase are computed, they are used as input to retrain the final layer of the model.</span></span> <span data-ttu-id="ca90b-148">Questo processo è iterativo e viene eseguito per il numero di volte specificato dai parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-148">This process is iterative and runs for the number of times specified by model parameters.</span></span> <span data-ttu-id="ca90b-149">Durante ogni corsa, la perdita e la precisione vengono valutate.</span><span class="sxs-lookup"><span data-stu-id="ca90b-149">During each run, the loss and accuracy are evaluated.</span></span> <span data-ttu-id="ca90b-150">Quindi, vengono apportate le regolazioni appropriate per migliorare il modello con l'obiettivo di ridurre al minimo la perdita e massimizzare la precisione.</span><span class="sxs-lookup"><span data-stu-id="ca90b-150">Then, the appropriate adjustments are made to improve the model with the goal of minimizing the loss and maximizing the accuracy.</span></span> <span data-ttu-id="ca90b-151">Al termine del training, vengono restituiti due formati di modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-151">Once training is finished, two model formats are output.</span></span> <span data-ttu-id="ca90b-152">Uno di essi `.pb` è la versione del `.zip` modello e l'altro è la versione serializzata ML.NET del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-152">One of them is the `.pb` version of the model and the other is the `.zip` ML.NET serialized version of the model.</span></span> <span data-ttu-id="ca90b-153">Quando si lavora in ambienti supportati da `.zip` ML.NET, si consiglia di utilizzare la versione del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-153">When working in environments supported by ML.NET, it is recommended to use the `.zip` version of the model.</span></span> <span data-ttu-id="ca90b-154">Tuttavia, in ambienti in cui ML.NET non è `.pb` supportato, è possibile utilizzare la versione.</span><span class="sxs-lookup"><span data-stu-id="ca90b-154">However, in environments where ML.NET is not supported, you have the option of using the `.pb` version.</span></span>

## <a name="understand-the-pretrained-model"></a><span data-ttu-id="ca90b-155">Comprendere il modello preformato</span><span class="sxs-lookup"><span data-stu-id="ca90b-155">Understand the pretrained model</span></span>

<span data-ttu-id="ca90b-156">Il modello preformato utilizzato in questa esercitazione è la variante a 101 livelli del modello Residual Network (ResNet) v2.</span><span class="sxs-lookup"><span data-stu-id="ca90b-156">The pretrained model used in this tutorial is the 101-layer variant of the Residual Network (ResNet) v2 model.</span></span> <span data-ttu-id="ca90b-157">Il modello originale viene addestrato per classificare le immagini in mille categorie.</span><span class="sxs-lookup"><span data-stu-id="ca90b-157">The original model is trained to classify images into a thousand categories.</span></span> <span data-ttu-id="ca90b-158">Il modello accetta come input un'immagine di dimensioni 224 x 224 e restituisce le probabilità di classe per ciascuna delle classi su cui è stato eseguito il training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-158">The model takes as input an image of size 224 x 224 and outputs the class probabilities for each of the classes it's trained on.</span></span> <span data-ttu-id="ca90b-159">Parte di questo modello viene usato per eseguire il training di un nuovo modello usando immagini personalizzate per eseguire stime tra due classi.</span><span class="sxs-lookup"><span data-stu-id="ca90b-159">Part of this model is used to train a new model using custom images to make predictions between two classes.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="ca90b-160">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="ca90b-160">Create console application</span></span>

<span data-ttu-id="ca90b-161">Ora che si ha una conoscenza generale dell'apprendimento dei trasferimenti e dell'API di classificazione delle immagini, è il momento di compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca90b-161">Now that you have a general understanding of transfer learning and the Image Classification API, it's time to build the application.</span></span>

1. <span data-ttu-id="ca90b-162">Creare **un'applicazione console di Core di C .NET** denominata "DeepLearning_ImageClassification_Binary".</span><span class="sxs-lookup"><span data-stu-id="ca90b-162">Create a **C# .NET Core Console Application** called "DeepLearning_ImageClassification_Binary".</span></span>
1. <span data-ttu-id="ca90b-163">Installare il pacchetto NuGet **di Microsoft.ML** versione **1.4.0:Install** the Microsoft.ML version 1.4.0 NuGet Package:</span><span class="sxs-lookup"><span data-stu-id="ca90b-163">Install the **Microsoft.ML** version **1.4.0** NuGet Package:</span></span>
    1. <span data-ttu-id="ca90b-164">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="ca90b-164">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="ca90b-165">Scegliere "nuget.org" come origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ca90b-165">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="ca90b-166">Selezionare la scheda **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="ca90b-166">Select the **Browse** tab.</span></span>
    1. <span data-ttu-id="ca90b-167">Selezionare la casella di **controllo Includi versione non definitiva.**</span><span class="sxs-lookup"><span data-stu-id="ca90b-167">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="ca90b-168">Cerca **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="ca90b-168">Search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="ca90b-169">Selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="ca90b-169">Select the **Install** button.</span></span>
    1. <span data-ttu-id="ca90b-170">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="ca90b-170">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="ca90b-171">Ripetere questi passaggi per i pacchetti **Microsoft.ML.Vision** **versione 1.4.0**, **SciSharp.TensorFlow.Redist** versione **1.15.0**e **Microsoft.ML.ImageAnalytics** versione **1.4.0** NuGet.</span><span class="sxs-lookup"><span data-stu-id="ca90b-171">Repeat these steps for the **Microsoft.ML.Vision** version **1.4.0**, **SciSharp.TensorFlow.Redist** version **1.15.0**, and **Microsoft.ML.ImageAnalytics** version **1.4.0** NuGet packages.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="ca90b-172">Preparare e identificare i dati</span><span class="sxs-lookup"><span data-stu-id="ca90b-172">Prepare and understand the data</span></span>

> [!NOTE]
> <span data-ttu-id="ca90b-173">I set di dati per questa esercitazione provengono da Maguire, Marc. Dorafshan, Sattar; e Thomas, Robert J., "SDNET2018: un set di dati di immagini crepa concreta per applicazioni di apprendimento automatico" (2018).</span><span class="sxs-lookup"><span data-stu-id="ca90b-173">The datasets for this tutorial are from Maguire, Marc; Dorafshan, Sattar; and Thomas, Robert J., "SDNET2018: A concrete crack image dataset for machine learning applications" (2018).</span></span> <span data-ttu-id="ca90b-174">Sfogliare tutti i set di dati.</span><span class="sxs-lookup"><span data-stu-id="ca90b-174">Browse all Datasets.</span></span> <span data-ttu-id="ca90b-175">Fascicolo 48.</span><span class="sxs-lookup"><span data-stu-id="ca90b-175">Paper 48.</span></span> <span data-ttu-id="ca90b-176">https://digitalcommons.usu.edu/all_datasets/48</span><span class="sxs-lookup"><span data-stu-id="ca90b-176">https://digitalcommons.usu.edu/all_datasets/48</span></span>

<span data-ttu-id="ca90b-177">SDNET2018 è un set di dati di immagini che contiene annotazioni per strutture in calcestruzzo incrinate e non (ponti, muri e pavimentazione).</span><span class="sxs-lookup"><span data-stu-id="ca90b-177">SDNET2018 is an image dataset that contains annotations for cracked and non-cracked concrete structures (bridge decks, walls, and pavement).</span></span>

![Esempi di bridge bridge di set di dati SDNET2018SDNET2018 dataset bridge deck samples](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

<span data-ttu-id="ca90b-179">I dati sono organizzati in tre sottodirectory:</span><span class="sxs-lookup"><span data-stu-id="ca90b-179">The data is organized in three subdirectories:</span></span>

- <span data-ttu-id="ca90b-180">D contiene immagini del ponte</span><span class="sxs-lookup"><span data-stu-id="ca90b-180">D contains bridge deck images</span></span>
- <span data-ttu-id="ca90b-181">P contiene immagini di pavimentazione</span><span class="sxs-lookup"><span data-stu-id="ca90b-181">P contains pavement images</span></span>
- <span data-ttu-id="ca90b-182">W contiene immagini a muro</span><span class="sxs-lookup"><span data-stu-id="ca90b-182">W contains wall images</span></span>

<span data-ttu-id="ca90b-183">Ognuna di queste sottodirectory contiene due sottodirectory con prefisso aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="ca90b-183">Each of these subdirectories contains two additional prefixed subdirectories:</span></span>

- <span data-ttu-id="ca90b-184">C è il prefisso utilizzato per le superfici incrinate</span><span class="sxs-lookup"><span data-stu-id="ca90b-184">C is the prefix used for cracked surfaces</span></span>
- <span data-ttu-id="ca90b-185">U è il prefisso utilizzato per le superfici non screpolate</span><span class="sxs-lookup"><span data-stu-id="ca90b-185">U is the prefix used for uncracked surfaces</span></span>

<span data-ttu-id="ca90b-186">In questa esercitazione vengono utilizzate solo le immagini del bridge.</span><span class="sxs-lookup"><span data-stu-id="ca90b-186">In this tutorial, only bridge deck images are used.</span></span>

1. <span data-ttu-id="ca90b-187">Scaricare il [set di dati](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) e decomprimere.</span><span class="sxs-lookup"><span data-stu-id="ca90b-187">Download the [dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) and unzip.</span></span>
1. <span data-ttu-id="ca90b-188">Creare una directory denominata "assets" nel progetto per salvare i file del dataset.</span><span class="sxs-lookup"><span data-stu-id="ca90b-188">Create a directory named "assets" in your project to save your dataset files.</span></span>
1. <span data-ttu-id="ca90b-189">Copiare le sottodirectory *CD* e *UD* dalla directory decompressa di recente nella directory *assets.*</span><span class="sxs-lookup"><span data-stu-id="ca90b-189">Copy the *CD* and *UD* subdirectories from the recently unzipped directory to the *assets* directory.</span></span>

### <a name="create-input-and-output-classes"></a><span data-ttu-id="ca90b-190">Creare classi di input e outputCreate input and output classes</span><span class="sxs-lookup"><span data-stu-id="ca90b-190">Create input and output classes</span></span>

1. <span data-ttu-id="ca90b-191">Aprire il file *Program.cs* `using` e sostituire le istruzioni esistenti all'inizio del file con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ca90b-191">Open the *Program.cs* file and replace the existing `using` statements at the top of the file with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. <span data-ttu-id="ca90b-192">Sotto `Program` la classe *di Program.cs* `ImageData`creare una classe denominata .</span><span class="sxs-lookup"><span data-stu-id="ca90b-192">Below the `Program` class in *Program.cs*, create a class called `ImageData`.</span></span> <span data-ttu-id="ca90b-193">Questa classe viene utilizzata per rappresentare i dati caricati inizialmente.</span><span class="sxs-lookup"><span data-stu-id="ca90b-193">This class is used to represent the initially loaded data.</span></span>

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L137-L142)]

    <span data-ttu-id="ca90b-194">`ImageData`contiene le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="ca90b-194">`ImageData` contains the following properties:</span></span>

    - <span data-ttu-id="ca90b-195">`ImagePath`è il percorso completo in cui è memorizzata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-195">`ImagePath` is the fully qualified path where the image is stored.</span></span>
    - <span data-ttu-id="ca90b-196">`Label`è la categoria a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-196">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="ca90b-197">Questo è il valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-197">This is the value to predict.</span></span>

1. <span data-ttu-id="ca90b-198">Creare classi per i dati di input e outputCreate classes for your input and output data</span><span class="sxs-lookup"><span data-stu-id="ca90b-198">Create classes for your input and output data</span></span>

    1. <span data-ttu-id="ca90b-199">Sotto `ImageData` la classe, definire lo schema dei dati `ModelInput`di input in una nuova classe denominata .</span><span class="sxs-lookup"><span data-stu-id="ca90b-199">Below the `ImageData` class, define the schema of your input data in a new class called `ModelInput`.</span></span>

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L144-L153)]

        <span data-ttu-id="ca90b-200">`ModelInput`contiene le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="ca90b-200">`ModelInput` contains the following properties:</span></span>

        - <span data-ttu-id="ca90b-201">`Image`è `byte[]` la rappresentazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-201">`Image` is the `byte[]` representation of the image.</span></span> <span data-ttu-id="ca90b-202">Il modello prevede che i dati immagine siano di questo tipo per il training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-202">The model expects image data to be of this type for training.</span></span>
        - <span data-ttu-id="ca90b-203">`LabelAsKey`è la rappresentazione `Label`numerica del file .</span><span class="sxs-lookup"><span data-stu-id="ca90b-203">`LabelAsKey` is the numerical representation of the `Label`.</span></span>
        - <span data-ttu-id="ca90b-204">`ImagePath`è il percorso completo in cui è memorizzata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-204">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="ca90b-205">`Label`è la categoria a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-205">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="ca90b-206">Questo è il valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-206">This is the value to predict.</span></span>

        <span data-ttu-id="ca90b-207">Solo `Image` `LabelAsKey` e vengono utilizzati per eseguire il training del modello ed eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="ca90b-207">Only `Image` and `LabelAsKey` are used to train the model and make predictions.</span></span> <span data-ttu-id="ca90b-208">Le `ImagePath` `Label` proprietà e vengono mantenute per comodità di accedere al nome e alla categoria del file di immagine originale.</span><span class="sxs-lookup"><span data-stu-id="ca90b-208">The `ImagePath` and `Label` properties are kept for convenience to access the original image file name and category.</span></span>

    1. <span data-ttu-id="ca90b-209">Quindi, sotto `ModelInput` la classe , definire lo schema dei `ModelOutput`dati di output in una nuova classe denominata .</span><span class="sxs-lookup"><span data-stu-id="ca90b-209">Then, below the `ModelInput` class, define the schema of your output data in a new class called `ModelOutput`.</span></span>

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L155-L162)]

        <span data-ttu-id="ca90b-210">`ModelOutput`contiene le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="ca90b-210">`ModelOutput` contains the following properties:</span></span>

        - <span data-ttu-id="ca90b-211">`ImagePath`è il percorso completo in cui è memorizzata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-211">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="ca90b-212">`Label`è la categoria originale a cui appartiene l'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-212">`Label` is the original category the image belongs to.</span></span> <span data-ttu-id="ca90b-213">Questo è il valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-213">This is the value to predict.</span></span>
        - <span data-ttu-id="ca90b-214">`PredictedLabel`è il valore previsto dal modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-214">`PredictedLabel` is the value predicted by the model.</span></span>

        <span data-ttu-id="ca90b-215">Simile `ModelInput`a , `PredictedLabel` solo l'oggetto è necessario per eseguire stime poiché contiene la stima effettuata dal modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-215">Similar to `ModelInput`, only the `PredictedLabel` is required to make predictions since it contains the prediction made by the model.</span></span> <span data-ttu-id="ca90b-216">Le `ImagePath` `Label` proprietà e vengono mantenute per comodità di accedere al nome e alla categoria del file di immagine originale.</span><span class="sxs-lookup"><span data-stu-id="ca90b-216">The `ImagePath` and `Label` properties are retained for convenience to access the original image file name and category.</span></span>

### <a name="create-workspace-directory"></a><span data-ttu-id="ca90b-217">Creare una directory dell'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="ca90b-217">Create workspace directory</span></span>

<span data-ttu-id="ca90b-218">Quando i dati di training e convalida non cambiano spesso, è consigliabile memorizzare nella cache i valori di collo di bottiglia calcolati per ulteriori esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="ca90b-218">When training and validation data do not change often, it is good practice to cache the computed bottleneck values for further runs.</span></span>

1. <span data-ttu-id="ca90b-219">Nel progetto creare una nuova directory denominata *workspace* per `.pb` archiviare i valori dei colli di bottiglia calcolati e la versione del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-219">In your project, create a new directory called *workspace* to store the computed bottleneck values and `.pb` version of the model.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="ca90b-220">Definire percorsi e inizializzare le variabiliDefine paths and initialize variables</span><span class="sxs-lookup"><span data-stu-id="ca90b-220">Define paths and initialize variables</span></span>

1. <span data-ttu-id="ca90b-221">All'interno del `Main` metodo, definire la posizione degli `.pb` asset, i valori di collo di bottiglia calcolati e la versione del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-221">Inside the `Main` method, define the location of your assets, computed bottleneck values and `.pb` version of the model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L17)]

1. <span data-ttu-id="ca90b-222">Inizializzare `mlContext` la variabile con una nuova istanza di [MLContext.](xref:Microsoft.ML.MLContext)</span><span class="sxs-lookup"><span data-stu-id="ca90b-222">Initialize the `mlContext` variable with a new instance of [MLContext](xref:Microsoft.ML.MLContext).</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L19)]

    <span data-ttu-id="ca90b-223">La classe [MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di mlContext crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-223">The [MLContext](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="ca90b-224">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ca90b-224">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="ca90b-225">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="ca90b-225">Load the data</span></span>

### <a name="create-data-loading-utility-method"></a><span data-ttu-id="ca90b-226">Creare il metodo di utilità di caricamento dei datiCreate data loading utility method</span><span class="sxs-lookup"><span data-stu-id="ca90b-226">Create data loading utility method</span></span>

<span data-ttu-id="ca90b-227">Le immagini sono memorizzate in due sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="ca90b-227">The images are stored in two subdirectories.</span></span> <span data-ttu-id="ca90b-228">Prima di caricare i dati, è necessario `ImageData` formattarli in un elenco di oggetti.</span><span class="sxs-lookup"><span data-stu-id="ca90b-228">Before loading the data, it needs to be formatted into a list of `ImageData` objects.</span></span> <span data-ttu-id="ca90b-229">A tale scopo, `LoadImagesFromDirectory` creare `Main` il metodo sotto il metodo .</span><span class="sxs-lookup"><span data-stu-id="ca90b-229">To do so, create the `LoadImagesFromDirectory` method below the `Main` method.</span></span>

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. <span data-ttu-id="ca90b-230">All'interno del `LoadImagesDirectory` codice aggiungere il codice seguente per ottenere tutti i percorsi dei file dalle sottodirectory:</span><span class="sxs-lookup"><span data-stu-id="ca90b-230">Inside the `LoadImagesDirectory` add the following code to get all of the file paths from the subdirectories:</span></span>

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L104-L105)]

1. <span data-ttu-id="ca90b-231">Quindi, scorrere ognuno dei `foreach` file utilizzando un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ca90b-231">Then, iterate through each of the files using a `foreach` statement.</span></span>

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. <span data-ttu-id="ca90b-232">All'interno dell'istruzione, `foreach` verificare che le estensioni dei file siano supportate.</span><span class="sxs-lookup"><span data-stu-id="ca90b-232">Inside the `foreach` statement, check that the file extensions are supported.</span></span> <span data-ttu-id="ca90b-233">L'API di classificazione delle immagini supporta i formati JPEG e PNG.</span><span class="sxs-lookup"><span data-stu-id="ca90b-233">The Image Classification API supports JPEG and PNG formats.</span></span>

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L109-L110)]

1. <span data-ttu-id="ca90b-234">Quindi, ottenere l'etichetta per il file.</span><span class="sxs-lookup"><span data-stu-id="ca90b-234">Then, get the label for the file.</span></span> <span data-ttu-id="ca90b-235">Se `useFolderNameAsLabel` il parametro `true`è impostato su , come etichetta viene utilizzata la directory padre in cui viene salvato il file.</span><span class="sxs-lookup"><span data-stu-id="ca90b-235">If the `useFolderNameAsLabel` parameter is set to `true`, then the parent directory where the file is saved is used as the label.</span></span> <span data-ttu-id="ca90b-236">In caso contrario, si prevede che l'etichetta sia un prefisso del nome del file o del nome del file stesso.</span><span class="sxs-lookup"><span data-stu-id="ca90b-236">Otherwise, it expects the label to be a prefix of the file name or the file name itself.</span></span>

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L112-L126)]

1. <span data-ttu-id="ca90b-237">Infine, creare una `ModelInput`nuova istanza di .</span><span class="sxs-lookup"><span data-stu-id="ca90b-237">Finally, create a new instance of `ModelInput`.</span></span>

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L128-L132)]

### <a name="prepare-the-data"></a><span data-ttu-id="ca90b-238">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="ca90b-238">Prepare the data</span></span>

1. <span data-ttu-id="ca90b-239">Nel `Main` metodo, utilizzare `LoadFromDirectory` il metodo di utilità per ottenere l'elenco delle immagini utilizzate per il training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-239">Back in the `Main` method, use the `LoadFromDirectory` utility method to get the list of images used for training.</span></span>

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L21)]

1. <span data-ttu-id="ca90b-240">Quindi, caricare le [`IDataView`](xref:Microsoft.ML.IDataView) immagini [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) in un utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="ca90b-240">Then, load the images into an [`IDataView`](xref:Microsoft.ML.IDataView) using the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method.</span></span>

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L23)]

1. <span data-ttu-id="ca90b-241">I dati vengono caricati nell'ordine in cui sono stati letti dalle directory.</span><span class="sxs-lookup"><span data-stu-id="ca90b-241">The data is loaded in the order it was read from the directories.</span></span> <span data-ttu-id="ca90b-242">Per bilanciare i dati, mischiali usando il [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) metodo .</span><span class="sxs-lookup"><span data-stu-id="ca90b-242">To balance the data, shuffle it using the [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) method.</span></span>

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L25)]

1. <span data-ttu-id="ca90b-243">I modelli di apprendimento automatico prevedono che l'input sia in formato numerico.</span><span class="sxs-lookup"><span data-stu-id="ca90b-243">Machine learning models expect input to be in numerical format.</span></span> <span data-ttu-id="ca90b-244">Pertanto, è necessario eseguire alcune pre-elaborazione sui dati prima del training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-244">Therefore, some preprocessing needs to be done on the data prior to training.</span></span> <span data-ttu-id="ca90b-245">Creare [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) un composto [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) di `LoadRawImageBytes` trasformazioni e .</span><span class="sxs-lookup"><span data-stu-id="ca90b-245">Create an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) made up of the [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) and `LoadRawImageBytes` transforms.</span></span> <span data-ttu-id="ca90b-246">La `MapValueToKey` trasformazione accetta il valore `Label` categorico nella colonna, `KeyType` lo converte in un `LabelAsKey`valore numerico e lo archivia in una nuova colonna denominata .</span><span class="sxs-lookup"><span data-stu-id="ca90b-246">The `MapValueToKey` transform takes the categorical value in the `Label` column, converts it to a numerical `KeyType` value and stores it in a new column called `LabelAsKey`.</span></span> <span data-ttu-id="ca90b-247">Accetta `LoadImages` i valori `ImagePath` dalla colonna `imageFolder` insieme al parametro per caricare le immagini per il training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-247">The `LoadImages` takes the values from the `ImagePath` column along with the `imageFolder` parameter to load images for training.</span></span>

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L27-L33)]

1. <span data-ttu-id="ca90b-248">Utilizzare [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) il metodo per applicare `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) i [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) dati a quelli [`IDataView`](xref:Microsoft.ML.IDataView) seguiti dal metodo , che restituisce un contenente i dati pre-elaborati.</span><span class="sxs-lookup"><span data-stu-id="ca90b-248">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to apply the data to the `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) followed by the [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) method, which returns an [`IDataView`](xref:Microsoft.ML.IDataView) containing the pre-processed data.</span></span>

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. <span data-ttu-id="ca90b-249">Per eseguire il training di un modello, è importante disporre di un set di dati di training e di un set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="ca90b-249">To train a model, it's important to have a training dataset as well as a validation dataset.</span></span> <span data-ttu-id="ca90b-250">Il modello viene eseguito il training sul set di training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-250">The model is trained on the training set.</span></span> <span data-ttu-id="ca90b-251">Il livello di ottimizzazione delle stime sui dati non visti viene misurato in base alle prestazioni rispetto al set di convalida.</span><span class="sxs-lookup"><span data-stu-id="ca90b-251">How well it makes predictions on unseen data is measured by the performance against the validation set.</span></span> <span data-ttu-id="ca90b-252">In base ai risultati di tali prestazioni, il modello apporta modifiche a ciò che ha appreso nel tentativo di migliorare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-252">Based on the results of that performance, the model makes adjustments to what it has learned in an effort to improve.</span></span> <span data-ttu-id="ca90b-253">Il set di convalida può derivare dalla suddivisione del set di dati originale o da un'altra origine che è già stata messa da parte per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="ca90b-253">The validation set can come from either splitting your original dataset or from another source that has already been set aside for this purpose.</span></span> <span data-ttu-id="ca90b-254">In questo caso, il set di dati pre-elaborato viene suddiviso in set di training, convalida e test.</span><span class="sxs-lookup"><span data-stu-id="ca90b-254">In this case, the pre-processed dataset is split into training, validation and test sets.</span></span>

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    <span data-ttu-id="ca90b-255">L'esempio di codice precedente esegue due divisioni.</span><span class="sxs-lookup"><span data-stu-id="ca90b-255">The code sample above performs two splits.</span></span> <span data-ttu-id="ca90b-256">In primo luogo, i dati pre-elaborati vengono suddivisi e il 70% viene utilizzato per il training mentre il restante 30% viene utilizzato per la convalida.</span><span class="sxs-lookup"><span data-stu-id="ca90b-256">First, the pre-processed data is split and 70% is used for training while the remaining 30% is used for validation.</span></span> <span data-ttu-id="ca90b-257">Quindi, il set di convalida 30% viene ulteriormente suddiviso in set di convalida e test in cui 90% viene utilizzato per la convalida e 10% viene utilizzato per il test.</span><span class="sxs-lookup"><span data-stu-id="ca90b-257">Then, the 30% validation set is further split into validation and test sets where 90% is used for validation and 10% is used for testing.</span></span>

    <span data-ttu-id="ca90b-258">Un modo per pensare allo scopo di queste partizioni di dati è sostenere un esame.</span><span class="sxs-lookup"><span data-stu-id="ca90b-258">A way to think about the purpose of these data partitions is taking an exam.</span></span> <span data-ttu-id="ca90b-259">Quando studi per un esame, rivedi le note, i libri o altre risorse per comprendere i concetti relativi all'esame.</span><span class="sxs-lookup"><span data-stu-id="ca90b-259">When studying for an exam, you review your notes, books, or other resources to get a grasp on the concepts that are on the exam.</span></span> <span data-ttu-id="ca90b-260">Questo è ciò che il treno è per.</span><span class="sxs-lookup"><span data-stu-id="ca90b-260">This is what the train set is for.</span></span> <span data-ttu-id="ca90b-261">Quindi, si potrebbe prendere un esame fittizio per convalidare le conoscenze.</span><span class="sxs-lookup"><span data-stu-id="ca90b-261">Then, you might take a mock exam to validate your knowledge.</span></span> <span data-ttu-id="ca90b-262">Questo è dove il set di convalida è utile.</span><span class="sxs-lookup"><span data-stu-id="ca90b-262">This is where the validation set comes in handy.</span></span> <span data-ttu-id="ca90b-263">Si desidera verificare se si dispone di una buona comprensione dei concetti prima di sostenere l'esame effettivo.</span><span class="sxs-lookup"><span data-stu-id="ca90b-263">You want to check whether you have a good grasp of the concepts before taking the actual exam.</span></span> <span data-ttu-id="ca90b-264">Sulla base di questi risultati, prendi nota di ciò che hai sbagliato o non hai capito bene e incorpora le modifiche mentre rivedi l'esame reale.</span><span class="sxs-lookup"><span data-stu-id="ca90b-264">Based on those results, you take note of what you got wrong or didn't understand well and incorporate your changes as you review for the real exam.</span></span> <span data-ttu-id="ca90b-265">Infine, fai l'esame.</span><span class="sxs-lookup"><span data-stu-id="ca90b-265">Finally, you take the exam.</span></span> <span data-ttu-id="ca90b-266">Questo è ciò per cui viene utilizzato il set di test.</span><span class="sxs-lookup"><span data-stu-id="ca90b-266">This is what the test set is used for.</span></span> <span data-ttu-id="ca90b-267">Non hai mai visto le domande che sono all'esame e ora usa ciò che hai imparato dalla formazione e dalla convalida per applicare le tue conoscenze al compito a portata di mano.</span><span class="sxs-lookup"><span data-stu-id="ca90b-267">You've never seen the questions that are on the exam and now use what you learned from training and validation to apply your knowledge to the task at hand.</span></span>

1. <span data-ttu-id="ca90b-268">Assegnare alle partizioni i rispettivi valori per i dati di training, convalida e test.</span><span class="sxs-lookup"><span data-stu-id="ca90b-268">Assign the partitions their respective values for the train, validation and test data.</span></span>

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a><span data-ttu-id="ca90b-269">Definire la pipeline di trainingDefine the training pipeline</span><span class="sxs-lookup"><span data-stu-id="ca90b-269">Define the training pipeline</span></span>

<span data-ttu-id="ca90b-270">L'addestramento del modello consiste in un paio di passaggi.</span><span class="sxs-lookup"><span data-stu-id="ca90b-270">Model training consists of a couple of steps.</span></span> <span data-ttu-id="ca90b-271">In primo luogo, l'API di classificazione delle immagini viene usata per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-271">First, Image Classification API is used to train the model.</span></span> <span data-ttu-id="ca90b-272">Quindi, le etichette `PredictedLabel` codificate nella colonna vengono riconvertite nel `MapKeyToValue` valore categorico originale utilizzando la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="ca90b-272">Then, the encoded labels in the `PredictedLabel` column are converted back to their original categorical value using the `MapKeyToValue` transform.</span></span>

1. <span data-ttu-id="ca90b-273">Creare una nuova variabile per archiviare un `ImageClassificationTrainer`set di parametri obbligatori e facoltativi per un oggetto .</span><span class="sxs-lookup"><span data-stu-id="ca90b-273">Create a new variable to store a set of required and optional parameters for an `ImageClassificationTrainer`.</span></span>

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L57)]

    <span data-ttu-id="ca90b-274">Un `ImageClassificationTrainer` accetta diversi parametri facoltativi:</span><span class="sxs-lookup"><span data-stu-id="ca90b-274">An `ImageClassificationTrainer` takes several optional parameters:</span></span>

    - <span data-ttu-id="ca90b-275">`FeatureColumnName`è la colonna utilizzata come input per il modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-275">`FeatureColumnName` is the column that is used as input for the model.</span></span>
    - <span data-ttu-id="ca90b-276">`LabelColumnName`è la colonna per il valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-276">`LabelColumnName` is the column for the value to predict.</span></span>
    - <span data-ttu-id="ca90b-277">`ValidationSet`è [`IDataView`](xref:Microsoft.ML.IDataView) l'oggetto contenente i dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="ca90b-277">`ValidationSet` is the [`IDataView`](xref:Microsoft.ML.IDataView) containing the validation data.</span></span>
    - <span data-ttu-id="ca90b-278">`Arch`definisce quale delle architetture di modelli pre-addestrati utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-278">`Arch` defines which of the pretrained model architectures to use.</span></span> <span data-ttu-id="ca90b-279">Questa esercitazione usa la variante a 101 livelli del modello ResNetv2.This tutorial uses the 101-layer variant of the ResNetv2 model.</span><span class="sxs-lookup"><span data-stu-id="ca90b-279">This tutorial uses the 101-layer variant of the ResNetv2 model.</span></span>
    - <span data-ttu-id="ca90b-280">`MetricsCallback`associa una funzione per tenere traccia dello stato di avanzamento durante l'allenamento.</span><span class="sxs-lookup"><span data-stu-id="ca90b-280">`MetricsCallback` binds a function to track the progress during training.</span></span>
    - <span data-ttu-id="ca90b-281">`TestOnTrainSet`indica al modello di misurare le prestazioni rispetto al set di training quando non è presente alcun set di convalida.</span><span class="sxs-lookup"><span data-stu-id="ca90b-281">`TestOnTrainSet` tells the model to measure performance against the training set when no validation set is present.</span></span>
    - <span data-ttu-id="ca90b-282">`ReuseTrainSetBottleneckCachedValues`indica al modello se utilizzare i valori memorizzati nella cache dalla fase di collo di bottiglia nelle esecuzioni successive.</span><span class="sxs-lookup"><span data-stu-id="ca90b-282">`ReuseTrainSetBottleneckCachedValues` tells the model whether to use the cached values from the bottleneck phase in subsequent runs.</span></span> <span data-ttu-id="ca90b-283">La fase di collo di bottiglia è un calcolo pass-through una tantera che richiede un utilizzo intensivo del calcolo alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ca90b-283">The bottleneck phase is a one-time pass-through computation that is computationally intensive the first time it is performed.</span></span> <span data-ttu-id="ca90b-284">Se i dati di training non cambiano e si vuole sperimentare usando un numero diverso di epoche o dimensioni del batch, l'uso dei valori memorizzati nella cache riduce in modo significativo la quantità di tempo necessaria per eseguire il training di un modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-284">If the training data does not change and you want to experiment using a different number of epochs or batch size, using the cached values significantly reduces the amount of time required to train a model.</span></span>
    - <span data-ttu-id="ca90b-285">`ReuseValidationSetBottleneckCachedValues`è simile `ReuseTrainSetBottleneckCachedValues` solo a quello che in questo caso è per il set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="ca90b-285">`ReuseValidationSetBottleneckCachedValues` is similar to `ReuseTrainSetBottleneckCachedValues` only that in this case it's for the validation dataset.</span></span>
    - <span data-ttu-id="ca90b-286">`WorkspacePath`definisce la directory in cui archiviare `.pb` i valori dei colli di bottiglia calcolati e la versione del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-286">`WorkspacePath` defines the directory where to store the computed bottleneck values and `.pb` version of the model.</span></span>

1. <span data-ttu-id="ca90b-287">Definire [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) la pipeline di training `mapLabelEstimator` costituita sia da e . `ImageClassificationTrainer`</span><span class="sxs-lookup"><span data-stu-id="ca90b-287">Define the [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) training pipeline that consists of both the `mapLabelEstimator` and the `ImageClassificationTrainer`.</span></span>

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L59-L60)]

1. <span data-ttu-id="ca90b-288">Usare [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) il metodo per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-288">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to train your model.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

## <a name="use-the-model"></a><span data-ttu-id="ca90b-289">Usare il modello</span><span class="sxs-lookup"><span data-stu-id="ca90b-289">Use the model</span></span>

<span data-ttu-id="ca90b-290">Dopo aver eseguito il training del modello, è necessario usarlo per classificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="ca90b-290">Now that you have trained your model, it's time to use it to classify images.</span></span>

<span data-ttu-id="ca90b-291">Sotto `Main` il metodo, creare un `OutputPrediction` nuovo metodo di utilità chiamato per visualizzare le informazioni di stima nella console.</span><span class="sxs-lookup"><span data-stu-id="ca90b-291">Below the `Main` method, create a new utility method called `OutputPrediction` to display prediction information in the console.</span></span>

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L96-L100)]

### <a name="classify-a-single-image"></a><span data-ttu-id="ca90b-292">Classificare una singola immagine</span><span class="sxs-lookup"><span data-stu-id="ca90b-292">Classify a single image</span></span>

1. <span data-ttu-id="ca90b-293">Aggiungere un nuovo `ClassifySingleImage` metodo `Main` chiamato sotto il metodo per eseguire e restituire una singola stima dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-293">Add a new method called `ClassifySingleImage` below the `Main` method to make and output a single image prediction.</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="ca90b-294">Creare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) un `ClassifySingleImage` all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="ca90b-294">Create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) inside the `ClassifySingleImage` method.</span></span> <span data-ttu-id="ca90b-295">Si [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) tratta di un'API di convenienza, che consente di passare e quindi eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="ca90b-295">The [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. <span data-ttu-id="ca90b-296">Per accedere `ModelInput` a una `data` [`IDataView`](xref:Microsoft.ML.IDataView) singola [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) istanza, [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) convertire l'oggetto in un utilizzando il metodo e quindi ottenere la prima osservazione.</span><span class="sxs-lookup"><span data-stu-id="ca90b-296">To access a single `ModelInput` instance, convert the `data` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first observation.</span></span>

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. <span data-ttu-id="ca90b-297">Utilizzare [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) il metodo per classificare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-297">Use the [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) method to classify the image.</span></span>

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77)]

1. <span data-ttu-id="ca90b-298">Eseguire l'output della `OutputPrediction` stima nella console con il metodo .</span><span class="sxs-lookup"><span data-stu-id="ca90b-298">Output the prediction to the console with the `OutputPrediction` method.</span></span>

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L79-L80)]

1. <span data-ttu-id="ca90b-299">All'interno `Main` del `ClassifySingleImage` metodo, chiamare utilizzando il set di test di immagini.</span><span class="sxs-lookup"><span data-stu-id="ca90b-299">Inside the `Main` method, call `ClassifySingleImage` using the test set of images.</span></span>

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

### <a name="classify-multiple-images"></a><span data-ttu-id="ca90b-300">Classificare più immagini</span><span class="sxs-lookup"><span data-stu-id="ca90b-300">Classify multiple images</span></span>

1. <span data-ttu-id="ca90b-301">Aggiungere un nuovo `ClassifyImages` metodo `ClassifySingleImage` chiamato sotto il metodo per eseguire ed eseguire più stime di immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-301">Add a new method called `ClassifyImages` below the `ClassifySingleImage` method to make and output multiple image predictions.</span></span>

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="ca90b-302">Creare [`IDataView`](xref:Microsoft.ML.IDataView) un contenente le stime utilizzando il [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) metodo .</span><span class="sxs-lookup"><span data-stu-id="ca90b-302">Create an [`IDataView`](xref:Microsoft.ML.IDataView) containing the predictions by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method.</span></span> <span data-ttu-id="ca90b-303">Aggiungere il codice seguente all'interno del metodo `ClassifyImages`.</span><span class="sxs-lookup"><span data-stu-id="ca90b-303">Add the following code inside the `ClassifyImages` method.</span></span>

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. <span data-ttu-id="ca90b-304">Per scorrere le stime, convertire `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) il [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) in [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) un utilizzando il metodo e quindi ottenere le prime 10 osservazioni.</span><span class="sxs-lookup"><span data-stu-id="ca90b-304">In order to iterate over the predictions, convert the `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first 10 observations.</span></span>

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87)]

1. <span data-ttu-id="ca90b-305">Iterare ed eseguire l'output delle etichette originali e stimate per le stime.</span><span class="sxs-lookup"><span data-stu-id="ca90b-305">Iterate and output the original and predicted labels for the predictions.</span></span>

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L89-L93)]

1. <span data-ttu-id="ca90b-306">Infine, all'interno `Main` `ClassifyImages` del metodo, chiamare utilizzando il set di test di immagini.</span><span class="sxs-lookup"><span data-stu-id="ca90b-306">Finally, inside the `Main` method, call `ClassifyImages` using the test set of images.</span></span>

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L66)]

## <a name="run-the-application"></a><span data-ttu-id="ca90b-307">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="ca90b-307">Run the application</span></span>

<span data-ttu-id="ca90b-308">Eseguire l'app console.</span><span class="sxs-lookup"><span data-stu-id="ca90b-308">Run your console app.</span></span> <span data-ttu-id="ca90b-309">L'output dovrebbe essere simile a quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ca90b-309">The output should be similar to that below.</span></span> <span data-ttu-id="ca90b-310">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="ca90b-310">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span> <span data-ttu-id="ca90b-311">Per brevità, l'output è stato condensato.</span><span class="sxs-lookup"><span data-stu-id="ca90b-311">For brevity, the output has been condensed.</span></span>

<span data-ttu-id="ca90b-312">**Fase collo di bottiglia**</span><span class="sxs-lookup"><span data-stu-id="ca90b-312">**Bottleneck phase**</span></span>

<span data-ttu-id="ca90b-313">Non viene stampato alcun valore per il nome `byte[]` dell'immagine perché le immagini vengono caricate in modo tale da non visualizzare alcun nome di immagine.</span><span class="sxs-lookup"><span data-stu-id="ca90b-313">No value is printed for the image name because the images are loaded as a `byte[]` therefore there is no image name to display.</span></span>

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

<span data-ttu-id="ca90b-314">**Fase di formazione**</span><span class="sxs-lookup"><span data-stu-id="ca90b-314">**Training phase**</span></span>

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

<span data-ttu-id="ca90b-315">**Classificare l'output delle immagini**</span><span class="sxs-lookup"><span data-stu-id="ca90b-315">**Classify images output**</span></span>

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

<span data-ttu-id="ca90b-316">Dopo l'ispezione dell'immagine *7001-220.jpg,* si può vedere che in realtà non è incrinato.</span><span class="sxs-lookup"><span data-stu-id="ca90b-316">Upon inspection of the *7001-220.jpg* image, you can see that it in fact is not cracked.</span></span>

![Immagine del set di dati SDNET2018 usata per la stimaSDNET2018 dataset image used for prediction](./media/image-classification-api-transfer-learning/predictedimage.jpg)

<span data-ttu-id="ca90b-318">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="ca90b-318">Congratulations!</span></span> <span data-ttu-id="ca90b-319">Ora hai creato con successo un modello di deep learning per classificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="ca90b-319">You've now successfully built a deep learning model for classifying images.</span></span>

### <a name="improve-the-model"></a><span data-ttu-id="ca90b-320">Migliorare il modello</span><span class="sxs-lookup"><span data-stu-id="ca90b-320">Improve the model</span></span>

<span data-ttu-id="ca90b-321">Se non si è soddisfatti dei risultati del modello, è possibile provare a migliorarne le prestazioni provando alcuni degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca90b-321">If you're not satisfied with the results of your model, you can try to improve its performance by trying some of the following approaches:</span></span>

- <span data-ttu-id="ca90b-322">**Più dati**: più esempi apprende un modello, meglio si comporta.</span><span class="sxs-lookup"><span data-stu-id="ca90b-322">**More Data**: The more examples a model learns from, the better it performs.</span></span> <span data-ttu-id="ca90b-323">Scaricare il [set di dati SDNET2018](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) completo e usarlo per il training.</span><span class="sxs-lookup"><span data-stu-id="ca90b-323">Download the full [SDNET2018 dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) and use it to train.</span></span>
- <span data-ttu-id="ca90b-324">**Aumentare i dati**: Una tecnica comune per aggiungere varietà ai dati è quello di aumentare i dati prendendo un'immagine e applicando diverse trasformazioni (ruotare, capovolgere, spostare, ritagliare).</span><span class="sxs-lookup"><span data-stu-id="ca90b-324">**Augment the data**: A common technique to add variety to the data is to augment the data by taking an image and applying different transforms (rotate, flip, shift, crop).</span></span> <span data-ttu-id="ca90b-325">Questo aggiunge esempi più diversi per il modello da cui imparare.</span><span class="sxs-lookup"><span data-stu-id="ca90b-325">This adds more varied examples for the model to learn from.</span></span>
- <span data-ttu-id="ca90b-326">**Allenati per un tempo più lungo**: Più a lungo ti alleni, più il modello sarà sintonizzato.</span><span class="sxs-lookup"><span data-stu-id="ca90b-326">**Train for a longer time**: The longer you train, the more tuned the model will be.</span></span> <span data-ttu-id="ca90b-327">L'aumento del numero di epoche può migliorare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="ca90b-327">Increasing the number of epochs may improve the performance of your model.</span></span>
- <span data-ttu-id="ca90b-328">**Sperimentare con gli iperparametri**: Oltre ai parametri utilizzati in questa esercitazione, altri parametri possono essere sintonizzati per migliorare potenzialmente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ca90b-328">**Experiment with the hyper-parameters**: In addition to the parameters used in this tutorial, other parameters can be tuned to potentially improve performance.</span></span> <span data-ttu-id="ca90b-329">La modifica della velocità di apprendimento, che determina l'entità degli aggiornamenti apportati al modello dopo ogni epoca può migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ca90b-329">Changing the learning rate, which determines the magnitude of updates made to the model after each epoch may improve performance.</span></span>
- <span data-ttu-id="ca90b-330">**Usare un'architettura**del modello diversa: a seconda dell'aspetto dei dati, il modello che meglio è in grado di apprendere le funzionalità potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="ca90b-330">**Use a different model architecture**: Depending on what your data looks like, the model that can best learn its features may differ.</span></span> <span data-ttu-id="ca90b-331">Se non si è soddisfatti delle prestazioni del modello, provare a modificare l'architettura.</span><span class="sxs-lookup"><span data-stu-id="ca90b-331">If you're not satisfied with the performance of your model, try changing the architecture.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ca90b-332">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ca90b-332">Additional Resources</span></span>

- <span data-ttu-id="ca90b-333">[Deep Learning vs Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="ca90b-333">[Deep Learning vs Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca90b-334">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ca90b-334">Next steps</span></span>

<span data-ttu-id="ca90b-335">In questa esercitazione è stato illustrato come creare un modello di deep learning personalizzato usando l'apprendimento tramite trasferimento, un modello TensorFlow di classificazione delle immagini con training preliminare e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non crittografate.</span><span class="sxs-lookup"><span data-stu-id="ca90b-335">In this tutorial, you learned how to build a custom deep learning model using transfer learning, a pretrained image classification TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="ca90b-336">Passare all'esercitazione successiva per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="ca90b-336">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ca90b-337">Rilevamento di oggetti</span><span class="sxs-lookup"><span data-stu-id="ca90b-337">Object Detection</span></span>](object-detection-onnx.md)
