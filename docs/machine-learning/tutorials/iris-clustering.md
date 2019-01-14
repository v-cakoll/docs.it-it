---
title: Raggruppare i fiori iris usando un algoritmo di apprendimento automatico basato sul clustering - ML.NET
description: Informazioni su come usare ML.NET in uno scenario di clustering
author: pkulikov
ms.author: johalex
ms.date: 01/11/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: ab888a2cd9469d5ce0131ba2b17f7c134cf2855c
ms.sourcegitcommit: 81bd16c7435a8c9183d2a7e878a2a5eff7d04584
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2019
ms.locfileid: "54249073"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="fe2c9-103">Esercitazione: Raggruppare i fiori iris usando un algoritmo di apprendimento automatico basato sul clustering con ML.NET</span><span class="sxs-lookup"><span data-stu-id="fe2c9-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="fe2c9-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="fe2c9-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="fe2c9-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="fe2c9-106">Questa esercitazione illustra come usare ML.NET per compilare un [modello di clustering](../resources/tasks.md#clustering) per il [set di dati dei fiori iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="fe2c9-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="fe2c9-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="fe2c9-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="fe2c9-108">Understand the problem</span></span>
> - <span data-ttu-id="fe2c9-109">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="fe2c9-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="fe2c9-110">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="fe2c9-110">Prepare the data</span></span>
> - <span data-ttu-id="fe2c9-111">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="fe2c9-111">Load and transform the data</span></span>
> - <span data-ttu-id="fe2c9-112">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="fe2c9-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="fe2c9-113">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="fe2c9-113">Train the model</span></span>
> - <span data-ttu-id="fe2c9-114">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="fe2c9-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe2c9-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fe2c9-115">Prerequisites</span></span>

- <span data-ttu-id="fe2c9-116">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="fe2c9-117">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="fe2c9-117">Understand the problem</span></span>

<span data-ttu-id="fe2c9-118">Questo problema riguarda il set dei fiori iris in gruppi diversi in base alle caratteristiche dei fiori.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="fe2c9-119">Tali caratteristiche sono la lunghezza e la larghezza di un sepalo e la lunghezza e la larghezza di un petalo.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="fe2c9-120">Per questa esercitazione, si supponga che il tipo di ogni fiore sia sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="fe2c9-121">Si desidera apprendere la struttura di un set di dati dalle caratteristiche e prevedere come un'istanza di dati si adatta a questa struttura.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="fe2c9-122">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="fe2c9-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="fe2c9-123">Poiché non si sa a quale gruppo appartenga ciascun fiore, scegliere l'attività di [apprendimento automatico senza supervisione](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="fe2c9-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="fe2c9-124">Per dividere un set di dati in gruppi in modo che gli elementi nello stesso gruppo siano più simili tra loro rispetto a quelli di altri gruppi, usare un'attività di apprendimento automatico di [clustering](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="fe2c9-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="fe2c9-125">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="fe2c9-125">Create a console application</span></span>

1. <span data-ttu-id="fe2c9-126">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="fe2c9-127">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="fe2c9-128">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="fe2c9-129">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="fe2c9-130">Nella casella di testo **Nome** digitare "IrisFlowerClustering" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-130">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="fe2c9-131">Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati e del modello:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="fe2c9-132">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="fe2c9-133">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="fe2c9-134">Installare il pacchetto NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="fe2c9-135">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="fe2c9-136">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda **Sfoglia**, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="fe2c9-137">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="fe2c9-138">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="fe2c9-138">Prepare the data</span></span>

1. <span data-ttu-id="fe2c9-139">Scaricare il set di dati [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) e salvarlo nella cartella *Dati* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="fe2c9-140">Per altre informazioni sui set di dati iris, vedere la pagina [Dataset Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) di Wikipedia e la pagina [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris), che rappresenta l'origine del set di dati.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="fe2c9-141">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *iris.data* e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="fe2c9-142">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="fe2c9-143">Il file *iris.data* contiene cinque colonne che rappresentano:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="fe2c9-144">lunghezza del sepalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="fe2c9-144">sepal length in centimetres</span></span>
- <span data-ttu-id="fe2c9-145">larghezza del sepalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="fe2c9-145">sepal width in centimetres</span></span>
- <span data-ttu-id="fe2c9-146">lunghezza del petalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="fe2c9-146">petal length in centimetres</span></span>
- <span data-ttu-id="fe2c9-147">larghezza del petalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="fe2c9-147">petal width in centimetres</span></span>
- <span data-ttu-id="fe2c9-148">tipo di fiore iris</span><span class="sxs-lookup"><span data-stu-id="fe2c9-148">type of iris flower</span></span>

<span data-ttu-id="fe2c9-149">Per l'esempio del clustering, questa esercitazione ignora l'ultima colonna.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="fe2c9-150">Creare classi di dati</span><span class="sxs-lookup"><span data-stu-id="fe2c9-150">Create data classes</span></span>

<span data-ttu-id="fe2c9-151">Creare le classi per i dati di input e le stime:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="fe2c9-152">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="fe2c9-153">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="fe2c9-154">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="fe2c9-155">Aggiungere la direttiva `using` seguente al nuovo file:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="fe2c9-156">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le classi `IrisData` e `ClusterPrediction`, al file *IrisData.cs*:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="fe2c9-157">`IrisData` è la classe dei dati di input e contiene le definizioni per ogni caratteristica del set di dati.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="fe2c9-158">Usare l'attributo [Column](xref:Microsoft.ML.Data.ColumnAttribute) per specificare gli indici delle colonne di origine nel file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-158">Use the [Column](xref:Microsoft.ML.Data.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="fe2c9-159">La classe `ClusterPrediction` rappresenta l'output del modello di clustering applicato a un'istanza `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="fe2c9-160">Usare l'attributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) per associare i campi `PredictedClusterId` e `Distances` rispettivamente alle colonne **PredictedLabel** e **Score**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-160">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="fe2c9-161">In caso di attività di clustering, queste colonne hanno il significato seguente:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="fe2c9-162">La colonna **PredictedLabel** include l'ID del cluster stimato.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="fe2c9-163">La colonna **Score** contiene una matrice con le distanze Euclidee quadrate rispetto ai centroidi del cluster.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="fe2c9-164">La lunghezza della matrice è uguale al numero di cluster.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="fe2c9-165">Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="fe2c9-166">Definire i percorsi dei dati e del modello</span><span class="sxs-lookup"><span data-stu-id="fe2c9-166">Define data and model paths</span></span>

<span data-ttu-id="fe2c9-167">Tornare al file *Program.cs* e aggiungere due campi per i percorsi del file dei set di dati e del file per il salvataggio del modello:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="fe2c9-168">`_dataPath` contiene il percorso del file con il set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="fe2c9-169">`_modelPath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="fe2c9-170">Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="fe2c9-171">Per consentire la compilazione del codice precedente, aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="fe2c9-172">Creare il contesto di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="fe2c9-172">Create ML context</span></span>

<span data-ttu-id="fe2c9-173">Aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="fe2c9-174">Nel metodo `Main` sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-174">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="fe2c9-175">La classe <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> rappresenta l'ambiente di machine learning (apprendimento automatico) e offre meccanismi per la registrazione e punti di ingresso per il caricamento dei dati, il training del modello, le stime e altre attività.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-175">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="fe2c9-176">A livello concettuale questa operazione è paragonabile all'uso di `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-176">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="fe2c9-177">Impostazione del caricamento di dati</span><span class="sxs-lookup"><span data-stu-id="fe2c9-177">Setup data loading</span></span>

<span data-ttu-id="fe2c9-178">Aggiungere il codice seguente al metodo `Main` per configurare la modalità di caricamento di dati:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-178">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SetupTextLoader)]

<span data-ttu-id="fe2c9-179">Si noti che i nomi e gli indici delle colonne corrispondono allo schema definito dalla classe `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-179">Note that the column names and indices match the schema defined by the `IrisData` class.</span></span> <span data-ttu-id="fe2c9-180">Il valore <xref:Microsoft.ML.Data.DataKind.R4?displayProperty=nameWithType> specifica il tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-180">The <xref:Microsoft.ML.Data.DataKind.R4?displayProperty=nameWithType> value specifies the `float` type.</span></span>

<span data-ttu-id="fe2c9-181">Usare l'istanza creata <xref:Microsoft.ML.Data.TextLoader> per creare un'istanza <xref:Microsoft.ML.Data.IDataView>, che rappresenta l'origine dati per il training set:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-181">Use instantiated <xref:Microsoft.ML.Data.TextLoader> instance to create an <xref:Microsoft.ML.Data.IDataView> instance, which represents the data source for the training data set:</span></span>

[!code-csharp[Create IDataView](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="fe2c9-182">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="fe2c9-182">Create a learning pipeline</span></span>

<span data-ttu-id="fe2c9-183">Per questa esercitazione, la pipeline di apprendimento dell'attività di clustering è costituita dai due passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-183">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="fe2c9-184">Concatenare le colonne caricate in un'unica colonna **Features**, che viene usata da un trainer di clustering;</span><span class="sxs-lookup"><span data-stu-id="fe2c9-184">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="fe2c9-185">Usare un trainer <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> per eseguire il training del modello usando l'algoritmo di clustering k-means++.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-185">use a <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="fe2c9-186">Aggiungere al metodo `Main` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-186">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="fe2c9-187">Il codice specifica che il set di dati deve essere suddiviso in tre cluster.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-187">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="fe2c9-188">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="fe2c9-188">Train the model</span></span>

<span data-ttu-id="fe2c9-189">I passaggi aggiunti nelle sezioni precedenti hanno preparato la pipeline per il training, che tuttavia non è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-189">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="fe2c9-190">Aggiungere la riga seguente al metodo `Main` per eseguire il caricamento dei dati e il training del modello:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-190">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="fe2c9-191">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="fe2c9-191">Save the model</span></span>

<span data-ttu-id="fe2c9-192">A questo punto, è disponibile un modello che può essere integrato in tutte le applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-192">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="fe2c9-193">Per salvare il modello in un file con estensione zip, aggiungere il codice seguente al metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-193">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="fe2c9-194">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="fe2c9-194">Use the model for predictions</span></span>

<span data-ttu-id="fe2c9-195">Per eseguire stime, usare la classe <xref:Microsoft.ML.PredictionEngine%602>, che accetta le istanze del tipo di input tramite la pipeline convertitore e genera istanze del tipo di output.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-195">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="fe2c9-196">Aggiungere la riga seguente al metodo `Main` per creare un'istanza della classe:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-196">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="fe2c9-197">Creare la classe `TestIrisData` per ospitare le istanze dei dati di test:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-197">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="fe2c9-198">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-198">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="fe2c9-199">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-199">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="fe2c9-200">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-200">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="fe2c9-201">Modificare la classe in modo da renderla statica, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-201">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="fe2c9-202">Questa esercitazione presenta un'istanza di dati iris all'interno di questa classe.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-202">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="fe2c9-203">È possibile aggiungere altri scenari da sperimentare con il modello.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-203">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="fe2c9-204">Aggiungere il codice seguente nella classe `TestIrisData`:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-204">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="fe2c9-205">Per individuare il cluster a cui appartiene l'elemento specificato, tornare al file *Program.cs* e aggiungere il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-205">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="fe2c9-206">Eseguire il programma per vedere quale cluster contiene l'istanza dati specificata e le distanze al quadrato da tale istanza ai centroidi del cluster.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-206">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="fe2c9-207">I risultati saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-207">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="fe2c9-208">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-208">Congratulations!</span></span> <span data-ttu-id="fe2c9-209">È stato creato un modello di apprendimento automatico per il clustering iris, quindi il modello è stato usato per produrre stime.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-209">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="fe2c9-210">È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering).</span><span class="sxs-lookup"><span data-stu-id="fe2c9-210">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe2c9-211">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fe2c9-211">Next steps</span></span>

<span data-ttu-id="fe2c9-212">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="fe2c9-212">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="fe2c9-213">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="fe2c9-213">Understand the problem</span></span>
> - <span data-ttu-id="fe2c9-214">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="fe2c9-214">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="fe2c9-215">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="fe2c9-215">Prepare the data</span></span>
> - <span data-ttu-id="fe2c9-216">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="fe2c9-216">Load and transform the data</span></span>
> - <span data-ttu-id="fe2c9-217">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="fe2c9-217">Choose a learning algorithm</span></span>
> - <span data-ttu-id="fe2c9-218">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="fe2c9-218">Train the model</span></span>
> - <span data-ttu-id="fe2c9-219">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="fe2c9-219">Use the model for predictions</span></span>

<span data-ttu-id="fe2c9-220">Visitare il repository GitHub per ottenere altre informazioni ed esempi.</span><span class="sxs-lookup"><span data-stu-id="fe2c9-220">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="fe2c9-221">Repository GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="fe2c9-221">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
