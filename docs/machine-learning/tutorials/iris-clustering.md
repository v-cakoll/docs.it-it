---
title: Usare ML.NET per raggruppare i fiori iris (clustering)
description: Informazioni su come usare ML.NET in uno scenario di clustering
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 46db9dc7ff425c483f1a9f61da5e806e598b16d5
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937166"
---
# <a name="tutorial-use-mlnet-to-cluster-iris-flowers-clustering"></a><span data-ttu-id="ce16f-103">Esercitazione: usare ML.NET per raggruppare i fiori iris (clustering)</span><span class="sxs-lookup"><span data-stu-id="ce16f-103">Tutorial: Use ML.NET to cluster iris flowers (clustering)</span></span>

> [!NOTE]
> <span data-ttu-id="ce16f-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="ce16f-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ce16f-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="ce16f-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ce16f-106">Questa esercitazione illustra come usare ML.NET per compilare un [modello di clustering](../resources/tasks.md#clustering) per il [set di dati dei fiori iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="ce16f-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="ce16f-107">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="ce16f-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="ce16f-108">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ce16f-108">Understand the problem</span></span>
> - <span data-ttu-id="ce16f-109">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="ce16f-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="ce16f-110">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="ce16f-110">Prepare the data</span></span>
> - <span data-ttu-id="ce16f-111">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="ce16f-111">Load and transform the data</span></span>
> - <span data-ttu-id="ce16f-112">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ce16f-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="ce16f-113">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ce16f-113">Train the model</span></span>
> - <span data-ttu-id="ce16f-114">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="ce16f-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ce16f-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ce16f-115">Prerequisites</span></span>

- <span data-ttu-id="ce16f-116">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="ce16f-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="ce16f-117">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ce16f-117">Understand the problem</span></span>

<span data-ttu-id="ce16f-118">Questo problema riguarda il set dei fiori iris in gruppi diversi in base alle caratteristiche dei fiori.</span><span class="sxs-lookup"><span data-stu-id="ce16f-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="ce16f-119">Tali caratteristiche sono la lunghezza e la larghezza di un sepalo e la lunghezza e la larghezza di un petalo.</span><span class="sxs-lookup"><span data-stu-id="ce16f-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="ce16f-120">Per questa esercitazione, si supponga che il tipo di ogni fiore sia sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ce16f-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="ce16f-121">Si desidera apprendere la struttura di un set di dati dalle caratteristiche e prevedere come un'istanza di dati si adatta a questa struttura.</span><span class="sxs-lookup"><span data-stu-id="ce16f-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="ce16f-122">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="ce16f-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="ce16f-123">Poiché non si sa a quale gruppo appartenga ciascun fiore, scegliere l'attività di [apprendimento automatico senza supervisione](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="ce16f-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="ce16f-124">Per dividere un set di dati in gruppi in modo che gli elementi nello stesso gruppo siano più simili tra loro rispetto a quelli di altri gruppi, usare un'attività di apprendimento automatico di [clustering](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="ce16f-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="ce16f-125">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="ce16f-125">Create a console application</span></span>

1. <span data-ttu-id="ce16f-126">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ce16f-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="ce16f-127">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="ce16f-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="ce16f-128">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="ce16f-129">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="ce16f-130">Nella casella di testo **Nome** digitare "IrisClustering" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-130">In the **Name** text box, type "IrisClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="ce16f-131">Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati e del modello:</span><span class="sxs-lookup"><span data-stu-id="ce16f-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="ce16f-132">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="ce16f-133">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="ce16f-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="ce16f-134">Installare il pacchetto NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="ce16f-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="ce16f-135">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="ce16f-136">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda **Sfoglia**, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="ce16f-137">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="ce16f-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="ce16f-138">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="ce16f-138">Prepare the data</span></span>

1. <span data-ttu-id="ce16f-139">Scaricare il set di dati [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) e salvarlo nella cartella *Dati* creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="ce16f-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="ce16f-140">Per altre informazioni sui set di dati iris, vedere la pagina [Dataset Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) di Wikipedia e la pagina [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris), che rappresenta l'origine del set di dati.</span><span class="sxs-lookup"><span data-stu-id="ce16f-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="ce16f-141">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *iris.data* e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="ce16f-142">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="ce16f-143">Il file *iris.data* contiene cinque colonne che rappresentano:</span><span class="sxs-lookup"><span data-stu-id="ce16f-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="ce16f-144">lunghezza del sepalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="ce16f-144">sepal length in centimetres</span></span>
- <span data-ttu-id="ce16f-145">larghezza del sepalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="ce16f-145">sepal width in centimetres</span></span>
- <span data-ttu-id="ce16f-146">lunghezza del petalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="ce16f-146">petal length in centimetres</span></span>
- <span data-ttu-id="ce16f-147">larghezza del petalo in centimetri</span><span class="sxs-lookup"><span data-stu-id="ce16f-147">petal width in centimetres</span></span>
- <span data-ttu-id="ce16f-148">tipo di fiore iris</span><span class="sxs-lookup"><span data-stu-id="ce16f-148">type of iris flower</span></span>

<span data-ttu-id="ce16f-149">Per l'esempio del clustering, questa esercitazione ignora l'ultima colonna.</span><span class="sxs-lookup"><span data-stu-id="ce16f-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="ce16f-150">Creare classi di dati</span><span class="sxs-lookup"><span data-stu-id="ce16f-150">Create data classes</span></span>

<span data-ttu-id="ce16f-151">Creare le classi per i dati di input e le stime:</span><span class="sxs-lookup"><span data-stu-id="ce16f-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="ce16f-152">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="ce16f-153">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="ce16f-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="ce16f-154">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="ce16f-155">Aggiungere la direttiva `using` seguente al nuovo file:</span><span class="sxs-lookup"><span data-stu-id="ce16f-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

<span data-ttu-id="ce16f-156">Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le classi `IrisData` e `ClusterPrediction`, al file *IrisData.cs*:</span><span class="sxs-lookup"><span data-stu-id="ce16f-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

<span data-ttu-id="ce16f-157">`IrisData` è la classe dei dati di input e contiene le definizioni per ogni caratteristica del set di dati.</span><span class="sxs-lookup"><span data-stu-id="ce16f-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="ce16f-158">Usare l'attributo [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) per specificare gli indici delle colonne di origine nel file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="ce16f-158">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="ce16f-159">La classe `ClusterPrediction` rappresenta l'output del modello di clustering applicato a un'istanza `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="ce16f-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="ce16f-160">Usare l'attributo [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) per associare i campi `PredictedClusterId` e `Distances` rispettivamente alle colonne **PredictedLabel** e **Score**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-160">Use the [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="ce16f-161">In caso di attività di clustering queste colonne hanno il seguente significato:</span><span class="sxs-lookup"><span data-stu-id="ce16f-161">In case of the clustering task those columns has the following meaning:</span></span>

- <span data-ttu-id="ce16f-162">La colonna **PredictedLabel** include l'ID del cluster stimato.</span><span class="sxs-lookup"><span data-stu-id="ce16f-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="ce16f-163">La colonna **Score** contiene una matrice con le distanze Euclidee quadrate rispetto ai centroidi del cluster.</span><span class="sxs-lookup"><span data-stu-id="ce16f-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="ce16f-164">La lunghezza della matrice è uguale al numero di cluster.</span><span class="sxs-lookup"><span data-stu-id="ce16f-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="ce16f-165">Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.</span><span class="sxs-lookup"><span data-stu-id="ce16f-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="ce16f-166">Definire i percorsi dei dati e del modello</span><span class="sxs-lookup"><span data-stu-id="ce16f-166">Define data and model paths</span></span>

<span data-ttu-id="ce16f-167">Tornare al file *Program.cs* e aggiungere due campi per i percorsi del file dei set di dati e del file per il salvataggio del modello:</span><span class="sxs-lookup"><span data-stu-id="ce16f-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="ce16f-168">`_dataPath` contiene il percorso del file con il set di dati usato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ce16f-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="ce16f-169">`_modelPath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="ce16f-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="ce16f-170">Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi:</span><span class="sxs-lookup"><span data-stu-id="ce16f-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

<span data-ttu-id="ce16f-171">Per consentire la compilazione del codice precedente, aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ce16f-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="ce16f-172">Creare una pipeline di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ce16f-172">Create a learning pipeline</span></span>

<span data-ttu-id="ce16f-173">Aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ce16f-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

<span data-ttu-id="ce16f-174">Nel metodo `Main` sostituire `Console.WriteLine("Hello World!")` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-174">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

<span data-ttu-id="ce16f-175">Il metodo `Train` esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ce16f-175">The `Train` method trains the model.</span></span> <span data-ttu-id="ce16f-176">Creare il metodo subito sotto il metodo `Main` usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-176">Create that method just below the `Main` method, using the following code:</span></span>

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

<span data-ttu-id="ce16f-177">La pipeline di apprendimento carica tutti i dati e gli algoritmi necessari per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ce16f-177">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="ce16f-178">Aggiungere nel metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-178">Add the following code into the `Train` method:</span></span>

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a><span data-ttu-id="ce16f-179">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="ce16f-179">Load and transform data</span></span>

<span data-ttu-id="ce16f-180">Il primo passaggio da eseguire consiste nel caricare il set di dati del training.</span><span class="sxs-lookup"><span data-stu-id="ce16f-180">The first step to perform is to load the training data set.</span></span> <span data-ttu-id="ce16f-181">Nel caso di questo esempio il training set è archiviato nel file di testo con un percorso definito dal campo `_dataPath`.</span><span class="sxs-lookup"><span data-stu-id="ce16f-181">In our case, the training data set is stored in the text file with a path defined by the `_dataPath` field.</span></span> <span data-ttu-id="ce16f-182">Le colonne nel file sono separate da una virgola (",").</span><span class="sxs-lookup"><span data-stu-id="ce16f-182">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="ce16f-183">Aggiungere nel metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-183">Add the following code into the `Train` method:</span></span>

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

<span data-ttu-id="ce16f-184">Il passaggio successivo combina tutte le colonne delle caratteristiche nella colonna **Features** usando la classe di trasformazione <xref:Microsoft.ML.Transforms.ColumnConcatenator>.</span><span class="sxs-lookup"><span data-stu-id="ce16f-184">The next step is to combine all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="ce16f-185">Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-185">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="ce16f-186">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-186">Add the following code:</span></span>

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="ce16f-187">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ce16f-187">Choose a learning algorithm</span></span>

<span data-ttu-id="ce16f-188">Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, selezionare un **algoritmo di apprendimento**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-188">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="ce16f-189">L'algoritmo di apprendimento esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ce16f-189">The learner trains the model.</span></span> <span data-ttu-id="ce16f-190">ML.NET fornisce un algoritmo di apprendimento <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer> che implementa l'[algoritmo k-means](https://en.wikipedia.org/wiki/K-means_clustering) con un metodo migliorato per la scelta dei centroidi del cluster iniziale.</span><span class="sxs-lookup"><span data-stu-id="ce16f-190">ML.NET provides a <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer> learner that implements [k-means algorithm](https://en.wikipedia.org/wiki/K-means_clustering) with an improved method for choosing the initial cluster centroids.</span></span>

<span data-ttu-id="ce16f-191">Aggiungere il codice seguente nel metodo `Train` dopo il codice di elaborazione dei dati aggiunto nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-191">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

<span data-ttu-id="ce16f-192">Usare la proprietà <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> per specificare il numero di cluster.</span><span class="sxs-lookup"><span data-stu-id="ce16f-192">Use the <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> property to specify number of clusters.</span></span> <span data-ttu-id="ce16f-193">Il codice precedente specifica che il set di dati deve essere suddiviso in tre cluster.</span><span class="sxs-lookup"><span data-stu-id="ce16f-193">The code above specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="ce16f-194">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ce16f-194">Train the model</span></span>

<span data-ttu-id="ce16f-195">I passaggi aggiunti nelle sezioni precedenti hanno preparato la pipeline per il training, che tuttavia non è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="ce16f-195">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="ce16f-196">Il metodo `pipeline.Train<TInput, TOutput>` produce il modello che accetta un'istanza del tipo `TInput` e restituisce un'istanza del tipo `TOutput`.</span><span class="sxs-lookup"><span data-stu-id="ce16f-196">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="ce16f-197">Aggiungere nel metodo `Train` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-197">Add the following code into the `Train` method:</span></span>

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a><span data-ttu-id="ce16f-198">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="ce16f-198">Save the model</span></span>

<span data-ttu-id="ce16f-199">A questo punto, è disponibile un modello che può essere integrato in tutte le applicazioni .NET nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="ce16f-199">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="ce16f-200">Per salvare il modello in un file con estensione zip, aggiungere il codice seguente al metodo `Main` sotto la chiamata al metodo `Train`:</span><span class="sxs-lookup"><span data-stu-id="ce16f-200">To save your model to a .zip file, add the following code to the `Main` method below the call to the `Train` method:</span></span>

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

<span data-ttu-id="ce16f-201">L'uso di `await` nel metodo `Main` implica che il metodo `Main` deve avere il modificatore `async` e restituire un elemento `Task`:</span><span class="sxs-lookup"><span data-stu-id="ce16f-201">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

<span data-ttu-id="ce16f-202">È anche necessario aggiungere la direttiva `using` seguente all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ce16f-202">You also need to add the following `using` directive at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

<span data-ttu-id="ce16f-203">Poiché il metodo `async Main` è la funzionalità aggiunta in C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ce16f-203">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="ce16f-204">A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-204">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="ce16f-205">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-205">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="ce16f-206">Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="ce16f-206">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="ce16f-207">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="ce16f-207">Select the **OK** button.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="ce16f-208">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="ce16f-208">Use the model for predictions</span></span>

<span data-ttu-id="ce16f-209">Creare la classe `TestIrisData` per ospitare le istanze dei dati di test:</span><span class="sxs-lookup"><span data-stu-id="ce16f-209">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="ce16f-210">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-210">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="ce16f-211">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="ce16f-211">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="ce16f-212">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ce16f-212">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="ce16f-213">Modificare la classe in modo da renderla statica, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ce16f-213">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

<span data-ttu-id="ce16f-214">Questa esercitazione presenta un'istanza di dati iris all'interno di questa classe.</span><span class="sxs-lookup"><span data-stu-id="ce16f-214">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="ce16f-215">È possibile aggiungere altri scenari da sperimentare con il modello.</span><span class="sxs-lookup"><span data-stu-id="ce16f-215">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="ce16f-216">Aggiungere il codice seguente nella classe `TestIrisData`:</span><span class="sxs-lookup"><span data-stu-id="ce16f-216">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

<span data-ttu-id="ce16f-217">Per individuare il cluster a cui appartiene l'elemento specificato, tornare al file *Program.cs* e aggiungere il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="ce16f-217">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

<span data-ttu-id="ce16f-218">Eseguire il programma per vedere quale cluster contiene l'istanza dati specificata e le distanze al quadrato da tale istanza ai centroidi del cluster.</span><span class="sxs-lookup"><span data-stu-id="ce16f-218">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="ce16f-219">I risultati dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ce16f-219">Your results should be similar to the following.</span></span> <span data-ttu-id="ce16f-220">Mentre la pipeline viene elaborata, potrebbe visualizzare avvisi o elaborare messaggi.</span><span class="sxs-lookup"><span data-stu-id="ce16f-220">As the pipeline processes, it might display warnings or processing messages.</span></span> <span data-ttu-id="ce16f-221">Questi elementi sono stati rimossi dall'output seguente per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="ce16f-221">These have been removed from the following output for clarity.</span></span>

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

<span data-ttu-id="ce16f-222">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ce16f-222">Congratulations!</span></span> <span data-ttu-id="ce16f-223">È stato creato un modello di apprendimento automatico per il clustering iris, quindi il modello è stato usato per produrre stime.</span><span class="sxs-lookup"><span data-stu-id="ce16f-223">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="ce16f-224">È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering).</span><span class="sxs-lookup"><span data-stu-id="ce16f-224">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce16f-225">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ce16f-225">Next steps</span></span>

<span data-ttu-id="ce16f-226">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="ce16f-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="ce16f-227">Informazioni sul problema</span><span class="sxs-lookup"><span data-stu-id="ce16f-227">Understand the problem</span></span>
> - <span data-ttu-id="ce16f-228">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="ce16f-228">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="ce16f-229">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="ce16f-229">Prepare the data</span></span>
> - <span data-ttu-id="ce16f-230">Caricare e trasformare i dati</span><span class="sxs-lookup"><span data-stu-id="ce16f-230">Load and transform the data</span></span>
> - <span data-ttu-id="ce16f-231">Scegliere un algoritmo di apprendimento</span><span class="sxs-lookup"><span data-stu-id="ce16f-231">Choose a learning algorithm</span></span>
> - <span data-ttu-id="ce16f-232">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ce16f-232">Train the model</span></span>
> - <span data-ttu-id="ce16f-233">Usare il modello per le stime</span><span class="sxs-lookup"><span data-stu-id="ce16f-233">Use the model for predictions</span></span>

<span data-ttu-id="ce16f-234">Visitare il repository GitHub per ottenere altre informazioni ed esempi.</span><span class="sxs-lookup"><span data-stu-id="ce16f-234">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ce16f-235">Repository GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="ce16f-235">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
