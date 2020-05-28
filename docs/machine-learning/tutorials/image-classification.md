---
title: 'Esercitazione: modello di classificazione delle immagini ML.NET da TensorFlow'
description: Informazioni su come trasferire le informazioni da un modello TensorFlow esistente in un nuovo modello di classificazione delle immagini ML.NET. Il modello TensorFlow è stato sottoposto a training per classificare le immagini in un centinaio di categorie. Il modello ML.NET usa l'apprendimento del trasferimento per classificare le immagini in un minor numero di categorie più ampie.
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: ae6094d5acd4d26482f3690e174d82bbf1807266
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144435"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a><span data-ttu-id="c5215-105">Esercitazione: generare un modello di classificazione delle immagini ML.NET da un modello di TensorFlow con training preliminare</span><span class="sxs-lookup"><span data-stu-id="c5215-105">Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model</span></span>

<span data-ttu-id="c5215-106">Informazioni su come trasferire le informazioni da un modello TensorFlow esistente in un nuovo modello di classificazione delle immagini ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c5215-106">Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.</span></span>

<span data-ttu-id="c5215-107">Il modello TensorFlow è stato sottoposto a training per classificare le immagini in un centinaio di categorie.</span><span class="sxs-lookup"><span data-stu-id="c5215-107">The TensorFlow model was trained to classify images into a thousand categories.</span></span> <span data-ttu-id="c5215-108">Il modello ML.NET utilizza parte del modello TensorFlow nella relativa pipeline per eseguire il training di un modello per classificare le immagini in 3 categorie.</span><span class="sxs-lookup"><span data-stu-id="c5215-108">The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.</span></span>

<span data-ttu-id="c5215-109">Il training di un modello di [classificazione delle immagini](https://en.wikipedia.org/wiki/Outline_of_object_recognition) da zero richiede l'impostazione di milioni di parametri, di una considerevole quantità di dati di training con etichetta e di un notevole importo di risorse di calcolo (centinaia di ore di GPU).</span><span class="sxs-lookup"><span data-stu-id="c5215-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="c5215-110">Anche se non è così efficace come il training di un modello personalizzato da zero, l'apprendimento trasferito consente di semplificare questo processo usando migliaia di immagini anziché milioni di immagini con etichetta e di creare un modello personalizzato abbastanza rapidamente (entro un'ora in un computer senza GPU).</span><span class="sxs-lookup"><span data-stu-id="c5215-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span> <span data-ttu-id="c5215-111">Questa esercitazione ridimensiona ulteriormente il processo, usando solo una decina di immagini di training.</span><span class="sxs-lookup"><span data-stu-id="c5215-111">This tutorial scales that process down even further, using only a dozen training images.</span></span>

<span data-ttu-id="c5215-112">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="c5215-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="c5215-113">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="c5215-113">Understand the problem</span></span>
> * <span data-ttu-id="c5215-114">Incorporare il modello di TensorFlow con training preliminare nella pipeline ML.NET</span><span class="sxs-lookup"><span data-stu-id="c5215-114">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="c5215-115">Eseguire il training e la valutazione del modello ML.NET</span><span class="sxs-lookup"><span data-stu-id="c5215-115">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="c5215-116">Classificare un'immagine di test</span><span class="sxs-lookup"><span data-stu-id="c5215-116">Classify a test image</span></span>

<span data-ttu-id="c5215-117">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="c5215-117">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="c5215-118">Si noti che per impostazione predefinita il progetto .NET per questa esercitazione è configurato per .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="c5215-118">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="c5215-119">Che cos'è l'apprendimento trasferito?</span><span class="sxs-lookup"><span data-stu-id="c5215-119">What is transfer learning?</span></span>

<span data-ttu-id="c5215-120">L'apprendimento del trasferimento è il processo di utilizzo delle informazioni acquisite durante la risoluzione di un problema e l'applicazione a un problema diverso ma correlato.</span><span class="sxs-lookup"><span data-stu-id="c5215-120">Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.</span></span>

<span data-ttu-id="c5215-121">Per questa esercitazione si userà parte di un modello TensorFlow con training per classificare le immagini in migliaia di categorie, in un modello ML.NET che classifica le immagini in 3 categorie.</span><span class="sxs-lookup"><span data-stu-id="c5215-121">For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5215-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c5215-122">Prerequisites</span></span>

* <span data-ttu-id="c5215-123">[Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o visual studio 2017 versione 15,6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="c5215-123">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
* [<span data-ttu-id="c5215-124">File ZIP della directory assets dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="c5215-124">The tutorial assets directory .ZIP file</span></span>](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)
* [<span data-ttu-id="c5215-125">Modello di Machine Learning InceptionV1</span><span class="sxs-lookup"><span data-stu-id="c5215-125">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a><span data-ttu-id="c5215-126">Selezionare l'attività di Machine Learning corretta</span><span class="sxs-lookup"><span data-stu-id="c5215-126">Select the right machine learning task</span></span>

### <a name="deep-learning"></a><span data-ttu-id="c5215-127">Deep Learning</span><span class="sxs-lookup"><span data-stu-id="c5215-127">Deep learning</span></span>

<span data-ttu-id="c5215-128">Il [Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) è un subset di Machine Learning che sta rivoluzionando aree quali Visione artificiale e Riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="c5215-128">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="c5215-129">I modelli di Deep Learning vengono sottoposti a training con set di grandi dimensioni di [dati con etichetta](https://en.wikipedia.org/wiki/Labeled_data) e [reti neurali](https://en.wikipedia.org/wiki/Artificial_neural_network) contenenti più livelli di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="c5215-129">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="c5215-130">Il Deep Learning:</span><span class="sxs-lookup"><span data-stu-id="c5215-130">Deep learning:</span></span>

* <span data-ttu-id="c5215-131">Offre prestazioni ottimali per alcune attività come Visione artificiale.</span><span class="sxs-lookup"><span data-stu-id="c5215-131">Performs better on some tasks like Computer Vision.</span></span>
* <span data-ttu-id="c5215-132">Richiede enormi quantità di dati di training.</span><span class="sxs-lookup"><span data-stu-id="c5215-132">Requires huge amounts of training data.</span></span>

<span data-ttu-id="c5215-133">La classificazione delle immagini è un'attività comune Machine Learning che consente di classificare automaticamente le immagini in categorie come:</span><span class="sxs-lookup"><span data-stu-id="c5215-133">Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:</span></span>

* <span data-ttu-id="c5215-134">Rilevamento di un volto umano in un'immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-134">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="c5215-135">Rilevamento di gatti e cani.</span><span class="sxs-lookup"><span data-stu-id="c5215-135">Detecting cats vs. dogs.</span></span>

 <span data-ttu-id="c5215-136">O come nelle immagini seguenti, determinare se un'immagine è un (n) cibo, giocattolo o Appliance:</span><span class="sxs-lookup"><span data-stu-id="c5215-136">Or as in the following images, determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="c5215-137">![immagine di una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![immagine di un orsetto](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![immagine di un tostapane](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="c5215-137">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="c5215-138">Le immagini precedenti appartengono a Wikimedia Commons, con gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5215-138">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="c5215-139">"220px-Pepperoni_pizza.jpg" pubblico dominio, <https://commons.wikimedia.org/w/index.php?curid=79505>,</span><span class="sxs-lookup"><span data-stu-id="c5215-139">"220px-Pepperoni_pizza.jpg" Public Domain, <https://commons.wikimedia.org/w/index.php?curid=79505>,</span></span>
> * <span data-ttu-id="c5215-140">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" di [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Fotografia autoprodotta, CC BY-SA 2.0, <https://commons.wikimedia.org/w/index.php?curid=48166>.</span><span class="sxs-lookup"><span data-stu-id="c5215-140">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, <https://commons.wikimedia.org/w/index.php?curid=48166>.</span></span>
> * <span data-ttu-id="c5215-141">"193px-Broodrooster.jpg" di [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Opera propria, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=27403></span><span class="sxs-lookup"><span data-stu-id="c5215-141">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=27403></span></span>

<span data-ttu-id="c5215-142">Viene eseguito il `Inception model` training per classificare le immagini in mille categorie, ma per questa esercitazione è necessario classificare le immagini in un set di categorie più piccolo e solo le categorie.</span><span class="sxs-lookup"><span data-stu-id="c5215-142">The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="c5215-143">Specificare la parte `transfer` di `transfer learning`.</span><span class="sxs-lookup"><span data-stu-id="c5215-143">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="c5215-144">È possibile trasferire la capacità del `Inception model` di riconoscere e classificare le immagini alle nuove categorie limitate del classificatore di immagini personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c5215-144">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>

* <span data-ttu-id="c5215-145">Food</span><span class="sxs-lookup"><span data-stu-id="c5215-145">Food</span></span>
* <span data-ttu-id="c5215-146">Giocattoli</span><span class="sxs-lookup"><span data-stu-id="c5215-146">Toy</span></span>
* <span data-ttu-id="c5215-147">Elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="c5215-147">Appliance</span></span>

<span data-ttu-id="c5215-148">Questa esercitazione usa il modello di apprendimento avanzato del [modello](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) TensorFlow, un modello di riconoscimento delle immagini più diffuso con training sul `ImageNet` set di dati.</span><span class="sxs-lookup"><span data-stu-id="c5215-148">This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset.</span></span> <span data-ttu-id="c5215-149">Il modello TensorFlow classifica intere immagini in mille classi, ad esempio "Umbrella", "Jersey" e "lavastoviglie".</span><span class="sxs-lookup"><span data-stu-id="c5215-149">The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="c5215-150">Poiché `Inception model` è già stato sottoposto a training su migliaia di immagini diverse, internamente contiene le [funzionalità di immagine](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necessarie per l'identificazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-150">Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="c5215-151">Per eseguire il training di un nuovo modello con un numero di classi molto inferiore, è possibile utilizzare queste funzionalità di immagine interne nel modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-151">We can make use of these internal image features in the model to train a new model with far fewer classes.</span></span>

<span data-ttu-id="c5215-152">Come illustrato nel diagramma seguente, viene aggiunto un riferimento ai pacchetti NuGet ML.NET nelle applicazioni .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c5215-152">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="c5215-153">Dietro le quinte, ML.NET include e fa riferimento alla `TensorFlow` libreria nativa che consente di scrivere codice per il caricamento di un file di modello con training esistente `TensorFlow` .</span><span class="sxs-lookup"><span data-stu-id="c5215-153">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.</span></span>

![Diagramma dell'architettura ML.NET per la trasformazione TensorFlow](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a><span data-ttu-id="c5215-155">Classificazione multiclasse</span><span class="sxs-lookup"><span data-stu-id="c5215-155">Multiclass classification</span></span>

<span data-ttu-id="c5215-156">Dopo aver usato il modello di Inception TensorFlow per estrarre le funzionalità adatte come input per un algoritmo di apprendimento automatico classico, viene aggiunto un [classificatore multiclasse](../resources/tasks.md#multiclass-classification)ml.NET.</span><span class="sxs-lookup"><span data-stu-id="c5215-156">After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span>

<span data-ttu-id="c5215-157">Il trainer specifico usato in questo caso è l' [algoritmo di regressione logistica multinomiale](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span><span class="sxs-lookup"><span data-stu-id="c5215-157">The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span></span>

<span data-ttu-id="c5215-158">L'algoritmo implementato da questo trainer garantisce prestazioni ottimali in caso di problemi con un numero elevato di funzionalità, come nel caso di un modello di apprendimento avanzato che opera sui dati di immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-158">The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.</span></span>

### <a name="data"></a><span data-ttu-id="c5215-159">Data</span><span class="sxs-lookup"><span data-stu-id="c5215-159">Data</span></span>

<span data-ttu-id="c5215-160">Ci sono due origini dati: il file `.tsv` e i file di immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-160">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="c5215-161">Il file `tags.tsv` contiene due colonne: la prima è definita come `ImagePath` e la seconda è l'oggetto `Label` corrispondente all'immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-161">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="c5215-162">Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="c5215-162">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="c5215-163">Le immagini di training e di test si trovano nelle cartelle assets che verranno scaricate in un file ZIP.</span><span class="sxs-lookup"><span data-stu-id="c5215-163">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="c5215-164">Queste immagini appartengono a Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="c5215-164">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="c5215-165">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), il repository di file multimediali gratuiti.*</span><span class="sxs-lookup"><span data-stu-id="c5215-165">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="c5215-166">Recuperato 10:48, 17 ottobre 2018 da:<https://commons.wikimedia.org/wiki/Pizza>
> <https://commons.wikimedia.org/wiki/Toaster>
> <https://commons.wikimedia.org/wiki/Teddy_bear></span><span class="sxs-lookup"><span data-stu-id="c5215-166">Retrieved 10:48, October 17, 2018 from: <https://commons.wikimedia.org/wiki/Pizza>
> <https://commons.wikimedia.org/wiki/Toaster>
<https://commons.wikimedia.org/wiki/Teddy_bear></span></span>

## <a name="setup"></a><span data-ttu-id="c5215-167">Configurazione</span><span class="sxs-lookup"><span data-stu-id="c5215-167">Setup</span></span>

### <a name="create-a-project"></a><span data-ttu-id="c5215-168">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="c5215-168">Create a project</span></span>

1. <span data-ttu-id="c5215-169">Creare un'**applicazione console di .NET Core** con nome "TransferLearningTF".</span><span class="sxs-lookup"><span data-stu-id="c5215-169">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

1. <span data-ttu-id="c5215-170">Installare il **pacchetto NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="c5215-170">Install the **Microsoft.ML NuGet Package**:</span></span>

    * <span data-ttu-id="c5215-171">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c5215-171">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    * <span data-ttu-id="c5215-172">Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="c5215-172">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    * <span data-ttu-id="c5215-173">Fare clic sull'elenco a discesa **Version (versione** ), selezionare il pacchetto **1.4.0** nell'elenco e selezionare il pulsante **Install (installa** ).</span><span class="sxs-lookup"><span data-stu-id="c5215-173">Click on the **Version** drop-down, select the **1.4.0** package in the list, and select the **Install** button.</span></span>
    * <span data-ttu-id="c5215-174">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** .</span><span class="sxs-lookup"><span data-stu-id="c5215-174">Select the **OK** button on the **Preview Changes** dialog.</span></span>
    * <span data-ttu-id="c5215-175">Selezionare il pulsante **Accetto** nella finestra di dialogo **accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="c5215-175">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    * <span data-ttu-id="c5215-176">Ripetere questi passaggi per **Microsoft. ml. ImageAnalytics v 1.4.0**, **SciSharp. TensorFlow. Redist v 1.15.0** e **Microsoft. ml. TensorFlow v 1.4.0**.</span><span class="sxs-lookup"><span data-stu-id="c5215-176">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.4.0**, **SciSharp.TensorFlow.Redist v1.15.0** and **Microsoft.ML.TensorFlow v1.4.0**.</span></span>

### <a name="download-assets"></a><span data-ttu-id="c5215-177">Scaricare gli asset</span><span class="sxs-lookup"><span data-stu-id="c5215-177">Download assets</span></span>

1. <span data-ttu-id="c5215-178">Scaricare [il file zip della directory asset progetto](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)e decomprimere.</span><span class="sxs-lookup"><span data-stu-id="c5215-178">Download [The project assets directory zip file](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip), and unzip.</span></span>

1. <span data-ttu-id="c5215-179">Copiare la directory `assets` nella directory del progetto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="c5215-179">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="c5215-180">Questa directory e le relative sottodirectory contengono i file di dati e supporto (fatta eccezione per il modello Inception, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="c5215-180">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="c5215-181">Scaricare il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) e decomprimere il file.</span><span class="sxs-lookup"><span data-stu-id="c5215-181">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

1. <span data-ttu-id="c5215-182">Copiare il contenuto della directory `inception5h` appena decompressa nella directory `assets/inception` del progetto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="c5215-182">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets/inception` directory.</span></span> <span data-ttu-id="c5215-183">Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="c5215-183">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Contenuto della directory Inception](./media/image-classification/inception-files.png)

1. <span data-ttu-id="c5215-185">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c5215-185">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="c5215-186">In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="c5215-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="c5215-187">Creare le classi e definire i percorsi</span><span class="sxs-lookup"><span data-stu-id="c5215-187">Create classes and define paths</span></span>

1. <span data-ttu-id="c5215-188">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*: </span><span class="sxs-lookup"><span data-stu-id="c5215-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#AddUsings)]

1. <span data-ttu-id="c5215-189">Aggiungere il codice seguente alla riga immediatamente sopra il `Main` metodo per specificare i percorsi dell'asset:</span><span class="sxs-lookup"><span data-stu-id="c5215-189">Add the following code to the line right above the `Main` method to specify the asset paths:</span></span>

    [!code-csharp[DeclareGlobalVariables](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DeclareGlobalVariables)]

1. <span data-ttu-id="c5215-190">Creare classi per i dati di input e le stime.</span><span class="sxs-lookup"><span data-stu-id="c5215-190">Create classes for your input data, and predictions.</span></span>

    [!code-csharp[DeclareImageData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DeclareImageData)]

    <span data-ttu-id="c5215-191">`ImageData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5215-191">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    * <span data-ttu-id="c5215-192">`ImagePath` contiene il nome del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-192">`ImagePath` contains the image file name.</span></span>
    * <span data-ttu-id="c5215-193">`Label` contiene un valore per l'etichetta dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-193">`Label` contains a value for the image label.</span></span>

1. <span data-ttu-id="c5215-194">Aggiungere una nuova classe al progetto per `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="c5215-194">Add a new class to your project for `ImagePrediction`:</span></span>

    [!code-csharp[DeclareImagePrediction](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DeclareImagePrediction)]

    <span data-ttu-id="c5215-195">`ImagePrediction` è la classe di stima delle immagini e ha i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5215-195">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

    * <span data-ttu-id="c5215-196">`Score` contiene la percentuale di probabilità per una data classificazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-196">`Score` contains the confidence percentage for a given image classification.</span></span>
    * <span data-ttu-id="c5215-197">`PredictedLabelValue` contiene un valore per l'etichetta di classificazione dell'immagine stimata.</span><span class="sxs-lookup"><span data-stu-id="c5215-197">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

    <span data-ttu-id="c5215-198">`ImagePrediction` è la classe usata per la stima dopo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-198">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="c5215-199">Ha un oggetto `string` (`ImagePath`) per il percorso dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c5215-199">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="c5215-200">`Label`Viene utilizzato per riutilizzare ed eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-200">The `Label` is used to reuse and train the model.</span></span> <span data-ttu-id="c5215-201">`PredictedLabelValue` viene usato durante la valutazione e la stima.</span><span class="sxs-lookup"><span data-stu-id="c5215-201">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="c5215-202">Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-202">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="c5215-203">Inizializzare le variabili in Main</span><span class="sxs-lookup"><span data-stu-id="c5215-203">Initialize variables in Main</span></span>

1. <span data-ttu-id="c5215-204">Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="c5215-204">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="c5215-205">Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="c5215-205">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

    [!code-csharp[CreateMLContext](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#CreateMLContext)]

    <span data-ttu-id="c5215-206">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-206">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="c5215-207">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="c5215-207">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="create-a-struct-for-inception-model-parameters"></a><span data-ttu-id="c5215-208">Creare uno struct per i parametri del modello di inizio</span><span class="sxs-lookup"><span data-stu-id="c5215-208">Create a struct for Inception model parameters</span></span>

1. <span data-ttu-id="c5215-209">Il modello di inizio contiene diversi parametri che è necessario passare.</span><span class="sxs-lookup"><span data-stu-id="c5215-209">The Inception model has several parameters you need to pass in.</span></span> <span data-ttu-id="c5215-210">Creare uno struct per eseguire il mapping dei valori del parametro ai nomi descrittivi con il codice seguente, subito dopo il `Main()` Metodo:</span><span class="sxs-lookup"><span data-stu-id="c5215-210">Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

    [!code-csharp[InceptionSettings](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="c5215-211">Creare un metodo dell'utilità di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c5215-211">Create a display utility method</span></span>

<span data-ttu-id="c5215-212">Poiché i dati dell'immagine e le relative stime verranno visualizzati più volte, creare un metodo dell'utilità di visualizzazione per gestire la visualizzazione dell'immagine e dei risultati delle stime.</span><span class="sxs-lookup"><span data-stu-id="c5215-212">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

1. <span data-ttu-id="c5215-213">Creare il metodo `DisplayResults()` subito dopo lo struct `InceptionSettings`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c5215-213">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. <span data-ttu-id="c5215-214">Compilare il corpo del `DisplayResults` Metodo:</span><span class="sxs-lookup"><span data-stu-id="c5215-214">Fill in the body of the `DisplayResults` method:</span></span>

    [!code-csharp[DisplayPredictions](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="c5215-215">Creare un metodo dell'utilità con file TSV</span><span class="sxs-lookup"><span data-stu-id="c5215-215">Create a .tsv file utility method</span></span>

1. <span data-ttu-id="c5215-216">Creare il metodo `ReadFromTsv()` subito dopo il metodo `DisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c5215-216">Create the `ReadFromTsv()` method, just after the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. <span data-ttu-id="c5215-217">Compilare il corpo del `ReadFromTsv` Metodo:</span><span class="sxs-lookup"><span data-stu-id="c5215-217">Fill in the body of the `ReadFromTsv` method:</span></span>

    [!code-csharp[ReadFromTsv](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ReadFromTsv)]

    <span data-ttu-id="c5215-218">Il codice analizza il `tags.tsv` file per aggiungere il percorso file al nome del file di immagine per la `ImagePath` proprietà e caricarlo e `Label` in un `ImageData` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c5215-218">The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span>

### <a name="create-a-method-to-make-a-prediction"></a><span data-ttu-id="c5215-219">Creare un metodo per eseguire una stima</span><span class="sxs-lookup"><span data-stu-id="c5215-219">Create a method to make a prediction</span></span>

1. <span data-ttu-id="c5215-220">Creare il metodo `ClassifySingleImage()` subito prima del metodo `DisplayResults()`, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c5215-220">Create the `ClassifySingleImage()` method, just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="c5215-221">Creare un `ImageData` oggetto che contiene il percorso completo e il nome del file di immagine per il singolo `ImagePath` .</span><span class="sxs-lookup"><span data-stu-id="c5215-221">Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="c5215-222">Aggiungere il codice seguente al metodo `ClassifySingleImage()` come righe successive:</span><span class="sxs-lookup"><span data-stu-id="c5215-222">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

    [!code-csharp[LoadImageData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#LoadImageData)]

1. <span data-ttu-id="c5215-223">Eseguire una singola stima, aggiungendo il codice seguente come riga successiva nel `ClassifySingleImage` Metodo:</span><span class="sxs-lookup"><span data-stu-id="c5215-223">Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:</span></span>

    [!code-csharp[PredictSingle](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#PredictSingle)]

    <span data-ttu-id="c5215-224">Per ottenere la stima, utilizzare il metodo [Predict ()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) .</span><span class="sxs-lookup"><span data-stu-id="c5215-224">To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method.</span></span> <span data-ttu-id="c5215-225">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="c5215-225">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="c5215-226">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="c5215-226">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="c5215-227">È accettabile usare in ambienti a thread singolo o prototipi.</span><span class="sxs-lookup"><span data-stu-id="c5215-227">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="c5215-228">Per migliorare le prestazioni e thread safety negli ambienti di produzione, utilizzare il `PredictionEnginePool` servizio, che consente di creare un oggetto [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da utilizzare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5215-228">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="c5215-229">Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="c5215-229">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5215-230">L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="c5215-230">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="c5215-231">Visualizzare i risultati della stima come riga di codice successiva nel metodo `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="c5215-231">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

   [!code-csharp[DisplayPrediction](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a><span data-ttu-id="c5215-232">Costruire la pipeline del modello ML.NET</span><span class="sxs-lookup"><span data-stu-id="c5215-232">Construct the ML.NET model pipeline</span></span>

<span data-ttu-id="c5215-233">Una pipeline del modello ML.NET è una catena di estimatori.</span><span class="sxs-lookup"><span data-stu-id="c5215-233">An ML.NET model pipeline is a chain of estimators.</span></span> <span data-ttu-id="c5215-234">Si noti che non viene eseguita alcuna esecuzione durante la costruzione della pipeline.</span><span class="sxs-lookup"><span data-stu-id="c5215-234">Note that no execution happens during pipeline construction.</span></span> <span data-ttu-id="c5215-235">Gli oggetti Estimator vengono creati ma non eseguiti.</span><span class="sxs-lookup"><span data-stu-id="c5215-235">The estimator objects are created but not executed.</span></span>

1. <span data-ttu-id="c5215-236">Aggiungere un metodo per generare il modello</span><span class="sxs-lookup"><span data-stu-id="c5215-236">Add a method to generate the model</span></span>

    <span data-ttu-id="c5215-237">Questo metodo è il fulcro dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="c5215-237">This method is the heart of the tutorial.</span></span> <span data-ttu-id="c5215-238">Consente di creare una pipeline per il modello e di eseguire il training della pipeline per produrre il modello ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c5215-238">It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model.</span></span> <span data-ttu-id="c5215-239">Valuta inoltre il modello rispetto ad alcuni dati di test precedentemente non visualizzati.</span><span class="sxs-lookup"><span data-stu-id="c5215-239">It also evaluates the model against some previously unseen test data.</span></span>

    <span data-ttu-id="c5215-240">Creare il metodo `GenerateModel()`, subito dopo lo struct `InceptionSettings` e subito prima del metodo `DisplayResults()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c5215-240">Create the `GenerateModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="c5215-241">Aggiungere gli estimatori per caricare, ridimensionare ed estrarre i pixel dai dati dell'immagine:</span><span class="sxs-lookup"><span data-stu-id="c5215-241">Add the estimators to load, resize and extract the pixels from the image data:</span></span>

    [!code-csharp[ImageTransforms](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ImageTransforms)]

    <span data-ttu-id="c5215-242">I dati dell'immagine devono essere elaborati nel formato previsto dal modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="c5215-242">The image data needs to be processed into the format that the TensorFlow model expects.</span></span> <span data-ttu-id="c5215-243">In questo caso, le immagini vengono caricate in memoria, ridimensionate in modo coerente e i pixel vengono estratti in un vettore numerico.</span><span class="sxs-lookup"><span data-stu-id="c5215-243">In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.</span></span>

1. <span data-ttu-id="c5215-244">Aggiungere lo strumento di stima per caricare il modello di TensorFlow e assegnare un punteggio:</span><span class="sxs-lookup"><span data-stu-id="c5215-244">Add the estimator to load the TensorFlow model, and score it:</span></span>

    [!code-csharp[ScoreTensorFlowModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="c5215-245">Questa fase della pipeline carica il modello TensorFlow in memoria, quindi elabora il vettore di valori pixel attraverso la rete del modello TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="c5215-245">This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network.</span></span> <span data-ttu-id="c5215-246">L'applicazione di input a un modello di apprendimento avanzato e la generazione di un output mediante il modello viene definita **Punteggio**.</span><span class="sxs-lookup"><span data-stu-id="c5215-246">Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**.</span></span> <span data-ttu-id="c5215-247">Quando si utilizza il modello nel suo complesso, il Punteggio crea un'inferenza o una stima.</span><span class="sxs-lookup"><span data-stu-id="c5215-247">When using the model in its entirety, scoring makes an inference, or prediction.</span></span>

    <span data-ttu-id="c5215-248">In questo caso, si usa tutto il modello TensorFlow, ad eccezione dell'ultimo livello, che è il livello che esegue l'inferenza.</span><span class="sxs-lookup"><span data-stu-id="c5215-248">In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference.</span></span> <span data-ttu-id="c5215-249">L'output del penultimo livello è contrassegnato `softmax_2_preactivation` .</span><span class="sxs-lookup"><span data-stu-id="c5215-249">The output of the penultimate layer is labeled `softmax_2_preactivation`.</span></span> <span data-ttu-id="c5215-250">L'output di questo livello è effettivamente un vettore di funzionalità che caratterizzano le immagini di input originali.</span><span class="sxs-lookup"><span data-stu-id="c5215-250">The output of this layer is effectively a vector of features that characterize the original input images.</span></span>

    <span data-ttu-id="c5215-251">Questo vettore di funzionalità generato dal modello TensorFlow verrà usato come input per un algoritmo di training di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c5215-251">This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.</span></span>

1. <span data-ttu-id="c5215-252">Aggiungere lo strumento di stima per eseguire il mapping tra le etichette di stringa nei dati di training e i valori di chiave Integer:</span><span class="sxs-lookup"><span data-stu-id="c5215-252">Add the estimator to map the string labels in the training data to integer key values:</span></span>

    [!code-csharp[MapValueToKey](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#MapValueToKey)]

    <span data-ttu-id="c5215-253">Il ML.NET Trainer aggiunto successivamente richiede che le etichette siano in `key` formato invece che stringhe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="c5215-253">The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings.</span></span> <span data-ttu-id="c5215-254">Una chiave è un numero con un mapping uno-a-uno a un valore stringa.</span><span class="sxs-lookup"><span data-stu-id="c5215-254">A key is a number that has a one to one mapping to a string value.</span></span>

1. <span data-ttu-id="c5215-255">Aggiungere l'algoritmo di training ML.NET:</span><span class="sxs-lookup"><span data-stu-id="c5215-255">Add the ML.NET training algorithm:</span></span>

    [!code-csharp[AddTrainer](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#AddTrainer)]

1. <span data-ttu-id="c5215-256">Aggiungere lo strumento di stima per eseguire il mapping del valore della chiave stimata in una stringa:</span><span class="sxs-lookup"><span data-stu-id="c5215-256">Add the estimator to map the predicted key value back into a string:</span></span>

    [!code-csharp[MapKeyToValue](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a><span data-ttu-id="c5215-257">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="c5215-257">Train the model</span></span>

1. <span data-ttu-id="c5215-258">Caricare i dati di training usando il wrapper [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) .</span><span class="sxs-lookup"><span data-stu-id="c5215-258">Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper.</span></span> <span data-ttu-id="c5215-259">Aggiungere il codice seguente al metodo `GenerateModel()` come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="c5215-259">Add the following code as the next line in the `GenerateModel()` method:</span></span>

    [!code-csharp[LoadData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#LoadData "Load the data")]

    <span data-ttu-id="c5215-260">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="c5215-260">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="c5215-261">`IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="c5215-261">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="c5215-262">È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="c5215-262">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="c5215-263">Eseguire il training del modello con i dati caricati in precedenza:</span><span class="sxs-lookup"><span data-stu-id="c5215-263">Train the model with the data loaded above:</span></span>

    [!code-csharp[TrainModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#TrainModel)]

    <span data-ttu-id="c5215-264">Il `Fit()` Metodo addestra il modello applicando il set di dati di training alla pipeline.</span><span class="sxs-lookup"><span data-stu-id="c5215-264">The `Fit()` method trains your model by applying the training dataset to the pipeline.</span></span>

## <a name="evaluate-the-accuracy-of-the-model"></a><span data-ttu-id="c5215-265">Valutare l'accuratezza del modello</span><span class="sxs-lookup"><span data-stu-id="c5215-265">Evaluate the accuracy of the model</span></span>

1. <span data-ttu-id="c5215-266">Caricare e trasformare i dati di test aggiungendo il codice seguente alla riga successiva del `GenerateModel` Metodo:</span><span class="sxs-lookup"><span data-stu-id="c5215-266">Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:</span></span>

    [!code-csharp[LoadAndTransformTestData](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    <span data-ttu-id="c5215-267">Sono disponibili alcune immagini di esempio che è possibile utilizzare per valutare il modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-267">There are a few sample images that you can use to evaluate the model.</span></span> <span data-ttu-id="c5215-268">Analogamente ai dati di training, questi devono essere caricati in un oggetto `IDataView` , in modo che possano essere trasformati dal modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-268">Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.</span></span>

1. <span data-ttu-id="c5215-269">Aggiungere il codice seguente al `GenerateModel()` metodo per valutare il modello:</span><span class="sxs-lookup"><span data-stu-id="c5215-269">Add the following code to the `GenerateModel()` method to evaluate the model:</span></span>

    [!code-csharp[Evaluate](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#Evaluate)]

    <span data-ttu-id="c5215-270">Dopo aver impostato la stima, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):</span><span class="sxs-lookup"><span data-stu-id="c5215-270">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

    * <span data-ttu-id="c5215-271">Consente di valutare il modello (confronta i valori stimati con il set di dati di test `labels` ).</span><span class="sxs-lookup"><span data-stu-id="c5215-271">Assesses the model (compares the predicted values with the test dataset `labels`).</span></span>
    * <span data-ttu-id="c5215-272">Restituisce le metriche relative alle prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="c5215-272">Returns the model performance metrics.</span></span>

1. <span data-ttu-id="c5215-273">Visualizzare le metriche di accuratezza del modello</span><span class="sxs-lookup"><span data-stu-id="c5215-273">Display the model accuracy metrics</span></span>

    <span data-ttu-id="c5215-274">Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:</span><span class="sxs-lookup"><span data-stu-id="c5215-274">Use the following code to display the metrics, share the results, and then act on them:</span></span>

    [!code-csharp[DisplayMetrics](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#DisplayMetrics)]

    <span data-ttu-id="c5215-275">Le metriche seguenti vengono valutate per la classificazione delle immagini:</span><span class="sxs-lookup"><span data-stu-id="c5215-275">The following metrics are evaluated for image classification:</span></span>

    * <span data-ttu-id="c5215-276">`Log-loss`: vedere [Perdita di log](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="c5215-276">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="c5215-277">Il valore desiderato per LogLoss è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="c5215-277">You want Log-loss to be as close to zero as possible.</span></span>
    * <span data-ttu-id="c5215-278">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="c5215-278">`Per class Log-loss`.</span></span> <span data-ttu-id="c5215-279">Il valore desiderato per LogLoss per classe è il valore più prossimo a 0.</span><span class="sxs-lookup"><span data-stu-id="c5215-279">You want per class Log-loss to be as close to zero as possible.</span></span>

1. <span data-ttu-id="c5215-280">Aggiungere il codice seguente per restituire il modello sottoposto a training come riga successiva:</span><span class="sxs-lookup"><span data-stu-id="c5215-280">Add the following code to return the trained model as the next line:</span></span>

    [!code-csharp[SaveModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#ReturnModel)]

## <a name="run-the-application"></a><span data-ttu-id="c5215-281">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5215-281">Run the application!</span></span>

1. <span data-ttu-id="c5215-282">Aggiungere la chiamata a `GenerateModel` nel `Main` metodo dopo la creazione della classe MLContext:</span><span class="sxs-lookup"><span data-stu-id="c5215-282">Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:</span></span>

    [!code-csharp[CallGenerateModel](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#CallGenerateModel)]

1. <span data-ttu-id="c5215-283">Aggiungere la chiamata al `ClassifySingleImage()` metodo come riga successiva del codice nel `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="c5215-283">Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

    [!code-csharp[CallClassifySingleImage](../../../samples/snippets/machine-learning/TransferLearningTF/csharp/Program.cs#CallClassifySingleImage)]

1. <span data-ttu-id="c5215-284">Eseguire l'app console (CTRL + F5).</span><span class="sxs-lookup"><span data-stu-id="c5215-284">Run your console app (Ctrl + F5).</span></span> <span data-ttu-id="c5215-285">I risultati saranno simili all'output seguente.</span><span class="sxs-lookup"><span data-stu-id="c5215-285">Your results should be similar to the following output.</span></span>  <span data-ttu-id="c5215-286">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="c5215-286">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

    ```console
    =============== Training classification model ===============
    Image: broccoli2.jpg predicted as: food with score: 0.8955513
    Image: pizza3.jpg predicted as: food with score: 0.9667718
    Image: teddy6.jpg predicted as: toy with score: 0.9797683
    =============== Classification metrics ===============
    LogLoss is: 0.0653774699265059
    PerClassLogLoss is: 0.110315812569315 , 0.0204391272836966 , 0
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9646884
    ```

<span data-ttu-id="c5215-287">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="c5215-287">Congratulations!</span></span> <span data-ttu-id="c5215-288">A questo punto è stato creato un modello di apprendimento automatico per la classificazione delle immagini applicando l'apprendimento del trasferimento a un `TensorFlow` modello in ml.NET.</span><span class="sxs-lookup"><span data-stu-id="c5215-288">You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="c5215-289">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="c5215-289">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="c5215-290">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="c5215-290">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="c5215-291">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="c5215-291">Understand the problem</span></span>
> * <span data-ttu-id="c5215-292">Incorporare il modello di TensorFlow con training preliminare nella pipeline ML.NET</span><span class="sxs-lookup"><span data-stu-id="c5215-292">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="c5215-293">Eseguire il training e la valutazione del modello ML.NET</span><span class="sxs-lookup"><span data-stu-id="c5215-293">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="c5215-294">Classificare un'immagine di test</span><span class="sxs-lookup"><span data-stu-id="c5215-294">Classify a test image</span></span>

<span data-ttu-id="c5215-295">Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di classificazione delle immagini esteso.</span><span class="sxs-lookup"><span data-stu-id="c5215-295">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="c5215-296">Repository GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="c5215-296">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
