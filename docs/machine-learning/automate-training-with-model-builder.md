---
title: Che cos'è il generatore di modelli e come funziona?
description: Come usare il generatore di modelli di ML.NET per eseguire automaticamente il training di un modello di Machine Learning
ms.date: 03/25/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 9cf66455109908ebd9fc10e62cf4f067609b57d9
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344777"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="75be2-103">Che cos'è il generatore di modelli e come funziona?</span><span class="sxs-lookup"><span data-stu-id="75be2-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="75be2-104">Il generatore di modelli di ML.NET è un'estensione grafica intuitiva di Visual Studio che consente di compilare, eseguire il training e distribuire modelli di Machine Learning personalizzati.</span><span class="sxs-lookup"><span data-stu-id="75be2-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="75be2-105">Il generatore di modelli usa il Machine Learning automatico (AutoML) per esplorare diversi algoritmi di Machine Learning e impostazioni per individuare quelli più adatti allo scenario.</span><span class="sxs-lookup"><span data-stu-id="75be2-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="75be2-106">Non è necessario avere competenze di Machine Learning per usare il generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="75be2-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="75be2-107">Servono solo alcuni dati e un problema da risolvere.</span><span class="sxs-lookup"><span data-stu-id="75be2-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="75be2-108">Il generatore di modelli genera il codice per aggiungere il modello all'applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="75be2-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Animazione dell'interfaccia utente dell'estensione del generatore di modelli di Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="75be2-110">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="75be2-110">Model Builder is currently in Preview.</span></span>

## <a name="scenario"></a><span data-ttu-id="75be2-111">Scenario</span><span class="sxs-lookup"><span data-stu-id="75be2-111">Scenario</span></span>

<span data-ttu-id="75be2-112">È possibile trasferire molti scenari diversi nel generatore di modelli per generare un modello di Machine Learning per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75be2-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="75be2-113">Uno scenario è una descrizione del tipo di previsione che si vuole eseguire usando i dati.</span><span class="sxs-lookup"><span data-stu-id="75be2-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="75be2-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="75be2-114">For example:</span></span>

- <span data-ttu-id="75be2-115">prevedere il volume di vendita futuro dei prodotti in base ai dati storici di vendita</span><span class="sxs-lookup"><span data-stu-id="75be2-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="75be2-116">classificare le valutazioni come positive o negative in base alle recensioni dei clienti</span><span class="sxs-lookup"><span data-stu-id="75be2-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="75be2-117">rilevare se una transazione bancaria è fraudolenta</span><span class="sxs-lookup"><span data-stu-id="75be2-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="75be2-118">indirizzare i problemi dei feedback dei clienti al team corretto nell'azienda</span><span class="sxs-lookup"><span data-stu-id="75be2-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="75be2-119">Quale scenario di Machine Learning è adatto alle mie esigenze?</span><span class="sxs-lookup"><span data-stu-id="75be2-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="75be2-120">In Model Builder, è necessario selezionare uno scenario.</span><span class="sxs-lookup"><span data-stu-id="75be2-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="75be2-121">Il tipo di scenario dipende dal tipo di stima che si sta tentando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="75be2-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="text-classification"></a><span data-ttu-id="75be2-122">Classificazione del testo</span><span class="sxs-lookup"><span data-stu-id="75be2-122">Text classification</span></span>

<span data-ttu-id="75be2-123">La classificazione viene utilizzata per classificare i dati in categorie.</span><span class="sxs-lookup"><span data-stu-id="75be2-123">Classification is used to categorize data into categories.</span></span>

![Diagramma che mostra esempi di classificazione binaria, tra cui il rilevamento delle frodi, la mitigazione dei rischi e lo screening delle applicazioni](media/binary-classification-examples.png)

![Esempi di classificazione multiclasse, tra cui la classificazione di documenti e prodotti, il routing dei ticket di supporto e l'assegnazione di priorità ai problemi dei clienti](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a><span data-ttu-id="75be2-126">Stima del valore</span><span class="sxs-lookup"><span data-stu-id="75be2-126">Value prediction</span></span>

<span data-ttu-id="75be2-127">La regressione viene usata per prevedere i numeri.</span><span class="sxs-lookup"><span data-stu-id="75be2-127">Regression is used to predict numbers.</span></span>

![Diagramma che mostra esempi di regressione, ad esempio stime del prezzo, previsioni di vendita e manutenzione predittiva](media/regression-examples.png)

#### <a name="image-classification"></a><span data-ttu-id="75be2-129">Classificazione di immagini</span><span class="sxs-lookup"><span data-stu-id="75be2-129">Image classification</span></span>

<span data-ttu-id="75be2-130">La classificazione delle immagini può essere utilizzata per identificare immagini di diverse categorie.</span><span class="sxs-lookup"><span data-stu-id="75be2-130">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="75be2-131">Ad esempio, diversi tipi di terreno o animali o difetti di produzione.</span><span class="sxs-lookup"><span data-stu-id="75be2-131">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="75be2-132">È possibile utilizzare lo scenario di classificazione delle immagini se si dispone di un set di immagini e si desidera classificare le immagini in categorie diverse.</span><span class="sxs-lookup"><span data-stu-id="75be2-132">You can use the image classification scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="recommendation"></a><span data-ttu-id="75be2-133">Recommendation</span><span class="sxs-lookup"><span data-stu-id="75be2-133">Recommendation</span></span>

<span data-ttu-id="75be2-134">Lo scenario di raccomandazione prevede un elenco di elementi suggeriti per un determinato utente, in base a quanto simili i loro like e antipatie sono ad altri utenti'.</span><span class="sxs-lookup"><span data-stu-id="75be2-134">The recommendation scenario predicts a list of suggested items for a particular user, based on how similar their likes and dislikes are to other users'.</span></span>

<span data-ttu-id="75be2-135">È possibile utilizzare lo scenario di raccomandazione quando si dispone di un insieme di utenti e di un insieme di "prodotti", ad esempio articoli da acquistare, film, libri o programmi TV, insieme a un insieme di "valutazioni" di tali prodotti da parte di un insieme di utenti.</span><span class="sxs-lookup"><span data-stu-id="75be2-135">You can use the recommendation scenario when you have a set of users and a set of "products", such as items to purchase, movies, books, or TV shows, along with a set of users' "ratings" of those products.</span></span>

## <a name="environment"></a><span data-ttu-id="75be2-136">Environment</span><span class="sxs-lookup"><span data-stu-id="75be2-136">Environment</span></span>

<span data-ttu-id="75be2-137">È possibile eseguire il training del modello di apprendimento automatico in un modo in locale nel computer o nel cloud in Azure.You can train your machine learning model locally on your machine or in the cloud on Azure.</span><span class="sxs-lookup"><span data-stu-id="75be2-137">You can train your machine learning model locally on your machine or in the cloud on Azure.</span></span>

<span data-ttu-id="75be2-138">Quando si esegue il training in locale, si lavora entro i vincoli delle risorse del computer (CPU, memoria e disco).</span><span class="sxs-lookup"><span data-stu-id="75be2-138">When you train locally, you work within the constraints of your computer resources (CPU, memory, and disk).</span></span> <span data-ttu-id="75be2-139">Quando si esegue il training nel cloud, è possibile aumentare le risorse per soddisfare le esigenze dello scenario, in particolare per set di dati di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="75be2-139">When you train in the cloud, you can scale up your resources to meet the demands of your scenario, especially for large datasets.</span></span>

<span data-ttu-id="75be2-140">La formazione locale è supportata per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="75be2-140">Local training is supported for all scenarios.</span></span>

<span data-ttu-id="75be2-141">Il training di Azure è supportato per la classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="75be2-141">Azure training is supported for Image Classification.</span></span>

## <a name="data"></a><span data-ttu-id="75be2-142">Dati</span><span class="sxs-lookup"><span data-stu-id="75be2-142">Data</span></span>

<span data-ttu-id="75be2-143">Dopo aver scelto lo scenario, Model Builder richiede di fornire un set di dati.</span><span class="sxs-lookup"><span data-stu-id="75be2-143">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="75be2-144">I dati vengono usati per il training, la valutazione e la scelta del modello più adatto per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="75be2-144">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Diagramma che illustra i passaggi del generatore di modelli](media/model-builder-steps.png)

<span data-ttu-id="75be2-146">Model Builder supporta set di dati in formato .tsv, .csv, .txt, così come il formato di database SQL.</span><span class="sxs-lookup"><span data-stu-id="75be2-146">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="75be2-147">Se si dispone di un file con `,`estensione `;` `/t` txt, le colonne devono essere separate da o e il file deve avere una riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="75be2-147">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="75be2-148">Se il set di dati è costituito `.jpg` `.png`da immagini, i tipi di file supportati sono e .</span><span class="sxs-lookup"><span data-stu-id="75be2-148">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="75be2-149">Per ulteriori informazioni, consultate Caricare dati di [training in Model Builder.](how-to-guides/load-data-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="75be2-149">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="75be2-150">Scegliere l'output da prevedere (etichetta)</span><span class="sxs-lookup"><span data-stu-id="75be2-150">Choose the output to predict (label)</span></span>

<span data-ttu-id="75be2-151">Un set di dati è una tabella di righe di esempi di training e di colonne di attributi.</span><span class="sxs-lookup"><span data-stu-id="75be2-151">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="75be2-152">Ogni riga include:</span><span class="sxs-lookup"><span data-stu-id="75be2-152">Each row has:</span></span>

- <span data-ttu-id="75be2-153">un'**etichetta** (l'attributo da prevedere)</span><span class="sxs-lookup"><span data-stu-id="75be2-153">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="75be2-154">le **caratteristiche** (gli attributi usati come input per la previsione dell'etichetta).</span><span class="sxs-lookup"><span data-stu-id="75be2-154">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="75be2-155">Per lo scenario di stima del prezzo della casa, è possibile usare le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="75be2-155">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="75be2-156">i metri quadrati della casa</span><span class="sxs-lookup"><span data-stu-id="75be2-156">the square footage of the house</span></span>
- <span data-ttu-id="75be2-157">il numero di camere da letto e bagni</span><span class="sxs-lookup"><span data-stu-id="75be2-157">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="75be2-158">il codice postale</span><span class="sxs-lookup"><span data-stu-id="75be2-158">the zip code</span></span>

<span data-ttu-id="75be2-159">L'etichetta è il prezzo storico della casa per la riga dei valori dei metri quadrati, delle camere da letto e dei bagni e il codice postale.</span><span class="sxs-lookup"><span data-stu-id="75be2-159">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Tabella che mostra le righe e le colonne di dati sui prezzi delle case con le caratteristiche delle dimensioni dei locali, del codice postale e dell'etichetta del prezzo](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="75be2-161">Set di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="75be2-161">Example datasets</span></span>

<span data-ttu-id="75be2-162">Se non sono ancora disponibili dati, provare uno dei set di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="75be2-162">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="75be2-163">Scenario</span><span class="sxs-lookup"><span data-stu-id="75be2-163">Scenario</span></span>|<span data-ttu-id="75be2-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="75be2-164">Example</span></span>|<span data-ttu-id="75be2-165">Dati</span><span class="sxs-lookup"><span data-stu-id="75be2-165">Data</span></span>|<span data-ttu-id="75be2-166">Etichetta</span><span class="sxs-lookup"><span data-stu-id="75be2-166">Label</span></span>|<span data-ttu-id="75be2-167">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="75be2-167">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="75be2-168">Classificazione</span><span class="sxs-lookup"><span data-stu-id="75be2-168">Classification</span></span>|<span data-ttu-id="75be2-169">Prevedere le anomalie di vendita</span><span class="sxs-lookup"><span data-stu-id="75be2-169">Predict sales anomalies</span></span>|[<span data-ttu-id="75be2-170">dati di vendita dei prodotti</span><span class="sxs-lookup"><span data-stu-id="75be2-170">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="75be2-171">Vendita dei prodotti</span><span class="sxs-lookup"><span data-stu-id="75be2-171">Product Sales</span></span>|<span data-ttu-id="75be2-172">Month</span><span class="sxs-lookup"><span data-stu-id="75be2-172">Month</span></span>|
||<span data-ttu-id="75be2-173">Prevedere il sentiment dei commenti del sito Web</span><span class="sxs-lookup"><span data-stu-id="75be2-173">Predict sentiment of website comments</span></span>|[<span data-ttu-id="75be2-174">dati dei commenti del sito Web</span><span class="sxs-lookup"><span data-stu-id="75be2-174">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="75be2-175">Etichetta (0 con sentiment negativo, 1 con sentiment positivo)</span><span class="sxs-lookup"><span data-stu-id="75be2-175">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="75be2-176">Commento, anno</span><span class="sxs-lookup"><span data-stu-id="75be2-176">Comment, Year</span></span>|
||<span data-ttu-id="75be2-177">Prevedere transazioni fraudolente con carta di credito</span><span class="sxs-lookup"><span data-stu-id="75be2-177">Predict fraudulent credit card transactions</span></span>|[<span data-ttu-id="75be2-178">dati della carta di credito</span><span class="sxs-lookup"><span data-stu-id="75be2-178">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="75be2-179">Classe (1 quando fraudolento, 0 in caso contrario)</span><span class="sxs-lookup"><span data-stu-id="75be2-179">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="75be2-180">Quantità, V1-V28 (caratteristiche anonime)</span><span class="sxs-lookup"><span data-stu-id="75be2-180">Amount, V1-V28 (anonymized features)</span></span>|
||<span data-ttu-id="75be2-181">Prevedere il tipo di problema in un repository GitHubPredict the type of issue in a GitHub repository</span><span class="sxs-lookup"><span data-stu-id="75be2-181">Predict the type of issue in a GitHub repository</span></span>|[<span data-ttu-id="75be2-182">dati del problema di GitHub</span><span class="sxs-lookup"><span data-stu-id="75be2-182">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="75be2-183">Area</span><span class="sxs-lookup"><span data-stu-id="75be2-183">Area</span></span>|<span data-ttu-id="75be2-184">Titolo, descrizione</span><span class="sxs-lookup"><span data-stu-id="75be2-184">Title, Description</span></span>|
|<span data-ttu-id="75be2-185">Stima del valore</span><span class="sxs-lookup"><span data-stu-id="75be2-185">Value prediction</span></span>|<span data-ttu-id="75be2-186">Prevedere il prezzo tariffario del taxi</span><span class="sxs-lookup"><span data-stu-id="75be2-186">Predict taxi fare price</span></span>|[<span data-ttu-id="75be2-187">dati delle tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="75be2-187">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="75be2-188">Tariffe</span><span class="sxs-lookup"><span data-stu-id="75be2-188">Fare</span></span>|<span data-ttu-id="75be2-189">Tempo della corsa, distanza</span><span class="sxs-lookup"><span data-stu-id="75be2-189">Trip time, distance</span></span>|
|<span data-ttu-id="75be2-190">Classificazione di immagini</span><span class="sxs-lookup"><span data-stu-id="75be2-190">Image classification</span></span>|<span data-ttu-id="75be2-191">Prevedere la categoria di un problema</span><span class="sxs-lookup"><span data-stu-id="75be2-191">Predict the category of an issue</span></span>|[<span data-ttu-id="75be2-192">immagini floreali</span><span class="sxs-lookup"><span data-stu-id="75be2-192">flower images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="75be2-193">Il tipo di fiore: margherita, tarassaco, rose, girasoli, tulipani</span><span class="sxs-lookup"><span data-stu-id="75be2-193">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="75be2-194">I dati dell'immagine stessa</span><span class="sxs-lookup"><span data-stu-id="75be2-194">The image data itself</span></span>|
|<span data-ttu-id="75be2-195">Recommendation</span><span class="sxs-lookup"><span data-stu-id="75be2-195">Recommendation</span></span>|<span data-ttu-id="75be2-196">Prevedi i film che piaceranno a qualcuno</span><span class="sxs-lookup"><span data-stu-id="75be2-196">Predict movies that someone will like</span></span>|[<span data-ttu-id="75be2-197">valutazioni dei film</span><span class="sxs-lookup"><span data-stu-id="75be2-197">movie ratings</span></span>](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|<span data-ttu-id="75be2-198">Utenti, Film</span><span class="sxs-lookup"><span data-stu-id="75be2-198">Users, Movies</span></span>|<span data-ttu-id="75be2-199">Classificazioni</span><span class="sxs-lookup"><span data-stu-id="75be2-199">Ratings</span></span>|

## <a name="train"></a><span data-ttu-id="75be2-200">Eseguire il training</span><span class="sxs-lookup"><span data-stu-id="75be2-200">Train</span></span>

<span data-ttu-id="75be2-201">Dopo aver selezionato lo scenario, i dati e l'etichetta, il generatore di modelli esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="75be2-201">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="75be2-202">Cos'è il training?</span><span class="sxs-lookup"><span data-stu-id="75be2-202">What is training?</span></span>

<span data-ttu-id="75be2-203">Il training è un processo automatico tramite il quale il generatore di modelli indica al modello come rispondere alle domande per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="75be2-203">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="75be2-204">Dopo aver eseguito il training, il modello può effettuare previsioni con dati di input completamente nuovi.</span><span class="sxs-lookup"><span data-stu-id="75be2-204">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="75be2-205">Ad esempio, se si sta eseguendo la stima dei prezzi e viene immessa sul mercato una nuova casa, è possibile prevederne il prezzo di vendita.</span><span class="sxs-lookup"><span data-stu-id="75be2-205">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="75be2-206">Poiché il generatore di modelli usa Il Machine Learning automatico (AutoML), non viene richiesto alcun input o ottimizzazione durante il training.</span><span class="sxs-lookup"><span data-stu-id="75be2-206">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="75be2-207">Per quanto tempo è consigliabile eseguire il training?</span><span class="sxs-lookup"><span data-stu-id="75be2-207">How long should I train for?</span></span>

<span data-ttu-id="75be2-208">Model Builder utilizza AutoML per esplorare più modelli per trovare il modello più performante.</span><span class="sxs-lookup"><span data-stu-id="75be2-208">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="75be2-209">Periodi di allenamento più lunghi consentono ad AutoML di esplorare più modelli con una gamma più ampia di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="75be2-209">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="75be2-210">La tabella seguente riepiloga il tempo medio impiegato per ottenere buone prestazioni per un gruppo di set di dati di esempio, in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="75be2-210">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="75be2-211">Dimensioni set di dati</span><span class="sxs-lookup"><span data-stu-id="75be2-211">Dataset size</span></span>|<span data-ttu-id="75be2-212">Tempo medio per allenarsi</span><span class="sxs-lookup"><span data-stu-id="75be2-212">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="75be2-213">0 - 10 MB</span><span class="sxs-lookup"><span data-stu-id="75be2-213">0 - 10 MB</span></span>|<span data-ttu-id="75be2-214">10 sec</span><span class="sxs-lookup"><span data-stu-id="75be2-214">10 sec</span></span>|
|<span data-ttu-id="75be2-215">Da 10 a 100 MB</span><span class="sxs-lookup"><span data-stu-id="75be2-215">10 - 100 MB</span></span>|<span data-ttu-id="75be2-216">10 min</span><span class="sxs-lookup"><span data-stu-id="75be2-216">10 min</span></span>|
|<span data-ttu-id="75be2-217">100 - 500 MB</span><span class="sxs-lookup"><span data-stu-id="75be2-217">100 - 500 MB</span></span>|<span data-ttu-id="75be2-218">30 min</span><span class="sxs-lookup"><span data-stu-id="75be2-218">30 min</span></span>|
|<span data-ttu-id="75be2-219">500 - 1 GB</span><span class="sxs-lookup"><span data-stu-id="75be2-219">500 - 1 GB</span></span>|<span data-ttu-id="75be2-220">60 min</span><span class="sxs-lookup"><span data-stu-id="75be2-220">60 min</span></span>|
|<span data-ttu-id="75be2-221">1 GB di lavoro</span><span class="sxs-lookup"><span data-stu-id="75be2-221">1 GB+</span></span>|<span data-ttu-id="75be2-222">Più di 3 ore</span><span class="sxs-lookup"><span data-stu-id="75be2-222">3+ hours</span></span>|

<span data-ttu-id="75be2-223">Questi numeri sono solo una guida.</span><span class="sxs-lookup"><span data-stu-id="75be2-223">These numbers are a guide only.</span></span> <span data-ttu-id="75be2-224">L'esatta durata della formazione dipende da:</span><span class="sxs-lookup"><span data-stu-id="75be2-224">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="75be2-225">il numero di feature (colonne) utilizzate come input per il modello</span><span class="sxs-lookup"><span data-stu-id="75be2-225">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="75be2-226">il tipo di colonne</span><span class="sxs-lookup"><span data-stu-id="75be2-226">the type of columns</span></span>
- <span data-ttu-id="75be2-227">l'attività ML</span><span class="sxs-lookup"><span data-stu-id="75be2-227">the ML task</span></span>
- <span data-ttu-id="75be2-228">le prestazioni della CPU, del disco e della memoria del computer utilizzato per il training</span><span class="sxs-lookup"><span data-stu-id="75be2-228">the CPU, disk, and memory performance of the machine used for training</span></span>

## <a name="evaluate"></a><span data-ttu-id="75be2-229">Valutazione</span><span class="sxs-lookup"><span data-stu-id="75be2-229">Evaluate</span></span>

<span data-ttu-id="75be2-230">La valutazione è il processo di misurazione della qualità del modello.</span><span class="sxs-lookup"><span data-stu-id="75be2-230">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="75be2-231">Model Builder usa il modello sottoposto a training per eseguire stime con nuovi dati di test e quindi misura l'efficacia delle stime.</span><span class="sxs-lookup"><span data-stu-id="75be2-231">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="75be2-232">Il generatore di modelli suddivide i dati di training in un set di training e un set di test.</span><span class="sxs-lookup"><span data-stu-id="75be2-232">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="75be2-233">I dati di training (80%) vengono usati per eseguire il training del modello, mentre i dati di test (20%) vengono usati per la valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="75be2-233">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="75be2-234">Come posso capire le prestazioni del mio modello?</span><span class="sxs-lookup"><span data-stu-id="75be2-234">How do I understand my model performance?</span></span>

<span data-ttu-id="75be2-235">Uno scenario esegue il mapping a un'attività di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="75be2-235">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="75be2-236">Ogni attività di ML dispone di un proprio set di metriche di valutazione.</span><span class="sxs-lookup"><span data-stu-id="75be2-236">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="value-prediction"></a><span data-ttu-id="75be2-237">Stima del valore</span><span class="sxs-lookup"><span data-stu-id="75be2-237">Value prediction</span></span>

<span data-ttu-id="75be2-238">La metrica predefinita per i problemi di stima del valore è RSquared, il valore degli intervalli RSquared compresi tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="75be2-238">The default metric for value prediction problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="75be2-239">1 è il miglior valore possibile o in altre parole più vicino è il valore di RSquared a 1 migliore sarà l'esecuzione del modello.</span><span class="sxs-lookup"><span data-stu-id="75be2-239">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="75be2-240">Altre metriche segnalate, ad esempio perdita assoluta, perdita quadrata e perdita RMS, sono metriche aggiuntive, che possono essere usate per comprendere le prestazioni del modello e confrontarlo con altri modelli di stima del valore.</span><span class="sxs-lookup"><span data-stu-id="75be2-240">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other value prediction models.</span></span>

#### <a name="classification-2-categories"></a><span data-ttu-id="75be2-241">Classificazione (2 categorie)</span><span class="sxs-lookup"><span data-stu-id="75be2-241">Classification (2 categories)</span></span>

<span data-ttu-id="75be2-242">La metrica predefinita per i problemi di classificazione è l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="75be2-242">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="75be2-243">Precisione definisce la proporzione di stime corrette che il modello sta facendo sul set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="75be2-243">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="75be2-244">Più vicino al 100% o 1,0 meglio è.</span><span class="sxs-lookup"><span data-stu-id="75be2-244">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="75be2-245">Altre metriche segnalate come AUC (Area sotto la curva), che misura il vero tasso positivo rispetto al tasso di falsi positivi dovrebbe essere maggiore di 0,50 per i modelli per essere accettabili.</span><span class="sxs-lookup"><span data-stu-id="75be2-245">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="75be2-246">Metriche aggiuntive come il punteggio F1 possono essere utilizzate per controllare il bilanciamento tra Precisione e Richiamo.</span><span class="sxs-lookup"><span data-stu-id="75be2-246">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="classification-3-categories"></a><span data-ttu-id="75be2-247">Classificazione (più di 3 categorie)</span><span class="sxs-lookup"><span data-stu-id="75be2-247">Classification (3+ categories)</span></span>

<span data-ttu-id="75be2-248">La metrica predefinita per la classificazione multiclasse è Precisione micro.</span><span class="sxs-lookup"><span data-stu-id="75be2-248">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="75be2-249">Più il Micro Accuracy è vicino al 100% o 1.0 meglio è.</span><span class="sxs-lookup"><span data-stu-id="75be2-249">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="75be2-250">Un'altra metrica importante per la classificazione multiclasse è l'accuratezza macro, simile alla Precisione Micro, più è meglio è.</span><span class="sxs-lookup"><span data-stu-id="75be2-250">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="75be2-251">Un buon modo per pensare a questi due tipi di precisione è:</span><span class="sxs-lookup"><span data-stu-id="75be2-251">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="75be2-252">Micro-precisione: con quale frequenza un biglietto in entrata viene classificato nella squadra giusta?</span><span class="sxs-lookup"><span data-stu-id="75be2-252">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="75be2-253">Macro-precisione: Per una squadra media, con quale frequenza un biglietto in entrata è corretto per la propria squadra?</span><span class="sxs-lookup"><span data-stu-id="75be2-253">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="75be2-254">Ulteriori informazioni sulle metriche di valutazione</span><span class="sxs-lookup"><span data-stu-id="75be2-254">More information on evaluation metrics</span></span>

<span data-ttu-id="75be2-255">Per altre informazioni, vedere [Metriche di valutazione dei modelli](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="75be2-255">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="75be2-256">Migliorare</span><span class="sxs-lookup"><span data-stu-id="75be2-256">Improve</span></span>

<span data-ttu-id="75be2-257">Se il punteggio delle prestazioni del modello non è quello desiderato, è possibile:</span><span class="sxs-lookup"><span data-stu-id="75be2-257">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="75be2-258">Eseguire il training per un periodo di tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="75be2-258">Train for a longer period of time.</span></span> <span data-ttu-id="75be2-259">Con più tempo, il motore di apprendimento automatico sperimenta più algoritmi e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="75be2-259">With more time, the automated machine learning engine experiments with more algorithms and settings.</span></span>

- <span data-ttu-id="75be2-260">Aggiungere altri dati.</span><span class="sxs-lookup"><span data-stu-id="75be2-260">Add more data.</span></span> <span data-ttu-id="75be2-261">A volte la quantità di dati non è sufficiente per eseguire il training di un modello di Machine Learning di qualità elevata.</span><span class="sxs-lookup"><span data-stu-id="75be2-261">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="75be2-262">Bilanciare i dati.</span><span class="sxs-lookup"><span data-stu-id="75be2-262">Balance your data.</span></span> <span data-ttu-id="75be2-263">Per le attività di classificazione, assicurarsi che il set di training sia bilanciato tra le categorie.</span><span class="sxs-lookup"><span data-stu-id="75be2-263">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="75be2-264">Ad esempio, se sono presenti quattro classi per 100 esempi di training e le prime due classi (tag1 e tag2) vengono usate per 90 record mentre le altre due classi (tag3 e tag4) vengono usate solo per i rimanenti 10 record, la mancanza di dati bilanciati può rendere più difficile per il modello prevedere correttamente tag3 o tag4.</span><span class="sxs-lookup"><span data-stu-id="75be2-264">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="75be2-265">Codice</span><span class="sxs-lookup"><span data-stu-id="75be2-265">Code</span></span>

<span data-ttu-id="75be2-266">Dopo la fase di valutazione, il generatore di modelli restituisce un file di modello e il codice che è possibile usare per aggiungere il modello all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75be2-266">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="75be2-267">I modelli di ML.NET vengono salvati come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="75be2-267">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="75be2-268">Il codice per caricare e usare il modello viene aggiunto come nuovo progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="75be2-268">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="75be2-269">Il generatore di modelli aggiunge anche un'app console di esempio che è possibile eseguire per visualizzare il modello in azione.</span><span class="sxs-lookup"><span data-stu-id="75be2-269">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="75be2-270">Il generatore di modelli restituisce anche il codice che ha generato il modello che consente di comprendere i passaggi eseguiti per generare il modello.</span><span class="sxs-lookup"><span data-stu-id="75be2-270">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="75be2-271">È anche possibile usare il codice di training del modello per ripetere il training del modello con nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="75be2-271">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="75be2-272">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="75be2-272">What's next?</span></span>

<span data-ttu-id="75be2-273">[Installare](how-to-guides/install-model-builder.md) l'estensione di Visual Studio per il generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="75be2-273">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="75be2-274">Provare [uno scenario di regressione o stima dei prezzi](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="75be2-274">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
