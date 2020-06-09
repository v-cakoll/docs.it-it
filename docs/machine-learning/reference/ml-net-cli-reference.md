---
title: Riferimento al comando CLI ML.NET
description: Panoramica, esempi e riferimento per il comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET.
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 397f6fda8554024624b3ef630856dc8eca9696b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594543"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="00061-103">Riferimento ai comandi dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="00061-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="00061-104">I `classification` `regression` comandi, e `recommendation` sono i comandi principali forniti dallo strumento dell'interfaccia della riga di comando ml.NET.</span><span class="sxs-lookup"><span data-stu-id="00061-104">The `classification`, `regression`, and `recommendation` commands are the main commands provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="00061-105">Questi comandi consentono di generare modelli ML.NET di qualità elevata per la classificazione, la regressione e i modelli di raccomandazione usando automazione Machine Learning (AutoML), nonché il codice C# di esempio per eseguire/assegnare un punteggio a tale modello.</span><span class="sxs-lookup"><span data-stu-id="00061-105">These commands allow you to generate good quality ML.NET models for classification, regression, and recommendation models using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="00061-106">Inoltre, il codice C# per eseguire il training del modello viene generato per la ricerca dell'algoritmo e delle impostazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="00061-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="00061-107">Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="00061-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="00061-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="00061-108">Overview</span></span>

<span data-ttu-id="00061-109">Sintassi di esempio:</span><span class="sxs-lookup"><span data-stu-id="00061-109">Example usage:</span></span>

```console
mlnet regression --dataset "cars.csv" --label-col price
```

<span data-ttu-id="00061-110">I `mlnet` comandi dell'attività ml ( `classification` , `regression` e `recommendation` ) generano gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="00061-110">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) generate the following assets:</span></span>

- <span data-ttu-id="00061-111">Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="00061-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="00061-112">Codice C# per eseguire/assegnare un punteggio al modello generato.</span><span class="sxs-lookup"><span data-stu-id="00061-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="00061-113">Codice C# con il codice di training utilizzato per generare il modello.</span><span class="sxs-lookup"><span data-stu-id="00061-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="00061-114">Le prime due risorse possono essere usate direttamente nelle app per gli utenti finali (ASP.NET Core app Web, servizi, app desktop e altro ancora) per eseguire stime con il modello.</span><span class="sxs-lookup"><span data-stu-id="00061-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="00061-115">Il terzo asset, il codice di training, Mostra il codice API ML.NET usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo da poter esaminare l'algoritmo e le impostazioni specifiche del modello.</span><span class="sxs-lookup"><span data-stu-id="00061-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="00061-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="00061-116">Examples</span></span>

<span data-ttu-id="00061-117">Il comando CLI più semplice per un problema di classificazione (AutoML deduce la maggior parte della configurazione dai dati forniti):</span><span class="sxs-lookup"><span data-stu-id="00061-117">The simplest CLI command for a classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet classification --dataset "customer-feedback.tsv" --label-col Sentiment
```

<span data-ttu-id="00061-118">Un altro comando dell'interfaccia della riga semplice per un problema di regressione:</span><span class="sxs-lookup"><span data-stu-id="00061-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet regression --dataset "cars.csv" --label-col Price
```

<span data-ttu-id="00061-119">Creazione ed addestramento di un modello di classificazione con un set di dati di training, un set di dati di test e altri argomenti espliciti di personalizzazione:</span><span class="sxs-lookup"><span data-stu-id="00061-119">Create and train a classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-col "InsuranceRisk" --cache on --train-time 600
```

## <a name="command-options"></a><span data-ttu-id="00061-120">Opzioni del comando</span><span class="sxs-lookup"><span data-stu-id="00061-120">Command options</span></span>

<span data-ttu-id="00061-121">I `mlnet` comandi dell'attività ml ( `classification` , `regression` e) consentono di eseguire il `recommendation` training di più modelli in base al set di dati fornito e alle opzioni CLI ml.NET.</span><span class="sxs-lookup"><span data-stu-id="00061-121">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) train multiple models based on the provided dataset and ML.NET CLI options.</span></span> <span data-ttu-id="00061-122">Questi comandi selezionano anche il modello migliore, salvano il modello come file con estensione zip serializzato e generano codice C# correlato per il punteggio e il training.</span><span class="sxs-lookup"><span data-stu-id="00061-122">These commands also select the best model, save the model as a serialized .zip file, and generate related C# code for scoring and training.</span></span>

### <a name="classification-options"></a><span data-ttu-id="00061-123">Opzioni di classificazione</span><span class="sxs-lookup"><span data-stu-id="00061-123">Classification options</span></span>

<span data-ttu-id="00061-124">In esecuzione `mlnet classification` viene eseguito il training di un modello di classificazione.</span><span class="sxs-lookup"><span data-stu-id="00061-124">Running `mlnet classification` will train a classification model.</span></span> <span data-ttu-id="00061-125">Scegliere questo comando se si vuole che un modello ML classifichi i dati in due o più classi, ad esempio l'analisi dei sentimenti.</span><span class="sxs-lookup"><span data-stu-id="00061-125">Choose this command if you want an ML Model to categorize data into 2 or more classes (e.g. sentiment analysis).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="regression-options"></a><span data-ttu-id="00061-126">Opzioni di regressione</span><span class="sxs-lookup"><span data-stu-id="00061-126">Regression options</span></span>

<span data-ttu-id="00061-127">`mlnet regression`L'esecuzione di eseguirà il training di un modello di regressione.</span><span class="sxs-lookup"><span data-stu-id="00061-127">Running `mlnet regression` will train a regression model.</span></span> <span data-ttu-id="00061-128">Scegliere questo comando se si vuole che un modello ML predichi un valore numerico, ad esempio la stima del prezzo.</span><span class="sxs-lookup"><span data-stu-id="00061-128">Choose this command if you want an ML Model to predict a numeric value (e.g. price prediction).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="recommendation-options"></a><span data-ttu-id="00061-129">Opzioni di raccomandazione</span><span class="sxs-lookup"><span data-stu-id="00061-129">Recommendation options</span></span>

<span data-ttu-id="00061-130">In esecuzione `mlnet recommendation` viene eseguito il training di un modello di raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="00061-130">Running `mlnet recommendation` will train a recommendation model.</span></span>  <span data-ttu-id="00061-131">Scegliere questo comando se si vuole che un modello ML consigli gli elementi agli utenti in base alle classificazioni (ad esempio, raccomandazione del prodotto).</span><span class="sxs-lookup"><span data-stu-id="00061-131">Choose this command if you want an ML Model to recommend items to users based on ratings (e.g. product recommendation).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--item-col <col> (REQUIRED)

--rating-col <col> (REQUIRED)

--user-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

<span data-ttu-id="00061-132">Opzioni di input non valide. lo strumento dell'interfaccia della riga di comando crea un elenco di input validi e un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="00061-132">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="dataset"></a><span data-ttu-id="00061-133">Set di dati</span><span class="sxs-lookup"><span data-stu-id="00061-133">Dataset</span></span>

<span data-ttu-id="00061-134">`--dataset | -d` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-134">`--dataset | -d` (string)</span></span>

<span data-ttu-id="00061-135">Questo argomento specifica il percorso file di una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00061-135">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="00061-136">*R: l'intero file del set di dati:* Se si usa questa opzione e l'utente non fornisce `--test-dataset` e `--validation-dataset` , la convalida incrociata (k-fold e così via) o gli approcci di suddivisione automatica dei dati verranno usati internamente per la convalida del modello.</span><span class="sxs-lookup"><span data-stu-id="00061-136">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="00061-137">In questo caso l'utente dovrà specificare soltanto il percorso file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="00061-137">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="00061-138">*B: file del set di dati di training:* Se l'utente fornisce anche set di dati per la convalida del modello (usando `--test-dataset` e `--validation-dataset` , facoltativamente), l' `--dataset` argomento significa solo il "set di dati di training".</span><span class="sxs-lookup"><span data-stu-id="00061-138">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="00061-139">Ad esempio, quando viene usato un approccio 80% - 20% per convalidare la qualità del modello e ottenere le metriche di accuratezza, il "training set" avrà l'80% dei dati, mentre il "set di dati di test" avrà il 20% dei dati.</span><span class="sxs-lookup"><span data-stu-id="00061-139">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="00061-140">Set di dati di test</span><span class="sxs-lookup"><span data-stu-id="00061-140">Test dataset</span></span>

<span data-ttu-id="00061-141">`--test-dataset | -t` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-141">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="00061-142">Percorso del file del set di dati di test, ad esempio quando viene usato un approccio 80% - 20% durante le convalide regolari per ottenere le metriche di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="00061-142">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="00061-143">Se viene usato `--test-dataset`, è necessario specificare anche `--dataset`.</span><span class="sxs-lookup"><span data-stu-id="00061-143">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="00061-144">L'argomento `--test-dataset` è facoltativo, a meno che non venga usato --validation-dataset.</span><span class="sxs-lookup"><span data-stu-id="00061-144">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="00061-145">In questo caso, l'utente deve usare i tre argomenti.</span><span class="sxs-lookup"><span data-stu-id="00061-145">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="00061-146">Set di dati di convalida</span><span class="sxs-lookup"><span data-stu-id="00061-146">Validation dataset</span></span>

<span data-ttu-id="00061-147">`--validation-dataset | -v` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-147">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="00061-148">Percorso del file del set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="00061-148">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="00061-149">In tutti i casi il set di dati di convalida è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="00061-149">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="00061-150">Se si usa `validation dataset`, il comportamento deve essere il seguente:</span><span class="sxs-lookup"><span data-stu-id="00061-150">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="00061-151">Anche gli argomenti `test-dataset` e `--dataset` sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="00061-151">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="00061-152">Il set di dati `validation-dataset` viene usato per stimare l'errore di previsione per la selezione del modello.</span><span class="sxs-lookup"><span data-stu-id="00061-152">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="00061-153">Il set di dati `test-dataset` viene usato per la valutazione dell'errore di generalizzazione del modello selezionato finale.</span><span class="sxs-lookup"><span data-stu-id="00061-153">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="00061-154">In teoria, il set di test deve essere conservato in un "vault" e usato solo alla fine dell'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="00061-154">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="00061-155">In pratica, quando vengono usati `validation dataset` e `test dataset`, la fase di convalida è suddivisa in due parti:</span><span class="sxs-lookup"><span data-stu-id="00061-155">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="00061-156">Si esaminano innanzitutto i modelli e si seleziona l'approccio migliore usando i dati di convalida (=validation)</span><span class="sxs-lookup"><span data-stu-id="00061-156">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="00061-157">Quindi si valuta l'accuratezza dell'approccio selezionato (=test).</span><span class="sxs-lookup"><span data-stu-id="00061-157">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="00061-158">Di conseguenza, la suddivisione dei dati potrebbe essere 80/10/10 o 75/15/10.</span><span class="sxs-lookup"><span data-stu-id="00061-158">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="00061-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00061-159">For example:</span></span>

- <span data-ttu-id="00061-160">Il file di `training-dataset` deve avere il 75% dei dati.</span><span class="sxs-lookup"><span data-stu-id="00061-160">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="00061-161">Il file di `validation-dataset` deve avere il 15% dei dati.</span><span class="sxs-lookup"><span data-stu-id="00061-161">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="00061-162">Il file di `test-dataset` deve avere il 10% dei dati.</span><span class="sxs-lookup"><span data-stu-id="00061-162">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="00061-163">In ogni caso, queste percentuali verranno decise dall'utente tramite l'interfaccia della riga di comando che fornirà i file già suddivisi.</span><span class="sxs-lookup"><span data-stu-id="00061-163">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column"></a><span data-ttu-id="00061-164">Colonna di etichetta</span><span class="sxs-lookup"><span data-stu-id="00061-164">Label column</span></span>

<span data-ttu-id="00061-165">`--label-col`(int o String)</span><span class="sxs-lookup"><span data-stu-id="00061-165">`--label-col` (int or string)</span></span>

<span data-ttu-id="00061-166">Con questo argomento, è possibile specificare una colonna objective/target specifica (la variabile che si desidera stimare) utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).</span><span class="sxs-lookup"><span data-stu-id="00061-166">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="00061-167">Questo argomento viene usato per i problemi di *classificazione* e *regressione* .</span><span class="sxs-lookup"><span data-stu-id="00061-167">This argument is used for *classification* and *regression* problems.</span></span>

## <a name="item-column"></a><span data-ttu-id="00061-168">Colonna elemento</span><span class="sxs-lookup"><span data-stu-id="00061-168">Item column</span></span>

<span data-ttu-id="00061-169">`--item-col`(int o String)</span><span class="sxs-lookup"><span data-stu-id="00061-169">`--item-col` (int or string)</span></span>

<span data-ttu-id="00061-170">La colonna Item contiene l'elenco degli elementi che vengono valutati dagli utenti (gli elementi sono consigliati per gli utenti).</span><span class="sxs-lookup"><span data-stu-id="00061-170">The item column has the list of items that users rate (items are recommended to users).</span></span> <span data-ttu-id="00061-171">Questa colonna può essere specificata utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).</span><span class="sxs-lookup"><span data-stu-id="00061-171">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="00061-172">Questo argomento viene utilizzato solo per l'attività *Recommendation* .</span><span class="sxs-lookup"><span data-stu-id="00061-172">This argument is used only for the *recommendation* task.</span></span>

## <a name="rating-column"></a><span data-ttu-id="00061-173">Colonna valutazione</span><span class="sxs-lookup"><span data-stu-id="00061-173">Rating column</span></span>

<span data-ttu-id="00061-174">`--rating-col`(int o String)</span><span class="sxs-lookup"><span data-stu-id="00061-174">`--rating-col` (int or string)</span></span>

<span data-ttu-id="00061-175">Nella colonna rating è presente l'elenco di classificazioni assegnato agli utenti dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="00061-175">The rating column has the list of ratings that are given to items by users.</span></span> <span data-ttu-id="00061-176">Questa colonna può essere specificata utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).</span><span class="sxs-lookup"><span data-stu-id="00061-176">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="00061-177">Questo argomento viene utilizzato solo per l'attività *Recommendation* .</span><span class="sxs-lookup"><span data-stu-id="00061-177">This argument is used only for the *recommendation* task.</span></span>

## <a name="user-column"></a><span data-ttu-id="00061-178">Colonna utente</span><span class="sxs-lookup"><span data-stu-id="00061-178">User column</span></span>

<span data-ttu-id="00061-179">`--user-col`(int o String)</span><span class="sxs-lookup"><span data-stu-id="00061-179">`--user-col` (int or string)</span></span>

<span data-ttu-id="00061-180">Nella colonna User è presente l'elenco di utenti che assegnano le classificazioni agli elementi.</span><span class="sxs-lookup"><span data-stu-id="00061-180">The user column has the list of users that give ratings to items.</span></span> <span data-ttu-id="00061-181">Questa colonna può essere specificata utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).</span><span class="sxs-lookup"><span data-stu-id="00061-181">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="00061-182">Questo argomento viene utilizzato solo per l'attività *Recommendation* .</span><span class="sxs-lookup"><span data-stu-id="00061-182">This argument is used only for the *recommendation* task.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="00061-183">Ignora colonne</span><span class="sxs-lookup"><span data-stu-id="00061-183">Ignore columns</span></span>

<span data-ttu-id="00061-184">`--ignore-columns` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-184">`--ignore-columns` (string)</span></span>

<span data-ttu-id="00061-185">Con questo argomento è possibile ignorare le colonne esistenti nel file del set di dati in modo che non vengano caricate e usate dai processi di training.</span><span class="sxs-lookup"><span data-stu-id="00061-185">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="00061-186">Specificare i nomi delle colonne da ignorare.</span><span class="sxs-lookup"><span data-stu-id="00061-186">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="00061-187">Usare ', ' (virgola seguita da uno spazio) oppure ' ' (spazio) per separare più nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="00061-187">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="00061-188">È possibile usare le virgolette per nomi di colonna che contengono uno spazio vuoto (ad esempio, "accesso eseguito").</span><span class="sxs-lookup"><span data-stu-id="00061-188">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="00061-189">Esempio:</span><span class="sxs-lookup"><span data-stu-id="00061-189">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="00061-190">Con intestazione</span><span class="sxs-lookup"><span data-stu-id="00061-190">Has header</span></span>

<span data-ttu-id="00061-191">`--has-header` (bool)</span><span class="sxs-lookup"><span data-stu-id="00061-191">`--has-header` (bool)</span></span>

<span data-ttu-id="00061-192">Specificare se i file di set di dati includono una riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="00061-192">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="00061-193">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="00061-193">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="00061-194">L'interfaccia della riga di comando di ML.NET tenterà di rilevare questa proprietà se questo argomento non è specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="00061-194">The ML.NET CLI will try to detect this property if this argument is not specified by the user.</span></span>

## <a name="train-time"></a><span data-ttu-id="00061-195">Tempo di training</span><span class="sxs-lookup"><span data-stu-id="00061-195">Train time</span></span>

<span data-ttu-id="00061-196">`--train-time` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-196">`--train-time` (string)</span></span>

<span data-ttu-id="00061-197">Per impostazione predefinita, il tempo massimo di esplorazione/Training è di 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="00061-197">By default, the maximum exploration / train time is 30 minutes.</span></span>

<span data-ttu-id="00061-198">Questo argomento imposta il tempo massimo (in secondi) per il processo per l'esplorazione di più trainer e configurazioni.</span><span class="sxs-lookup"><span data-stu-id="00061-198">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="00061-199">Il tempo configurato può essere superato se il tempo specificato è troppo breve (ad esempio, 2 secondi) per una singola iterazione.</span><span class="sxs-lookup"><span data-stu-id="00061-199">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="00061-200">In questo caso, il tempo effettivo corrisponde al tempo necessario per produrre una configurazione di modello in una singola iterazione.</span><span class="sxs-lookup"><span data-stu-id="00061-200">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="00061-201">Il tempo necessario per le iterazioni può variare a seconda delle dimensioni del set di dati.</span><span class="sxs-lookup"><span data-stu-id="00061-201">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="00061-202">Cache</span><span class="sxs-lookup"><span data-stu-id="00061-202">Cache</span></span>

<span data-ttu-id="00061-203">`--cache` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-203">`--cache` (string)</span></span>

<span data-ttu-id="00061-204">Se si usa la memorizzazione nella cache, verrà caricato in memoria l'intero training set.</span><span class="sxs-lookup"><span data-stu-id="00061-204">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="00061-205">Per set di dati di piccole e medie dimensioni, l'uso della cache può migliorare nettamente le prestazioni di training riducendo il tempo di training rispetto a quando non si usa la cache.</span><span class="sxs-lookup"><span data-stu-id="00061-205">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="00061-206">Tuttavia, per i set di dati di grandi dimensioni, il caricamento di tutti i dati in memoria può influire negativamente ed esaurire la memoria.</span><span class="sxs-lookup"><span data-stu-id="00061-206">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="00061-207">Quando viene eseguito il training con file di set di dati di grandi dimensioni senza usare la cache, ML.NET esegue lo streaming di blocchi di dati dell'unità quando è necessario caricare più dati durante il training.</span><span class="sxs-lookup"><span data-stu-id="00061-207">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="00061-208">È possibile specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="00061-208">You can specify the following values:</span></span>

<span data-ttu-id="00061-209">`on`: Forza la cache da usare durante il training.</span><span class="sxs-lookup"><span data-stu-id="00061-209">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="00061-210">`off`: Forza la cache a non essere utilizzata durante il training.</span><span class="sxs-lookup"><span data-stu-id="00061-210">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="00061-211">`auto`: A seconda dell'euristica AutoML, la cache verrà utilizzata o meno.</span><span class="sxs-lookup"><span data-stu-id="00061-211">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="00061-212">In genere i set di dati di piccole e medie dimensioni usano la cache, mentre i set di dati di grandi dimensioni non usano la cache se viene usata l'opzione `auto`.</span><span class="sxs-lookup"><span data-stu-id="00061-212">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="00061-213">Se non si specifica il parametro `--cache`, viene usata la configurazione `auto` della cache per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="00061-213">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="00061-214">Nome</span><span class="sxs-lookup"><span data-stu-id="00061-214">Name</span></span>

<span data-ttu-id="00061-215">`--name` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-215">`--name` (string)</span></span>

<span data-ttu-id="00061-216">Nome del progetto di output o della soluzione creata.</span><span class="sxs-lookup"><span data-stu-id="00061-216">The name for the created output project or solution.</span></span> <span data-ttu-id="00061-217">Se viene specificato alcun nome, viene usato il nome `sample-{mltask}`.</span><span class="sxs-lookup"><span data-stu-id="00061-217">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="00061-218">Verrà assegnato lo stesso nome anche al file di modello di ML.NET (file con estensione zip).</span><span class="sxs-lookup"><span data-stu-id="00061-218">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="00061-219">Percorso di output</span><span class="sxs-lookup"><span data-stu-id="00061-219">Output path</span></span>

<span data-ttu-id="00061-220">`--output-path | -o` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-220">`--output-path | -o` (string)</span></span>

<span data-ttu-id="00061-221">Percorso o cartella radice in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="00061-221">Root location/folder to place the generated output.</span></span> <span data-ttu-id="00061-222">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="00061-222">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="00061-223">Livello di dettaglio</span><span class="sxs-lookup"><span data-stu-id="00061-223">Verbosity</span></span>

<span data-ttu-id="00061-224">`--verbosity | -v` (string)</span><span class="sxs-lookup"><span data-stu-id="00061-224">`--verbosity | -v` (string)</span></span>

<span data-ttu-id="00061-225">Imposta il livello di dettaglio dell'output standard.</span><span class="sxs-lookup"><span data-stu-id="00061-225">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="00061-226">I valori consentiti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="00061-226">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="00061-227">`m[inimal]`  (per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="00061-227">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="00061-228">`diag[nostic]` (livello informazioni di registrazione)</span><span class="sxs-lookup"><span data-stu-id="00061-228">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="00061-229">Per impostazione predefinita, lo strumento dell'interfaccia della riga di comando deve visualizzare un feedback minimo ( `minimal` ) quando funziona, ad esempio indicando che è funzionante e se possibile quanto tempo rimane o quale percentuale del tempo è stata completata.</span><span class="sxs-lookup"><span data-stu-id="00061-229">By default, the CLI tool should show some minimum feedback (`minimal`) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="00061-230">Guida</span><span class="sxs-lookup"><span data-stu-id="00061-230">Help</span></span>

`-h |--help`

<span data-ttu-id="00061-231">Visualizza le informazioni della Guida per il comando con una descrizione per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="00061-231">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="00061-232">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00061-232">See also</span></span>

- [<span data-ttu-id="00061-233">Come installare lo strumento dell'interfaccia della riga comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="00061-233">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="00061-234">Panoramica dell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="00061-234">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="00061-235">Esercitazione: analizzare i sentimenti usando l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="00061-235">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="00061-236">Telemetria nell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="00061-236">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
