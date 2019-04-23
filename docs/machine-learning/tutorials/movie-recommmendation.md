---
title: Usare ML.NET in uno scenario di raccomandazione di film
description: Informazioni su come usare ML.NET in uno scenario di raccomandazione per consigliare i film agli utenti.
author: briacht
ms.author: johalex
ms.date: 03/08/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: efa217440ae636422bc8d2bd429f0396d7d28057
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311097"
---
# <a name="tutorial-create-a-movie-recommender-with-mlnet"></a><span data-ttu-id="8279f-103">Esercitazione: Creare un sistema di raccomandazione di film con ML.NET</span><span class="sxs-lookup"><span data-stu-id="8279f-103">Tutorial: Create a Movie Recommender with ML.NET</span></span>

<span data-ttu-id="8279f-104">Questa esercitazione di esempio illustra come usare ML.NET per creare un sistema di raccomandazione di film tramite un'applicazione console .NET Core usando C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8279f-104">This sample tutorial illustrates using ML.NET to build a movie recommender via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="8279f-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="8279f-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="8279f-106">Selezionare un algoritmo di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8279f-106">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="8279f-107">Preparare e caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8279f-107">Prepare and load your data</span></span>
> * <span data-ttu-id="8279f-108">Creare un modello ed eseguirne il training</span><span class="sxs-lookup"><span data-stu-id="8279f-108">Build and train a model</span></span>
> * <span data-ttu-id="8279f-109">Valutare un modello</span><span class="sxs-lookup"><span data-stu-id="8279f-109">Evaluate a model</span></span>
> * <span data-ttu-id="8279f-110">Distribuire e usare un modello</span><span class="sxs-lookup"><span data-stu-id="8279f-110">Deploy and consume a model</span></span>

> [!NOTE]
> <span data-ttu-id="8279f-111">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="8279f-111">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="8279f-112">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="8279f-112">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="8279f-113">Questa esercitazione e l'esempio correlato usano attualmente **ML.NET versione 0.11**.</span><span class="sxs-lookup"><span data-stu-id="8279f-113">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="8279f-114">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="8279f-114">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="8279f-115">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="8279f-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="8279f-116">Flusso di lavoro di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="8279f-116">Machine learning workflow</span></span>

<span data-ttu-id="8279f-117">Per completare questa attività, così come qualsiasi altra attività ML.NET, si useranno i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8279f-117">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="8279f-118">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8279f-118">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="8279f-119">Creare il modello ed eseguirne il training</span><span class="sxs-lookup"><span data-stu-id="8279f-119">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="8279f-120">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="8279f-120">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="8279f-121">Usare il modello</span><span class="sxs-lookup"><span data-stu-id="8279f-121">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="8279f-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8279f-122">Prerequisites</span></span>

* <span data-ttu-id="8279f-123">[Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="8279f-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="8279f-124">Selezionare l'attività di apprendimento automatico appropriata</span><span class="sxs-lookup"><span data-stu-id="8279f-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="8279f-125">I problemi relativi alla raccomandazione, ad esempio la raccomandazione di un elenco di film o di un elenco di prodotti correlati, possono essere affrontati in diversi modi, ma in questo caso si effettuerà la previsione della valutazione (da 1 a 5) che un utente assegnerà a un determinato film e si raccomanderà il film se è stato valutato al di sopra di una soglia definita (tanto più elevata è la valutazione, quanto più elevata sarà la probabilità che a un utente piaccia un determinato film).</span><span class="sxs-lookup"><span data-stu-id="8279f-125">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="8279f-126">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="8279f-126">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="8279f-127">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="8279f-127">Create a project</span></span>

1. <span data-ttu-id="8279f-128">Aprire Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8279f-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="8279f-129">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="8279f-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="8279f-130">Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="8279f-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="8279f-131">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="8279f-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="8279f-132">Nella casella di testo **Nome** digitare "MovieRecommender" e quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="8279f-132">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="8279f-133">Creare una directory denominata *Data* nel progetto per archiviare il set di dati:</span><span class="sxs-lookup"><span data-stu-id="8279f-133">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="8279f-134">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="8279f-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="8279f-135">Digitare "Data" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8279f-135">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="8279f-136">Installare i pacchetti NuGet **Microsoft.ML** e **Microsoft.ML.Recommender**:</span><span class="sxs-lookup"><span data-stu-id="8279f-136">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    <span data-ttu-id="8279f-137">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="8279f-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8279f-138">Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda **Sfoglia**, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**.</span><span class="sxs-lookup"><span data-stu-id="8279f-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="8279f-139">Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.</span><span class="sxs-lookup"><span data-stu-id="8279f-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="8279f-140">Ripetere questi passaggi per **Microsoft.ML.Recommender**.</span><span class="sxs-lookup"><span data-stu-id="8279f-140">Repeat these steps for **Microsoft.ML.Recommender**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8279f-141">Questa esercitazione usa **Microsoft.ML v0.11.0** e **Microsoft.ML.Recommender v0.11.0**.</span><span class="sxs-lookup"><span data-stu-id="8279f-141">This tutorial uses **Microsoft.ML v0.11.0** and **Microsoft.ML.Recommender v0.11.0**.</span></span>

4. <span data-ttu-id="8279f-142">Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="8279f-142">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[UsingStatements](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="8279f-143">Scaricare i dati</span><span class="sxs-lookup"><span data-stu-id="8279f-143">Download your data</span></span>

1. <span data-ttu-id="8279f-144">Scaricare i due set di dati e salvarli nella cartella *Data* precedentemente creata:</span><span class="sxs-lookup"><span data-stu-id="8279f-144">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="8279f-145">Fare clic con il pulsante destro del mouse su [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."</span><span class="sxs-lookup"><span data-stu-id="8279f-145">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
   * <span data-ttu-id="8279f-146">Fare clic con il pulsante destro del mouse su [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."</span><span class="sxs-lookup"><span data-stu-id="8279f-146">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="8279f-147">Assicurarsi di salvare i file \*.csv nella cartella *Data* oppure, dopo averli salvati in un altro percorso, spostare i file \*.csv nella cartella *Data*.</span><span class="sxs-lookup"><span data-stu-id="8279f-147">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="8279f-148">In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione csv e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8279f-148">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="8279f-149">In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="8279f-149">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![Copia se più recente in VS](./media/movie-recommendation/copytoout.gif)

## <a name="load-your-data"></a><span data-ttu-id="8279f-151">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8279f-151">Load your data</span></span>

<span data-ttu-id="8279f-152">Il primo passaggio del processo ML.NET è la preparazione e il caricamento dei dati di training e test del modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-152">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="8279f-153">I dati delle valutazioni della raccomandazione vengono divisi in set di dati `Train` e `Test`.</span><span class="sxs-lookup"><span data-stu-id="8279f-153">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="8279f-154">I dati `Train` vengono usati per il fit del modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-154">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="8279f-155">I dati `Test` vengono usati per effettuare previsioni con il modello sottoposto a training e valutarne le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8279f-155">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="8279f-156">Per i dati `Train` e `Test` in genere si applica una suddivisione 80/20.</span><span class="sxs-lookup"><span data-stu-id="8279f-156">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="8279f-157">Di seguito è un'anteprima dei dati di \*file con estensione csv:</span><span class="sxs-lookup"><span data-stu-id="8279f-157">Below is a preview of the data from your \*.csv files:</span></span>

![anteprima dei dati](./media/movie-recommendation/csv-dataset-preview.png)

<span data-ttu-id="8279f-159">Nel \*file con estensione csv, sono disponibili quattro colonne:</span><span class="sxs-lookup"><span data-stu-id="8279f-159">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="8279f-160">Nel Machine Learning le colonne usate per effettuare una previsione sono denominate [Features](../resources/glossary.md#feature) (Caratteristiche) e la colonna con la previsione restituita è denominata [Label](../resources/glossary.md#label) (Etichetta).</span><span class="sxs-lookup"><span data-stu-id="8279f-160">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="8279f-161">In questo caso si vuole prevedere le valutazioni di film, quindi la colonna della valutazione è la colonna `Label`.</span><span class="sxs-lookup"><span data-stu-id="8279f-161">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="8279f-162">Le altre tre colonne, `userId`, `movieId` e `timestamp`, sono tutte `Features` usate per la previsione di `Label`.</span><span class="sxs-lookup"><span data-stu-id="8279f-162">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="8279f-163">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="8279f-163">Features</span></span>      | <span data-ttu-id="8279f-164">Label</span><span class="sxs-lookup"><span data-stu-id="8279f-164">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

<span data-ttu-id="8279f-165">È possibile decidere quali `Features` vengono usate per la previsione di `Label`.</span><span class="sxs-lookup"><span data-stu-id="8279f-165">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="8279f-166">Per selezionare le `Features` migliori si possono anche usare metodi quali [Permutation Feature Importance](../how-to-guides/determine-global-feature-importance-in-model.md).</span><span class="sxs-lookup"><span data-stu-id="8279f-166">You can also use methods like [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="8279f-167">In questo caso è consigliabile eliminare la colonna `timestamp` come `Feature` perché il timestamp in realtà non influisce sulla valutazione di un determinato film da parte di un utente e quindi non contribuisce a effettuare una previsione più accurata:</span><span class="sxs-lookup"><span data-stu-id="8279f-167">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="8279f-168">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="8279f-168">Features</span></span>      | <span data-ttu-id="8279f-169">Label</span><span class="sxs-lookup"><span data-stu-id="8279f-169">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

<span data-ttu-id="8279f-170">È quindi necessario definire la struttura dei dati per la classe di input.</span><span class="sxs-lookup"><span data-stu-id="8279f-170">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="8279f-171">Aggiungere una nuova classe al progetto:</span><span class="sxs-lookup"><span data-stu-id="8279f-171">Add a new class to your project:</span></span>

1. <span data-ttu-id="8279f-172">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Aggiungi > Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8279f-172">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="8279f-173">Nella **finestra di dialogo Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** in *MovieRatingData.cs*.</span><span class="sxs-lookup"><span data-stu-id="8279f-173">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="8279f-174">Selezionare quindi il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8279f-174">Then, select the **Add** button.</span></span>

<span data-ttu-id="8279f-175">Il file *MovieRatingData.cs* verrà aperto nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="8279f-175">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="8279f-176">Aggiungere l'istruzione `using` seguente all'inizio di *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="8279f-176">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="8279f-177">Creare una classe denominata `MovieRating` rimuovendo la definizione di classe esistente e aggiungendo il codice seguente in *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="8279f-177">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

`MovieRating` <span data-ttu-id="8279f-178">specifica una classe di dati di input.</span><span class="sxs-lookup"><span data-stu-id="8279f-178">specifies an input data class.</span></span> <span data-ttu-id="8279f-179">L'attributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) specifica quali colonne (in base all'indice delle colonne) nel set di dati è necessario caricare.</span><span class="sxs-lookup"><span data-stu-id="8279f-179">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="8279f-180">Le colonne `userId` e `movieId` sono le `Features`, ovvero gli input che si forniranno al modello per la previsione di `Label`, e la colonna della valutazione è l'oggetto `Label` di cui si otterrà la previsione, ovvero l'output del modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-180">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="8279f-181">Creare un'altra classe, `MovieRatingPrediction`, per rappresentare i risultati previsti aggiungendo il codice seguente dopo la classe `MovieRating` in *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="8279f-181">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="8279f-182">In *Program.cs* sostituire `Console.WriteLine("Hello World!")` con il codice seguente all'interno di `Main()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-182">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="8279f-183">La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-183">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="8279f-184">Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8279f-184">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="8279f-185">Dopo `Main()`, creare un metodo denominato `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-185">After `Main()`, create a method called `LoadData()`:</span></span>

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> <span data-ttu-id="8279f-186">Questo metodo restituisce un errore finché non si aggiungerà un'istruzione return nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8279f-186">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="8279f-187">Inizializzare le variabili di percorso dei dati, caricare i dati dai file con estensione csv e restituire i dati `Train` e `Test` come oggetti `IDataView` aggiungendo il codice seguente come riga successiva in `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-187">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="8279f-188">I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="8279f-188">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> `IDataView` <span data-ttu-id="8279f-189">è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo).</span><span class="sxs-lookup"><span data-stu-id="8279f-189">is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="8279f-190">È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="8279f-190">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="8279f-191">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="8279f-191">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="8279f-192">Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="8279f-192">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="8279f-193">In questo caso viene specificato il percorso dei file `Test` e `Train` e vengono indicati sia l'intestazione del file di testo, in modo che il metodo possa usare correttamente i nomi di colonna, sia la virgola come separatore dei dati di tipo carattere (il separatore predefinito è una tabulazione).</span><span class="sxs-lookup"><span data-stu-id="8279f-193">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="8279f-194">Aggiungere queste due righe di codice come righe successive nel metodo `Main()` per chiamare il metodo `LoadData()` e restituire i dati `Train` e `Test`:</span><span class="sxs-lookup"><span data-stu-id="8279f-194">Add the following as the next two lines of code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a><span data-ttu-id="8279f-195">Creare il modello ed eseguirne il training</span><span class="sxs-lookup"><span data-stu-id="8279f-195">Build and train your model</span></span>

<span data-ttu-id="8279f-196">ML.NET si basa su tre concetti fondamentali: [dati](../basic-concepts-model-training-in-mldotnet.md#data), [trasformatori](../basic-concepts-model-training-in-mldotnet.md#transformer) e [strumenti di stima](../basic-concepts-model-training-in-mldotnet.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="8279f-196">There are three major concepts in ML.NET: [Data](../basic-concepts-model-training-in-mldotnet.md#data), [Transformers](../basic-concepts-model-training-in-mldotnet.md#transformer), and [Estimators](../basic-concepts-model-training-in-mldotnet.md#estimator).</span></span>

<span data-ttu-id="8279f-197">Gli algoritmi di training del Machine Learning necessitano di dati in un determinato formato.</span><span class="sxs-lookup"><span data-stu-id="8279f-197">Machine learning training algorithms require data in a certain format.</span></span> `Transformers` <span data-ttu-id="8279f-198">sono usati per trasformare i dati tabulari in un formato compatibile.</span><span class="sxs-lookup"><span data-stu-id="8279f-198">are used to transform tabular data to a compatible format.</span></span>

![immagine di trasformatore](./media/movie-recommendation/transformer.png)

<span data-ttu-id="8279f-200">In ML.NET è possibile creare `Transformers` tramite la creazione di `Estimators`.</span><span class="sxs-lookup"><span data-stu-id="8279f-200">You create `Transformers` in ML.NET by creating `Estimators`.</span></span> `Estimators` <span data-ttu-id="8279f-201">acquisiscono i dati e restituiscono `Transformers`.</span><span class="sxs-lookup"><span data-stu-id="8279f-201">take in data and return `Transformers`.</span></span>

![immagine di strumento di stima](./media/movie-recommendation/estimator.png)

<span data-ttu-id="8279f-203">L'algoritmo di training della raccomandazione che si userà per il training del modello è un esempio di `Estimator`.</span><span class="sxs-lookup"><span data-stu-id="8279f-203">The recommendation training algorithm you will use for training your model is an example of an `Estimator`.</span></span>

<span data-ttu-id="8279f-204">Creare un `Estimator` seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="8279f-204">Build an `Estimator` with the following steps:</span></span>

<span data-ttu-id="8279f-205">Creare il metodo `BuildAndTrainModel()` subito dopo il metodo `LoadData()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8279f-205">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> <span data-ttu-id="8279f-206">Questo metodo restituisce un errore finché non si aggiungerà un'istruzione return nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8279f-206">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="8279f-207">Definire le trasformazioni dei dati aggiungendo il codice seguente a `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-207">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>
   
[!code-csharp[DataTransformations](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="8279f-208">Poiché `userId` e `movieId` rappresentano utenti e titoli di film, non valori reali, viene usato il metodo [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) per trasformare ogni `userId` e ogni `movieId` in una colonna chiave di tipo numerico `Feature` (un formato accettato dagli algoritmi di raccomandazione) e aggiungerle come nuove colonne del set di dati:</span><span class="sxs-lookup"><span data-stu-id="8279f-208">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="8279f-209">userId</span><span class="sxs-lookup"><span data-stu-id="8279f-209">userId</span></span> | <span data-ttu-id="8279f-210">movieId</span><span class="sxs-lookup"><span data-stu-id="8279f-210">movieId</span></span> | <span data-ttu-id="8279f-211">Label</span><span class="sxs-lookup"><span data-stu-id="8279f-211">Label</span></span> | <span data-ttu-id="8279f-212">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="8279f-212">userIdEncoded</span></span> | <span data-ttu-id="8279f-213">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="8279f-213">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="8279f-214">1</span><span class="sxs-lookup"><span data-stu-id="8279f-214">1</span></span> | <span data-ttu-id="8279f-215">1</span><span class="sxs-lookup"><span data-stu-id="8279f-215">1</span></span> | <span data-ttu-id="8279f-216">4</span><span class="sxs-lookup"><span data-stu-id="8279f-216">4</span></span> | <span data-ttu-id="8279f-217">userKey1</span><span class="sxs-lookup"><span data-stu-id="8279f-217">userKey1</span></span> | <span data-ttu-id="8279f-218">movieKey1</span><span class="sxs-lookup"><span data-stu-id="8279f-218">movieKey1</span></span> |
| <span data-ttu-id="8279f-219">1</span><span class="sxs-lookup"><span data-stu-id="8279f-219">1</span></span> | <span data-ttu-id="8279f-220">3</span><span class="sxs-lookup"><span data-stu-id="8279f-220">3</span></span> | <span data-ttu-id="8279f-221">4</span><span class="sxs-lookup"><span data-stu-id="8279f-221">4</span></span> | <span data-ttu-id="8279f-222">userKey1</span><span class="sxs-lookup"><span data-stu-id="8279f-222">userKey1</span></span> | <span data-ttu-id="8279f-223">movieKey2</span><span class="sxs-lookup"><span data-stu-id="8279f-223">movieKey2</span></span> |
| <span data-ttu-id="8279f-224">1</span><span class="sxs-lookup"><span data-stu-id="8279f-224">1</span></span> | <span data-ttu-id="8279f-225">6</span><span class="sxs-lookup"><span data-stu-id="8279f-225">6</span></span> | <span data-ttu-id="8279f-226">4</span><span class="sxs-lookup"><span data-stu-id="8279f-226">4</span></span> | <span data-ttu-id="8279f-227">userKey1</span><span class="sxs-lookup"><span data-stu-id="8279f-227">userKey1</span></span> | <span data-ttu-id="8279f-228">movieKey3</span><span class="sxs-lookup"><span data-stu-id="8279f-228">movieKey3</span></span> |

<span data-ttu-id="8279f-229">Scegliere l'algoritmo di Machine Learning e aggiungerlo alle definizioni di trasformazione dei dati aggiungendo il codice seguente come riga successiva in `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-229">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="8279f-230">[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) è l'algoritmo di training della raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="8279f-230">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="8279f-231">La [fattorizzazione di matrice](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) è un approccio comune alla raccomandazione quando si hanno a disposizione dati su come gli utenti hanno valutato i prodotti in passato, come nel caso dei set di dati usati in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="8279f-231">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="8279f-232">Per le situazioni in cui sono disponibili dati diversi, esistono altri algoritmi di raccomandazione. Per altre informazioni, vedere la sezione [Altri algoritmi di raccomandazione](#other-recommendation-algorithms) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8279f-232">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span> 

<span data-ttu-id="8279f-233">In questo caso, l'algoritmo `Matrix Factorization` usa un metodo denominato "filtraggio collaborativo" il quale presuppone che se l'utente 1 ha la stessa opinione dell'utente 2 relativamente a un determinato problema, è probabile che l'utente 1 sia d'accordo con l'utente 2 riguardo a un altro problema.</span><span class="sxs-lookup"><span data-stu-id="8279f-233">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="8279f-234">Se ad esempio l'utente 1 e l'utente 2 valutano i film in modo simile, è probabile che all'utente 2 piaccia un film che l'utente 1 ha visto e a cui ha assegnato una valutazione elevata:</span><span class="sxs-lookup"><span data-stu-id="8279f-234">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="8279f-235">Utente 1</span><span class="sxs-lookup"><span data-stu-id="8279f-235">User 1</span></span> | <span data-ttu-id="8279f-236">Ha visto e apprezzato il film</span><span class="sxs-lookup"><span data-stu-id="8279f-236">Watched and liked movie</span></span> | <span data-ttu-id="8279f-237">Ha visto e apprezzato il film</span><span class="sxs-lookup"><span data-stu-id="8279f-237">Watched and liked movie</span></span> | <span data-ttu-id="8279f-238">Ha visto e apprezzato il film</span><span class="sxs-lookup"><span data-stu-id="8279f-238">Watched and liked movie</span></span> |
| <span data-ttu-id="8279f-239">Utente 2</span><span class="sxs-lookup"><span data-stu-id="8279f-239">User 2</span></span> | <span data-ttu-id="8279f-240">Ha visto e apprezzato il film</span><span class="sxs-lookup"><span data-stu-id="8279f-240">Watched and liked movie</span></span> | <span data-ttu-id="8279f-241">Ha visto e apprezzato il film</span><span class="sxs-lookup"><span data-stu-id="8279f-241">Watched and liked movie</span></span> | <span data-ttu-id="8279f-242">Non l'ha visto - RACCOMANDARE il film</span><span class="sxs-lookup"><span data-stu-id="8279f-242">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="8279f-243">Il trainer `Matrix Factorization` include diverse [opzioni](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options). Per altre informazioni, vedere la sezione [Iperparametri dell'algoritmo](#algorithm-hyperparameters) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8279f-243">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="8279f-244">Eseguire il fit del modello ai dati `Train` e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-244">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="8279f-245">Il metodo [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) esegue il training del modello con il set di dati di training specificato.</span><span class="sxs-lookup"><span data-stu-id="8279f-245">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="8279f-246">Tecnicamente il metodo esegue le definizioni `Estimator` trasformando i dati e applicando il training, quindi restituisce il modello sottoposto a training, ovvero un `Transformer`.</span><span class="sxs-lookup"><span data-stu-id="8279f-246">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="8279f-247">Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `BuildAndTrainModel()` e restituire il modello sottoposto a training:</span><span class="sxs-lookup"><span data-stu-id="8279f-247">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="8279f-248">Valutare il modello</span><span class="sxs-lookup"><span data-stu-id="8279f-248">Evaluate your model</span></span>

<span data-ttu-id="8279f-249">Dopo aver eseguito il training del modello, usare i dati di test per valutare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-249">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span> 

<span data-ttu-id="8279f-250">Creare il metodo `EvaluateModel()` subito dopo il metodo `BuildAndTrainModel()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8279f-250">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

<span data-ttu-id="8279f-251">Trasformare i dati `Test` aggiungendo il codice seguente a `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-251">Transform the `Test` data by adding the following code to `EvaluateModel()`:</span></span>
[!code-csharp[Transform](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]

<span data-ttu-id="8279f-252">Il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) effettua previsioni per più righe di input specificate di un set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="8279f-252">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="8279f-253">Valutare il modello aggiungendo il codice seguente come riga successiva nel metodo `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-253">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="8279f-254">Dopo aver impostato la previsione, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) valuta il modello confrontando i valori stimati con gli oggetti `Labels` effettivi presenti nel set di dati di test e restituisce le metriche relative alle prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-254">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="8279f-255">Stampare le metriche di valutazione nella console aggiungendo il codice seguente come riga successiva nel metodo `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-255">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="8279f-256">Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-256">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="8279f-257">A questo punto, l'output dovrebbe avere un aspetto simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="8279f-257">The output so far should look similar to the following text:</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

<span data-ttu-id="8279f-258">Questo output presenta 20 iterazioni.</span><span class="sxs-lookup"><span data-stu-id="8279f-258">In this output, there are 20 iterations.</span></span> <span data-ttu-id="8279f-259">In ogni iterazione la misura di errore diminuisce ed è sempre più prossima allo 0.</span><span class="sxs-lookup"><span data-stu-id="8279f-259">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="8279f-260">La metrica `root of mean squared error` (RMS o RMSE) viene usata per misurare le differenze tra i valori stimati da un modello e quelli osservati in set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="8279f-260">The `root of mean squared error` (RMS or RMSE) is used to measure the differences between the model predicted values and the test dataset observed values.</span></span> <span data-ttu-id="8279f-261">Tecnicamente è la radice quadrata della media dei quadrati degli errori.</span><span class="sxs-lookup"><span data-stu-id="8279f-261">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="8279f-262">Più basso è il valore, migliore è il modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-262">The lower it is, the better the model is.</span></span>

`R Squared` <span data-ttu-id="8279f-263">indica il livello di adattamento dei dati a un modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-263">indicates how well data fits a model.</span></span> <span data-ttu-id="8279f-264">È compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="8279f-264">Ranges from 0 to 1.</span></span> <span data-ttu-id="8279f-265">Un valore pari a 0 indica che i dati sono casuali o non possono essere adattati al modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-265">A value of 0 means that the data is random or otherwise can't be fit to the model.</span></span> <span data-ttu-id="8279f-266">Un valore pari a 1 indica che il modello corrisponde esattamente ai dati.</span><span class="sxs-lookup"><span data-stu-id="8279f-266">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="8279f-267">Il punteggio `R Squared` deve essere il più vicino possibile a 1.</span><span class="sxs-lookup"><span data-stu-id="8279f-267">You want your `R Squared` score to be as close to 1 as possible.</span></span>

<span data-ttu-id="8279f-268">La creazione di modelli efficaci è un processo iterativo.</span><span class="sxs-lookup"><span data-stu-id="8279f-268">Building successful models is an iterative process.</span></span> <span data-ttu-id="8279f-269">Questo modello ha inizialmente una qualità inferiore, perché l'esercitazione usa set di dati di dimensioni contenute per consentire il training rapido del modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-269">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="8279f-270">Se non si è soddisfatti della qualità del modello, è possibile provare a migliorarla fornendo set di dati di training più grandi o scegliendo algoritmi di training diversi con iperparametri diversi per ogni algoritmo.</span><span class="sxs-lookup"><span data-stu-id="8279f-270">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span> <span data-ttu-id="8279f-271">Per altre informazioni, vedere la sezione [Migliorare il modello](#improve-your-model) più avanti.</span><span class="sxs-lookup"><span data-stu-id="8279f-271">For more information, check out the [Improve your model](#improve-your-model) section below.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="8279f-272">Usare il modello</span><span class="sxs-lookup"><span data-stu-id="8279f-272">Use your model</span></span>

<span data-ttu-id="8279f-273">Ora è possibile usare il modello sottoposto a training per effettuare previsioni sui nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="8279f-273">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="8279f-274">Creare il metodo `UseModelForSinglePrediction()` subito dopo il metodo `EvaluateModel()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8279f-274">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>
```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="8279f-275">Usare `PredictionEngine` per prevedere la valutazione aggiungendo il codice seguente a `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-275">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="8279f-276">La [classe PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di servizio che consente di passare una singola istanza di dati e di effettuare quindi una previsione su questa singola istanza di dati.</span><span class="sxs-lookup"><span data-stu-id="8279f-276">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass a single instance of data and then perform a prediction on this single instance of data.</span></span>

<span data-ttu-id="8279f-277">Creare un'istanza di `MovieRating` denominata `testInput` e passarla al motore di previsione aggiungendo il codice seguente come righe successive nel metodo `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-277">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="8279f-278">La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) effettua una previsione su una singola colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="8279f-278">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="8279f-279">È quindi possibile usare `Score`, o la valutazione prevista, per determinare se si vuole raccomandare il film con movieId 10 all'utente 6.</span><span class="sxs-lookup"><span data-stu-id="8279f-279">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="8279f-280">Tanto più elevato è il valore di `Score`, quanto più elevata sarà la probabilità che a un utente piaccia un determinato film.</span><span class="sxs-lookup"><span data-stu-id="8279f-280">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="8279f-281">In questo caso, si raccomanderanno film con una valutazione prevista di > 3.5.</span><span class="sxs-lookup"><span data-stu-id="8279f-281">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="8279f-282">Per stampare i risultati, aggiungere il codice seguente come righe successive nel metodo `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-282">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="8279f-283">Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-283">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="8279f-284">L'output di questo metodo dovrebbe avere un aspetto simile al testo seguente:</span><span class="sxs-lookup"><span data-stu-id="8279f-284">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="8279f-285">Salvare il modello</span><span class="sxs-lookup"><span data-stu-id="8279f-285">Save your model</span></span>

<span data-ttu-id="8279f-286">Per usare il modello per effettuare previsioni nelle applicazioni per l'utente finale, è prima necessario salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="8279f-286">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="8279f-287">Creare il metodo `SaveModel()` subito dopo il metodo `UseModelForSinglePrediction()`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8279f-287">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>

```csharp
public static void SaveModel(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="8279f-288">Salvare il modello sottoposto a training aggiungendo il codice seguente nel metodo `SaveModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-288">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="8279f-289">Questo metodo salva il modello sottoposto a training in un file con estensione zip (nella cartella "Data") che potrà essere successivamente usato in altre applicazioni .NET per effettuare previsioni.</span><span class="sxs-lookup"><span data-stu-id="8279f-289">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="8279f-290">Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `SaveModel()`:</span><span class="sxs-lookup"><span data-stu-id="8279f-290">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="8279f-291">Usare il modello salvato</span><span class="sxs-lookup"><span data-stu-id="8279f-291">Use your saved model</span></span>

<span data-ttu-id="8279f-292">Dopo che il modello sottoposto a training è stato salvato, sarà possibile usarlo in diversi ambienti (vedere la ["Guida pratica"](../how-to-guides/consuming-model-ml-net.md) per informazioni su come rendere operativo un modello di Machine Learning sottoposto a training nelle app).</span><span class="sxs-lookup"><span data-stu-id="8279f-292">Once you have saved your trained model, you can consume the model in different environments (see the ["How-to guide"](../how-to-guides/consuming-model-ml-net.md) to learn how to operationalize a trained machine learning model in apps).</span></span>

## <a name="results"></a><span data-ttu-id="8279f-293">Risultati</span><span class="sxs-lookup"><span data-stu-id="8279f-293">Results</span></span>

<span data-ttu-id="8279f-294">Dopo aver completato la procedura descritta sopra, eseguire l'app console (CTRL + F5).</span><span class="sxs-lookup"><span data-stu-id="8279f-294">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="8279f-295">I risultati della previsione singola indicata in precedenza dovrebbero essere simili a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8279f-295">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="8279f-296">È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8279f-296">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

<span data-ttu-id="8279f-297">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8279f-297">Congratulations!</span></span> <span data-ttu-id="8279f-298">È stato creato un modello di Machine Learning per raccomandare film.</span><span class="sxs-lookup"><span data-stu-id="8279f-298">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="8279f-299">È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="8279f-299">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="8279f-300">Migliorare il modello</span><span class="sxs-lookup"><span data-stu-id="8279f-300">Improve your model</span></span>

<span data-ttu-id="8279f-301">È possibile migliorare le prestazioni del modello in diversi modi per ottenere previsioni più accurate.</span><span class="sxs-lookup"><span data-stu-id="8279f-301">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="8279f-302">Dati</span><span class="sxs-lookup"><span data-stu-id="8279f-302">Data</span></span>

<span data-ttu-id="8279f-303">L'aggiunta di altri dati di training con sufficienti esempi per ogni utente e ID film contribuisce a migliorare la qualità del modello di raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="8279f-303">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="8279f-304">La [convalida incrociata](../how-to-guides/train-cross-validation-ml-net.md) è una tecnica per la valutazione dei modelli che divide in modo casuale i dati in subset, anziché estrarre i dati di test dal set di dati come in questa esercitazione, e acquisisce alcuni gruppi come dati di training e altri come dati di test.</span><span class="sxs-lookup"><span data-stu-id="8279f-304">[Cross validation](../how-to-guides/train-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="8279f-305">In termini di qualità del modello, questo metodo offre prestazioni migliori rispetto alla divisione train-test.</span><span class="sxs-lookup"><span data-stu-id="8279f-305">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="8279f-306">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="8279f-306">Features</span></span>

<span data-ttu-id="8279f-307">In questa esercitazione vengono usate solo le tre `Features` (`user id`, `movie id` e `rating`) offerte dal set di dati.</span><span class="sxs-lookup"><span data-stu-id="8279f-307">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span> 

<span data-ttu-id="8279f-308">È un buon inizio, ma nella realtà è utile aggiungere altri attributi o `Features`, ad esempio età, sesso, posizione geografica e così via, se sono inclusi nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="8279f-308">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="8279f-309">L'aggiunta di `Features` più rilevanti può contribuire a migliorare le prestazioni del modello di raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="8279f-309">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span> 

<span data-ttu-id="8279f-310">Se non si è sicuri di quali `Features` potrebbero essere più rilevanti per la propria attività di Machine Learning, è anche possibile usare gli strumenti Feature Contribution Calculation (FCC) e [Permutation Feature Importance](../how-to-guides/determine-global-feature-importance-in-model.md) offerti da ML.NET per individuare le `Features` più influenti.</span><span class="sxs-lookup"><span data-stu-id="8279f-310">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="8279f-311">Iperparametri dell'algoritmo</span><span class="sxs-lookup"><span data-stu-id="8279f-311">Algorithm hyperparameters</span></span>

<span data-ttu-id="8279f-312">Anche se gli algoritmi di training predefiniti di ML.NET sono di ottima qualità, è possibile ottimizzare ulteriormente le prestazioni modificando gli [iperparametri](../resources/glossary.md#hyperparameter) dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="8279f-312">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="8279f-313">Per `Matrix Factorization`, è possibile sperimentare con iperparametri quali [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) e [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) per vedere se vengono restituiti risultati migliori.</span><span class="sxs-lookup"><span data-stu-id="8279f-313">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="8279f-314">Ad esempio, in questa esercitazione le opzioni di algoritmo sono:</span><span class="sxs-lookup"><span data-stu-id="8279f-314">For instance, in this tutorial the algorithm options are:</span></span>

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded", 
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="8279f-315">Altri algoritmi per la raccomandazione</span><span class="sxs-lookup"><span data-stu-id="8279f-315">Other Recommendation Algorithms</span></span>

<span data-ttu-id="8279f-316">L'algoritmo di fattorizzazione di matrice con filtraggio collaborativo è solo uno degli approcci per l'esecuzione di raccomandazioni di film.</span><span class="sxs-lookup"><span data-stu-id="8279f-316">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="8279f-317">In molti casi, è possibile che i dati delle valutazioni non siano disponibili e che sia disponibile solo la cronologia del film relativa all'utente.</span><span class="sxs-lookup"><span data-stu-id="8279f-317">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="8279f-318">In altri casi, si potrebbe avere di più dei soli dati di valutazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8279f-318">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="8279f-319">Algoritmo</span><span class="sxs-lookup"><span data-stu-id="8279f-319">Algorithm</span></span>       | <span data-ttu-id="8279f-320">Scenario</span><span class="sxs-lookup"><span data-stu-id="8279f-320">Scenario</span></span>           | <span data-ttu-id="8279f-321">Esempio</span><span class="sxs-lookup"><span data-stu-id="8279f-321">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="8279f-322">One Class Matrix Factorization</span><span class="sxs-lookup"><span data-stu-id="8279f-322">One Class Matrix Factorization</span></span> | <span data-ttu-id="8279f-323">Usare questo algoritmo quando sono disponibili solo userId e movieId.</span><span class="sxs-lookup"><span data-stu-id="8279f-323">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="8279f-324">Questo stile di raccomandazione si basa sullo scenario di acquisto congiunto o di prodotti acquistati di frequente insieme e consiglierà quindi al cliente un set di prodotti in base alla propria cronologia di acquisto.</span><span class="sxs-lookup"><span data-stu-id="8279f-324">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="8279f-325">>Provare</span><span class="sxs-lookup"><span data-stu-id="8279f-325">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="8279f-326">Field Aware Factorization Machines</span><span class="sxs-lookup"><span data-stu-id="8279f-326">Field Aware Factorization Machines</span></span> | <span data-ttu-id="8279f-327">Usare questo algoritmo per creare raccomandazioni quando sono disponibili altre caratteristiche oltre a userId, productId e rating, ad esempio la descrizione del prodotto o il prezzo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="8279f-327">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="8279f-328">Questo metodo usa anche un approccio di filtraggio collaborativo.</span><span class="sxs-lookup"><span data-stu-id="8279f-328">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="8279f-329">>Provare</span><span class="sxs-lookup"><span data-stu-id="8279f-329">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="8279f-330">Scenario con nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="8279f-330">New user scenario</span></span>

<span data-ttu-id="8279f-331">Un problema comune nel filtraggio collaborativo è quello relativo ai nuovi utenti per i quali non sono disponibili dati precedenti da cui trarre inferenze.</span><span class="sxs-lookup"><span data-stu-id="8279f-331">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="8279f-332">Questo problema viene spesso risolto chiedendo ai nuovi utenti di creare un profilo e, ad esempio, valutare i film che hanno visto in passato.</span><span class="sxs-lookup"><span data-stu-id="8279f-332">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="8279f-333">Anche se questo metodo introduce un compito in più per l'utente, esso consente di ottenere alcuni dati di partenza per i nuovi utenti senza una cronologia di valutazioni.</span><span class="sxs-lookup"><span data-stu-id="8279f-333">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="8279f-334">Risorse</span><span class="sxs-lookup"><span data-stu-id="8279f-334">Resources</span></span>

<span data-ttu-id="8279f-335">I dati usati in questa esercitazione sono derivati dal [set di dati MovieLens](http://files.grouplens.org/datasets/movielens/).</span><span class="sxs-lookup"><span data-stu-id="8279f-335">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8279f-336">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8279f-336">Next steps</span></span>

<span data-ttu-id="8279f-337">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="8279f-337">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="8279f-338">Selezionare un algoritmo di Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8279f-338">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="8279f-339">Preparare e caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8279f-339">Prepare and load your data</span></span>
> * <span data-ttu-id="8279f-340">Creare un modello ed eseguirne il training</span><span class="sxs-lookup"><span data-stu-id="8279f-340">Build and train a model</span></span>
> * <span data-ttu-id="8279f-341">Valutare un modello</span><span class="sxs-lookup"><span data-stu-id="8279f-341">Evaluate a model</span></span>
> * <span data-ttu-id="8279f-342">Distribuire e usare un modello</span><span class="sxs-lookup"><span data-stu-id="8279f-342">Deploy and consume a model</span></span>

<span data-ttu-id="8279f-343">Passare all'esercitazione successiva per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="8279f-343">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="8279f-344">Analisi del sentiment</span><span class="sxs-lookup"><span data-stu-id="8279f-344">Sentiment Analysis</span></span>](sentiment-analysis.md)
