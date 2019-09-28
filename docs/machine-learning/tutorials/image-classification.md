---
title: 'Esercitazione: Generare un modello di classificazione delle immagini ML.NET da un modello di TensorFlow con training preliminare'
description: Informazioni su come trasferire le informazioni da un modello TensorFlow esistente in un nuovo modello di classificazione delle immagini ML.NET. Il modello TensorFlow è stato sottoposto a training per classificare le immagini in un centinaio di categorie. Il modello ML.NET usa l'apprendimento del trasferimento per classificare le immagini in un minor numero di categorie più ampie.
ms.date: 09/26/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
author: natke
ms.author: nakersha
ms.openlocfilehash: 28d8c18721bd353e961284935758a87679c8c8e0
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353688"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a><span data-ttu-id="ca9d7-105">Esercitazione: Generare un modello di classificazione delle immagini ML.NET da un modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="ca9d7-105">Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model</span></span>

<span data-ttu-id="ca9d7-106">Informazioni su come trasferire le informazioni da un modello TensorFlow esistente in un nuovo modello di classificazione delle immagini ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-106">Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.</span></span>

<span data-ttu-id="ca9d7-107">Il modello TensorFlow è stato sottoposto a training per classificare le immagini in un centinaio di categorie.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-107">The TensorFlow model was trained to classify images into a thousand categories.</span></span> <span data-ttu-id="ca9d7-108">Il modello ML.NET utilizza parte del modello TensorFlow nella relativa pipeline per eseguire il training di un modello per classificare le immagini in 3 categorie.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-108">The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.</span></span>

<span data-ttu-id="ca9d7-109">Il training di un modello di [classificazione delle immagini](https://en.wikipedia.org/wiki/Outline_of_object_recognition) da zero richiede l'impostazione di milioni di parametri, di una considerevole quantità di dati di training con etichetta e di un notevole importo di risorse di calcolo (centinaia di ore di GPU).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="ca9d7-110">Anche se non è così efficace come il training di un modello personalizzato da zero, l'apprendimento trasferito consente di semplificare questo processo usando migliaia di immagini anziché milioni di immagini con etichetta e di creare un modello personalizzato abbastanza rapidamente (entro un'ora in un computer senza GPU).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span> <span data-ttu-id="ca9d7-111">Questa esercitazione ridimensiona ulteriormente il processo, usando solo una decina di immagini di training.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-111">This tutorial scales that process down even further, using only a dozen training images.</span></span>

<span data-ttu-id="ca9d7-112">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="ca9d7-113">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ca9d7-113">Understand the problem</span></span>
> * <span data-ttu-id="ca9d7-114">Incorporare il modello di TensorFlow con training preliminare nella pipeline ML.NET</span><span class="sxs-lookup"><span data-stu-id="ca9d7-114">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="ca9d7-115">Eseguire il training e la valutazione del modello ML.NET</span><span class="sxs-lookup"><span data-stu-id="ca9d7-115">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="ca9d7-116">Classificare un'immagine di test</span><span class="sxs-lookup"><span data-stu-id="ca9d7-116">Classify a test image</span></span>

<span data-ttu-id="ca9d7-117">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-117">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="ca9d7-118">Si noti che per impostazione predefinita il progetto .NET per questa esercitazione è configurato per .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-118">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="ca9d7-119">Che cos'è l'apprendimento trasferito?</span><span class="sxs-lookup"><span data-stu-id="ca9d7-119">What is transfer learning?</span></span>

<span data-ttu-id="ca9d7-120">L'apprendimento del trasferimento è il processo di utilizzo delle informazioni acquisite durante la risoluzione di un problema e l'applicazione a un problema diverso ma correlato.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-120">Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.</span></span>

<span data-ttu-id="ca9d7-121">Per questa esercitazione si userà parte di un modello TensorFlow con training per classificare le immagini in migliaia di categorie, in un modello ML.NET che classifica le immagini in 3 categorie.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-121">For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca9d7-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ca9d7-122">Prerequisites</span></span>

* <span data-ttu-id="ca9d7-123">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="ca9d7-124">Pacchetto NuGet Microsoft.ML 1.3.1</span><span class="sxs-lookup"><span data-stu-id="ca9d7-124">Microsoft.ML 1.3.1 Nuget package</span></span>
* <span data-ttu-id="ca9d7-125">Pacchetto NuGet Microsoft. ML. ImageAnalytics 1.3.1</span><span class="sxs-lookup"><span data-stu-id="ca9d7-125">Microsoft.ML.ImageAnalytics 1.3.1 Nuget package</span></span>
* <span data-ttu-id="ca9d7-126">Pacchetto NuGet Microsoft. ML. TensorFlow 1.3.1</span><span class="sxs-lookup"><span data-stu-id="ca9d7-126">Microsoft.ML.TensorFlow 1.3.1 Nuget package</span></span>

* [<span data-ttu-id="ca9d7-127">File ZIP della directory assets dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="ca9d7-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="ca9d7-128">Modello di Machine Learning InceptionV1</span><span class="sxs-lookup"><span data-stu-id="ca9d7-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a><span data-ttu-id="ca9d7-129">Selezionare l'attività di Machine Learning corretta</span><span class="sxs-lookup"><span data-stu-id="ca9d7-129">Select the right machine learning task</span></span>

### <a name="deep-learning"></a><span data-ttu-id="ca9d7-130">Deep Learning</span><span class="sxs-lookup"><span data-stu-id="ca9d7-130">Deep learning</span></span>

<span data-ttu-id="ca9d7-131">Il [Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) è un subset di Machine Learning che sta rivoluzionando aree quali Visione artificiale e Riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-131">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="ca9d7-132">I modelli di Deep Learning vengono sottoposti a training con set di grandi dimensioni di [dati con etichetta](https://en.wikipedia.org/wiki/Labeled_data) e [reti neurali](https://en.wikipedia.org/wiki/Artificial_neural_network) contenenti più livelli di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-132">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="ca9d7-133">Il Deep Learning:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-133">Deep learning:</span></span>

* <span data-ttu-id="ca9d7-134">Offre prestazioni ottimali per alcune attività come Visione artificiale.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-134">Performs better on some tasks like Computer Vision.</span></span>
* <span data-ttu-id="ca9d7-135">Richiede enormi quantità di dati di training.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-135">Requires huge amounts of training data.</span></span>

<span data-ttu-id="ca9d7-136">La classificazione delle immagini è un'attività comune Machine Learning che consente di classificare automaticamente le immagini in categorie come:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-136">Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:</span></span>

* <span data-ttu-id="ca9d7-137">Rilevamento di un volto umano in un'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-137">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="ca9d7-138">Rilevamento di gatti e cani.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-138">Detecting cats vs. dogs.</span></span>

 <span data-ttu-id="ca9d7-139">O come nelle immagini seguenti, determinare se un'immagine è un (n) cibo, giocattolo o Appliance:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-139">Or as in the following images, determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="ca9d7-140">![immagine di una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![immagine di un orsetto](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![immagine di un tostapane](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="ca9d7-140">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="ca9d7-141">Le immagini precedenti appartengono a Wikimedia Commons, con gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-141">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="ca9d7-142">"220px-Pepperoni_pizza.jpg" pubblico dominio, https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="ca9d7-142">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="ca9d7-143">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" di [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Fotografia autoprodotta, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-143">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="ca9d7-144">"193px-Broodrooster.jpg" di [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Opera propria, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="ca9d7-144">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="ca9d7-145">Il `Inception model` è stato sottoposto a training per classificare le immagini in mille categorie. Tuttavia, per questa esercitazione, è necessario classificare le immagini in un set di categorie più piccolo e solo in quelle categorie.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-145">The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="ca9d7-146">Specificare la parte `transfer` di `transfer learning`.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-146">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="ca9d7-147">È possibile trasferire la capacità del `Inception model` di riconoscere e classificare le immagini alle nuove categorie limitate del classificatore di immagini personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-147">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>

* <span data-ttu-id="ca9d7-148">Cibo</span><span class="sxs-lookup"><span data-stu-id="ca9d7-148">Food</span></span>
* <span data-ttu-id="ca9d7-149">Giocattoli</span><span class="sxs-lookup"><span data-stu-id="ca9d7-149">Toy</span></span>
* <span data-ttu-id="ca9d7-150">Elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="ca9d7-150">Appliance</span></span>

<span data-ttu-id="ca9d7-151">Questa esercitazione usa il modello di apprendimento avanzato del [modello](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) TensorFlow, un modello di riconoscimento delle immagini più diffuso con training sul set di dati `ImageNet`.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-151">This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset.</span></span> <span data-ttu-id="ca9d7-152">Il modello TensorFlow classifica intere immagini in mille classi, ad esempio "Umbrella", "Jersey" e "lavastoviglie".</span><span class="sxs-lookup"><span data-stu-id="ca9d7-152">The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="ca9d7-153">Poiché il `Inception model` è già stato sottoposto a training su migliaia di immagini diverse, internamente contiene le [funzionalità di immagine](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necessarie per l'identificazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-153">Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="ca9d7-154">Per eseguire il training di un nuovo modello con un numero di classi molto inferiore, è possibile utilizzare queste funzionalità di immagine interne nel modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-154">We can make use of these internal image features in the model to train a new model with far fewer classes.</span></span>

<span data-ttu-id="ca9d7-155">Come illustrato nel diagramma seguente, viene aggiunto un riferimento ai pacchetti NuGet ML.NET nelle applicazioni .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-155">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="ca9d7-156">Dietro le quinte, ML.NET include e fa riferimento alla libreria nativa `TensorFlow` che consente di scrivere codice per il caricamento di un file di modello `TensorFlow` con training esistente.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-156">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.</span></span>

![Diagramma dell'architettura ML.NET per la trasformazione TensorFlow](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a><span data-ttu-id="ca9d7-158">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="ca9d7-158">Multiclass classification</span></span>

<span data-ttu-id="ca9d7-159">Dopo aver usato il modello di Inception TensorFlow per estrarre le funzionalità adatte come input per un algoritmo di apprendimento automatico classico, viene aggiunto un [classificatore multiclasse](../resources/tasks.md#multiclass-classification)ml.NET.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-159">After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span>

<span data-ttu-id="ca9d7-160">Il trainer specifico usato in questo caso è l' [algoritmo di regressione logistica multinomiale](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-160">The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span></span>

<span data-ttu-id="ca9d7-161">L'algoritmo implementato da questo trainer garantisce prestazioni ottimali in caso di problemi con un numero elevato di funzionalità, come nel caso di un modello di apprendimento avanzato che opera sui dati di immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-161">The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.</span></span>

### <a name="data"></a><span data-ttu-id="ca9d7-162">Data</span><span class="sxs-lookup"><span data-stu-id="ca9d7-162">Data</span></span>

<span data-ttu-id="ca9d7-163">Ci sono due origini dati: il file `.tsv` e i file di immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-163">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="ca9d7-164">Il file `tags.tsv` contiene due colonne: la prima è definita come `ImagePath` e la seconda è l'oggetto `Label` corrispondente all'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-164">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="ca9d7-165">Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-165">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="ca9d7-166">Le immagini di training e di test si trovano nelle cartelle assets che verranno scaricate in un file ZIP.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-166">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="ca9d7-167">Queste immagini appartengono a Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-167">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="ca9d7-168">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), il repository di file multimediali gratuiti.*</span><span class="sxs-lookup"><span data-stu-id="ca9d7-168">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="ca9d7-169">Recuperato 10:48, 17 ottobre 2018 da: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span><span class="sxs-lookup"><span data-stu-id="ca9d7-169">Retrieved 10:48, October 17, 2018 from: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span></span>

## <a name="setup"></a><span data-ttu-id="ca9d7-170">Configurazione</span><span class="sxs-lookup"><span data-stu-id="ca9d7-170">Setup</span></span>

### <a name="create-a-project"></a><span data-ttu-id="ca9d7-171">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="ca9d7-171">Create a project</span></span>

1. <span data-ttu-id="ca9d7-172">Creare un'**applicazione console di .NET Core** con nome "TransferLearningTF".</span><span class="sxs-lookup"><span data-stu-id="ca9d7-172">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

1. <span data-ttu-id="ca9d7-173">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    * <span data-ttu-id="ca9d7-174">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    * <span data-ttu-id="ca9d7-175">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    * <span data-ttu-id="ca9d7-176">Fare clic sull'elenco a discesa **versione** , selezionare il pacchetto **1.3.1** nell'elenco e selezionare il pulsante **Installa** .</span><span class="sxs-lookup"><span data-stu-id="ca9d7-176">Click on the **Version** drop-down, select the **1.3.1** package in the list, and select the **Install** button.</span></span>
    * <span data-ttu-id="ca9d7-177">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** .</span><span class="sxs-lookup"><span data-stu-id="ca9d7-177">Select the **OK** button on the **Preview Changes** dialog.</span></span>
    * <span data-ttu-id="ca9d7-178">Selezionare il pulsante **Accetto** nella finestra di dialogo **accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-178">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    * <span data-ttu-id="ca9d7-179">Ripetere questi passaggi per **Microsoft. ml. ImageAnalytics v 1.3.1** e **Microsoft. ml. TensorFlow v 1.3.1**.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-179">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.3.1** and **Microsoft.ML.TensorFlow v1.3.1**.</span></span>

### <a name="download-assets"></a><span data-ttu-id="ca9d7-180">Scarica asset</span><span class="sxs-lookup"><span data-stu-id="ca9d7-180">Download assets</span></span>

1. <span data-ttu-id="ca9d7-181">Scaricare il [file ZIP della directory assets del progetto](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) e decomprimerlo.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-181">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

1. <span data-ttu-id="ca9d7-182">Copiare la directory `assets` nella directory del progetto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-182">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="ca9d7-183">Questa directory e le relative sottodirectory contengono i file di dati e supporto (fatta eccezione per il modello Inception, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-183">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="ca9d7-184">Scaricare il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) e decomprimere il file.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-184">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

1. <span data-ttu-id="ca9d7-185">Copiare il contenuto della directory `inception5h` appena decompressa nella directory `assets/inputs-train/inception` del progetto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-185">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets/inputs-train/inception` directory.</span></span> <span data-ttu-id="ca9d7-186">Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-186">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Contenuto della directory Inception](./media/image-classification/inception-files.png)

1. <span data-ttu-id="ca9d7-188">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-188">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="ca9d7-189">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="ca9d7-190">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="ca9d7-190">Create classes and define paths</span></span>

1. <span data-ttu-id="ca9d7-191">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-191">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

1. <span data-ttu-id="ca9d7-192">Aggiungere il codice seguente alla riga immediatamente sopra il metodo `Main` per specificare i percorsi degli asset:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-192">Add the following code to the line right above the `Main` method to specify the asset paths:</span></span>

    [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

1. <span data-ttu-id="ca9d7-193">Creare classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-193">Create classes for your input data, and predictions.</span></span>

    [!code-csharp[DeclareImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImageData)]

    <span data-ttu-id="ca9d7-194">`ImageData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-194">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    * <span data-ttu-id="ca9d7-195">`ImagePath` contiene il nome del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-195">`ImagePath` contains the image file name.</span></span>
    * <span data-ttu-id="ca9d7-196">`Label` contiene un valore per l'etichetta dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-196">`Label` contains a value for the image label.</span></span>

1. <span data-ttu-id="ca9d7-197">Aggiungere una nuova classe al progetto per `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-197">Add a new class to your project for `ImagePrediction`:</span></span>

    [!code-csharp[DeclareImagePrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImagePrediction)]

    <span data-ttu-id="ca9d7-198">`ImagePrediction` è la classe di stima delle immagini e ha i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-198">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

    * <span data-ttu-id="ca9d7-199">`Score` contiene la percentuale di probabilità per una data classificazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-199">`Score` contains the confidence percentage for a given image classification.</span></span>
    * <span data-ttu-id="ca9d7-200">`PredictedLabelValue` contiene un valore per l'etichetta di classificazione dell'immagine stimata.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-200">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

    <span data-ttu-id="ca9d7-201">`ImagePrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-201">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="ca9d7-202">Ha un oggetto `string` (`ImagePath`) per il percorso dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-202">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="ca9d7-203">Il `Label` viene utilizzato per riutilizzare ed eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-203">The `Label` is used to reuse and train the model.</span></span> <span data-ttu-id="ca9d7-204">`PredictedLabelValue` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-204">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="ca9d7-205">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-205">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="ca9d7-206">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="ca9d7-206">Initialize variables in Main</span></span>

1. <span data-ttu-id="ca9d7-207">Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-207">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="ca9d7-208">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-208">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

    [!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

    <span data-ttu-id="ca9d7-209">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-209">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="ca9d7-210">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-210">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="create-a-struct-for-inception-model-parameters"></a><span data-ttu-id="ca9d7-211">Creare uno struct per i parametri del modello di inizio</span><span class="sxs-lookup"><span data-stu-id="ca9d7-211">Create a struct for Inception model parameters</span></span>

1. <span data-ttu-id="ca9d7-212">Il modello di inizio contiene diversi parametri che è necessario passare.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-212">The Inception model has several parameters you need to pass in.</span></span> <span data-ttu-id="ca9d7-213">Creare uno struct per eseguire il mapping dei valori del parametro ai nomi descrittivi con il codice seguente, subito dopo il metodo `Main()`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-213">Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

    [!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="ca9d7-214">Creare un metodo dell'utilità di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="ca9d7-214">Create a display utility method</span></span>

<span data-ttu-id="ca9d7-215">Poiché i dati dell'immagine e le relative stime verranno visualizzati più volte, creare un metodo dell'utilità di visualizzazione per gestire la visualizzazione dell'immagine e dei risultati delle stime.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-215">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

1. <span data-ttu-id="ca9d7-216">Creare il metodo `DisplayResults()` subito dopo lo struct `InceptionSettings`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-216">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. <span data-ttu-id="ca9d7-217">Compilare il corpo del metodo `DisplayResults`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-217">Fill in the body of the `DisplayResults` method:</span></span>

    [!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="ca9d7-218">Creare un metodo dell'utilità con file TSV</span><span class="sxs-lookup"><span data-stu-id="ca9d7-218">Create a .tsv file utility method</span></span>

1. <span data-ttu-id="ca9d7-219">Creare il metodo `ReadFromTsv()` subito dopo il metodo `DisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-219">Create the `ReadFromTsv()` method, just after the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. <span data-ttu-id="ca9d7-220">Compilare il corpo del metodo `ReadFromTsv`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-220">Fill in the body of the `ReadFromTsv` method:</span></span>

    [!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]

    <span data-ttu-id="ca9d7-221">Il codice analizza il file `tags.tsv` per aggiungere il percorso del file di immagine per la proprietà `ImagePath` e caricarlo e il `Label` in un oggetto `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-221">The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span>

### <a name="create-a-method-to-make-a-prediction"></a><span data-ttu-id="ca9d7-222">Creare un metodo per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="ca9d7-222">Create a method to make a prediction</span></span>

1. <span data-ttu-id="ca9d7-223">Creare il metodo `ClassifySingleImage()` subito prima del metodo `DisplayResults()`, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-223">Create the `ClassifySingleImage()` method, just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="ca9d7-224">Creare un oggetto `ImageData` che contiene il percorso completo e il nome del file di immagine per il singolo `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-224">Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="ca9d7-225">Aggiungere il codice seguente al metodo `ClassifySingleImage()` come righe successive:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-225">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

    [!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

1. <span data-ttu-id="ca9d7-226">Eseguire una singola stima, aggiungendo il codice seguente come riga successiva nel metodo `ClassifySingleImage`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-226">Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:</span></span>

    [!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

    <span data-ttu-id="ca9d7-227">La classe [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità che esegue una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-227">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) class is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="ca9d7-228">Per ottenere la stima, utilizzare il metodo [Predict ()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) .</span><span class="sxs-lookup"><span data-stu-id="ca9d7-228">To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method.</span></span>

1. <span data-ttu-id="ca9d7-229">Visualizzare i risultati della stima come riga di codice successiva nel metodo `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-229">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

   [!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a><span data-ttu-id="ca9d7-230">Costruire la pipeline del modello ML.NET</span><span class="sxs-lookup"><span data-stu-id="ca9d7-230">Construct the ML.NET model pipeline</span></span>

<span data-ttu-id="ca9d7-231">Una pipeline del modello ML.NET è una catena di estimatori.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-231">An ML.NET model pipeline is a chain of estimators.</span></span> <span data-ttu-id="ca9d7-232">Si noti che non viene eseguita alcuna esecuzione durante la costruzione della pipeline.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-232">Note that no execution happens during pipeline construction.</span></span> <span data-ttu-id="ca9d7-233">Gli oggetti Estimator vengono creati ma non eseguiti.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-233">The estimator objects are created but not executed.</span></span>

1. <span data-ttu-id="ca9d7-234">Aggiungere un metodo per generare il modello</span><span class="sxs-lookup"><span data-stu-id="ca9d7-234">Add a method to generate the model</span></span>

    <span data-ttu-id="ca9d7-235">Questo metodo è il fulcro dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-235">This method is the heart of the tutorial.</span></span> <span data-ttu-id="ca9d7-236">Consente di creare una pipeline per il modello e di eseguire il training della pipeline per produrre il modello ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-236">It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model.</span></span> <span data-ttu-id="ca9d7-237">Valuta inoltre il modello rispetto ad alcuni dati di test precedentemente non visualizzati.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-237">It also evaluates the model against some previously unseen test data.</span></span>

    <span data-ttu-id="ca9d7-238">Creare il metodo `GenerateModel()`, subito dopo lo struct `InceptionSettings` e subito prima del metodo `DisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-238">Create the `GenerateModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="ca9d7-239">Aggiungere gli estimatori per caricare, ridimensionare ed estrarre i pixel dai dati dell'immagine:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-239">Add the estimators to load, resize and extract the pixels from the image data:</span></span>

    [!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

    <span data-ttu-id="ca9d7-240">I dati dell'immagine devono essere elaborati nel formato previsto dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-240">The image data needs to be processed into the format that the TensorFlow model expects.</span></span> <span data-ttu-id="ca9d7-241">In questo caso, le immagini vengono caricate in memoria, ridimensionate in modo coerente e i pixel vengono estratti in un vettore numerico.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-241">In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.</span></span>

1. <span data-ttu-id="ca9d7-242">Aggiungere lo strumento di stima per caricare il modello di TensorFlow e assegnare un punteggio:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-242">Add the estimator to load the TensorFlow model, and score it:</span></span>

    [!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="ca9d7-243">Questa fase della pipeline carica il modello TensorFlow in memoria, quindi elabora il vettore di valori pixel attraverso la rete del modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-243">This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network.</span></span> <span data-ttu-id="ca9d7-244">L'applicazione di input a un modello di apprendimento avanzato e la generazione di un output mediante il modello viene definita **Punteggio**.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-244">Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**.</span></span> <span data-ttu-id="ca9d7-245">Quando si utilizza il modello nel suo complesso, il Punteggio crea un'inferenza o una stima.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-245">When using the model in its entirety, scoring makes an inference, or prediction.</span></span> 

    <span data-ttu-id="ca9d7-246">In questo caso, si usa tutto il modello TensorFlow, ad eccezione dell'ultimo livello, che è il livello che esegue l'inferenza.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-246">In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference.</span></span> <span data-ttu-id="ca9d7-247">L'output del penultimo livello è denominato `softmax_2_preactivation`.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-247">The output of the penultimate layer is labeled `softmax_2_preactivation`.</span></span> <span data-ttu-id="ca9d7-248">L'output di questo livello è effettivamente un vettore di funzionalità che caratterizzano le immagini di input originali.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-248">The output of this layer is effectively a vector of features that characterize the original input images.</span></span>

    <span data-ttu-id="ca9d7-249">Questo vettore di funzionalità generato dal modello TensorFlow verrà usato come input per un algoritmo di training di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-249">This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.</span></span>

1. <span data-ttu-id="ca9d7-250">Aggiungere lo strumento di stima per eseguire il mapping tra le etichette di stringa nei dati di training e i valori di chiave Integer:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-250">Add the estimator to map the string labels in the training data to integer key values:</span></span>

    [!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey)]

    <span data-ttu-id="ca9d7-251">Il ML.NET Trainer aggiunto successivamente richiede che le etichette siano in formato `key` invece che stringhe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-251">The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings.</span></span> <span data-ttu-id="ca9d7-252">Una chiave è un numero con un mapping uno-a-uno a un valore stringa.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-252">A key is a number that has a one to one mapping to a string value.</span></span>

1. <span data-ttu-id="ca9d7-253">Aggiungere l'algoritmo di training ML.NET:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-253">Add the ML.NET training algorithm:</span></span>

    [!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

1. <span data-ttu-id="ca9d7-254">Aggiungere lo strumento di stima per eseguire il mapping del valore della chiave stimata in una stringa:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-254">Add the estimator to map the predicted key value back into a string:</span></span>

    [!code-csharp[MapKeyToValue](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a><span data-ttu-id="ca9d7-255">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ca9d7-255">Train the model</span></span>

1. <span data-ttu-id="ca9d7-256">Caricare i dati di training usando il wrapper [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) .</span><span class="sxs-lookup"><span data-stu-id="ca9d7-256">Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper.</span></span> <span data-ttu-id="ca9d7-257">Aggiungere il codice seguente al metodo `GenerateModel()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-257">Add the following code as the next line in the `GenerateModel()` method:</span></span>

    [!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

    <span data-ttu-id="ca9d7-258">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-258">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="ca9d7-259">`IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-259">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="ca9d7-260">È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-260">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="ca9d7-261">Eseguire il training del modello con i dati caricati in precedenza:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-261">Train the model with the data loaded above:</span></span>

    [!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

    <span data-ttu-id="ca9d7-262">Il metodo `Fit()` addestra il modello applicando il set di dati di training alla pipeline.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-262">The `Fit()` method trains your model by applying the training dataset to the pipeline.</span></span>

## <a name="evaluate-the-accuracy-of-the-model"></a><span data-ttu-id="ca9d7-263">Valutare l'accuratezza del modello</span><span class="sxs-lookup"><span data-stu-id="ca9d7-263">Evaluate the accuracy of the model</span></span>

1. <span data-ttu-id="ca9d7-264">Caricare e trasformare i dati di test aggiungendo il codice seguente alla riga successiva del metodo `GenerateModel`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-264">Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:</span></span>

    [!code-csharp[LoadAndTransformTestData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    <span data-ttu-id="ca9d7-265">Sono disponibili alcune immagini di esempio che è possibile utilizzare per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-265">There are a few sample images that you can use to evaluate the model.</span></span> <span data-ttu-id="ca9d7-266">Analogamente ai dati di training, questi devono essere caricati in un `IDataView`, in modo che possano essere trasformati dal modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-266">Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.</span></span>
   
1. <span data-ttu-id="ca9d7-267">Aggiungere il codice seguente al metodo `GenerateModel()` per valutare il modello:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-267">Add the following code to the `GenerateModel()` method to evaluate the model:</span></span>

    [!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

    <span data-ttu-id="ca9d7-268">Dopo aver impostato la stima, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):</span><span class="sxs-lookup"><span data-stu-id="ca9d7-268">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

    * <span data-ttu-id="ca9d7-269">Consente di valutare il modello (confronta i valori stimati con il set di dati di test `labels`).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-269">Assesses the model (compares the predicted values with the test dataset `labels`).</span></span>
    * <span data-ttu-id="ca9d7-270">Restituisce le metriche relative alle prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-270">Returns the model performance metrics.</span></span>

1. <span data-ttu-id="ca9d7-271">Visualizzare le metriche di accuratezza del modello</span><span class="sxs-lookup"><span data-stu-id="ca9d7-271">Display the model accuracy metrics</span></span>

    <span data-ttu-id="ca9d7-272">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-272">Use the following code to display the metrics, share the results, and then act on them:</span></span>

    [!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

    <span data-ttu-id="ca9d7-273">Le metriche seguenti vengono valutate per la classificazione delle immagini:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-273">The following metrics are evaluated for image classification:</span></span>

    * <span data-ttu-id="ca9d7-274">`Log-loss`: vedere [Perdita di log](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-274">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="ca9d7-275">Il valore desiderato per LogLoss è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-275">You want Log-loss to be as close to zero as possible.</span></span>
    * <span data-ttu-id="ca9d7-276">`Per class Log-loss` (Indici per tabelle con ottimizzazione per la memoria).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-276">`Per class Log-loss`.</span></span> <span data-ttu-id="ca9d7-277">Il valore desiderato per LogLoss per classe è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-277">You want per class Log-loss to be as close to zero as possible.</span></span>

1. <span data-ttu-id="ca9d7-278">Aggiungere il codice seguente per restituire il modello sottoposto a training come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-278">Add the following code to return the trained model as the next line:</span></span>

    [!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="run-the-application"></a><span data-ttu-id="ca9d7-279">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-279">Run the application!</span></span>

1. <span data-ttu-id="ca9d7-280">Aggiungere la chiamata a `GenerateModel` nel metodo `Main` dopo la creazione della classe MLContext:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-280">Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:</span></span>

    [!code-csharp[CallGenerateModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallGenerateModel)]

1. <span data-ttu-id="ca9d7-281">Aggiungere la chiamata al metodo `ClassifySingleImage()` come riga di codice successiva nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-281">Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

    [!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

1. <span data-ttu-id="ca9d7-282">Eseguire l'app console (CTRL + F5).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-282">Run your console app (Ctrl + F5).</span></span> <span data-ttu-id="ca9d7-283">I risultati saranno simili all'output seguente.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-283">Your results should be similar to the following output.</span></span>  <span data-ttu-id="ca9d7-284">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-284">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9625379

    C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
    Press any key to close this window . . .
    ```

<span data-ttu-id="ca9d7-285">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-285">Congratulations!</span></span> <span data-ttu-id="ca9d7-286">A questo punto è stato creato un modello di apprendimento automatico per la classificazione delle immagini applicando l'apprendimento del trasferimento a un modello `TensorFlow` in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-286">You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="ca9d7-287">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="ca9d7-287">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="ca9d7-288">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="ca9d7-288">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="ca9d7-289">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ca9d7-289">Understand the problem</span></span>
> * <span data-ttu-id="ca9d7-290">Incorporare il modello di TensorFlow con training preliminare nella pipeline ML.NET</span><span class="sxs-lookup"><span data-stu-id="ca9d7-290">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="ca9d7-291">Eseguire il training e la valutazione del modello ML.NET</span><span class="sxs-lookup"><span data-stu-id="ca9d7-291">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="ca9d7-292">Classificare un'immagine di test</span><span class="sxs-lookup"><span data-stu-id="ca9d7-292">Classify a test image</span></span>

<span data-ttu-id="ca9d7-293">Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di classificazione delle immagini esteso.</span><span class="sxs-lookup"><span data-stu-id="ca9d7-293">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ca9d7-294">Repository GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="ca9d7-294">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
