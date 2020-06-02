---
title: Che cos'è il generatore di modelli e come funziona?
description: Come usare il generatore di modelli di ML.NET per eseguire automaticamente il training di un modello di Machine Learning
ms.date: 06/01/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 2ed4a0c3c94ae9f46bb1cf6ddb1e9774baf82367
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289499"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="26bff-103">Che cos'è il generatore di modelli e come funziona?</span><span class="sxs-lookup"><span data-stu-id="26bff-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="26bff-104">Il generatore di modelli di ML.NET è un'estensione grafica intuitiva di Visual Studio che consente di compilare, eseguire il training e distribuire modelli di Machine Learning personalizzati.</span><span class="sxs-lookup"><span data-stu-id="26bff-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="26bff-105">Il generatore di modelli usa il Machine Learning automatico (AutoML) per esplorare diversi algoritmi di Machine Learning e impostazioni per individuare quelli più adatti allo scenario.</span><span class="sxs-lookup"><span data-stu-id="26bff-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="26bff-106">Non è necessario avere competenze di Machine Learning per usare il generatore di modelli.</span><span class="sxs-lookup"><span data-stu-id="26bff-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="26bff-107">Servono solo alcuni dati e un problema da risolvere.</span><span class="sxs-lookup"><span data-stu-id="26bff-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="26bff-108">Il generatore di modelli genera il codice per aggiungere il modello all'applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="26bff-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Animazione dell'interfaccia utente dell'estensione del generatore di modelli di Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="26bff-110">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="26bff-110">Model Builder is currently in Preview.</span></span>

## <a name="scenario"></a><span data-ttu-id="26bff-111">Scenario</span><span class="sxs-lookup"><span data-stu-id="26bff-111">Scenario</span></span>

<span data-ttu-id="26bff-112">È possibile trasferire molti scenari diversi nel generatore di modelli per generare un modello di Machine Learning per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26bff-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="26bff-113">Uno scenario è una descrizione del tipo di previsione che si vuole eseguire usando i dati.</span><span class="sxs-lookup"><span data-stu-id="26bff-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="26bff-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="26bff-114">For example:</span></span>

- <span data-ttu-id="26bff-115">prevedere il volume di vendita futuro dei prodotti in base ai dati storici di vendita</span><span class="sxs-lookup"><span data-stu-id="26bff-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="26bff-116">classificare le valutazioni come positive o negative in base alle recensioni dei clienti</span><span class="sxs-lookup"><span data-stu-id="26bff-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="26bff-117">rilevare se una transazione bancaria è fraudolenta</span><span class="sxs-lookup"><span data-stu-id="26bff-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="26bff-118">indirizzare i problemi dei feedback dei clienti al team corretto nell'azienda</span><span class="sxs-lookup"><span data-stu-id="26bff-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="26bff-119">Quale scenario di Machine Learning è adatto alle mie esigenze?</span><span class="sxs-lookup"><span data-stu-id="26bff-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="26bff-120">In Generatore di modelli è necessario selezionare uno scenario.</span><span class="sxs-lookup"><span data-stu-id="26bff-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="26bff-121">Il tipo di scenario dipende dal tipo di stima che si sta tentando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="26bff-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="text-classification"></a><span data-ttu-id="26bff-122">Classificazione del testo</span><span class="sxs-lookup"><span data-stu-id="26bff-122">Text classification</span></span>

<span data-ttu-id="26bff-123">La classificazione viene utilizzata per categorizzare i dati in categorie.</span><span class="sxs-lookup"><span data-stu-id="26bff-123">Classification is used to categorize data into categories.</span></span>

![Diagramma che mostra esempi di classificazione binaria, tra cui il rilevamento delle frodi, la mitigazione dei rischi e lo screening delle applicazioni](media/binary-classification-examples.png)

![Esempi di classificazione multiclasse, tra cui la classificazione di documenti e prodotti, il routing dei ticket di supporto e l'assegnazione di priorità ai problemi dei clienti](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a><span data-ttu-id="26bff-126">Stima del valore</span><span class="sxs-lookup"><span data-stu-id="26bff-126">Value prediction</span></span>

<span data-ttu-id="26bff-127">La regressione viene usata per prevedere i numeri.</span><span class="sxs-lookup"><span data-stu-id="26bff-127">Regression is used to predict numbers.</span></span>

![Diagramma che mostra esempi di regressione, ad esempio stime del prezzo, previsioni di vendita e manutenzione predittiva](media/regression-examples.png)

#### <a name="image-classification"></a><span data-ttu-id="26bff-129">Classificazione di immagini</span><span class="sxs-lookup"><span data-stu-id="26bff-129">Image classification</span></span>

<span data-ttu-id="26bff-130">È possibile usare la classificazione delle immagini per identificare immagini di diverse categorie.</span><span class="sxs-lookup"><span data-stu-id="26bff-130">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="26bff-131">Ad esempio, diversi tipi di terreno o animali o difetti di produzione.</span><span class="sxs-lookup"><span data-stu-id="26bff-131">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="26bff-132">È possibile utilizzare lo scenario di classificazione delle immagini se si dispone di un set di immagini e si desidera classificare le immagini in categorie diverse.</span><span class="sxs-lookup"><span data-stu-id="26bff-132">You can use the image classification scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="recommendation"></a><span data-ttu-id="26bff-133">Recommendation</span><span class="sxs-lookup"><span data-stu-id="26bff-133">Recommendation</span></span>

<span data-ttu-id="26bff-134">Lo scenario di raccomandazione prevede un elenco di elementi consigliati per un determinato utente, in base alla somiglianza e alle dispiacenze di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="26bff-134">The recommendation scenario predicts a list of suggested items for a particular user, based on how similar their likes and dislikes are to other users'.</span></span>

<span data-ttu-id="26bff-135">È possibile utilizzare lo scenario di raccomandazione quando si dispone di un set di utenti e un set di "prodotti", ad esempio articoli da acquistare, filmati, libri o programmi TELEVISIVi, insieme a un set di "classificazioni" degli utenti di questi prodotti.</span><span class="sxs-lookup"><span data-stu-id="26bff-135">You can use the recommendation scenario when you have a set of users and a set of "products", such as items to purchase, movies, books, or TV shows, along with a set of users' "ratings" of those products.</span></span>

## <a name="environment"></a><span data-ttu-id="26bff-136">Environment</span><span class="sxs-lookup"><span data-stu-id="26bff-136">Environment</span></span>

<span data-ttu-id="26bff-137">È possibile eseguire il training del modello di Machine Learning localmente nel computer o nel cloud in Azure.</span><span class="sxs-lookup"><span data-stu-id="26bff-137">You can train your machine learning model locally on your machine or in the cloud on Azure.</span></span>

<span data-ttu-id="26bff-138">Quando si esegue il training in locale, si lavora nei vincoli delle risorse del computer (CPU, memoria e disco).</span><span class="sxs-lookup"><span data-stu-id="26bff-138">When you train locally, you work within the constraints of your computer resources (CPU, memory, and disk).</span></span> <span data-ttu-id="26bff-139">Quando si esegue il training nel cloud, è possibile ridimensionare le risorse per soddisfare le esigenze dello scenario, soprattutto per i set di impostazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="26bff-139">When you train in the cloud, you can scale up your resources to meet the demands of your scenario, especially for large datasets.</span></span>

<span data-ttu-id="26bff-140">Il training locale è supportato per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="26bff-140">Local training is supported for all scenarios.</span></span>

<span data-ttu-id="26bff-141">La formazione di Azure è supportata per la classificazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="26bff-141">Azure training is supported for Image Classification.</span></span>

## <a name="data"></a><span data-ttu-id="26bff-142">Data</span><span class="sxs-lookup"><span data-stu-id="26bff-142">Data</span></span>

<span data-ttu-id="26bff-143">Una volta scelto lo scenario, generatore di modelli richiede di fornire un set di dati.</span><span class="sxs-lookup"><span data-stu-id="26bff-143">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="26bff-144">I dati vengono usati per il training, la valutazione e la scelta del modello più adatto per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="26bff-144">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Diagramma che illustra i passaggi del generatore di modelli](media/model-builder-steps.png)

<span data-ttu-id="26bff-146">Il generatore di modelli supporta i set di dati nei formati TSV, CSV, txt, oltre al formato del database SQL.</span><span class="sxs-lookup"><span data-stu-id="26bff-146">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="26bff-147">Se si dispone di un file con estensione txt, le colonne devono essere separate da `,` `;` o `/t` e il file deve contenere una riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="26bff-147">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="26bff-148">Se il set di dati è costituito da immagini, i tipi di file supportati sono `.jpg` e `.png` .</span><span class="sxs-lookup"><span data-stu-id="26bff-148">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="26bff-149">Per altre informazioni, vedere [caricare i dati di training in Generatore di modelli](how-to-guides/load-data-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="26bff-149">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="26bff-150">Scegliere l'output da prevedere (etichetta)</span><span class="sxs-lookup"><span data-stu-id="26bff-150">Choose the output to predict (label)</span></span>

<span data-ttu-id="26bff-151">Un set di dati è una tabella di righe di esempi di training e di colonne di attributi.</span><span class="sxs-lookup"><span data-stu-id="26bff-151">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="26bff-152">Ogni riga include:</span><span class="sxs-lookup"><span data-stu-id="26bff-152">Each row has:</span></span>

- <span data-ttu-id="26bff-153">un'**etichetta** (l'attributo da prevedere)</span><span class="sxs-lookup"><span data-stu-id="26bff-153">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="26bff-154">le **caratteristiche** (gli attributi usati come input per la previsione dell'etichetta).</span><span class="sxs-lookup"><span data-stu-id="26bff-154">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="26bff-155">Per lo scenario di stima del prezzo della casa, è possibile usare le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="26bff-155">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="26bff-156">i metri quadrati della casa</span><span class="sxs-lookup"><span data-stu-id="26bff-156">the square footage of the house</span></span>
- <span data-ttu-id="26bff-157">il numero di camere da letto e bagni</span><span class="sxs-lookup"><span data-stu-id="26bff-157">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="26bff-158">il codice postale</span><span class="sxs-lookup"><span data-stu-id="26bff-158">the zip code</span></span>

<span data-ttu-id="26bff-159">L'etichetta è il prezzo storico della casa per la riga dei valori dei metri quadrati, delle camere da letto e dei bagni e il codice postale.</span><span class="sxs-lookup"><span data-stu-id="26bff-159">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Tabella che mostra le righe e le colonne di dati sui prezzi delle case con le caratteristiche delle dimensioni dei locali, del codice postale e dell'etichetta del prezzo](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="26bff-161">Set di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="26bff-161">Example datasets</span></span>

<span data-ttu-id="26bff-162">Se non sono ancora disponibili dati, provare uno dei set di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="26bff-162">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="26bff-163">Scenario</span><span class="sxs-lookup"><span data-stu-id="26bff-163">Scenario</span></span>|<span data-ttu-id="26bff-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="26bff-164">Example</span></span>|<span data-ttu-id="26bff-165">Data</span><span class="sxs-lookup"><span data-stu-id="26bff-165">Data</span></span>|<span data-ttu-id="26bff-166">Label</span><span class="sxs-lookup"><span data-stu-id="26bff-166">Label</span></span>|<span data-ttu-id="26bff-167">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="26bff-167">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="26bff-168">Classificazione</span><span class="sxs-lookup"><span data-stu-id="26bff-168">Classification</span></span>|<span data-ttu-id="26bff-169">Stimare le anomalie di vendita</span><span class="sxs-lookup"><span data-stu-id="26bff-169">Predict sales anomalies</span></span>|[<span data-ttu-id="26bff-170">dati di vendita dei prodotti</span><span class="sxs-lookup"><span data-stu-id="26bff-170">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="26bff-171">Vendita dei prodotti</span><span class="sxs-lookup"><span data-stu-id="26bff-171">Product Sales</span></span>|<span data-ttu-id="26bff-172">Month</span><span class="sxs-lookup"><span data-stu-id="26bff-172">Month</span></span>|
||<span data-ttu-id="26bff-173">Stimare i sentimenti dei commenti del sito Web</span><span class="sxs-lookup"><span data-stu-id="26bff-173">Predict sentiment of website comments</span></span>|[<span data-ttu-id="26bff-174">dati dei commenti del sito Web</span><span class="sxs-lookup"><span data-stu-id="26bff-174">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="26bff-175">Etichetta (0 con sentiment negativo, 1 con sentiment positivo)</span><span class="sxs-lookup"><span data-stu-id="26bff-175">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="26bff-176">Commento, anno</span><span class="sxs-lookup"><span data-stu-id="26bff-176">Comment, Year</span></span>|
||<span data-ttu-id="26bff-177">Stimare le transazioni della carta di credito fraudolente</span><span class="sxs-lookup"><span data-stu-id="26bff-177">Predict fraudulent credit card transactions</span></span>|[<span data-ttu-id="26bff-178">dati della carta di credito</span><span class="sxs-lookup"><span data-stu-id="26bff-178">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="26bff-179">Classe (1 quando fraudolento, 0 in caso contrario)</span><span class="sxs-lookup"><span data-stu-id="26bff-179">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="26bff-180">Quantità, V1-V28 (caratteristiche anonime)</span><span class="sxs-lookup"><span data-stu-id="26bff-180">Amount, V1-V28 (anonymized features)</span></span>|
||<span data-ttu-id="26bff-181">Prevedere il tipo di problema in un repository GitHub</span><span class="sxs-lookup"><span data-stu-id="26bff-181">Predict the type of issue in a GitHub repository</span></span>|[<span data-ttu-id="26bff-182">dati del problema di GitHub</span><span class="sxs-lookup"><span data-stu-id="26bff-182">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="26bff-183">Area</span><span class="sxs-lookup"><span data-stu-id="26bff-183">Area</span></span>|<span data-ttu-id="26bff-184">Titolo, descrizione</span><span class="sxs-lookup"><span data-stu-id="26bff-184">Title, Description</span></span>|
|<span data-ttu-id="26bff-185">Stima del valore</span><span class="sxs-lookup"><span data-stu-id="26bff-185">Value prediction</span></span>|<span data-ttu-id="26bff-186">Stimare il prezzo della tariffa di taxi</span><span class="sxs-lookup"><span data-stu-id="26bff-186">Predict taxi fare price</span></span>|[<span data-ttu-id="26bff-187">dati delle tariffe dei taxi</span><span class="sxs-lookup"><span data-stu-id="26bff-187">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="26bff-188">Tariffe</span><span class="sxs-lookup"><span data-stu-id="26bff-188">Fare</span></span>|<span data-ttu-id="26bff-189">Tempo della corsa, distanza</span><span class="sxs-lookup"><span data-stu-id="26bff-189">Trip time, distance</span></span>|
|<span data-ttu-id="26bff-190">Classificazione di immagini</span><span class="sxs-lookup"><span data-stu-id="26bff-190">Image classification</span></span>|<span data-ttu-id="26bff-191">Stimare la categoria di un fiore</span><span class="sxs-lookup"><span data-stu-id="26bff-191">Predict the category of a flower</span></span> |[<span data-ttu-id="26bff-192">immagini floreali</span><span class="sxs-lookup"><span data-stu-id="26bff-192">flower images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="26bff-193">Tipo di fiore: Daisy, Dandelion, Roses, girasoli, tulipani</span><span class="sxs-lookup"><span data-stu-id="26bff-193">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="26bff-194">Dati dell'immagine</span><span class="sxs-lookup"><span data-stu-id="26bff-194">The image data itself</span></span>|
|<span data-ttu-id="26bff-195">Recommendation</span><span class="sxs-lookup"><span data-stu-id="26bff-195">Recommendation</span></span>|<span data-ttu-id="26bff-196">Prevedere i film che un utente vuole</span><span class="sxs-lookup"><span data-stu-id="26bff-196">Predict movies that someone will like</span></span>|[<span data-ttu-id="26bff-197">classificazioni film</span><span class="sxs-lookup"><span data-stu-id="26bff-197">movie ratings</span></span>](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|<span data-ttu-id="26bff-198">Utenti, filmati</span><span class="sxs-lookup"><span data-stu-id="26bff-198">Users, Movies</span></span>|<span data-ttu-id="26bff-199">Classificazioni</span><span class="sxs-lookup"><span data-stu-id="26bff-199">Ratings</span></span>|

## <a name="train"></a><span data-ttu-id="26bff-200">Eseguire il training</span><span class="sxs-lookup"><span data-stu-id="26bff-200">Train</span></span>

<span data-ttu-id="26bff-201">Dopo aver selezionato lo scenario, l'ambiente, i dati e l'etichetta, generatore di modelli esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="26bff-201">Once you select your scenario, environment, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="26bff-202">Cos'è il training?</span><span class="sxs-lookup"><span data-stu-id="26bff-202">What is training?</span></span>

<span data-ttu-id="26bff-203">Il training è un processo automatico tramite il quale il generatore di modelli indica al modello come rispondere alle domande per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="26bff-203">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="26bff-204">Dopo aver eseguito il training, il modello può effettuare previsioni con dati di input completamente nuovi.</span><span class="sxs-lookup"><span data-stu-id="26bff-204">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="26bff-205">Ad esempio, se si sta eseguendo la stima dei prezzi e viene immessa sul mercato una nuova casa, è possibile prevederne il prezzo di vendita.</span><span class="sxs-lookup"><span data-stu-id="26bff-205">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="26bff-206">Poiché il generatore di modelli usa Il Machine Learning automatico (AutoML), non viene richiesto alcun input o ottimizzazione durante il training.</span><span class="sxs-lookup"><span data-stu-id="26bff-206">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="26bff-207">Per quanto tempo è consigliabile eseguire il training?</span><span class="sxs-lookup"><span data-stu-id="26bff-207">How long should I train for?</span></span>

<span data-ttu-id="26bff-208">Il generatore di modelli USA AutoML per esplorare più modelli per trovare il modello con le prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="26bff-208">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="26bff-209">I periodi di training più lunghi consentono a AutoML di esplorare più modelli con una gamma più ampia di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="26bff-209">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="26bff-210">La tabella seguente riepiloga il tempo medio necessario per ottenere prestazioni ottimali per una suite di set di impostazioni di esempio, in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="26bff-210">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="26bff-211">Dimensioni del set di dati</span><span class="sxs-lookup"><span data-stu-id="26bff-211">Dataset size</span></span>|<span data-ttu-id="26bff-212">Tempo medio per il training</span><span class="sxs-lookup"><span data-stu-id="26bff-212">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="26bff-213">0-10 MB</span><span class="sxs-lookup"><span data-stu-id="26bff-213">0 - 10 MB</span></span>|<span data-ttu-id="26bff-214">10 sec</span><span class="sxs-lookup"><span data-stu-id="26bff-214">10 sec</span></span>|
|<span data-ttu-id="26bff-215">10-100 MB</span><span class="sxs-lookup"><span data-stu-id="26bff-215">10 - 100 MB</span></span>|<span data-ttu-id="26bff-216">10 min</span><span class="sxs-lookup"><span data-stu-id="26bff-216">10 min</span></span>|
|<span data-ttu-id="26bff-217">100-500 MB</span><span class="sxs-lookup"><span data-stu-id="26bff-217">100 - 500 MB</span></span>|<span data-ttu-id="26bff-218">30 min</span><span class="sxs-lookup"><span data-stu-id="26bff-218">30 min</span></span>|
|<span data-ttu-id="26bff-219">500-1 GB</span><span class="sxs-lookup"><span data-stu-id="26bff-219">500 - 1 GB</span></span>|<span data-ttu-id="26bff-220">60 min</span><span class="sxs-lookup"><span data-stu-id="26bff-220">60 min</span></span>|
|<span data-ttu-id="26bff-221">1 GB +</span><span class="sxs-lookup"><span data-stu-id="26bff-221">1 GB+</span></span>|<span data-ttu-id="26bff-222">3 + ore</span><span class="sxs-lookup"><span data-stu-id="26bff-222">3+ hours</span></span>|

<span data-ttu-id="26bff-223">Questi numeri sono solo una guida.</span><span class="sxs-lookup"><span data-stu-id="26bff-223">These numbers are a guide only.</span></span> <span data-ttu-id="26bff-224">La lunghezza esatta del training dipende da:</span><span class="sxs-lookup"><span data-stu-id="26bff-224">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="26bff-225">il numero di funzioni (colonne) utilizzate come input per il modello</span><span class="sxs-lookup"><span data-stu-id="26bff-225">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="26bff-226">tipo di colonne</span><span class="sxs-lookup"><span data-stu-id="26bff-226">the type of columns</span></span>
- <span data-ttu-id="26bff-227">attività ML</span><span class="sxs-lookup"><span data-stu-id="26bff-227">the ML task</span></span>
- <span data-ttu-id="26bff-228">le prestazioni della CPU, del disco e della memoria del computer utilizzato per il training</span><span class="sxs-lookup"><span data-stu-id="26bff-228">the CPU, disk, and memory performance of the machine used for training</span></span>

<span data-ttu-id="26bff-229">Si consiglia in genere di usare più di 100 righe come set di dati con un valore minore di quello che potrebbe non produrre alcun risultato e potrebbe richiedere un tempo molto più lungo per il training.</span><span class="sxs-lookup"><span data-stu-id="26bff-229">It's generally advised that you use more than 100 rows as datasets with less than that may not produce any results and may take a significantly longer time to train.</span></span>

## <a name="evaluate"></a><span data-ttu-id="26bff-230">Valutazione</span><span class="sxs-lookup"><span data-stu-id="26bff-230">Evaluate</span></span>

<span data-ttu-id="26bff-231">La valutazione è il processo di misurazione della qualità del modello.</span><span class="sxs-lookup"><span data-stu-id="26bff-231">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="26bff-232">Il generatore di modelli utilizza il modello sottoposto a training per eseguire stime con nuovi dati di test e quindi misura la qualità delle stime.</span><span class="sxs-lookup"><span data-stu-id="26bff-232">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="26bff-233">Il generatore di modelli suddivide i dati di training in un set di training e un set di test.</span><span class="sxs-lookup"><span data-stu-id="26bff-233">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="26bff-234">I dati di training (80%) vengono usati per eseguire il training del modello, mentre i dati di test (20%) vengono usati per la valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="26bff-234">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="26bff-235">Ricerca per categorie comprendere le prestazioni del modello?</span><span class="sxs-lookup"><span data-stu-id="26bff-235">How do I understand my model performance?</span></span>

<span data-ttu-id="26bff-236">Uno scenario è mappato a un'attività di machine learning.</span><span class="sxs-lookup"><span data-stu-id="26bff-236">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="26bff-237">Ogni attività ML dispone di un proprio set di metriche di valutazione.</span><span class="sxs-lookup"><span data-stu-id="26bff-237">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="value-prediction"></a><span data-ttu-id="26bff-238">Stima del valore</span><span class="sxs-lookup"><span data-stu-id="26bff-238">Value prediction</span></span>

<span data-ttu-id="26bff-239">La metrica predefinita per i problemi di stima del valore è RSquared, il valore di RSquared è compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="26bff-239">The default metric for value prediction problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="26bff-240">1 è il miglior valore possibile o, in altre parole, più il valore di RSquared è più vicino a 1 migliore sarà l'esecuzione del modello.</span><span class="sxs-lookup"><span data-stu-id="26bff-240">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="26bff-241">Altre metriche segnalate come la perdita assoluta, la perdita quadrata e la perdita di RMS sono metriche aggiuntive, che possono essere usate per comprendere il modo in cui il modello esegue e il confronto con altri modelli di stima del valore.</span><span class="sxs-lookup"><span data-stu-id="26bff-241">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other value prediction models.</span></span>

#### <a name="classification-2-categories"></a><span data-ttu-id="26bff-242">Classificazione (2 categorie)</span><span class="sxs-lookup"><span data-stu-id="26bff-242">Classification (2 categories)</span></span>

<span data-ttu-id="26bff-243">La metrica predefinita per i problemi di classificazione è l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="26bff-243">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="26bff-244">L'accuratezza definisce la percentuale di stime corrette che il modello sta eseguendo sul set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="26bff-244">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="26bff-245">Il più vicino a 100% o 1,0 è migliore.</span><span class="sxs-lookup"><span data-stu-id="26bff-245">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="26bff-246">Altre metriche segnalate, ad esempio AUC (area sotto la curva), che misura il vero tasso positivo rispetto a. il tasso di falsi positivi deve essere maggiore di 0,50 per i modelli in modo che siano accettabili.</span><span class="sxs-lookup"><span data-stu-id="26bff-246">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="26bff-247">Metriche aggiuntive, come il Punteggio F1, possono essere usate per controllare il saldo tra precisione e richiamo.</span><span class="sxs-lookup"><span data-stu-id="26bff-247">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="classification-3-categories"></a><span data-ttu-id="26bff-248">Classificazione (3 + categorie)</span><span class="sxs-lookup"><span data-stu-id="26bff-248">Classification (3+ categories)</span></span>

<span data-ttu-id="26bff-249">La metrica predefinita per la classificazione multiclasse è la precisione Micro.</span><span class="sxs-lookup"><span data-stu-id="26bff-249">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="26bff-250">Maggiore è il modo in cui l'accuratezza Micro è più vicina al 100% o 1,0.</span><span class="sxs-lookup"><span data-stu-id="26bff-250">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="26bff-251">Un'altra metrica importante per la classificazione multiclasse è l'accuratezza della macro, analogamente alla micro-precisione, più vicina a 1,0, migliore è.</span><span class="sxs-lookup"><span data-stu-id="26bff-251">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="26bff-252">Un modo efficace per considerare questi due tipi di accuratezza è:</span><span class="sxs-lookup"><span data-stu-id="26bff-252">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="26bff-253">Micro-precisione: con quale frequenza un ticket in arrivo viene Classificato al team appropriato?</span><span class="sxs-lookup"><span data-stu-id="26bff-253">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="26bff-254">Accuratezza macro: per un team medio, con quale frequenza un ticket in ingresso è corretto per il proprio team?</span><span class="sxs-lookup"><span data-stu-id="26bff-254">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="26bff-255">Altre informazioni sulle metriche di valutazione</span><span class="sxs-lookup"><span data-stu-id="26bff-255">More information on evaluation metrics</span></span>

<span data-ttu-id="26bff-256">Per altre informazioni, vedere [Metriche di valutazione dei modelli](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="26bff-256">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="26bff-257">Migliorare</span><span class="sxs-lookup"><span data-stu-id="26bff-257">Improve</span></span>

<span data-ttu-id="26bff-258">Se il punteggio delle prestazioni del modello non è quello desiderato, è possibile:</span><span class="sxs-lookup"><span data-stu-id="26bff-258">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="26bff-259">Eseguire il training per un periodo di tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="26bff-259">Train for a longer period of time.</span></span> <span data-ttu-id="26bff-260">Con più tempo, il motore di Machine Learning automatico sperimenta più algoritmi e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="26bff-260">With more time, the automated machine learning engine experiments with more algorithms and settings.</span></span>

- <span data-ttu-id="26bff-261">Aggiungere altri dati.</span><span class="sxs-lookup"><span data-stu-id="26bff-261">Add more data.</span></span> <span data-ttu-id="26bff-262">A volte la quantità di dati non è sufficiente per eseguire il training di un modello di apprendimento automatico di alta qualità. Ciò vale soprattutto per i set di impostazioni con un numero ridotto di esempi.</span><span class="sxs-lookup"><span data-stu-id="26bff-262">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.This is especially true with datasets that have a small number of examples.</span></span>

- <span data-ttu-id="26bff-263">Bilanciare i dati.</span><span class="sxs-lookup"><span data-stu-id="26bff-263">Balance your data.</span></span> <span data-ttu-id="26bff-264">Per le attività di classificazione, assicurarsi che il set di training sia bilanciato tra le categorie.</span><span class="sxs-lookup"><span data-stu-id="26bff-264">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="26bff-265">Ad esempio, se sono presenti quattro classi per 100 esempi di training e le prime due classi (tag1 e tag2) vengono usate per 90 record mentre le altre due classi (tag3 e tag4) vengono usate solo per i rimanenti 10 record, la mancanza di dati bilanciati può rendere più difficile per il modello prevedere correttamente tag3 o tag4.</span><span class="sxs-lookup"><span data-stu-id="26bff-265">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="26bff-266">Codice</span><span class="sxs-lookup"><span data-stu-id="26bff-266">Code</span></span>

<span data-ttu-id="26bff-267">Dopo la fase di valutazione, il generatore di modelli restituisce un file di modello e il codice che è possibile usare per aggiungere il modello all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26bff-267">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="26bff-268">I modelli di ML.NET vengono salvati come file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="26bff-268">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="26bff-269">Il codice per caricare e usare il modello viene aggiunto come nuovo progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="26bff-269">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="26bff-270">Il generatore di modelli aggiunge anche un'app console di esempio che è possibile eseguire per visualizzare il modello in azione.</span><span class="sxs-lookup"><span data-stu-id="26bff-270">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="26bff-271">Il generatore di modelli restituisce anche il codice che ha generato il modello che consente di comprendere i passaggi eseguiti per generare il modello.</span><span class="sxs-lookup"><span data-stu-id="26bff-271">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="26bff-272">È anche possibile usare il codice di training del modello per ripetere il training del modello con nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="26bff-272">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="26bff-273">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="26bff-273">What's next?</span></span>

<span data-ttu-id="26bff-274">[Installare](how-to-guides/install-model-builder.md) l'estensione di Visual Studio per il generatore di modelli</span><span class="sxs-lookup"><span data-stu-id="26bff-274">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="26bff-275">Provare [uno scenario di regressione o stima dei prezzi](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="26bff-275">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
