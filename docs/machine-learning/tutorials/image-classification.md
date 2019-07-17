---
title: 'Esercitazione: Ripetere il training del classificatore di immagini TensorFlow - apprendimento trasferito'
description: Informazioni su come ripetere il training di un modello TensorFlow di classificazione delle immagini con l'apprendimento trasferito e ML.NET. Il modello originale è stato sottoposto a training per classificare le singole immagini. Dopo la ripetizione del training, il nuovo modello organizza le immagini in categorie ampie.
ms.date: 07/09/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 65f94fa5e725703d79d0dddae761cbfbc3f89e0e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804752"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a><span data-ttu-id="15fd5-105">Esercitazione: Ripetere il training di un classificatore di immagini TensorFlow con l'apprendimento trasferito e ML.NET</span><span class="sxs-lookup"><span data-stu-id="15fd5-105">Tutorial: Retrain a TensorFlow image classifier with transfer learning and ML.NET</span></span>

<span data-ttu-id="15fd5-106">Informazioni su come ripetere il training di un modello TensorFlow di classificazione delle immagini con l'apprendimento trasferito e ML.NET.</span><span class="sxs-lookup"><span data-stu-id="15fd5-106">Learn how to retrain an image classification TensorFlow model with transfer learning and ML.NET.</span></span> <span data-ttu-id="15fd5-107">Il modello originale è stato sottoposto a training per classificare le singole immagini.</span><span class="sxs-lookup"><span data-stu-id="15fd5-107">The original model was trained to classify individual images.</span></span> <span data-ttu-id="15fd5-108">Dopo la ripetizione del training, il nuovo modello organizza le immagini in categorie ampie.</span><span class="sxs-lookup"><span data-stu-id="15fd5-108">After retraining, the new model organizes the images into broad categories.</span></span> 

<span data-ttu-id="15fd5-109">Il training di un modello di [classificazione delle immagini](https://en.wikipedia.org/wiki/Outline_of_object_recognition) da zero richiede l'impostazione di milioni di parametri, di una considerevole quantità di dati di training con etichetta e di un notevole importo di risorse di calcolo (centinaia di ore di GPU).</span><span class="sxs-lookup"><span data-stu-id="15fd5-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="15fd5-110">Anche se non è così efficace come il training di un modello personalizzato da zero, l'apprendimento trasferito consente di semplificare questo processo usando migliaia di immagini anziché milioni di immagini con etichetta e di creare un modello personalizzato abbastanza rapidamente (entro un'ora in un computer senza GPU).</span><span class="sxs-lookup"><span data-stu-id="15fd5-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="15fd5-111">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="15fd5-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="15fd5-112">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="15fd5-112">Understand the problem</span></span>
> * <span data-ttu-id="15fd5-113">Riutilizzare e ottimizzare il modello con training preliminare</span><span class="sxs-lookup"><span data-stu-id="15fd5-113">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="15fd5-114">Classificare le immagini</span><span class="sxs-lookup"><span data-stu-id="15fd5-114">Classify Images</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="15fd5-115">Che cos'è l'apprendimento trasferito?</span><span class="sxs-lookup"><span data-stu-id="15fd5-115">What is transfer learning?</span></span>

<span data-ttu-id="15fd5-116">Sarebbe bello poter riutilizzare un modello che è già stato sottoposto a training per risolvere un problema analogo e rieseguire il training di tutti o di alcuni livelli di tale modello per risolvere un problema riscontrato.</span><span class="sxs-lookup"><span data-stu-id="15fd5-116">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="15fd5-117">Questa tecnica che prevede il riutilizzo di parte di un modello già sottoposto a training per crearne uno nuovo è nota come [apprendimento trasferito](https://en.wikipedia.org/wiki/Transfer_learning).</span><span class="sxs-lookup"><span data-stu-id="15fd5-117">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="15fd5-118">Panoramica dell'esempio di classificazione delle immagini</span><span class="sxs-lookup"><span data-stu-id="15fd5-118">Image classification sample overview</span></span>

<span data-ttu-id="15fd5-119">L'esempio è un'applicazione console che usa ML.NET per creare un classificatore di immagini riutilizzando un modello con training preliminare per classificare le immagini con una piccola quantità di dati di training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-119">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="15fd5-120">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="15fd5-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="15fd5-121">Si noti che per impostazione predefinita il progetto .NET per questa esercitazione è configurato per .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="15fd5-121">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15fd5-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="15fd5-122">Prerequisites</span></span>

* <span data-ttu-id="15fd5-123">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="15fd5-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span> 

* <span data-ttu-id="15fd5-124">Pacchetto NuGet Microsoft.ML 1.0.0</span><span class="sxs-lookup"><span data-stu-id="15fd5-124">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="15fd5-125">Pacchetto NuGet Microsoft.ML.ImageAnalytics 1.0.0</span><span class="sxs-lookup"><span data-stu-id="15fd5-125">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="15fd5-126">Pacchetto NuGet Microsoft.ML.TensorFlow 0.12.0</span><span class="sxs-lookup"><span data-stu-id="15fd5-126">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="15fd5-127">File ZIP della directory assets dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="15fd5-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="15fd5-128">Modello di Machine Learning InceptionV1</span><span class="sxs-lookup"><span data-stu-id="15fd5-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="15fd5-129">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="15fd5-129">Select the appropriate machine learning task</span></span>

<span data-ttu-id="15fd5-130">Il [Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) è un subset di Machine Learning che sta rivoluzionando aree quali Visione artificiale e Riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="15fd5-130">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="15fd5-131">I modelli di Deep Learning vengono sottoposti a training con set di grandi dimensioni di [dati con etichetta](https://en.wikipedia.org/wiki/Labeled_data) e [reti neurali](https://en.wikipedia.org/wiki/Artificial_neural_network) contenenti più livelli di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="15fd5-131">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="15fd5-132">Il Deep Learning:</span><span class="sxs-lookup"><span data-stu-id="15fd5-132">Deep learning:</span></span>

* <span data-ttu-id="15fd5-133">Offre prestazioni ottimali per alcune attività come Visione artificiale.</span><span class="sxs-lookup"><span data-stu-id="15fd5-133">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="15fd5-134">Assicura buone prestazioni con quantità di dati molto elevate.</span><span class="sxs-lookup"><span data-stu-id="15fd5-134">Performs well on huge data amounts.</span></span>

<span data-ttu-id="15fd5-135">La classificazione delle immagini è un'attività comune di Machine Learning che consente di classificare automaticamente le immagini in più categorie, ad esempio tramite:</span><span class="sxs-lookup"><span data-stu-id="15fd5-135">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="15fd5-136">Rilevamento di un volto umano in un'immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-136">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="15fd5-137">Rilevamento di cani o gatti.</span><span class="sxs-lookup"><span data-stu-id="15fd5-137">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="15fd5-138">Oppure, come nelle immagini seguenti, determinando se un'immagine appartiene alla categoria dei cibi, dei giocattoli o degli elettrodomestici:</span><span class="sxs-lookup"><span data-stu-id="15fd5-138">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="15fd5-139">![immagine di una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![immagine di un orsetto](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![immagine di un tostapane](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="15fd5-139">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="15fd5-140">Le immagini precedenti appartengono a Wikimedia Commons, con gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-140">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="15fd5-141">"220px-Pepperoni_pizza.jpg" pubblico dominio, https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="15fd5-141">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="15fd5-142">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" di [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Fotografia autoprodotta, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="15fd5-142">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="15fd5-143">"193px-Broodrooster.jpg" di [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Opera propria, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="15fd5-143">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="15fd5-144">L'apprendimento trasferito prevede alcune strategie, come la *ripetizione del training di tutti i livelli* e il *penultimo livello*.</span><span class="sxs-lookup"><span data-stu-id="15fd5-144">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="15fd5-145">Questa esercitazione illustrerà e spiegherà come usare la *strategia del penultimo livello*.</span><span class="sxs-lookup"><span data-stu-id="15fd5-145">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="15fd5-146">La *strategia del penultimo livello* riutilizza un modello che è già stato sottoposto a training per risolvere un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="15fd5-146">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="15fd5-147">Questa strategia prevede quindi la ripetizione del training del livello finale del modello per consentire la risoluzione di un nuovo problema.</span><span class="sxs-lookup"><span data-stu-id="15fd5-147">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="15fd5-148">Il riutilizzo del modello già sottoposto a training nell'ambito del nuovo modello comporterà un risparmio significativo di tempo e risorse.</span><span class="sxs-lookup"><span data-stu-id="15fd5-148">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="15fd5-149">Il modello di classificazione delle immagini riutilizza il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), un modello di riconoscimento delle immagini ampiamente diffuso sottoposto a training con il set di dati `ImageNet`, in cui il modello TensorFlow prova a classificare intere immagini in migliaia di classi, come "Umbrella", "Jersey" e "Dishwasher".</span><span class="sxs-lookup"><span data-stu-id="15fd5-149">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="15fd5-150">`Inception v1 model` può essere classificato come una [rete neurale convoluzionale profonda](https://en.wikipedia.org/wiki/Convolutional_neural_network) e può ottenere prestazioni ragionevoli con attività di riconoscimento visivo complesse, uguagliando o superando le prestazioni umane in alcuni campi.</span><span class="sxs-lookup"><span data-stu-id="15fd5-150">The `Inception v1 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="15fd5-151">Il modello/algoritmo è stato sviluppato da più ricercatori ed è basato sul whitepaper originale ["Rethinking the Inception Architecture for Computer Vision" a cura di Szegedy e altri autori](https://arxiv.org/abs/1512.00567).</span><span class="sxs-lookup"><span data-stu-id="15fd5-151">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="15fd5-152">Poiché il `Inception model` è già stato sottoposto a training con migliaia di immagini diverse, contiene le [caratteristiche delle immagini](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necessarie per la loro identificazione.</span><span class="sxs-lookup"><span data-stu-id="15fd5-152">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="15fd5-153">I livelli delle caratteristiche delle immagini inferiori riconoscono caratteristiche semplici (come i contorni), mentre quelli più elevati riconoscono caratteristiche più complesse (come le forme).</span><span class="sxs-lookup"><span data-stu-id="15fd5-153">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="15fd5-154">Il livello finale è sottoposto a training con un set di dati molto più piccolo perché si inizia con un modello con training preliminare che è già in grado di classificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="15fd5-154">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="15fd5-155">Dal momento che il modello consente di classificare più di due categorie, questo è un esempio di un [classificatore multiclasse](../resources/tasks.md#multiclass-classification).</span><span class="sxs-lookup"><span data-stu-id="15fd5-155">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="15fd5-156">`TensorFlow` è un popolare toolkit di Deep Learning e Machine Learning che consente il training delle reti neurali profonde (e i calcoli numerici generali) e viene implementato come `transformer` in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="15fd5-156">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="15fd5-157">Per questa esercitazione, viene usato per riutilizzare il `Inception model`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-157">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="15fd5-158">Come illustrato nel diagramma seguente, viene aggiunto un riferimento ai pacchetti NuGet ML.NET nelle applicazioni .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="15fd5-158">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="15fd5-159">Dietro le quinte, ML.NET include e fa riferimento alla libreria `TensorFlow` nativa che consente di scrivere codice che carica un file del modello `TensorFlow` esistente già sottoposto a training per l'assegnazione del punteggio.</span><span class="sxs-lookup"><span data-stu-id="15fd5-159">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![Diagramma dell'architettura ML.NET per la trasformazione TensorFlow](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="15fd5-161">Il `Inception model` viene sottoposto a training per classificare le immagini in migliaia di categorie, ma è necessario classificare le immagini in un set più piccolo di categorie limitate.</span><span class="sxs-lookup"><span data-stu-id="15fd5-161">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="15fd5-162">Specificare la parte `transfer` di `transfer learning`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-162">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="15fd5-163">È possibile trasferire la capacità del `Inception model` di riconoscere e classificare le immagini alle nuove categorie limitate del classificatore di immagini personalizzato.</span><span class="sxs-lookup"><span data-stu-id="15fd5-163">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="15fd5-164">Si intende ripetere il training dell'ultimo livello di tale modello usando un set di tre categorie:</span><span class="sxs-lookup"><span data-stu-id="15fd5-164">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="15fd5-165">Cibo</span><span class="sxs-lookup"><span data-stu-id="15fd5-165">Food</span></span>
* <span data-ttu-id="15fd5-166">Giocattoli</span><span class="sxs-lookup"><span data-stu-id="15fd5-166">Toy</span></span>
* <span data-ttu-id="15fd5-167">Elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="15fd5-167">Appliance</span></span>

<span data-ttu-id="15fd5-168">Il livello usa un [algoritmo di regressione logistica multinomiale](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) per trovare la categoria corretta nel minor tempo possibile.</span><span class="sxs-lookup"><span data-stu-id="15fd5-168">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="15fd5-169">Questo algoritmo procede alla classificazione tramite l'uso delle probabilità per determinare la risposta, assegnando un valore uno alla categoria corretta e un valore zero alle altre.</span><span class="sxs-lookup"><span data-stu-id="15fd5-169">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="15fd5-170">DataSet</span><span class="sxs-lookup"><span data-stu-id="15fd5-170">DataSet</span></span>

<span data-ttu-id="15fd5-171">Ci sono due origini dati: il file `.tsv` e i file di immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-171">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="15fd5-172">Il file `tags.tsv` contiene due colonne: la prima è definita come `ImagePath` e la seconda è l'oggetto `Label` corrispondente all'immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-172">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="15fd5-173">Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-173">The following example file doesn't have a header row, and looks like this:</span></span>

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="15fd5-174">Le immagini di training e di test si trovano nelle cartelle assets che verranno scaricate in un file ZIP.</span><span class="sxs-lookup"><span data-stu-id="15fd5-174">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="15fd5-175">Queste immagini appartengono a Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="15fd5-175">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="15fd5-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), il repository di file multimediali gratuiti.*</span><span class="sxs-lookup"><span data-stu-id="15fd5-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="15fd5-177">Recuperate il 17 ottobre 2018, alle 10.48, da:</span><span class="sxs-lookup"><span data-stu-id="15fd5-177">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="15fd5-178">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="15fd5-178">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="15fd5-179">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="15fd5-179">Create a project</span></span>

1. <span data-ttu-id="15fd5-180">Creare un'**applicazione console di .NET Core** con nome "TransferLearningTF".</span><span class="sxs-lookup"><span data-stu-id="15fd5-180">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="15fd5-181">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="15fd5-181">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="15fd5-182">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-182">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="15fd5-183">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-183">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="15fd5-184">Fare clic sull'elenco a discesa **Versione**, selezionare il pacchetto **1.0.0** nell'elenco e quindi il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-184">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="15fd5-185">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="15fd5-185">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="15fd5-186">Ripetere questi passaggi per **Microsoft.ML.ImageAnalytics v1.0.0** e **Microsoft.ML.TensorFlow v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-186">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="15fd5-187">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="15fd5-187">Prepare your data</span></span>

1. <span data-ttu-id="15fd5-188">Scaricare il [file ZIP della directory assets del progetto](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) e decomprimerlo.</span><span class="sxs-lookup"><span data-stu-id="15fd5-188">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="15fd5-189">Copiare la directory `assets` nella directory del progetto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="15fd5-189">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="15fd5-190">Questa directory e le relative sottodirectory contengono i file di dati e supporto (fatta eccezione per il modello Inception, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="15fd5-190">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="15fd5-191">Scaricare il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) e decomprimere il file.</span><span class="sxs-lookup"><span data-stu-id="15fd5-191">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="15fd5-192">Copiare il contenuto della directory `inception5h` appena decompressa nella directory `assets\inputs-train\inception` del progetto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="15fd5-192">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="15fd5-193">Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-193">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Contenuto della directory Inception](./media/image-classification/inception-files.png)

5. <span data-ttu-id="15fd5-195">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-195">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="15fd5-196">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-196">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="15fd5-197">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="15fd5-197">Create classes and define paths</span></span>

<span data-ttu-id="15fd5-198">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="15fd5-198">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="15fd5-199">Creare campi globali per i percorsi delle diverse risorse e variabili globali per `LabelTokey`, `ImageReal` e `PredictedLabelValue`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-199">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="15fd5-200">`_assetsPath` contiene il percorso delle risorse.</span><span class="sxs-lookup"><span data-stu-id="15fd5-200">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="15fd5-201">`_trainTagsTsv` contiene il percorso del file TSV dei tag dei dati delle immagini di training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-201">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="15fd5-202">`_predictTagsTsv` contiene il percorso del file TSV dei tag dei dati delle immagini di stima.</span><span class="sxs-lookup"><span data-stu-id="15fd5-202">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="15fd5-203">`_trainImagesFolder` contiene il percorso delle immagini usate per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-203">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="15fd5-204">`_predictImagesFolder` contiene il percorso delle immagini che devono essere classificate dal modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-204">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="15fd5-205">`_inceptionPb` contiene il percorso del modello Inception con training preliminare da riutilizzare per ripetere il training del modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-205">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="15fd5-206">`_inputImageClassifierZip` contiene il percorso da cui viene caricato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-206">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="15fd5-207">`_outputImageClassifierZip` contiene il percorso in cui è salvato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-207">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="15fd5-208">`LabelTokey` è il valore `Label` associato a una chiave.</span><span class="sxs-lookup"><span data-stu-id="15fd5-208">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="15fd5-209">`ImageReal` è la colonna contenente il valore dell'immagine stimato.</span><span class="sxs-lookup"><span data-stu-id="15fd5-209">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="15fd5-210">`PredictedLabelValue` è la colonna contenente il valore dell'etichetta stimato.</span><span class="sxs-lookup"><span data-stu-id="15fd5-210">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="15fd5-211">Aggiungere il codice seguente nella riga subito sopra il metodo `Main` per specificare questi percorsi e le altre variabili:</span><span class="sxs-lookup"><span data-stu-id="15fd5-211">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="15fd5-212">Creare alcune classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="15fd5-212">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="15fd5-213">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="15fd5-213">Add a new class to your project:</span></span>

1. <span data-ttu-id="15fd5-214">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-214">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="15fd5-215">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ImageData.cs*.</span><span class="sxs-lookup"><span data-stu-id="15fd5-215">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="15fd5-216">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-216">Then, select the **Add** button.</span></span>

    <span data-ttu-id="15fd5-217">Il file *ImageData.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="15fd5-217">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="15fd5-218">Aggiungere l'istruzione `using` seguente all'inizio di *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="15fd5-218">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="15fd5-219">Rimuovere la definizione di classe esistente e aggiungere il codice seguente per la classe `ImageData` al file *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="15fd5-219">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="15fd5-220">`ImageData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-220">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="15fd5-221">`ImagePath` contiene il nome del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-221">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="15fd5-222">`Label` contiene un valore per l'etichetta dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-222">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="15fd5-223">Aggiungere una nuova classe al progetto per `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-223">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="15fd5-224">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-224">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="15fd5-225">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ImagePrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="15fd5-225">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="15fd5-226">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-226">Then, select the **Add** button.</span></span>

    <span data-ttu-id="15fd5-227">Il file *ImagePrediction.cs* verrà aperto nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="15fd5-227">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="15fd5-228">Rimuovere entrambe le istruzioni `using` `System.Collections.Generic` e `System.Text` all'inizio di *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="15fd5-228">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="15fd5-229">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene la classe `ImagePrediction`, al file *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="15fd5-229">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="15fd5-230">`ImagePrediction` è la classe di stima delle immagini e ha i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-230">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="15fd5-231">`Score` contiene la percentuale di probabilità per una data classificazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-231">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="15fd5-232">`PredictedLabelValue` contiene un valore per l'etichetta di classificazione dell'immagine stimata.</span><span class="sxs-lookup"><span data-stu-id="15fd5-232">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="15fd5-233">`ImagePrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-233">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="15fd5-234">Ha un oggetto `string` (`ImagePath`) per il percorso dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-234">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="15fd5-235">L'elemento `Label` viene usato per riutilizzare il modello e ripeterne il training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-235">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="15fd5-236">`PredictedLabelValue` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="15fd5-236">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="15fd5-237">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-237">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="15fd5-238">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-238">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="15fd5-239">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="15fd5-239">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="15fd5-240">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="15fd5-240">Initialize variables in Main</span></span>

<span data-ttu-id="15fd5-241">Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-241">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="15fd5-242">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-242">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="15fd5-243">Creare uno struct per i parametri predefiniti</span><span class="sxs-lookup"><span data-stu-id="15fd5-243">Create a struct for default parameters</span></span>

<span data-ttu-id="15fd5-244">Il modello Inception ha diversi parametri predefiniti che è necessario passare.</span><span class="sxs-lookup"><span data-stu-id="15fd5-244">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="15fd5-245">Creare uno struct per eseguire il mapping dei valori dei parametri predefiniti a nomi descrittivi con il codice seguente, subito dopo il metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-245">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="15fd5-246">Creare un metodo dell'utilità di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="15fd5-246">Create a display utility method</span></span>

<span data-ttu-id="15fd5-247">Poiché i dati dell'immagine e le relative stime verranno visualizzati più volte, creare un metodo dell'utilità di visualizzazione per gestire la visualizzazione dell'immagine e dei risultati delle stime.</span><span class="sxs-lookup"><span data-stu-id="15fd5-247">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="15fd5-248">Il metodo `DisplayResults()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-248">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="15fd5-249">Visualizza i risultati stimati.</span><span class="sxs-lookup"><span data-stu-id="15fd5-249">Displays the predicted results.</span></span>

<span data-ttu-id="15fd5-250">Creare il metodo `DisplayResults()` subito dopo lo struct `InceptionSettings`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-250">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="15fd5-251">Il metodo `Transform()` ha popolato `ImagePath` in `ImagePrediction` insieme ai campi stimati.</span><span class="sxs-lookup"><span data-stu-id="15fd5-251">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="15fd5-252">Nel corso del processo ML.NET ogni componente aggiunge colonne e ciò rende più facile visualizzare i risultati:</span><span class="sxs-lookup"><span data-stu-id="15fd5-252">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="15fd5-253">Verrà chiamato il metodo `DisplayResults()` nei due metodi di classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="15fd5-253">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="15fd5-254">Creare un metodo dell'utilità con file TSV</span><span class="sxs-lookup"><span data-stu-id="15fd5-254">Create a .tsv file utility method</span></span>

<span data-ttu-id="15fd5-255">Il metodo `ReadFromTsv()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-255">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="15fd5-256">Legge il file `tags.tsv` dei dati di immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-256">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="15fd5-257">Aggiunge il percorso del file al nome del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="15fd5-257">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="15fd5-258">Carica i dati del file in un oggetto IEnumerable`ImageData`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-258">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="15fd5-259">Creare il metodo `ReadFromTsv()` subito dopo il metodo `PairAndDisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-259">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="15fd5-260">Il codice seguente analizza il file `tags.tsv` per aggiungere il percorso del file al nome del file di immagine per la proprietà `ImagePath` e carica `Label` in un oggetto `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-260">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="15fd5-261">Aggiungerlo come prima riga del metodo `ReadFromTsv()`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-261">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="15fd5-262">È necessario il percorso completo del file per visualizzare i risultati della stima.</span><span class="sxs-lookup"><span data-stu-id="15fd5-262">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="15fd5-263">ML.NET si basa su tre concetti fondamentali: [dati](../resources/glossary.md#data), [trasformatori](../resources/glossary.md#transformer) e [strumenti di stima](../resources/glossary.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="15fd5-263">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="15fd5-264">Riutilizzare e ottimizzare il modello con training preliminare</span><span class="sxs-lookup"><span data-stu-id="15fd5-264">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="15fd5-265">Aggiungere la seguente chiamata al metodo `ReuseAndTuneInceptionModel()` come riga successiva nel metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-265">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="15fd5-266">Il metodo `ReuseAndTuneInceptionModel()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-266">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="15fd5-267">Carica i dati.</span><span class="sxs-lookup"><span data-stu-id="15fd5-267">Loads the data</span></span>
* <span data-ttu-id="15fd5-268">Estrae e trasforma i dati.</span><span class="sxs-lookup"><span data-stu-id="15fd5-268">Extracts and transforms the data.</span></span>
* <span data-ttu-id="15fd5-269">Assegna un punteggio al modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="15fd5-269">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="15fd5-270">Ottimizza il modello (ripete il training).</span><span class="sxs-lookup"><span data-stu-id="15fd5-270">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="15fd5-271">Visualizza i risultati del modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-271">Displays model results.</span></span>
* <span data-ttu-id="15fd5-272">Valuta il modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-272">Evaluates the model.</span></span>
* <span data-ttu-id="15fd5-273">Restituisce il modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-273">Returns the model.</span></span>

<span data-ttu-id="15fd5-274">Creare il metodo `ReuseAndTuneInceptionModel()`, subito dopo lo struct `InceptionSettings` e subito prima del metodo `DisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-274">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="15fd5-275">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="15fd5-275">Load the data</span></span>

<span data-ttu-id="15fd5-276">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="15fd5-276">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="15fd5-277">`IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="15fd5-277">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="15fd5-278">È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-278">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="15fd5-279">Caricare i dati usando il wrapper `MLContext.Data.LoadFromTextFile`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-279">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="15fd5-280">Aggiungere il codice seguente al metodo `ReuseAndTuneInceptionModel()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="15fd5-280">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="15fd5-281">Estrarre le funzionalità e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="15fd5-281">Extract Features and transform the data</span></span>

<span data-ttu-id="15fd5-282">La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="15fd5-282">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="15fd5-283">L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.</span><span class="sxs-lookup"><span data-stu-id="15fd5-283">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="15fd5-284">Gli algoritmi di Machine Learning sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) e quando si ha a che fare con reti neurali profonde è necessario adattare le immagini al formato previsto dalla rete.</span><span class="sxs-lookup"><span data-stu-id="15fd5-284">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="15fd5-285">Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="15fd5-285">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="15fd5-286">Dopo il training e la valutazione, eseguire una stima con i valori della colonna **Etichetta**.</span><span class="sxs-lookup"><span data-stu-id="15fd5-286">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="15fd5-287">Dal momento che si usa un modello con training preliminare, eseguire il mapping dei campi al nuovo modello con il metodo [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A).</span><span class="sxs-lookup"><span data-stu-id="15fd5-287">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="15fd5-288">Questo metodo trasforma `Label` in una colonna di tipo chiave numerica (`LabelTokey`) aggiungendola come nuova colonna del set di dati.  Assegnare il nome `estimator` dal momento che verrà aggiunto anche l'algoritmo di training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-288">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="15fd5-289">Aggiungere la riga di codice successiva:</span><span class="sxs-lookup"><span data-stu-id="15fd5-289">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="15fd5-290">Lo strumento di stima per l'elaborazione delle immagini usa algoritmi di estrazione delle caratteristiche della [rete neurale profonda](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) con training preliminare per l'estrazione delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="15fd5-290">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="15fd5-291">Quando si usano reti neurali profonde, si adattano le immagini al formato di rete previsto.</span><span class="sxs-lookup"><span data-stu-id="15fd5-291">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="15fd5-292">Questo è il motivo per cui si usano numerose trasformazioni delle immagini per ottenere i dati di immagine nel formato previsto del modello:</span><span class="sxs-lookup"><span data-stu-id="15fd5-292">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="15fd5-293">Le immagini della trasformazione `LoadImages` vengono caricate in memoria come tipo bitmap.</span><span class="sxs-lookup"><span data-stu-id="15fd5-293">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="15fd5-294">La trasformazione `ResizeImages` ridimensiona le immagini dal momento che il modello con training preliminare ha una larghezza e un'altezza definite dell'immagine di input.</span><span class="sxs-lookup"><span data-stu-id="15fd5-294">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="15fd5-295">La trasformazione `ExtractPixels` estrae i pixel dalle immagini di input e li converte in un vettore numerico.</span><span class="sxs-lookup"><span data-stu-id="15fd5-295">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="15fd5-296">Aggiungere queste trasformazioni delle immagini come righe di codice successive:</span><span class="sxs-lookup"><span data-stu-id="15fd5-296">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="15fd5-297">`LoadTensorFlowModel` è un metodo pratico che consente di caricare il modello `TensorFlow` una sola volta e quindi crea `TensorFlowEstimator` usando `ScoreTensorFlowModel`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-297">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="15fd5-298">`ScoreTensorFlowModel` estrae gli output specificati (le caratteristiche dell'immagine `softmax2_pre_activation` di `Inception model`) e assegna un punteggio a un set di dati usando il modello `TensorFlow` con training preliminare.</span><span class="sxs-lookup"><span data-stu-id="15fd5-298">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="15fd5-299">`softmax2_pre_activation` supporta il modello nella determinazione della classe a cui appartengono le immagini.</span><span class="sxs-lookup"><span data-stu-id="15fd5-299">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="15fd5-300">`softmax2_pre_activation` restituisce una probabilità per ognuna delle categorie per un'immagine e tutte queste probabilità devono ammontare a 1.</span><span class="sxs-lookup"><span data-stu-id="15fd5-300">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="15fd5-301">Si presuppone che un'immagine apparterrà solo a una categoria, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-301">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="15fd5-302">Classe</span><span class="sxs-lookup"><span data-stu-id="15fd5-302">Class</span></span>         | <span data-ttu-id="15fd5-303">Probabilità</span><span class="sxs-lookup"><span data-stu-id="15fd5-303">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="15fd5-304">0.001</span><span class="sxs-lookup"><span data-stu-id="15fd5-304">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="15fd5-305">0.95</span><span class="sxs-lookup"><span data-stu-id="15fd5-305">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="15fd5-306">0.06</span><span class="sxs-lookup"><span data-stu-id="15fd5-306">0.06</span></span>         |

<span data-ttu-id="15fd5-307">Aggiungere `TensorFlowTransform` a `estimator` con la riga di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-307">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="15fd5-308">Scegliere un algoritmo di training</span><span class="sxs-lookup"><span data-stu-id="15fd5-308">Choose a training algorithm</span></span>

<span data-ttu-id="15fd5-309">Per aggiungere l'algoritmo di training, chiamare il metodo wrapper `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-309">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="15fd5-310">L'oggetto [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) viene aggiunto a `estimator` e accetta le caratteristiche delle immagini di Inception (`softmax2_pre_activation`) e i parametri di input `Label` per l'apprendimento dai dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="15fd5-310">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="15fd5-311">Aggiungere l'algoritmo di training con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-311">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="15fd5-312">È anche necessario eseguire il mapping di `predictedlabel` a `predictedlabelvalue`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-312">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="15fd5-313">Il metodo `Fit()` esegue il training del modello trasformando il set di dati e applicando il training.</span><span class="sxs-lookup"><span data-stu-id="15fd5-313">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="15fd5-314">Eseguire il fit del modello al set di dati e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-314">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="15fd5-315">Il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) effettua previsioni per più righe di input specificate di un set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="15fd5-315">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="15fd5-316">Trasformare i dati `Training` aggiungendo il codice seguente a `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-316">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="15fd5-317">Convertire i dati di immagine e gli elementi `DataViews` della stima in `IEnumerables` fortemente tipizzati per associarli per una visualizzazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="15fd5-317">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="15fd5-318">Usare il metodo `MLContext.CreateEnumerable()` a tale scopo, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-318">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="15fd5-319">Chiamare il metodo `DisplayResults()` per visualizzare i dati e le stime come riga successiva nel metodo `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-319">Call the `DisplayResults()` method to display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="15fd5-320">Dopo aver impostato la stima, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):</span><span class="sxs-lookup"><span data-stu-id="15fd5-320">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="15fd5-321">Valuta il modello (confrontando i valori stimati con gli oggetti `Labels` effettivi nel set di dati).</span><span class="sxs-lookup"><span data-stu-id="15fd5-321">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="15fd5-322">Restituisce le metriche relative alle prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="15fd5-322">Returns the model performance metrics.</span></span>

<span data-ttu-id="15fd5-323">Aggiungere il codice seguente al metodo `ReuseAndTuneInceptionModel()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="15fd5-323">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="15fd5-324">Le metriche seguenti vengono valutate per la classificazione delle immagini:</span><span class="sxs-lookup"><span data-stu-id="15fd5-324">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="15fd5-325">`Log-loss`: vedere [Perdita di log](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="15fd5-325">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="15fd5-326">Il valore desiderato per LogLoss è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="15fd5-326">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="15fd5-327">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-327">`Per class Log-loss`.</span></span> <span data-ttu-id="15fd5-328">Il valore desiderato per LogLoss per classe è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="15fd5-328">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="15fd5-329">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="15fd5-329">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="15fd5-330">Aggiungere il codice seguente per restituire il modello sottoposto a training come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="15fd5-330">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="15fd5-331">Classificare le immagini con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="15fd5-331">Classify images with a loaded model</span></span>

<span data-ttu-id="15fd5-332">Aggiungere la chiamata seguente al metodo `ClassifyImages()` come riga di codice successiva nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-332">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="15fd5-333">Il metodo `ClassifyImages()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-333">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="15fd5-334">Legge il file TSV in `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-334">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="15fd5-335">Stima le classificazioni delle immagini in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="15fd5-335">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="15fd5-336">Creare il metodo `ClassifyImages()`, subito dopo il metodo `ReuseAndTuneInceptionModel()` e subito prima del metodo `PairAndDisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-336">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="15fd5-337">Per prima cosa, chiamare il metodo `ReadFromTsv()` per creare una classe `IEnumerable<ImageData>` contenente il percorso completo per ogni `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-337">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="15fd5-338">Questo percorso del file è necessario per associare i dati e i risultati della stima.</span><span class="sxs-lookup"><span data-stu-id="15fd5-338">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="15fd5-339">È anche necessario convertire la classe `IEnumerable<ImageData>` in un elemento `IDataView` che verrà usato per la stima.</span><span class="sxs-lookup"><span data-stu-id="15fd5-339">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="15fd5-340">Aggiungere il codice seguente al metodo `ClassifyImages()` come le due righe successive:</span><span class="sxs-lookup"><span data-stu-id="15fd5-340">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="15fd5-341">Come è stato fatto in precedenza con i dati delle immagini di training, stimare la categoria dei dati di immagine di test usando il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) del modello passato.</span><span class="sxs-lookup"><span data-stu-id="15fd5-341">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="15fd5-342">Aggiungere il codice seguente al metodo `ClassifyImages()` per le stime e per convertire gli elementi `IDataView` di `predictions` in un `IEnumerable` per l'associazione e la visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="15fd5-342">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="15fd5-343">Per associare e visualizzare i dati di immagine di test e le stime, aggiungere il codice seguente per chiamare il metodo `DisplayResults()` precedentemente creato come riga successiva nel metodo `ClassifyImages()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-343">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="15fd5-344">Classificare una singola immagine con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="15fd5-344">Classify a single image with a loaded model</span></span>

<span data-ttu-id="15fd5-345">Aggiungere la chiamata seguente al metodo `ClassifySingleImage()` come riga di codice successiva nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-345">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="15fd5-346">Il metodo `ClassifySingleImage()` esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fd5-346">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="15fd5-347">Carica un'istanza di `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-347">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="15fd5-348">Stima la classificazione delle immagini in base ai dati di test.</span><span class="sxs-lookup"><span data-stu-id="15fd5-348">Predicts image classification based on test data.</span></span>

<span data-ttu-id="15fd5-349">Creare il metodo `ClassifySingleImage()`, subito dopo il metodo `ClassifyImages()` e subito prima del metodo `PairAndDisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15fd5-349">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="15fd5-350">Per prima cosa, creare una classe `ImageData` contenente il percorso completo e il nome del file di immagine per il singolo `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="15fd5-350">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="15fd5-351">Aggiungere il codice seguente al metodo `ClassifySingleImage()` come righe successive:</span><span class="sxs-lookup"><span data-stu-id="15fd5-351">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="15fd5-352">La [classe PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API utile che esegue una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="15fd5-352">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="15fd5-353">La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) effettua una previsione su una singola colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="15fd5-353">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="15fd5-354">Passare `imageData` a `PredictionEngine` per prevedere la categoria dell'immagine aggiungendo il codice seguente a `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-354">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="15fd5-355">Visualizzare i risultati della stima come riga di codice successiva nel metodo `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="15fd5-355">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="15fd5-356">Risultati</span><span class="sxs-lookup"><span data-stu-id="15fd5-356">Results</span></span>

<span data-ttu-id="15fd5-357">Dopo aver completato i passaggi precedenti, eseguire l'app console (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="15fd5-357">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="15fd5-358">I risultati saranno simili all'output seguente.</span><span class="sxs-lookup"><span data-stu-id="15fd5-358">Your results should be similar to the following output.</span></span>  <span data-ttu-id="15fd5-359">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="15fd5-359">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="15fd5-360">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="15fd5-360">Congratulations!</span></span> <span data-ttu-id="15fd5-361">È stato creato un modello di Machine Learning per la classificazione delle immagini riutilizzando un modello `TensorFlow` con training preliminare in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="15fd5-361">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="15fd5-362">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="15fd5-362">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="15fd5-363">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="15fd5-363">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="15fd5-364">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="15fd5-364">Understand the problem</span></span>
> * <span data-ttu-id="15fd5-365">Riutilizzare e ottimizzare il modello con training preliminare</span><span class="sxs-lookup"><span data-stu-id="15fd5-365">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="15fd5-366">Classificare le immagini con un modello caricato</span><span class="sxs-lookup"><span data-stu-id="15fd5-366">Classify images with a loaded model</span></span>

<span data-ttu-id="15fd5-367">Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di classificazione delle immagini esteso.</span><span class="sxs-lookup"><span data-stu-id="15fd5-367">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="15fd5-368">Repository GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="15fd5-368">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
