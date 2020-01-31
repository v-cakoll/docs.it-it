---
title: 'Esercitazione: rilevare oggetti tramite Deep Learning con ONNX e ML.NET'
description: Questa esercitazione illustra come usare un modello di Deep Learning ONNX già sottoposto a training in ML.NET per rilevare gli oggetti nelle immagini.
author: luisquintanilla
ms.author: luquinta
ms.date: 12/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 6aaf5acc605067f378ff5d42f713fe1c63d91e46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794631"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a><span data-ttu-id="01beb-103">Esercitazione: rilevare oggetti con ONNX in ML.NET</span><span class="sxs-lookup"><span data-stu-id="01beb-103">Tutorial: Detect objects using ONNX in ML.NET</span></span>

<span data-ttu-id="01beb-104">Informazioni su come usare un modello ONNX già sottoposto a training in ML.NET per rilevare gli oggetti nelle immagini.</span><span class="sxs-lookup"><span data-stu-id="01beb-104">Learn how to use a pre-trained ONNX model in ML.NET to detect objects in images.</span></span>

<span data-ttu-id="01beb-105">Il training di un modello di rilevamento degli oggetti da zero richiede l'impostazione di milioni di parametri, numerosi dati di training con etichetta e una notevole quantità di risorse di calcolo (centinaia di ore di GPU).</span><span class="sxs-lookup"><span data-stu-id="01beb-105">Training an object detection model from scratch requires setting millions of parameters, a large amount of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="01beb-106">L'uso di un modello già sottoposto a training consente di abbreviare il processo di training.</span><span class="sxs-lookup"><span data-stu-id="01beb-106">Using a pre-trained model allows you to shortcut the training process.</span></span>

<span data-ttu-id="01beb-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="01beb-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="01beb-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="01beb-108">Understand the problem</span></span>
> - <span data-ttu-id="01beb-109">Acquisire familiarità con ONNX e comprenderne il funzionamento con ML.NET</span><span class="sxs-lookup"><span data-stu-id="01beb-109">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="01beb-110">Acquisire familiarità con il modello</span><span class="sxs-lookup"><span data-stu-id="01beb-110">Understand the model</span></span>
> - <span data-ttu-id="01beb-111">Riutilizzare il modello già sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="01beb-111">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="01beb-112">Rilevare oggetti con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="01beb-112">Detect objects with a loaded model</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="01beb-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="01beb-113">Pre-requisites</span></span>

- <span data-ttu-id="01beb-114">[Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="01beb-114">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- [<span data-ttu-id="01beb-115">Pacchetto NuGet Microsoft.ML</span><span class="sxs-lookup"><span data-stu-id="01beb-115">Microsoft.ML NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML/)
- [<span data-ttu-id="01beb-116">Pacchetto NuGet Microsoft.ML.ImageAnalytics</span><span class="sxs-lookup"><span data-stu-id="01beb-116">Microsoft.ML.ImageAnalytics NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [<span data-ttu-id="01beb-117">Pacchetto NuGet Microsoft.ML.OnnxTransformer</span><span class="sxs-lookup"><span data-stu-id="01beb-117">Microsoft.ML.OnnxTransformer NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [<span data-ttu-id="01beb-118">Modello Tiny YOLOv2 già sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="01beb-118">Tiny YOLOv2 pre-trained model</span></span>](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2)
- <span data-ttu-id="01beb-119">[Netron](https://github.com/lutzroeder/netron) (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="01beb-119">[Netron](https://github.com/lutzroeder/netron) (optional)</span></span>

## <a name="onnx-object-detection-sample-overview"></a><span data-ttu-id="01beb-120">Panoramica dell'esempio di rilevamento degli oggetti ONNX</span><span class="sxs-lookup"><span data-stu-id="01beb-120">ONNX object detection sample overview</span></span>

<span data-ttu-id="01beb-121">Questo esempio crea un'applicazione console .NET Core che rileva gli oggetti all'interno di un'immagine usando un modello ONNX di Deep Learning già sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="01beb-121">This sample creates a .NET core console application that detects objects within an image using a pre-trained deep learning ONNX model.</span></span> <span data-ttu-id="01beb-122">Il codice per questo esempio è disponibile nel [repository dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="01beb-122">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) on GitHub.</span></span>

## <a name="what-is-object-detection"></a><span data-ttu-id="01beb-123">Che cos'è il rilevamento degli oggetti?</span><span class="sxs-lookup"><span data-stu-id="01beb-123">What is object detection?</span></span>

<span data-ttu-id="01beb-124">Il rilevamento degli oggetti è una questione correlata alla visione artificiale.</span><span class="sxs-lookup"><span data-stu-id="01beb-124">Object detection is a computer vision problem.</span></span> <span data-ttu-id="01beb-125">Sebbene sia un concetto strettamente correlato alla classificazione delle immagini, il rilevamento degli oggetti esegue l'operazione di classificazione delle immagini su scala più granulare.</span><span class="sxs-lookup"><span data-stu-id="01beb-125">While closely related to image classification, object detection performs image classification at a more granular scale.</span></span> <span data-ttu-id="01beb-126">Il rilevamento degli oggetti individua _e_ classifica le entità all'interno delle immagini.</span><span class="sxs-lookup"><span data-stu-id="01beb-126">Object detection both locates _and_ categorizes entities within images.</span></span> <span data-ttu-id="01beb-127">Usare il rilevamento degli oggetti quando le immagini contengono più oggetti di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="01beb-127">Use object detection when images contain multiple objects of different types.</span></span>

![Schermate che mostrano la classificazione delle immagini rispetto alla classificazione degli oggetti.](./media/object-detection-onnx/img-classification-obj-detection.png)

<span data-ttu-id="01beb-129">Ecco alcuni casi d'uso per il rilevamento degli oggetti:</span><span class="sxs-lookup"><span data-stu-id="01beb-129">Some use cases for object detection include:</span></span>

- <span data-ttu-id="01beb-130">Auto senza guidatore</span><span class="sxs-lookup"><span data-stu-id="01beb-130">Self-Driving Cars</span></span>
- <span data-ttu-id="01beb-131">Robotica</span><span class="sxs-lookup"><span data-stu-id="01beb-131">Robotics</span></span>
- <span data-ttu-id="01beb-132">Rilevamento viso</span><span class="sxs-lookup"><span data-stu-id="01beb-132">Face Detection</span></span>
- <span data-ttu-id="01beb-133">Sicurezza nell'ambiente di lavoro</span><span class="sxs-lookup"><span data-stu-id="01beb-133">Workplace Safety</span></span>
- <span data-ttu-id="01beb-134">Conteggio di oggetti</span><span class="sxs-lookup"><span data-stu-id="01beb-134">Object Counting</span></span>
- <span data-ttu-id="01beb-135">Riconoscimento di attività</span><span class="sxs-lookup"><span data-stu-id="01beb-135">Activity Recognition</span></span>

## <a name="select-a-deep-learning-model"></a><span data-ttu-id="01beb-136">Selezionare un modello di Deep Learning</span><span class="sxs-lookup"><span data-stu-id="01beb-136">Select a deep learning model</span></span>

<span data-ttu-id="01beb-137">Il Deep Learning è un subset del Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="01beb-137">Deep learning is a subset of machine learning.</span></span> <span data-ttu-id="01beb-138">Per eseguire il training di modelli di Deep Learning, sono necessarie grandi quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="01beb-138">To train deep learning models, large quantities of data are required.</span></span> <span data-ttu-id="01beb-139">I modelli nei dati sono rappresentati da una serie di livelli.</span><span class="sxs-lookup"><span data-stu-id="01beb-139">Patterns in the data are represented by a series of layers.</span></span> <span data-ttu-id="01beb-140">Le relazioni nei dati sono codificate come connessioni tra i livelli contenenti pesi.</span><span class="sxs-lookup"><span data-stu-id="01beb-140">The relationships in the data are encoded as connections between the layers containing weights.</span></span> <span data-ttu-id="01beb-141">Maggiore è il peso, più forte è la relazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-141">The higher the weight, the stronger the relationship.</span></span> <span data-ttu-id="01beb-142">Collettivamente, questa serie di livelli e connessioni è nota come rete neurale artificiale.</span><span class="sxs-lookup"><span data-stu-id="01beb-142">Collectively, this series of layers and connections are known as artificial neural networks.</span></span> <span data-ttu-id="01beb-143">Maggiore è il numero di livelli in una rete, più "profonda" è la rete, che diventa una rete neurale profonda.</span><span class="sxs-lookup"><span data-stu-id="01beb-143">The more layers in a network, the "deeper" it is, making it a deep neural network.</span></span>

<span data-ttu-id="01beb-144">Ci sono diversi tipi di reti neurali, tra cui i più comuni sono percettrone multistrato (MLP, Multi-Layered Perceptron), rete neurale convoluzionale (CNN, Convolutional Neural Network) e rete neurale ricorrente (RNN, Recurrent Neural Network).</span><span class="sxs-lookup"><span data-stu-id="01beb-144">There are different types of neural networks, the most common being Multi-Layered Perceptron (MLP), Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN).</span></span> <span data-ttu-id="01beb-145">Il tipo più semplice è MLP, che esegue il mapping di un set di input a un set di output.</span><span class="sxs-lookup"><span data-stu-id="01beb-145">The most basic is the MLP, which maps a set of inputs to a set of outputs.</span></span> <span data-ttu-id="01beb-146">Questa rete neurale è efficace quando i dati non hanno una componente spaziale o temporale.</span><span class="sxs-lookup"><span data-stu-id="01beb-146">This neural network is good when the data does not have a spatial or time component.</span></span> <span data-ttu-id="01beb-147">La rete CNN usa i livelli convoluzionali per elaborare le informazioni spaziali contenute nei dati.</span><span class="sxs-lookup"><span data-stu-id="01beb-147">The CNN makes use of convolutional layers to process spatial information contained in the data.</span></span> <span data-ttu-id="01beb-148">Un buon caso d'uso per le reti CNN è l'elaborazione di immagini per rilevare la presenza di una caratteristica in un'area di un'immagine (ad esempio, è presente un naso al centro di un'immagine?).</span><span class="sxs-lookup"><span data-stu-id="01beb-148">A good use case for CNNs is image processing to detect the presence of a feature in a region of an image (for example, is there a nose in the center of an image?).</span></span> <span data-ttu-id="01beb-149">Infine, le reti RNN consentono di usare come input la persistenza dello stato o della memoria.</span><span class="sxs-lookup"><span data-stu-id="01beb-149">Finally, RNNs allow for the persistence of state or memory to be used as input.</span></span> <span data-ttu-id="01beb-150">Le reti RNN vengono usate per l'analisi delle serie temporali, in cui l'ordinamento sequenziale e il contesto degli eventi sono importanti.</span><span class="sxs-lookup"><span data-stu-id="01beb-150">RNNs are used for time-series analysis, where the sequential ordering and context of events is important.</span></span>

### <a name="understand-the-model"></a><span data-ttu-id="01beb-151">Acquisire familiarità con il modello</span><span class="sxs-lookup"><span data-stu-id="01beb-151">Understand the model</span></span>

<span data-ttu-id="01beb-152">Il rilevamento di oggetti è un'attività di elaborazione di immagini.</span><span class="sxs-lookup"><span data-stu-id="01beb-152">Object detection is an image-processing task.</span></span> <span data-ttu-id="01beb-153">Per questo motivo, i modelli di Deep Learning sottoposti a training per risolvere questo problema sono prevalentemente di tipo CNN.</span><span class="sxs-lookup"><span data-stu-id="01beb-153">Therefore, most deep learning models trained to solve this problem are CNNs.</span></span> <span data-ttu-id="01beb-154">Il modello usato in questa esercitazione è il piccolo modello YOLOv2, una versione più compatta del modello YOLOv2 descritto nel documento ["YOLO9000: migliore, più veloce, più forte" di Redmon e Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span><span class="sxs-lookup"><span data-stu-id="01beb-154">The model used in this tutorial is the Tiny YOLOv2 model, a more compact version of the YOLOv2 model described in the paper: ["YOLO9000: Better, Faster, Stronger" by Redmon and Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span></span> <span data-ttu-id="01beb-155">Il training di Tiny YOLOv2 viene eseguito sul set di dati Pascal VOC ed è costituito da 15 livelli in grado di eseguire stime per 20 diverse classi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="01beb-155">Tiny YOLOv2 is trained on the Pascal VOC dataset and is made up of 15 layers that can predict 20 different classes of objects.</span></span> <span data-ttu-id="01beb-156">Poiché il modello Tiny YOLOv2 è una versione ridotta del modello YOLOv2 originale, rappresenta un compromesso tra velocità e accuratezza.</span><span class="sxs-lookup"><span data-stu-id="01beb-156">Because Tiny YOLOv2 is a condensed version of the original YOLOv2 model, a tradeoff is made between speed and accuracy.</span></span> <span data-ttu-id="01beb-157">I diversi livelli che compongono il modello possono essere visualizzati usando strumenti come Netron.</span><span class="sxs-lookup"><span data-stu-id="01beb-157">The different layers that make up the model can be visualized using tools like Netron.</span></span> <span data-ttu-id="01beb-158">L'esame del modello restituirebbe un mapping delle connessioni tra tutti i livelli che compongono la rete neurale, in cui ogni livello contiene il nome del livello insieme alle dimensioni del rispettivo input/output.</span><span class="sxs-lookup"><span data-stu-id="01beb-158">Inspecting the model would yield a mapping of the connections between all the layers that make up the neural network, where each layer would contain the name of the layer along with the dimensions of the respective input / output.</span></span> <span data-ttu-id="01beb-159">Le strutture di dati usate per descrivere gli input e gli output del modello sono note come tensori.</span><span class="sxs-lookup"><span data-stu-id="01beb-159">The data structures used to describe the inputs and outputs of the model are known as tensors.</span></span> <span data-ttu-id="01beb-160">I tensori possono essere considerati contenitori che archiviano i dati in N dimensioni.</span><span class="sxs-lookup"><span data-stu-id="01beb-160">Tensors can be thought of as containers that store data in N-dimensions.</span></span> <span data-ttu-id="01beb-161">Nel caso di Tiny YOLOv2, il nome del livello di input è `image` e prevede un tensore con dimensioni `3 x 416 x 416`.</span><span class="sxs-lookup"><span data-stu-id="01beb-161">In the case of Tiny YOLOv2, the name of the input layer is `image` and it expects a tensor of dimensions `3 x 416 x 416`.</span></span> <span data-ttu-id="01beb-162">Il nome del livello di output è `grid` e genera un tensore di output con dimensioni `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="01beb-162">The name of the output layer is `grid` and generates an output tensor of dimensions `125 x 13 x 13`.</span></span>

![Livello di input suddiviso in livelli nascosti, quindi livello di output](./media/object-detection-onnx/netron-model-map-layers.png)

<span data-ttu-id="01beb-164">Il modello YOLO accetta un'immagine `3(RGB) x 416px x 416px`.</span><span class="sxs-lookup"><span data-stu-id="01beb-164">The YOLO model takes an image `3(RGB) x 416px x 416px`.</span></span> <span data-ttu-id="01beb-165">Il modello accetta questo input e lo passa attraverso i diversi livelli per produrre un output.</span><span class="sxs-lookup"><span data-stu-id="01beb-165">The model takes this input and passes it through the different layers to produce an output.</span></span> <span data-ttu-id="01beb-166">L'output divide l'immagine di input in una griglia `13 x 13`, con ogni cella della griglia costituita da `125` valori.</span><span class="sxs-lookup"><span data-stu-id="01beb-166">The output divides the input image into a `13 x 13` grid, with each cell in the grid consisting of `125` values.</span></span>

### <a name="what-is-an-onnx-model"></a><span data-ttu-id="01beb-167">Che cos'è un modello ONNX?</span><span class="sxs-lookup"><span data-stu-id="01beb-167">What is an ONNX model?</span></span>

<span data-ttu-id="01beb-168">Open Neural Network Exchange (ONNX) è un formato open source per i modelli di intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="01beb-168">The Open Neural Network Exchange (ONNX) is an open source format for AI models.</span></span> <span data-ttu-id="01beb-169">ONNX supporta l'interoperabilità tra framework.</span><span class="sxs-lookup"><span data-stu-id="01beb-169">ONNX supports interoperability between frameworks.</span></span> <span data-ttu-id="01beb-170">Ciò significa che è possibile eseguire il training di un modello in uno dei numerosi framework di apprendimento automatico diffusi, ad esempio PyTorch, eseguire la conversione in formato ONNX e utilizzare il modello ONNX in un framework diverso, come ML.NET.</span><span class="sxs-lookup"><span data-stu-id="01beb-170">This means you can train a model in one of the many popular machine learning frameworks like PyTorch, convert it into ONNX format and consume the ONNX model in a different framework like ML.NET.</span></span> <span data-ttu-id="01beb-171">Per altre informazioni, vedere il [sito Web ONNX](https://onnx.ai/).</span><span class="sxs-lookup"><span data-stu-id="01beb-171">To learn more, visit the [ONNX website](https://onnx.ai/).</span></span>

![Diagramma dei formati supportati da ONNX in uso.](./media/object-detection-onnx/onnx-supported-formats.png)

<span data-ttu-id="01beb-173">Il modello Tiny YOLOv2 già sottoposto a training è archiviato in formato ONNX, una rappresentazione serializzata dei livelli e dei modelli appresi di tali livelli.</span><span class="sxs-lookup"><span data-stu-id="01beb-173">The pre-trained Tiny YOLOv2 model is stored in ONNX format, a serialized representation of the layers and learned patterns of those layers.</span></span> <span data-ttu-id="01beb-174">In ML.NET, l'interoperabilità con ONNX viene raggiunta con i pacchetti NuGet [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) e [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer).</span><span class="sxs-lookup"><span data-stu-id="01beb-174">In ML.NET, interoperability with ONNX is achieved with the [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) and [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) NuGet packages.</span></span> <span data-ttu-id="01beb-175">Il pacchetto [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) contiene una serie di trasformazioni che accettano un'immagine e la codificano in valori numerici che possono essere usati come input in una pipeline di stima o di training.</span><span class="sxs-lookup"><span data-stu-id="01beb-175">The [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) package contains a series of transforms that take an image and encode it into numerical values that can be used as input into a prediction or training pipeline.</span></span> <span data-ttu-id="01beb-176">Il pacchetto [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) sfrutta il runtime ONNX per caricare un modello ONNX e usarlo per eseguire stime basate sull'input fornito.</span><span class="sxs-lookup"><span data-stu-id="01beb-176">The [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) package leverages the ONNX Runtime to load an ONNX model and use it to make predictions based on input provided.</span></span>

![Flusso di dati del file ONNX nel runtime di ONNX.](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a><span data-ttu-id="01beb-178">Configurare il progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="01beb-178">Set up the .NET Core project</span></span>

<span data-ttu-id="01beb-179">Ora che sono state apprese le nozioni generali su ONNX e sul funzionamento di Tiny YOLOv2, è possibile creare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-179">Now that you have a general understanding of what ONNX is and how Tiny YOLOv2 works, it's time to build the application.</span></span>

### <a name="create-a-console-application"></a><span data-ttu-id="01beb-180">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="01beb-180">Create a console application</span></span>

1. <span data-ttu-id="01beb-181">Creare un'**applicazione console .NET Core** denominata "ObjectDetection".</span><span class="sxs-lookup"><span data-stu-id="01beb-181">Create a **.NET Core Console Application** called "ObjectDetection".</span></span>

1. <span data-ttu-id="01beb-182">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="01beb-182">Install the **Microsoft.ML NuGet Package**:</span></span>

    - <span data-ttu-id="01beb-183">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="01beb-183">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    - <span data-ttu-id="01beb-184">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="01beb-184">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    - <span data-ttu-id="01beb-185">Selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="01beb-185">Select the **Install** button.</span></span>
    - <span data-ttu-id="01beb-186">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="01beb-186">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    - <span data-ttu-id="01beb-187">Ripetere questi passaggi per **Microsoft.ML.ImageAnalytics** e **Microsoft.ML.OnnxTransformer**.</span><span class="sxs-lookup"><span data-stu-id="01beb-187">Repeat these steps for **Microsoft.ML.ImageAnalytics** and **Microsoft.ML.OnnxTransformer**.</span></span>

### <a name="prepare-your-data-and-pre-trained-model"></a><span data-ttu-id="01beb-188">Preparare i dati e il modello già sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="01beb-188">Prepare your data and pre-trained model</span></span>

1. <span data-ttu-id="01beb-189">Scaricare il [file ZIP della directory assets del progetto](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) e decomprimerlo.</span><span class="sxs-lookup"><span data-stu-id="01beb-189">Download [The project assets directory zip file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) and unzip.</span></span>

1. <span data-ttu-id="01beb-190">Copiare la directory `assets` nella directory del progetto *ObjectDetection*.</span><span class="sxs-lookup"><span data-stu-id="01beb-190">Copy the `assets` directory into your *ObjectDetection* project directory.</span></span> <span data-ttu-id="01beb-191">Questa directory e le relative sottodirectory contengono i file di immagine (ad eccezione del modello Tiny YOLOv2, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-191">This directory and its subdirectories contain the image files (except for the Tiny YOLOv2 model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="01beb-192">Scaricare il [modello Tiny YOLOv2](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) da [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2) e decomprimerlo.</span><span class="sxs-lookup"><span data-stu-id="01beb-192">Download the [Tiny YOLOv2 model](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) from the [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2), and unzip.</span></span>

    <span data-ttu-id="01beb-193">Aprire il prompt dei comandi e immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="01beb-193">Open the command prompt and enter the following command:</span></span>

    ```shell
    tar -xvzf tiny_yolov2.tar.gz
    ```

1. <span data-ttu-id="01beb-194">Copiare il file `model.onnx` estratto dalla directory appena decompressa nella directory `assets\Model` del progetto*ObjectDetection* e rinominarlo in `TinyYolo2_model.onnx`.</span><span class="sxs-lookup"><span data-stu-id="01beb-194">Copy the extracted `model.onnx` file from the directory just unzipped into your *ObjectDetection* project `assets\Model` directory and rename it to `TinyYolo2_model.onnx`.</span></span> <span data-ttu-id="01beb-195">Questa directory contiene il modello necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-195">This directory contains the model needed for this tutorial.</span></span>

1. <span data-ttu-id="01beb-196">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="01beb-196">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="01beb-197">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="01beb-197">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="01beb-198">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="01beb-198">Create classes and define paths</span></span>

<span data-ttu-id="01beb-199">Aprire il file *Program.cs* e aggiungere le istruzioni `using` aggiuntive seguenti all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="01beb-199">Open the *Program.cs* file and add the following additional `using` statements to the top of the file:</span></span>

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L7)]

<span data-ttu-id="01beb-200">Definire quindi i percorsi dei diversi asset.</span><span class="sxs-lookup"><span data-stu-id="01beb-200">Next, define the paths of the various assets.</span></span>

1. <span data-ttu-id="01beb-201">Prima di tutto, aggiungere il metodo `GetAbsolutePath` seguente al metodo `Main` nella classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="01beb-201">First, add the `GetAbsolutePath` method below the `Main` method in the `Program` class.</span></span>

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. <span data-ttu-id="01beb-202">Quindi, all'interno del metodo `Main` creare i campi per archiviare il percorso degli asset.</span><span class="sxs-lookup"><span data-stu-id="01beb-202">Then, inside the `Main` method, create fields to store the location of your assets.</span></span>

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

<span data-ttu-id="01beb-203">Aggiungere una nuova directory al progetto per archiviare i dati di input e le classi di stima.</span><span class="sxs-lookup"><span data-stu-id="01beb-203">Add a new directory to your project to store your input data and prediction classes.</span></span>

<span data-ttu-id="01beb-204">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="01beb-204">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="01beb-205">Quando la nuova cartella viene visualizzata in Esplora soluzioni, assegnarle il nome "DataStructures".</span><span class="sxs-lookup"><span data-stu-id="01beb-205">When the new folder appears in the Solution Explorer, name it "DataStructures".</span></span>

<span data-ttu-id="01beb-206">Creare la classe di dati di input nella directory *DataStructures* appena creata.</span><span class="sxs-lookup"><span data-stu-id="01beb-206">Create your input data class in the newly created *DataStructures* directory.</span></span>

1. <span data-ttu-id="01beb-207">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *DataStructures* e quindi scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="01beb-207">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="01beb-208">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *ImageNetData.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-208">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetData.cs*.</span></span> <span data-ttu-id="01beb-209">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="01beb-209">Then, select the **Add** button.</span></span>

    <span data-ttu-id="01beb-210">Il file *ImageNetData.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="01beb-210">The *ImageNetData.cs* file opens in the code editor.</span></span> <span data-ttu-id="01beb-211">Aggiungere l'istruzione `using` seguente all'inizio di *ImageNetData.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-211">Add the following `using` statement to the top of *ImageNetData.cs*:</span></span>

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    <span data-ttu-id="01beb-212">Rimuovere la definizione di classe esistente e aggiungere il codice seguente per la classe `ImageNetData` al file *ImageNetData.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-212">Remove the existing class definition and add the following code for the `ImageNetData` class to the *ImageNetData.cs* file:</span></span>

    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    <span data-ttu-id="01beb-213">`ImageNetData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:</span><span class="sxs-lookup"><span data-stu-id="01beb-213">`ImageNetData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    - <span data-ttu-id="01beb-214">`ImagePath` contiene il percorso in cui è archiviata l'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-214">`ImagePath` contains the path where the image is stored.</span></span>
    - <span data-ttu-id="01beb-215">`Label` contiene il nome del file.</span><span class="sxs-lookup"><span data-stu-id="01beb-215">`Label` contains the name of the file.</span></span>

    <span data-ttu-id="01beb-216">Inoltre, `ImageNetData` contiene un metodo `ReadFromFile` che carica più file di immagine archiviati nel percorso `imageFolder` specificato e li restituisce come una raccolta di oggetti `ImageNetData`.</span><span class="sxs-lookup"><span data-stu-id="01beb-216">Additionally, `ImageNetData` contains a method `ReadFromFile` that loads multiple image files stored in the `imageFolder` path specified and returns them as a collection of `ImageNetData` objects.</span></span>

<span data-ttu-id="01beb-217">Creare la classe di stima nella directory *DataStructures*.</span><span class="sxs-lookup"><span data-stu-id="01beb-217">Create your prediction class in the *DataStructures* directory.</span></span>

1. <span data-ttu-id="01beb-218">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *DataStructures* e quindi scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="01beb-218">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="01beb-219">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *ImageNetPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-219">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetPrediction.cs*.</span></span> <span data-ttu-id="01beb-220">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="01beb-220">Then, select the **Add** button.</span></span>

    <span data-ttu-id="01beb-221">Il file *ImageNetPrediction.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="01beb-221">The *ImageNetPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="01beb-222">Aggiungere l'istruzione `using` seguente all'inizio di *ImageNetPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-222">Add the following `using` statement to the top of *ImageNetPrediction.cs*:</span></span>

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    <span data-ttu-id="01beb-223">Rimuovere la definizione di classe esistente e aggiungere il codice seguente per la classe `ImageNetPrediction` al file *ImageNetPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-223">Remove the existing class definition and add the following code for the `ImageNetPrediction` class to the *ImageNetPrediction.cs* file:</span></span>

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    <span data-ttu-id="01beb-224">`ImageNetPrediction` è la classe di dati di stima e ha il campo `float[]` seguente:</span><span class="sxs-lookup"><span data-stu-id="01beb-224">`ImageNetPrediction` is the prediction data class and has the following `float[]` field:</span></span>

    - <span data-ttu-id="01beb-225">`PredictedLabel` contiene le dimensioni, il Punteggio di oggetto e le probabilità della classe per ogni riquadro di delimitazione rilevato in un'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-225">`PredictedLabel` contains the dimensions, objectness score, and class probabilities for each of the bounding boxes detected in an image.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="01beb-226">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="01beb-226">Initialize variables in Main</span></span>

<span data-ttu-id="01beb-227">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-227">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="01beb-228">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="01beb-228">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="01beb-229">Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext` aggiungendo la riga seguente al metodo `Main` di *Program.cs* sotto il campo `outputFolder`.</span><span class="sxs-lookup"><span data-stu-id="01beb-229">Initialize the `mlContext` variable with a new instance of `MLContext` by adding the following line to the `Main` method of *Program.cs* below the `outputFolder` field.</span></span>

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

## <a name="create-a-parser-to-post-process-model-outputs"></a><span data-ttu-id="01beb-230">Creare un parser per la post-elaborazione degli output del modello</span><span class="sxs-lookup"><span data-stu-id="01beb-230">Create a parser to post-process model outputs</span></span>

<span data-ttu-id="01beb-231">Il modello segmenta un'immagine in una griglia `13 x 13`, in cui ogni cella è `32px x 32px`.</span><span class="sxs-lookup"><span data-stu-id="01beb-231">The model segments an image into a `13 x 13` grid, where each grid cell is `32px x 32px`.</span></span> <span data-ttu-id="01beb-232">Ogni cella della griglia contiene 5 rettangoli di selezione di oggetti potenziali.</span><span class="sxs-lookup"><span data-stu-id="01beb-232">Each grid cell contains 5 potential object bounding boxes.</span></span> <span data-ttu-id="01beb-233">Un rettangolo di selezione contiene 25 elementi:</span><span class="sxs-lookup"><span data-stu-id="01beb-233">A bounding box has  25 elements:</span></span>

![Esempio di griglia a sinistra e di esempio di rettangolo di delimitazione a destra](./media/object-detection-onnx/model-output-description.png)

- <span data-ttu-id="01beb-235">`x` la posizione x del centro del rettangolo di selezione rispetto alla cella della griglia a cui è associato.</span><span class="sxs-lookup"><span data-stu-id="01beb-235">`x` the x position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="01beb-236">`y` la posizione y del centro del rettangolo di selezione rispetto alla cella della griglia a cui è associato.</span><span class="sxs-lookup"><span data-stu-id="01beb-236">`y` the y position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="01beb-237">`w` la larghezza del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-237">`w` the width of the bounding box.</span></span>
- <span data-ttu-id="01beb-238">`h` l'altezza del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-238">`h` the height of the bounding box.</span></span>
- <span data-ttu-id="01beb-239">`o` il valore di confidenza che un oggetto esiste nel rettangolo di selezione, noto anche come punteggio di riconoscimento degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="01beb-239">`o` the confidence value that an object exists within the bounding box, also known as objectness score.</span></span>
- <span data-ttu-id="01beb-240">`p1-p20` le probabilità delle classi per ognuna delle 20 classi stimate dal modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-240">`p1-p20` class probabilities for each of the 20 classes predicted by the model.</span></span>

<span data-ttu-id="01beb-241">In totale, i 25 elementi che descrivono ognuno dei 5 rettangoli di selezione costituiscono i 125 elementi contenuti in ogni cella della griglia.</span><span class="sxs-lookup"><span data-stu-id="01beb-241">In total, the 25 elements describing each of the 5 bounding boxes make up the 125 elements contained in each grid cell.</span></span>

<span data-ttu-id="01beb-242">L'output generato dal modello ONNX già sottoposto a training è una matrice mobile di lunghezza `21125` che rappresenta gli elementi di un tensore con dimensioni `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="01beb-242">The output generated by the pre-trained ONNX model is a float array of length `21125`, representing the elements of a tensor with dimensions `125 x 13 x 13`.</span></span> <span data-ttu-id="01beb-243">Per trasformare le stime generate dal modello in un tensore, è necessario eseguire alcune operazioni di post-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-243">In order to transform the predictions generated by the model into a tensor, some post-processing work is required.</span></span> <span data-ttu-id="01beb-244">A tale scopo, creare un set di classi per l'analisi dell'output.</span><span class="sxs-lookup"><span data-stu-id="01beb-244">To do so, create a set of classes to help parse the output.</span></span>

<span data-ttu-id="01beb-245">Aggiungere una nuova directory al progetto per organizzare il set di classi parser.</span><span class="sxs-lookup"><span data-stu-id="01beb-245">Add a new directory to your project to organize the set of parser classes.</span></span>

1. <span data-ttu-id="01beb-246">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="01beb-246">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="01beb-247">Quando la nuova cartella viene visualizzata in Esplora soluzioni, assegnarle il nome "YoloParser".</span><span class="sxs-lookup"><span data-stu-id="01beb-247">When the new folder appears in the Solution Explorer, name it "YoloParser".</span></span>

### <a name="create-bounding-boxes-and-dimensions"></a><span data-ttu-id="01beb-248">Creare rettangoli di selezione e dimensioni</span><span class="sxs-lookup"><span data-stu-id="01beb-248">Create bounding boxes and dimensions</span></span>

<span data-ttu-id="01beb-249">I dati restituiti dal modello contengono le coordinate e le dimensioni dei rettangoli di selezione degli oggetti all'interno dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-249">The data output by the model contains coordinates and dimensions of the bounding boxes of objects within the image.</span></span> <span data-ttu-id="01beb-250">Creare una classe di base per le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="01beb-250">Create a base class for dimensions.</span></span>

1. <span data-ttu-id="01beb-251">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *YoloParser* e quindi scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="01beb-251">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="01beb-252">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *DimensionsBase.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-252">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *DimensionsBase.cs*.</span></span> <span data-ttu-id="01beb-253">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="01beb-253">Then, select the **Add** button.</span></span>

    <span data-ttu-id="01beb-254">Il file *DimensionsBase.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="01beb-254">The *DimensionsBase.cs* file opens in the code editor.</span></span> <span data-ttu-id="01beb-255">Rimuovere tutte le istruzioni `using` e la definizione di classe esistente.</span><span class="sxs-lookup"><span data-stu-id="01beb-255">Remove all `using` statements and existing class definition.</span></span>

    <span data-ttu-id="01beb-256">Aggiungere il codice seguente per la classe `DimensionsBase` al file *DimensionsBase.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-256">Add the following code for the `DimensionsBase` class to the *DimensionsBase.cs* file:</span></span>

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    <span data-ttu-id="01beb-257">`DimensionsBase` presenta le proprietà `float` seguenti:</span><span class="sxs-lookup"><span data-stu-id="01beb-257">`DimensionsBase` has the following `float` properties:</span></span>

    - <span data-ttu-id="01beb-258">`X` contiene la posizione dell'oggetto lungo l'asse x.</span><span class="sxs-lookup"><span data-stu-id="01beb-258">`X` contains the position of the object along the x-axis.</span></span>
    - <span data-ttu-id="01beb-259">`Y` contiene la posizione dell'oggetto lungo l'asse y.</span><span class="sxs-lookup"><span data-stu-id="01beb-259">`Y` contains the position of the object along the y-axis.</span></span>
    - <span data-ttu-id="01beb-260">`Height` contiene l'altezza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="01beb-260">`Height` contains the height of the object.</span></span>
    - <span data-ttu-id="01beb-261">`Width` contiene la larghezza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="01beb-261">`Width` contains the width of the object.</span></span>

<span data-ttu-id="01beb-262">Creare quindi una classe per i rettangoli di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-262">Next, create a class for your bounding boxes.</span></span>

1. <span data-ttu-id="01beb-263">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *YoloParser* e quindi scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="01beb-263">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="01beb-264">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *YoloBoundingBox.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-264">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloBoundingBox.cs*.</span></span> <span data-ttu-id="01beb-265">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="01beb-265">Then, select the **Add** button.</span></span>

    <span data-ttu-id="01beb-266">Il file *YoloBoundingBox.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="01beb-266">The *YoloBoundingBox.cs* file opens in the code editor.</span></span> <span data-ttu-id="01beb-267">Aggiungere l'istruzione `using` seguente all'inizio di *YoloBoundingBox.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-267">Add the following `using` statement to the top of *YoloBoundingBox.cs*:</span></span>

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    <span data-ttu-id="01beb-268">Appena sopra la definizione di classe esistente, aggiungere una nuova definizione di classe denominata `BoundingBoxDimensions` che eredita dalla classe `DimensionsBase` per contenere le dimensioni del rispettivo rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-268">Just above the existing class definition, add a new class definition called `BoundingBoxDimensions` that inherits from the `DimensionsBase` class to contain the dimensions of the respective bounding box.</span></span>

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    <span data-ttu-id="01beb-269">Rimuovere la definizione di classe `YoloBoundingBox` esistente e aggiungere il codice seguente per la classe `YoloBoundingBox` al file *YoloBoundingBox.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-269">Remove the existing `YoloBoundingBox` class definition and add the following code for the `YoloBoundingBox` class to the *YoloBoundingBox.cs* file:</span></span>

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]

    <span data-ttu-id="01beb-270">`YoloBoundingBox` presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="01beb-270">`YoloBoundingBox` has the following properties:</span></span>

    - <span data-ttu-id="01beb-271">`Dimensions` contiene le dimensioni del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-271">`Dimensions` contains dimensions of the bounding box.</span></span>
    - <span data-ttu-id="01beb-272">`Label` contiene la classe dell'oggetto rilevato nel rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-272">`Label` contains the class of object detected within the bounding box.</span></span>
    - <span data-ttu-id="01beb-273">`Confidence` contiene la confidenza della classe.</span><span class="sxs-lookup"><span data-stu-id="01beb-273">`Confidence` contains the confidence of the class.</span></span>
    - <span data-ttu-id="01beb-274">`Rect` contiene la rappresentazione del rettangolo delle dimensioni del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-274">`Rect` contains the rectangle representation of the bounding box's dimensions.</span></span>
    - <span data-ttu-id="01beb-275">`BoxColor` contiene il colore associato alla rispettiva classe usata per disegnare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-275">`BoxColor` contains the color associated with the respective class used to draw on the image.</span></span>

### <a name="create-the-parser"></a><span data-ttu-id="01beb-276">Creare il parser</span><span class="sxs-lookup"><span data-stu-id="01beb-276">Create the parser</span></span>

<span data-ttu-id="01beb-277">Dopo aver creato le classi per le dimensioni e i rettangoli di selezione, è possibile creare il parser.</span><span class="sxs-lookup"><span data-stu-id="01beb-277">Now that the classes for dimensions and bounding boxes are created, it's time to create the parser.</span></span>

1. <span data-ttu-id="01beb-278">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *YoloParser* e quindi scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="01beb-278">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="01beb-279">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *YoloOutputParser.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-279">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloOutputParser.cs*.</span></span> <span data-ttu-id="01beb-280">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="01beb-280">Then, select the **Add** button.</span></span>

    <span data-ttu-id="01beb-281">Il file *YoloOutputParser.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="01beb-281">The *YoloOutputParser.cs* file opens in the code editor.</span></span> <span data-ttu-id="01beb-282">Aggiungere l'istruzione `using` seguente all'inizio di *YoloOutputParser.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-282">Add the following `using` statement to the top of *YoloOutputParser.cs*:</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    <span data-ttu-id="01beb-283">All'interno della definizione di classe `YoloOutputParser` esistente aggiungere una classe annidata che contiene le dimensioni di ciascuna cella nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-283">Inside the existing `YoloOutputParser` class definition, add a nested class that contains the dimensions of each of the cells in the image.</span></span> <span data-ttu-id="01beb-284">Aggiungere il codice seguente per la classe `CellDimensions` che eredita dalla classe `DimensionsBase` all'inizio della definizione della classe `YoloOutputParser`.</span><span class="sxs-lookup"><span data-stu-id="01beb-284">Add the following code for the `CellDimensions` class that inherits from the `DimensionsBase` class at the top of the `YoloOutputParser` class definition.</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. <span data-ttu-id="01beb-285">All'interno della definizione della classe `YoloOutputParser` aggiungere le costanti e i campi seguenti.</span><span class="sxs-lookup"><span data-stu-id="01beb-285">Inside the `YoloOutputParser` class definition, add the following constants and fields.</span></span>

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]

    - <span data-ttu-id="01beb-286">`ROW_COUNT`: numero di righe nella griglia in cui è divisa l'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-286">`ROW_COUNT` is the number of rows in the grid the image is divided into.</span></span>
    - <span data-ttu-id="01beb-287">`COL_COUNT`: numero di colonne nella griglia in cui è divisa l'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-287">`COL_COUNT` is the number of columns in the grid the image is divided into.</span></span>
    - <span data-ttu-id="01beb-288">`CHANNEL_COUNT`: numero totale di valori contenuti in una cella della griglia.</span><span class="sxs-lookup"><span data-stu-id="01beb-288">`CHANNEL_COUNT` is the total number of values contained in one cell of the grid.</span></span>
    - <span data-ttu-id="01beb-289">`BOXES_PER_CELL`: numero di rettangoli di selezione in una cella.</span><span class="sxs-lookup"><span data-stu-id="01beb-289">`BOXES_PER_CELL` is the number of bounding boxes in a cell,</span></span>
    - <span data-ttu-id="01beb-290">`BOX_INFO_FEATURE_COUNT`: numero di funzionalità contenute all'interno di un rettangolo di selezione (x, y, altezza, larghezza, confidenza).</span><span class="sxs-lookup"><span data-stu-id="01beb-290">`BOX_INFO_FEATURE_COUNT` is the number of features contained within a box (x,y,height,width,confidence).</span></span>
    - <span data-ttu-id="01beb-291">`CLASS_COUNT` numero di stime delle classi contenute in ogni rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-291">`CLASS_COUNT` is the number of class predictions contained in each bounding box.</span></span>
    - <span data-ttu-id="01beb-292">`CELL_WIDTH`: larghezza di una cella nella griglia dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-292">`CELL_WIDTH` is the width of one cell in the image grid.</span></span>
    - <span data-ttu-id="01beb-293">`CELL_HEIGHT`: altezza di una cella nella griglia dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-293">`CELL_HEIGHT` is the height of one cell in the image grid.</span></span>
    - <span data-ttu-id="01beb-294">`channelStride`: posizione iniziale della cella corrente nella griglia.</span><span class="sxs-lookup"><span data-stu-id="01beb-294">`channelStride` is the starting position of the current cell in the grid.</span></span>

    <span data-ttu-id="01beb-295">Quando il modello esegue una stima, operazione nota anche come assegnazione di punteggi, divide l'immagine di input `416px x 416px` in una griglia di celle delle dimensioni di `13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="01beb-295">When the model makes a prediction, also known as scoring, it divides the `416px x 416px` input image into a grid of cells the size of `13 x 13`.</span></span> <span data-ttu-id="01beb-296">Ogni cella contenuta è `32px x 32px`.</span><span class="sxs-lookup"><span data-stu-id="01beb-296">Each cell contains is `32px x 32px`.</span></span> <span data-ttu-id="01beb-297">All'interno di ogni cella sono presenti 5 rettangoli di selezione, ognuno contenente 5 funzionalità (x, y, larghezza, altezza, confidenza).</span><span class="sxs-lookup"><span data-stu-id="01beb-297">Within each cell, there are 5 bounding boxes each containing 5 features (x, y, width, height, confidence).</span></span> <span data-ttu-id="01beb-298">Ogni rettangolo di delimitazione contiene inoltre la probabilità di ogni classe, che in questo caso è 20.</span><span class="sxs-lookup"><span data-stu-id="01beb-298">In addition, each bounding box contains the probability of each of the classes, which in this case is 20.</span></span> <span data-ttu-id="01beb-299">Di conseguenza, ogni cella contiene 125 informazioni (5 funzionalità + 20 probabilità delle classi).</span><span class="sxs-lookup"><span data-stu-id="01beb-299">Therefore, each cell contains 125 pieces of information (5 features + 20 class probabilities).</span></span>

<span data-ttu-id="01beb-300">Creare un elenco di ancoraggi sotto `channelStride` per tutti i 5 rettangoli di selezione:</span><span class="sxs-lookup"><span data-stu-id="01beb-300">Create a list of anchors below `channelStride` for all 5 bounding boxes:</span></span>

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]

<span data-ttu-id="01beb-301">Gli ancoraggi sono rapporti di altezza e larghezza predefiniti per i rettangoli di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-301">Anchors are pre-defined height and width ratios of bounding boxes.</span></span> <span data-ttu-id="01beb-302">La maggior parte degli oggetti o delle classi rilevate da un modello ha proporzioni simili.</span><span class="sxs-lookup"><span data-stu-id="01beb-302">Most object or classes detected by a model have similar ratios.</span></span> <span data-ttu-id="01beb-303">Questo è importante quando si tratta di creare rettangoli di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-303">This is valuable when it comes to creating bounding boxes.</span></span> <span data-ttu-id="01beb-304">Anziché stimare i rettangoli di selezione, viene calcolato l'offset dalle dimensioni predefinite, riducendo di conseguenza il calcolo necessario per stimare il rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-304">Instead of predicting the bounding boxes, the offset from the pre-defined dimensions is calculated therefore reducing the computation required to predict the bounding box.</span></span> <span data-ttu-id="01beb-305">In genere i rapporti di ancoraggio vengono calcolati in base al set di dati usato.</span><span class="sxs-lookup"><span data-stu-id="01beb-305">Typically these anchor ratios are calculated based on the dataset used.</span></span> <span data-ttu-id="01beb-306">In questo caso, poiché il set di dati è noto e i valori sono stati pre-calcolati, gli ancoraggi possono essere hardcoded.</span><span class="sxs-lookup"><span data-stu-id="01beb-306">In this case, because the dataset is known and the values have been pre-computed, the anchors can be hard-coded.</span></span>

<span data-ttu-id="01beb-307">Definire quindi le etichette o le classi che devono essere stimate dal modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-307">Next, define the labels or classes that the model will predict.</span></span> <span data-ttu-id="01beb-308">Questo modello stima 20 classi, ovvero un subset del numero totale di classi stimate dal modello YOLOv2 originale.</span><span class="sxs-lookup"><span data-stu-id="01beb-308">This model predicts 20 classes, which is a subset of the total number of classes predicted by the original YOLOv2 model.</span></span>

<span data-ttu-id="01beb-309">Aggiungere l'elenco di etichette sotto `anchors`.</span><span class="sxs-lookup"><span data-stu-id="01beb-309">Add your list of labels below the `anchors`.</span></span>

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

<span data-ttu-id="01beb-310">A ognuna delle classi sono associati colori specifici.</span><span class="sxs-lookup"><span data-stu-id="01beb-310">There are colors associated with each of the classes.</span></span> <span data-ttu-id="01beb-311">Assegnare i colori delle classi sotto `labels`:</span><span class="sxs-lookup"><span data-stu-id="01beb-311">Assign your class colors below your `labels`:</span></span>

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a><span data-ttu-id="01beb-312">Creare funzioni di supporto</span><span class="sxs-lookup"><span data-stu-id="01beb-312">Create helper functions</span></span>

<span data-ttu-id="01beb-313">La fase di post-elaborazione prevede una serie di passaggi.</span><span class="sxs-lookup"><span data-stu-id="01beb-313">There are a series of steps involved in the post-processing phase.</span></span> <span data-ttu-id="01beb-314">Per semplificare questi passaggi, è possibile usare diversi metodi di supporto.</span><span class="sxs-lookup"><span data-stu-id="01beb-314">To help with that, several helper methods can be employed.</span></span>

<span data-ttu-id="01beb-315">I metodi di supporto usati dal parser sono:</span><span class="sxs-lookup"><span data-stu-id="01beb-315">The helper methods used in by the parser are:</span></span>

- <span data-ttu-id="01beb-316">`Sigmoid`: applica la funzione sigma che restituisce un numero compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="01beb-316">`Sigmoid` applies the sigmoid function that outputs a number between 0 and 1.</span></span>
- <span data-ttu-id="01beb-317">`Softmax`: normalizza un vettore di input in una distribuzione di probabilità.</span><span class="sxs-lookup"><span data-stu-id="01beb-317">`Softmax` normalizes an input vector into a probability distribution.</span></span>
- <span data-ttu-id="01beb-318">`GetOffset`: esegue il mapping degli elementi nell'output di un modello unidimensionale alla posizione corrispondente in un tensore `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="01beb-318">`GetOffset` maps elements in the one-dimensional model output to the corresponding position in a `125 x 13 x 13` tensor.</span></span>
- <span data-ttu-id="01beb-319">`ExtractBoundingBoxes`: estrae le dimensioni dei rettangoli di selezione usando il metodo `GetOffset` dall'output del modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-319">`ExtractBoundingBoxes` extracts the bounding box dimensions using the `GetOffset` method from the model output.</span></span>
- <span data-ttu-id="01beb-320">`GetConfidence` estrae il valore di confidenza che indica il modo in cui il modello ha rilevato un oggetto e utilizza la funzione `Sigmoid` per trasformarla in una percentuale.</span><span class="sxs-lookup"><span data-stu-id="01beb-320">`GetConfidence` extracts the confidence value that states how sure the model is that it has detected an object and uses the `Sigmoid` function to turn it into a percentage.</span></span>
- <span data-ttu-id="01beb-321">`MapBoundingBoxToCell`: usa le dimensioni del rettangolo di selezione e ne esegue il mapping alla rispettiva cella all'interno dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-321">`MapBoundingBoxToCell` uses the bounding box dimensions and maps them onto its respective cell within the image.</span></span>
- <span data-ttu-id="01beb-322">`ExtractClasses`: estrae le stime delle classi per il rettangolo di selezione dall'output del modello usando il metodo `GetOffset` e le converte in una distribuzione di probabilità tramite il metodo `Softmax`.</span><span class="sxs-lookup"><span data-stu-id="01beb-322">`ExtractClasses` extracts the class predictions for the bounding box from the model output using the `GetOffset` method and turns them into a probability distribution using the `Softmax` method.</span></span>
- <span data-ttu-id="01beb-323">`GetTopResult`: seleziona la classe dall'elenco delle classi stimate con la probabilità maggiore.</span><span class="sxs-lookup"><span data-stu-id="01beb-323">`GetTopResult` selects the class from the list of predicted classes with the highest probability.</span></span>
- <span data-ttu-id="01beb-324">`IntersectionOverUnion`: filtra i rettangoli di selezione sovrapposti con probabilità inferiori.</span><span class="sxs-lookup"><span data-stu-id="01beb-324">`IntersectionOverUnion` filters overlapping bounding boxes with lower probabilities.</span></span>

<span data-ttu-id="01beb-325">Aggiungere il codice per tutti i metodi di supporto sotto l'elenco `classColors`.</span><span class="sxs-lookup"><span data-stu-id="01beb-325">Add the code for all the helper methods below your list of `classColors`.</span></span>

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

<span data-ttu-id="01beb-326">Dopo aver definito tutti i metodi di supporto, è possibile usarli per elaborare l'output del modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-326">Once you have defined all of the helper methods, it's time to use them to process the model output.</span></span>

<span data-ttu-id="01beb-327">Sotto il metodo `IntersectionOverUnion` creare il metodo `ParseOutputs` per elaborare l'output generato dal modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-327">Below the `IntersectionOverUnion` method, create the `ParseOutputs` method to process the output generated by the model.</span></span>

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```

<span data-ttu-id="01beb-328">Creare un elenco per archiviare i rettangoli di selezione e definire variabili all'interno del metodo `ParseOutputs`.</span><span class="sxs-lookup"><span data-stu-id="01beb-328">Create a list to store your bounding boxes and define variables inside the `ParseOutputs` method.</span></span>

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

<span data-ttu-id="01beb-329">Ogni immagine è divisa in una griglia di celle `13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="01beb-329">Each image is divided into a grid of `13 x 13` cells.</span></span> <span data-ttu-id="01beb-330">Ogni cella contiene cinque rettangoli di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-330">Each cell contains five bounding boxes.</span></span> <span data-ttu-id="01beb-331">Sotto la variabile `boxes` aggiungere il codice per elaborare tutti i rettangoli in ognuna delle celle.</span><span class="sxs-lookup"><span data-stu-id="01beb-331">Below the `boxes` variable, add code to process all of the boxes in each of the cells.</span></span>

```csharp
for (int row = 0; row < ROW_COUNT; row++)
{
    for (int column = 0; column < COL_COUNT; column++)
    {
        for (int box = 0; box < BOXES_PER_CELL; box++)
        {

        }
    }
}
```

<span data-ttu-id="01beb-332">All'interno del ciclo più interno calcolare la posizione iniziale del rettangolo corrente all'interno dell'output del modello unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="01beb-332">Inside the inner-most loop, calculate the starting position of the current box within the one-dimensional model output.</span></span>

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

<span data-ttu-id="01beb-333">Direttamente sotto usare il metodo `ExtractBoundingBoxDimensions` per ottenere le dimensioni del rettangolo di selezione corrente.</span><span class="sxs-lookup"><span data-stu-id="01beb-333">Directly below that, use the `ExtractBoundingBoxDimensions` method to get the dimensions of the current bounding box.</span></span>

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

<span data-ttu-id="01beb-334">Usare quindi il metodo `GetConfidence` per ottenere la confidenza per il rettangolo di selezione corrente.</span><span class="sxs-lookup"><span data-stu-id="01beb-334">Then, use the `GetConfidence` method to get the confidence for the current bounding box.</span></span>

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

<span data-ttu-id="01beb-335">Usare ora il metodo `MapBoundingBoxToCell` per eseguire il mapping del rettangolo di selezione corrente alla cella corrente in fase di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-335">After that, use the `MapBoundingBoxToCell` method to map the current bounding box to the current cell being processed.</span></span>

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

<span data-ttu-id="01beb-336">Prima di eseguire altre operazioni di elaborazione, controllare se il valore di confidenza è maggiore della soglia specificata.</span><span class="sxs-lookup"><span data-stu-id="01beb-336">Before doing any further processing, check whether your confidence value is greater than the threshold provided.</span></span> <span data-ttu-id="01beb-337">In caso contrario, elaborare il rettangolo di selezione successivo.</span><span class="sxs-lookup"><span data-stu-id="01beb-337">If not, process the next bounding box.</span></span>

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

<span data-ttu-id="01beb-338">Altrimenti, proseguire con l'elaborazione dell'output.</span><span class="sxs-lookup"><span data-stu-id="01beb-338">Otherwise, continue processing the output.</span></span> <span data-ttu-id="01beb-339">Il passaggio successivo consiste nell'ottenere la distribuzione di probabilità delle classi stimate per il rettangolo di selezione corrente usando il metodo `ExtractClasses`.</span><span class="sxs-lookup"><span data-stu-id="01beb-339">The next step is to get the probability distribution of the predicted classes for the current bounding box using the `ExtractClasses` method.</span></span>

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

<span data-ttu-id="01beb-340">Usare quindi il metodo `GetTopResult` per ottenere il valore e l'indice della classe con la probabilità maggiore per il rettangolo corrente e calcolarne il punteggio.</span><span class="sxs-lookup"><span data-stu-id="01beb-340">Then, use the `GetTopResult` method to get the value and index of the class with the highest probability for the current box and compute its score.</span></span>

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

<span data-ttu-id="01beb-341">Usare `topScore` ancora una volta per mantenere solo i rettangoli di selezione che superano la soglia specificata.</span><span class="sxs-lookup"><span data-stu-id="01beb-341">Use the `topScore` to once again keep only those bounding boxes that are above the specified threshold.</span></span>

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

<span data-ttu-id="01beb-342">Infine, se il rettangolo di selezione corrente supera la soglia, creare un nuovo oggetto `BoundingBox` e aggiungerlo all'elenco `boxes`.</span><span class="sxs-lookup"><span data-stu-id="01beb-342">Finally, if the current bounding box exceeds the threshold, create a new `BoundingBox` object and add it to the `boxes` list.</span></span>

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

<span data-ttu-id="01beb-343">Dopo aver elaborato tutte le celle nell'immagine, restituire l'elenco `boxes`.</span><span class="sxs-lookup"><span data-stu-id="01beb-343">Once all cells in the image have been processed, return the `boxes` list.</span></span> <span data-ttu-id="01beb-344">Aggiungere l'istruzione return seguente sotto il ciclo for più esterno nel metodo `ParseOutputs`.</span><span class="sxs-lookup"><span data-stu-id="01beb-344">Add the following return statement below the outer-most for-loop in the `ParseOutputs` method.</span></span>

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a><span data-ttu-id="01beb-345">Filtrare i rettangoli sovrapposti</span><span class="sxs-lookup"><span data-stu-id="01beb-345">Filter overlapping boxes</span></span>

<span data-ttu-id="01beb-346">Ora che tutti i rettangoli di selezione con confidenza elevata sono stati estratti dall'output del modello, è necessario filtrarli ulteriormente per rimuovere le immagini sovrapposte.</span><span class="sxs-lookup"><span data-stu-id="01beb-346">Now that all of the highly confident bounding boxes have been extracted from the model output, additional filtering needs to be done to remove overlapping images.</span></span> <span data-ttu-id="01beb-347">Aggiungere un metodo denominato `FilterBoundingBoxes` sotto il metodo `ParseOutputs`:</span><span class="sxs-lookup"><span data-stu-id="01beb-347">Add a method called `FilterBoundingBoxes` below the `ParseOutputs` method:</span></span>

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

<span data-ttu-id="01beb-348">All'interno del metodo `FilterBoundingBoxes` iniziare creando una matrice uguale alle dimensioni dei rettangoli rilevati e contrassegnando tutti gli slot come attivi o pronti per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-348">Inside the `FilterBoundingBoxes` method, start off by creating an array equal to the size of detected boxes and marking all slots as active or ready for processing.</span></span>

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

<span data-ttu-id="01beb-349">Ordinare quindi l'elenco contenente i rettangoli di selezione in ordine decrescente in base alla confidenza.</span><span class="sxs-lookup"><span data-stu-id="01beb-349">Then, sort the list containing your bounding boxes in descending order based on confidence.</span></span>

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

<span data-ttu-id="01beb-350">Infine, creare un elenco che conterrà i risultati filtrati.</span><span class="sxs-lookup"><span data-stu-id="01beb-350">After that, create a list to hold the filtered results.</span></span>

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

<span data-ttu-id="01beb-351">Iniziare a elaborare ogni rettangolo di selezione tramite l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-351">Begin processing each bounding box by iterating over each of the bounding boxes.</span></span>

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

<span data-ttu-id="01beb-352">All'interno di questo ciclo for controllare se il rettangolo di selezione corrente può essere elaborato.</span><span class="sxs-lookup"><span data-stu-id="01beb-352">Inside of this for-loop, check whether the current bounding box can be processed.</span></span>

```csharp
if (isActiveBoxes[i])
{

}
```

<span data-ttu-id="01beb-353">Se sì, aggiungere il rettangolo di selezione all'elenco dei risultati.</span><span class="sxs-lookup"><span data-stu-id="01beb-353">If so, add the bounding box to the list of results.</span></span> <span data-ttu-id="01beb-354">Se i risultati superano il limite specificato di caselle da estrarre, interrompere il ciclo.</span><span class="sxs-lookup"><span data-stu-id="01beb-354">If the results exceed the specified limit of boxes to be extracted, break out of the loop.</span></span> <span data-ttu-id="01beb-355">Aggiungere il codice seguente all'interno dell'istruzione if.</span><span class="sxs-lookup"><span data-stu-id="01beb-355">Add the following code inside the if-statement.</span></span>

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

<span data-ttu-id="01beb-356">In caso contrario, controllare i rettangoli di selezione adiacenti.</span><span class="sxs-lookup"><span data-stu-id="01beb-356">Otherwise, look at the adjacent bounding boxes.</span></span> <span data-ttu-id="01beb-357">Aggiungere il codice seguente sotto il controllo del limite di rettangoli.</span><span class="sxs-lookup"><span data-stu-id="01beb-357">Add the following code below the box limit check.</span></span>

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

<span data-ttu-id="01beb-358">Come per il primo rettangolo, se il rettangolo adiacente è attivo o pronto per l'elaborazione, usare il metodo `IntersectionOverUnion` per verificare se il primo e il secondo rettangolo superano la soglia specificata.</span><span class="sxs-lookup"><span data-stu-id="01beb-358">Like the first box, if the adjacent box is active or ready to be processed, use the `IntersectionOverUnion` method to check whether the first box and the second box exceed the specified threshold.</span></span> <span data-ttu-id="01beb-359">Aggiungere il codice seguente al ciclo for più interno.</span><span class="sxs-lookup"><span data-stu-id="01beb-359">Add the following code to your innermost for-loop.</span></span>

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

<span data-ttu-id="01beb-360">All'esterno del ciclo for più interno che controlla i rettangoli di selezione adiacenti, verificare se sono presenti altri rettangoli di selezione da elaborare.</span><span class="sxs-lookup"><span data-stu-id="01beb-360">Outside of the inner-most for-loop that checks adjacent bounding boxes, see whether there are any remaining bounding boxes to be processed.</span></span> <span data-ttu-id="01beb-361">In caso contrario, interrompere il ciclo for esterno.</span><span class="sxs-lookup"><span data-stu-id="01beb-361">If not, break out of the outer for-loop.</span></span>

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

<span data-ttu-id="01beb-362">Infine, all'esterno del ciclo for iniziale del metodo `FilterBoundingBoxes` restituire i risultati:</span><span class="sxs-lookup"><span data-stu-id="01beb-362">Finally, outside of the initial for-loop of the `FilterBoundingBoxes` method, return the results:</span></span>

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

<span data-ttu-id="01beb-363">Ottimo!</span><span class="sxs-lookup"><span data-stu-id="01beb-363">Great!</span></span> <span data-ttu-id="01beb-364">È ora possibile usare il codice insieme al modello per l'assegnazione dei punteggi.</span><span class="sxs-lookup"><span data-stu-id="01beb-364">Now it's time to use this code along with the model for scoring.</span></span>

## <a name="use-the-model-for-scoring"></a><span data-ttu-id="01beb-365">Usare il modello per l'assegnazione dei punteggi</span><span class="sxs-lookup"><span data-stu-id="01beb-365">Use the model for scoring</span></span>

<span data-ttu-id="01beb-366">Analogamente alla post-elaborazione, la fase di assegnazione dei punteggi prevede alcuni passaggi.</span><span class="sxs-lookup"><span data-stu-id="01beb-366">Just like with post-processing, there are a few steps in the scoring steps.</span></span> <span data-ttu-id="01beb-367">Per semplificare questi passaggi, aggiungere una classe che conterrà la logica di assegnazione dei punteggi al progetto.</span><span class="sxs-lookup"><span data-stu-id="01beb-367">To help with this, add a class that will contain the scoring logic to your project.</span></span>

1. <span data-ttu-id="01beb-368">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="01beb-368">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="01beb-369">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *OnnxModelScorer.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-369">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *OnnxModelScorer.cs*.</span></span> <span data-ttu-id="01beb-370">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="01beb-370">Then, select the **Add** button.</span></span>

    <span data-ttu-id="01beb-371">Il file *OnnxModelScorer.cs* viene aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="01beb-371">The *OnnxModelScorer.cs* file opens in the code editor.</span></span> <span data-ttu-id="01beb-372">Aggiungere l'istruzione `using` seguente all'inizio di *OnnxModelScorer.cs*:</span><span class="sxs-lookup"><span data-stu-id="01beb-372">Add the following `using` statement to the top of *OnnxModelScorer.cs*:</span></span>

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    <span data-ttu-id="01beb-373">Aggiungere le variabili seguenti all'interno della definizione di classe `OnnxModelScorer`.</span><span class="sxs-lookup"><span data-stu-id="01beb-373">Inside the `OnnxModelScorer` class definition, add the following variables.</span></span>

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    <span data-ttu-id="01beb-374">Direttamente sotto creare un costruttore per la classe `OnnxModelScorer` che Inizializzerà le variabili definite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="01beb-374">Directly below that, create a constructor for the `OnnxModelScorer` class that will initialize the previously defined variables.</span></span>

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    <span data-ttu-id="01beb-375">Dopo aver creato il costruttore, definire un paio di struct che contengono variabili correlate alle impostazioni dell'immagine e del modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-375">Once you have created the constructor, define a couple of structs that contain variables related to the image and model settings.</span></span> <span data-ttu-id="01beb-376">Creare uno struct denominato `ImageNetSettings` che conterrà l'altezza e la larghezza previste come input per il modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-376">Create a struct called `ImageNetSettings` to contain the height and width expected as input for the model.</span></span>

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    <span data-ttu-id="01beb-377">Successivamente, creare un altro struct denominato `TinyYoloModelSettings` contenente i nomi dei livelli di input e di output del modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-377">After that, create another struct called `TinyYoloModelSettings` that contains the names of the input and output layers of the model.</span></span> <span data-ttu-id="01beb-378">Per visualizzare il nome dei livelli di input e output del modello, è possibile usare uno strumento come [Netron](https://github.com/lutzroeder/netron).</span><span class="sxs-lookup"><span data-stu-id="01beb-378">To visualize the name of the input and output layers of the model, you can use a tool like [Netron](https://github.com/lutzroeder/netron).</span></span>

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    <span data-ttu-id="01beb-379">Creare quindi il primo set di metodi da usare per l'assegnazione dei punteggi.</span><span class="sxs-lookup"><span data-stu-id="01beb-379">Next, create the first set of methods use for scoring.</span></span> <span data-ttu-id="01beb-380">Creare il metodo `LoadModel` all'interno della classe `OnnxModelScorer`.</span><span class="sxs-lookup"><span data-stu-id="01beb-380">Create the `LoadModel` method inside of your `OnnxModelScorer` class.</span></span>

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    <span data-ttu-id="01beb-381">All'interno del metodo `LoadModel` aggiungere il codice seguente per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-381">Inside the `LoadModel` method, add the following code for logging.</span></span>

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    <span data-ttu-id="01beb-382">Le pipeline ML.NET devono conoscere lo schema dei dati su cui agire quando viene chiamato il metodo [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*).</span><span class="sxs-lookup"><span data-stu-id="01beb-382">ML.NET pipelines need to know the data schema to operate on when the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method is called.</span></span> <span data-ttu-id="01beb-383">In questo caso, verrà usato un processo simile al training.</span><span class="sxs-lookup"><span data-stu-id="01beb-383">In this case, a process similar to training will be used.</span></span> <span data-ttu-id="01beb-384">Tuttavia, poiché di fatto non viene eseguito alcun training, è accettabile usare un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) vuota.</span><span class="sxs-lookup"><span data-stu-id="01beb-384">However, because no actual training is happening, it is acceptable to use an empty [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="01beb-385">Creare una nuova interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) per la pipeline da un elenco vuoto.</span><span class="sxs-lookup"><span data-stu-id="01beb-385">Create a new [`IDataView`](xref:Microsoft.ML.IDataView) for the pipeline from an empty list.</span></span>

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]

    <span data-ttu-id="01beb-386">Sotto questo codice definire la pipeline.</span><span class="sxs-lookup"><span data-stu-id="01beb-386">Below that, define the pipeline.</span></span> <span data-ttu-id="01beb-387">La pipeline sarà costituita da quattro trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="01beb-387">The pipeline will consist of four transforms.</span></span>

    - <span data-ttu-id="01beb-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*): carica l'immagine come bitmap.</span><span class="sxs-lookup"><span data-stu-id="01beb-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) loads the image as a Bitmap.</span></span>
    - <span data-ttu-id="01beb-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*): ridimensiona l'immagine in base alla dimensione specificata (in questo caso `416 x 416`).</span><span class="sxs-lookup"><span data-stu-id="01beb-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) rescales the image to the size specified (in this case, `416 x 416`).</span></span>
    - <span data-ttu-id="01beb-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*): modifica la rappresentazione in pixel dell'immagine da bitmap a vettore numerico.</span><span class="sxs-lookup"><span data-stu-id="01beb-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) changes the pixel representation of the image from a Bitmap to a numerical vector.</span></span>
    - <span data-ttu-id="01beb-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*): carica il modello ONNX e lo usa per assegnare un punteggio ai dati forniti.</span><span class="sxs-lookup"><span data-stu-id="01beb-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) loads the ONNX model and uses it to score on the data provided.</span></span>

    <span data-ttu-id="01beb-392">Definire la pipeline nel metodo `LoadModel` sotto la variabile `data`.</span><span class="sxs-lookup"><span data-stu-id="01beb-392">Define your pipeline in the `LoadModel` method below the `data` variable.</span></span>

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    <span data-ttu-id="01beb-393">È ora possibile creare un'istanza del modello per l'assegnazione dei punteggi.</span><span class="sxs-lookup"><span data-stu-id="01beb-393">Now it's time to instantiate the model for scoring.</span></span> <span data-ttu-id="01beb-394">Chiamare il metodo [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) nella pipeline e restituirlo per un'ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-394">Call the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method on the pipeline and return it for further processing.</span></span>

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

<span data-ttu-id="01beb-395">Una volta caricato, il modello può essere usato per eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="01beb-395">Once the model is loaded, it can then be used to make predictions.</span></span> <span data-ttu-id="01beb-396">Per semplificare il processo, creare un metodo denominato `PredictDataUsingModel` sotto il metodo `LoadModel`.</span><span class="sxs-lookup"><span data-stu-id="01beb-396">To facilitate that process, create a method called `PredictDataUsingModel` below the `LoadModel` method.</span></span>

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

<span data-ttu-id="01beb-397">All'interno di `PredictDataUsingModel` aggiungere il codice seguente per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-397">Inside the `PredictDataUsingModel`, add the following code for logging.</span></span>

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

<span data-ttu-id="01beb-398">Usare quindi il metodo [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) per assegnare punteggi ai dati.</span><span class="sxs-lookup"><span data-stu-id="01beb-398">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to score the data.</span></span>

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

<span data-ttu-id="01beb-399">Estrarre le probabilità stimate e restituirle per l'ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-399">Extract the predicted probabilities and return them for additional processing.</span></span>

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

<span data-ttu-id="01beb-400">Una volta configurati entrambi i passaggi, combinarli in un unico metodo.</span><span class="sxs-lookup"><span data-stu-id="01beb-400">Now that both steps are set up, combine them into a single method.</span></span> <span data-ttu-id="01beb-401">Sotto il metodo `PredictDataUsingModel` aggiungere un nuovo metodo denominato `Score`.</span><span class="sxs-lookup"><span data-stu-id="01beb-401">Below the `PredictDataUsingModel` method, add a new method called `Score`.</span></span>

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

<span data-ttu-id="01beb-402">La configurazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="01beb-402">Almost there!</span></span> <span data-ttu-id="01beb-403">È ora possibile usarla per lo scopo di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-403">Now it's time to put it all to use.</span></span>

## <a name="detect-objects"></a><span data-ttu-id="01beb-404">Rilevare oggetti</span><span class="sxs-lookup"><span data-stu-id="01beb-404">Detect objects</span></span>

<span data-ttu-id="01beb-405">Dopo aver completato la configurazione, è possibile iniziare a rilevare alcuni oggetti.</span><span class="sxs-lookup"><span data-stu-id="01beb-405">Now that all of the setup is complete, it's time to detect some objects.</span></span> <span data-ttu-id="01beb-406">Per iniziare, aggiungere i riferimenti al marcatore e al parser nella classe *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-406">Start off by adding references to the scorer and parser in your *Program.cs* class.</span></span>

[!code-csharp [ReferenceScorerParser](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L8-L9)]

### <a name="score-and-parse-model-outputs"></a><span data-ttu-id="01beb-407">Assegnare punteggi agli output del modello e analizzarli</span><span class="sxs-lookup"><span data-stu-id="01beb-407">Score and parse model outputs</span></span>

<span data-ttu-id="01beb-408">All'interno del metodo `Main` della classe *Program.cs* aggiungere un'istruzione try-catch.</span><span class="sxs-lookup"><span data-stu-id="01beb-408">Inside the `Main` method of your *Program.cs* class, add a try-catch statement.</span></span>

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

<span data-ttu-id="01beb-409">All'interno del blocco `try` iniziare a implementare la logica di rilevamento degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="01beb-409">Inside of the `try` block, start implementing the object detection logic.</span></span> <span data-ttu-id="01beb-410">Prima di tutto, caricare i dati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="01beb-410">First, load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

<span data-ttu-id="01beb-411">Creare quindi un'istanza di `OnnxModelScorer` e usarla per assegnare punteggi ai dati caricati.</span><span class="sxs-lookup"><span data-stu-id="01beb-411">Then, create an instance of `OnnxModelScorer` and use it to score the loaded data.</span></span>

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

<span data-ttu-id="01beb-412">È ora possibile passare alla fase di post-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-412">Now it's time for the post-processing step.</span></span> <span data-ttu-id="01beb-413">Creare un'istanza di `YoloOutputParser` e usarla per elaborare l'output del modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-413">Create an instance of `YoloOutputParser` and use it to process the model output.</span></span>

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

<span data-ttu-id="01beb-414">Dopo aver elaborato l'output del modello, è possibile tracciare i rettangoli di selezione sulle immagini.</span><span class="sxs-lookup"><span data-stu-id="01beb-414">Once the model output has been processed, it's time to draw the bounding boxes on the images.</span></span>

### <a name="visualize-predictions"></a><span data-ttu-id="01beb-415">Visualizzare stime</span><span class="sxs-lookup"><span data-stu-id="01beb-415">Visualize predictions</span></span>

<span data-ttu-id="01beb-416">Dopo che il modello ha assegnato un punteggio alle immagini e gli output sono stati elaborati, è necessario disegnare i rettangoli di selezione sull'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-416">After the model has scored the images and the outputs have been processed, the bounding boxes have to be drawn on the image.</span></span> <span data-ttu-id="01beb-417">A tale scopo, aggiungere un metodo denominato `DrawBoundingBox` sotto il metodo `GetAbsolutePath` all'interno di *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="01beb-417">To do so, add a method called `DrawBoundingBox` below the `GetAbsolutePath` method inside of *Program.cs*.</span></span>

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

<span data-ttu-id="01beb-418">Caricare prima di tutto l'immagine e ottenere le dimensioni di altezza e larghezza nel metodo `DrawBoundingBox`.</span><span class="sxs-lookup"><span data-stu-id="01beb-418">First, load the image and get the height and width dimensions in the `DrawBoundingBox` method.</span></span>

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

<span data-ttu-id="01beb-419">Creare quindi un ciclo for-each per eseguire l'iterazione di ogni rettangolo di selezione rilevato dal modello.</span><span class="sxs-lookup"><span data-stu-id="01beb-419">Then, create a for-each loop to iterate over each of the bounding boxes detected by the model.</span></span>

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

<span data-ttu-id="01beb-420">All'interno del ciclo for-each, ottenere le dimensioni del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-420">Inside of the for-each loop, get the dimensions of the bounding box.</span></span>

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

<span data-ttu-id="01beb-421">Poiché le dimensioni del rettangolo di selezione corrispondono all'input del modello di `416 x 416`, ridimensionare il rettangolo di selezione in modo che le sue dimensioni corrispondano a quelle effettive dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-421">Because the dimensions of the bounding box correspond to the model input of `416 x 416`, scale the bounding box dimensions to match the actual size of the image.</span></span>

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

<span data-ttu-id="01beb-422">Definire quindi un modello per il testo che verrà visualizzato al di sopra di ogni rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="01beb-422">Then, define a template for text that will appear above each bounding box.</span></span> <span data-ttu-id="01beb-423">Il testo conterrà la classe dell'oggetto all'interno del rispettivo rettangolo di selezione e la confidenza.</span><span class="sxs-lookup"><span data-stu-id="01beb-423">The text will contain the class of the object inside of the respective bounding box as well as the confidence.</span></span>

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

<span data-ttu-id="01beb-424">Per disegnare sull'immagine, convertirla in un oggetto [`Graphics`](xref:System.Drawing.Graphics).</span><span class="sxs-lookup"><span data-stu-id="01beb-424">In order to draw on the image, convert it to a [`Graphics`](xref:System.Drawing.Graphics) object.</span></span>

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{

}
```

<span data-ttu-id="01beb-425">All'interno del blocco di codice `using` ottimizzare le impostazioni dell'oggetto [`Graphics`](xref:System.Drawing.Graphics) del grafico.</span><span class="sxs-lookup"><span data-stu-id="01beb-425">Inside the `using` code block, tune the graphic's [`Graphics`](xref:System.Drawing.Graphics) object settings.</span></span>

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

<span data-ttu-id="01beb-426">Al di sotto, impostare le opzioni relative al tipo di carattere e al colore per il testo e il rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="01beb-426">Below that, set the font and color options for the text and bounding box.</span></span>

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

<span data-ttu-id="01beb-427">Creare e riempire un rettangolo sopra il rettangolo di selezione per contenere il testo usando il metodo [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*).</span><span class="sxs-lookup"><span data-stu-id="01beb-427">Create and fill a rectangle above the bounding box to contain the text using the [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*) method.</span></span> <span data-ttu-id="01beb-428">Ciò consentirà di creare un contrasto per il testo e migliorare la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="01beb-428">This will help contrast the text and improve readability.</span></span>

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

<span data-ttu-id="01beb-429">Disegnare quindi il testo e il rettangolo di selezione nell'immagine usando i metodi [`DrawString`](xref:System.Drawing.Graphics.DrawString*) e [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*).</span><span class="sxs-lookup"><span data-stu-id="01beb-429">Then, Draw the text and bounding box on the image using the [`DrawString`](xref:System.Drawing.Graphics.DrawString*) and [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*) methods.</span></span>

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

<span data-ttu-id="01beb-430">Al di fuori del ciclo for-each aggiungere il codice per salvare le immagini in `outputDirectory`.</span><span class="sxs-lookup"><span data-stu-id="01beb-430">Outside of the for-each loop, add code to save the images in the `outputDirectory`.</span></span>

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

<span data-ttu-id="01beb-431">Per ottenere un ulteriore riscontro che l'applicazione stia eseguendo le stime come previsto in fase di runtime, aggiungere un metodo denominato `LogDetectedObjects` sotto il metodo `DrawBoundingBox` nel file *Program.cs* per restituire gli oggetti rilevati nella console.</span><span class="sxs-lookup"><span data-stu-id="01beb-431">For additional feedback that the application is making predictions as expected at runtime, add a method called `LogDetectedObjects` below the `DrawBoundingBox` method in the *Program.cs* file to output the detected objects to the console.</span></span>

[!code-csharp [LogOutputs](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

<span data-ttu-id="01beb-432">Ora che sono disponibili metodi helper per creare un riscontro visivo dalle stime, aggiungere un ciclo for per scorrere ognuna delle immagini con punteggio.</span><span class="sxs-lookup"><span data-stu-id="01beb-432">Now that you have helper methods to create visual feedback from the predictions, add a for-loop to iterate over each of the scored images.</span></span>

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

<span data-ttu-id="01beb-433">All'interno del ciclo for ottenere il nome del file di immagine e dei rettangoli di selezione associati.</span><span class="sxs-lookup"><span data-stu-id="01beb-433">Inside of the for-loop, get the name of the image file and the bounding boxes associated with it.</span></span>

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

<span data-ttu-id="01beb-434">Sotto questo codice usare il metodo `DrawBoundingBox` per tracciare i rettangoli di selezione sull'immagine.</span><span class="sxs-lookup"><span data-stu-id="01beb-434">Below that, use the `DrawBoundingBox` method to draw the bounding boxes on the image.</span></span>

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

<span data-ttu-id="01beb-435">Infine, usare il metodo `LogDetectedObjects` per restituire le stime alla console.</span><span class="sxs-lookup"><span data-stu-id="01beb-435">Lastly, use the `LogDetectedObjects` method to output predictions to the console.</span></span>

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

<span data-ttu-id="01beb-436">Dopo l'istruzione try-catch aggiungere logica aggiuntiva per indicare che l'esecuzione del processo è stata completata.</span><span class="sxs-lookup"><span data-stu-id="01beb-436">After the try-catch statement, add additional logic to indicate the process is done running.</span></span>

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

<span data-ttu-id="01beb-437">La procedura è terminata.</span><span class="sxs-lookup"><span data-stu-id="01beb-437">That's it!</span></span>

## <a name="results"></a><span data-ttu-id="01beb-438">Risultati</span><span class="sxs-lookup"><span data-stu-id="01beb-438">Results</span></span>

<span data-ttu-id="01beb-439">Dopo aver completato i passaggi precedenti, eseguire l'app console (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="01beb-439">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="01beb-440">I risultati saranno simili all'output seguente.</span><span class="sxs-lookup"><span data-stu-id="01beb-440">Your results should be similar to the following output.</span></span> <span data-ttu-id="01beb-441">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="01beb-441">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=====Identify the objects in the images=====

.....The objects in the image image1.jpg are detected as below....
car and its Confidence score: 0.9697262
car and its Confidence score: 0.6674225
person and its Confidence score: 0.5226039
car and its Confidence score: 0.5224892
car and its Confidence score: 0.4675332

.....The objects in the image image2.jpg are detected as below....
cat and its Confidence score: 0.6461141
cat and its Confidence score: 0.6400049

.....The objects in the image image3.jpg are detected as below....
chair and its Confidence score: 0.840578
chair and its Confidence score: 0.796363
diningtable and its Confidence score: 0.6056048
diningtable and its Confidence score: 0.3737402

.....The objects in the image image4.jpg are detected as below....
dog and its Confidence score: 0.7608147
person and its Confidence score: 0.6321323
dog and its Confidence score: 0.5967442
person and its Confidence score: 0.5730394
person and its Confidence score: 0.5551759

========= End of Process..Hit any Key ========
```

<span data-ttu-id="01beb-442">Per visualizzare le immagini con i rettangoli di selezione, passare alla directory `assets/images/output/`.</span><span class="sxs-lookup"><span data-stu-id="01beb-442">To see the images with bounding boxes, navigate to the `assets/images/output/` directory.</span></span> <span data-ttu-id="01beb-443">Di seguito viene fornito un esempio da una delle immagini elaborate.</span><span class="sxs-lookup"><span data-stu-id="01beb-443">Below is a sample from one of the processed images.</span></span>

![Esempio di immagine elaborata di una sala da pranzo](./media/object-detection-onnx/dinning-room-table-chairs.png)

<span data-ttu-id="01beb-445">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="01beb-445">Congratulations!</span></span> <span data-ttu-id="01beb-446">È stato creato un modello di Machine Learning per il rilevamento di oggetti riutilizzando un modello `ONNX` già sottoposto a training in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="01beb-446">You've now successfully built a machine learning model for object detection by reusing a pre-trained `ONNX` model in ML.NET.</span></span>

<span data-ttu-id="01beb-447">Il codice sorgente per questa esercitazione è reperibile nel repository [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) .</span><span class="sxs-lookup"><span data-stu-id="01beb-447">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) repository.</span></span>

<span data-ttu-id="01beb-448">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="01beb-448">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="01beb-449">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="01beb-449">Understand the problem</span></span>
> - <span data-ttu-id="01beb-450">Acquisire familiarità con ONNX e comprenderne il funzionamento con ML.NET</span><span class="sxs-lookup"><span data-stu-id="01beb-450">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="01beb-451">Acquisire familiarità con il modello</span><span class="sxs-lookup"><span data-stu-id="01beb-451">Understand the model</span></span>
> - <span data-ttu-id="01beb-452">Riutilizzare il modello già sottoposto a training</span><span class="sxs-lookup"><span data-stu-id="01beb-452">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="01beb-453">Rilevare oggetti con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="01beb-453">Detect objects with a loaded model</span></span>

<span data-ttu-id="01beb-454">Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di rilevamento di oggetti esteso.</span><span class="sxs-lookup"><span data-stu-id="01beb-454">Check out the Machine Learning samples GitHub repository to explore an expanded object detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="01beb-455">Repository GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="01beb-455">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)
