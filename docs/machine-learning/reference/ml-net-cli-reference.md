---
title: Comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET
description: Panoramica, esempi e riferimento per il comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET.
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: ce5994f392c492e80676b9e65ce54fe010cf03ab
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722608"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a><span data-ttu-id="b091e-103">Comando 'auto-train' nell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="b091e-103">The 'auto-train' command in ML.NET CLI</span></span>

> [!NOTE]
> <span data-ttu-id="b091e-104">Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="b091e-104">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="b091e-105">Il comando `auto-train` è il comando principale dello strumento dell'interfaccia della riga di comando di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="b091e-105">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="b091e-106">Il comando consente di generare un modello di ML.NET di buona qualità (file di modello serializzato con estensione zip) e il codice C# di esempio per eseguire/assegnare un punteggio al modello.</span><span class="sxs-lookup"><span data-stu-id="b091e-106">The command allows you to generate a good quality ML.NET model (serialized model .zip file) plus the example C# code to run/score that model.</span></span> <span data-ttu-id="b091e-107">Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello per ricercare l'algoritmo e le impostazioni usate per il "miglior modello" generato.</span><span class="sxs-lookup"><span data-stu-id="b091e-107">In addition, the C# code to create/train that model is also generated for you to research what algorithm and settings it is using for that generated "best model".</span></span>

<span data-ttu-id="b091e-108">Poiché è possibile generare questi asset dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.</span><span class="sxs-lookup"><span data-stu-id="b091e-108">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="b091e-109">Attualmente, le attività di Machine Learning supportate dall'interfaccia della riga di comando di ML.NET sono:</span><span class="sxs-lookup"><span data-stu-id="b091e-109">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`

- <span data-ttu-id="b091e-110">In futuro saranno supportate altre attività di Machine Learning, ad esempio</span><span class="sxs-lookup"><span data-stu-id="b091e-110">Future: Other machine learning tasks, such as</span></span>
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

<span data-ttu-id="b091e-111">Esempio di utilizzo nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="b091e-111">Example of usage on the command prompt:</span></span>

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="b091e-112">Il comando `mlnet auto-train` genera gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="b091e-112">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="b091e-113">Un file di modello serializzato con estensione zip ("miglior modello") pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="b091e-113">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="b091e-114">Il codice C# per eseguire/assegnare un punteggio al modello generato (per effettuare previsioni nelle app degli utenti finali con il modello).</span><span class="sxs-lookup"><span data-stu-id="b091e-114">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
- <span data-ttu-id="b091e-115">Il codice C# con il codice di training usato per generare il modello (a scopo di apprendimento).</span><span class="sxs-lookup"><span data-stu-id="b091e-115">C# code with the training code used to generate that model (Learning purposes).</span></span>

<span data-ttu-id="b091e-116">I primi due asset possono essere usati direttamente nelle app degli utenti finali (app Web ASP.NET Core, servizi, app desktop, ecc.) per effettuare previsioni con il modello di Machine Learning generato.</span><span class="sxs-lookup"><span data-stu-id="b091e-116">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="b091e-117">Poiché il terzo asset, il codice di training, mostra il codice API di ML.NET usato dall'interfaccia della riga di comando per eseguire il training del modello generato, è possibile individuare il trainer/algoritmo specifico e gli iperparametri selezionati dall'interfaccia della riga di comando e dal motore di Machine Learning automatico di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="b091e-117">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-paramenters were selected by the CLI and the ML.NET AutoML engine.</span></span>

## <a name="the-auto-train-command-uses-the-automl-engine"></a><span data-ttu-id="b091e-118">Il comando 'auto-train' usa il motore di Machine Learning automatico</span><span class="sxs-lookup"><span data-stu-id="b091e-118">The 'auto-train' command uses the AutoML engine</span></span>

<span data-ttu-id="b091e-119">L'interfaccia della riga di comando usa il motore di Machine Learning automatico di ML.NET (pacchetto NuGet) per cercare in modo intelligente i modelli di migliore qualità, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="b091e-119">The CLI uses the ML.NET AutoML engine (NuGet package) to intelligently search for the best quality models, as shown in the following diagram:</span></span>

<span data-ttu-id="b091e-120">![immagine](./media/ml-net-automl-working-diagram.png "Motore di Machine Learning automatico usato all'interno dell'interfaccia della riga di comando di ML.NET")</span><span class="sxs-lookup"><span data-stu-id="b091e-120">![image](./media/ml-net-automl-working-diagram.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="b091e-121">Quando si esegue lo strumento dell'interfaccia della riga comando ML.NET con il comando 'auto-train', è possibile osservare che lo strumento prova a eseguire numerose iterazioni con diversi algoritmi e combinazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b091e-121">When running the ML.NET CLI tool with the \`auto-train- command, you'll see the tool trying many iterations with different algorithms and combinations of configuration.</span></span>

## <a name="reference-for-auto-train-command"></a><span data-ttu-id="b091e-122">Riferimento per il comando 'auto-train'</span><span class="sxs-lookup"><span data-stu-id="b091e-122">Reference for 'auto-train' command</span></span>

## <a name="examples"></a><span data-ttu-id="b091e-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="b091e-123">Examples</span></span>

<span data-ttu-id="b091e-124">Comando dell'interfaccia della riga di comando più semplice per un problema di classificazione binaria (la funzionalità di Machine Learning automatico dovrà dedurre la maggior parte della configurazione dai dati forniti):</span><span class="sxs-lookup"><span data-stu-id="b091e-124">Simplest CLI command for a binary classification problem (AutoML will need to infer most of the configuration from the provided data):</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="b091e-125">Un altro comando dell'interfaccia della riga semplice per un problema di regressione:</span><span class="sxs-lookup"><span data-stu-id="b091e-125">Another simple CLI command for a regression problem:</span></span>

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="b091e-126">Creare ed eseguire il training di un modello di classificazione binaria con un set di dati con training, un set di dati di test e ulteriori argomenti espliciti di personalizzazione:</span><span class="sxs-lookup"><span data-stu-id="b091e-126">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a><span data-ttu-id="b091e-127">nome</span><span class="sxs-lookup"><span data-stu-id="b091e-127">Name</span></span>

<span data-ttu-id="b091e-128">`mlnet auto-train` - Esegue il training di più modelli ('n' iterazioni) in base al set di dati fornito e seleziona il modello migliore, lo salva come file serializzato con estensione zip e genera il codice C# correlato per l'assegnazione del punteggio e il training.</span><span class="sxs-lookup"><span data-stu-id="b091e-128">`mlnet auto-train` - Trains multiple models ('n' iterations) based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b091e-129">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b091e-129">Synopsis</span></span>

```console
> mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

<span data-ttu-id="b091e-130">Le opzioni di input non valide devono causare la generazione da parte dello strumento dell'interfaccia della riga di comando di un elenco di valori di input validi e un messaggio di errore che indica l'argomento mancante, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="b091e-130">Invalid input options should cause the CLI tool to emit a list of valid inputs and an error message explaining which arg is missing, if that is the case.</span></span>

## <a name="options"></a><span data-ttu-id="b091e-131">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b091e-131">Options</span></span>

 ----------------------------------------------------------

<span data-ttu-id="b091e-132">`--task | --mltask | -T` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-132">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="b091e-133">Stringa singola che specifica il problema di Machine Learning da risolvere.</span><span class="sxs-lookup"><span data-stu-id="b091e-133">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="b091e-134">Ad esempio, una delle attività seguenti (l'interfaccia della riga di comando supporterà tutte le attività supportate nella funzionalità di Machine Learning automatico):</span><span class="sxs-lookup"><span data-stu-id="b091e-134">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="b091e-135">`regression` - Scegliere se verrà usato il modello di Machine Learning per effettuare la previsione di un valore numerico</span><span class="sxs-lookup"><span data-stu-id="b091e-135">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="b091e-136">`binary-classification` - Scegliere se il risultato del modello di Machine Learning ha due valori booleani categorici possibili (0 o 1).</span><span class="sxs-lookup"><span data-stu-id="b091e-136">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="b091e-137">`multiclass-classification` - Scegliere se il risultato del modello di Machine Learning ha più valori categorici possibili.</span><span class="sxs-lookup"><span data-stu-id="b091e-137">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="b091e-138">Nelle versioni successive saranno supportati ulteriori scenari e attività di Machine Learning, ad esempio `recommendations`, `clustering` e `ranking`.</span><span class="sxs-lookup"><span data-stu-id="b091e-138">In future releases additional ML Tasks and scenarios such as `recommendations`, `clustering` and `ranking` will be supported.</span></span>

 <span data-ttu-id="b091e-139">In questo argomento è necessario specificare una sola attività di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="b091e-139">Only one ML task should be provided in this argument.</span></span>

 ----------------------------------------------------------

<span data-ttu-id="b091e-140">`--dataset | -d` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-140">`--dataset | -d` (string)</span></span>

<span data-ttu-id="b091e-141">Questo argomento specifica il percorso file di una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b091e-141">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="b091e-142">*A: File del set di dati completo:* se si usa questa opzione e l'utente non specifica `--test-dataset` e `--validation-dataset`, verranno usati internamente gli approcci di convalida incrociata (k-fold e così via) o di suddivisione dati automatizzata per la convalida del modello.</span><span class="sxs-lookup"><span data-stu-id="b091e-142">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="b091e-143">In questo caso l'utente dovrà specificare soltanto il percorso file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-143">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="b091e-144">*B: File del training set:* se l'utente specifica anche set di dati per la convalida del modello (usando `--test-dataset` e facoltativamente `--validation-dataset`), l'argomento `--dataset` indica solo la presenza del "training set".</span><span class="sxs-lookup"><span data-stu-id="b091e-144">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="b091e-145">Ad esempio, quando viene usato un approccio 80% - 20% per convalidare la qualità del modello e ottenere le metriche di accuratezza, il "training set" avrà l'80% dei dati, mentre il "set di dati di test" avrà il 20% dei dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-145">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-146">`--test-dataset | -t` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-146">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="b091e-147">Percorso del file del set di dati di test, ad esempio quando viene usato un approccio 80% - 20% durante le convalide regolari per ottenere le metriche di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="b091e-147">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="b091e-148">Se viene usato `--test-dataset`, è necessario specificare anche `--dataset`.</span><span class="sxs-lookup"><span data-stu-id="b091e-148">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="b091e-149">L'argomento `--test-dataset` è facoltativo, a meno che non venga usato --validation-dataset.</span><span class="sxs-lookup"><span data-stu-id="b091e-149">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="b091e-150">In questo caso, l'utente deve usare i tre argomenti.</span><span class="sxs-lookup"><span data-stu-id="b091e-150">In that case, the user must use the three arguments.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-151">`--validation-dataset | -v` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-151">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="b091e-152">Percorso del file del set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="b091e-152">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="b091e-153">In tutti i casi il set di dati di convalida è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b091e-153">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="b091e-154">Se si usa `validation dataset`, il comportamento deve essere il seguente:</span><span class="sxs-lookup"><span data-stu-id="b091e-154">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="b091e-155">Anche gli argomenti `test-dataset` e `--dataset` sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="b091e-155">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="b091e-156">Il set di dati `validation-dataset` viene usato per stimare l'errore di previsione per la selezione del modello.</span><span class="sxs-lookup"><span data-stu-id="b091e-156">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="b091e-157">Il set di dati `test-dataset` viene usato per la valutazione dell'errore di generalizzazione del modello selezionato finale.</span><span class="sxs-lookup"><span data-stu-id="b091e-157">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="b091e-158">In teoria, il set di test deve essere conservato in un "vault" e usato solo alla fine dell'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-158">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="b091e-159">In pratica, quando vengono usati `validation dataset` e `test dataset`, la fase di convalida è suddivisa in due parti:</span><span class="sxs-lookup"><span data-stu-id="b091e-159">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="b091e-160">Si esaminano innanzitutto i modelli e si seleziona l'approccio migliore usando i dati di convalida (=validation)</span><span class="sxs-lookup"><span data-stu-id="b091e-160">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="b091e-161">Quindi si valuta l'accuratezza dell'approccio selezionato (=test).</span><span class="sxs-lookup"><span data-stu-id="b091e-161">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="b091e-162">Di conseguenza, la suddivisione dei dati potrebbe essere 80/10/10 o 75/15/10.</span><span class="sxs-lookup"><span data-stu-id="b091e-162">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="b091e-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b091e-163">For example:</span></span>

- <span data-ttu-id="b091e-164">Il file di `training-dataset` deve avere il 75% dei dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-164">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="b091e-165">Il file di `validation-dataset` deve avere il 15% dei dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-165">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="b091e-166">Il file di `test-dataset` deve avere il 10% dei dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-166">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="b091e-167">In ogni caso, queste percentuali verranno decise dall'utente tramite l'interfaccia della riga di comando che fornirà i file già suddivisi.</span><span class="sxs-lookup"><span data-stu-id="b091e-167">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-168">`--label-column-name | -n` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-168">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="b091e-169">Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando il nome della colonna impostato nell'intestazione del set di dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="b091e-170">Questo argomento viene usato solo per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*.</span><span class="sxs-lookup"><span data-stu-id="b091e-170">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="b091e-171">Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.</span><span class="sxs-lookup"><span data-stu-id="b091e-171">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-172">`--label-column-index | -i` (int)</span><span class="sxs-lookup"><span data-stu-id="b091e-172">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="b091e-173">Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando l'indice numerico della colonna nel file del set di dati (i valori di indice della colonna iniziano da 1).</span><span class="sxs-lookup"><span data-stu-id="b091e-173">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="b091e-174">*Nota:* se l'utente usa anche `--label-column-name`, viene usato `--label-column-name`.</span><span class="sxs-lookup"><span data-stu-id="b091e-174">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="b091e-175">Questo argomento viene usato per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*.</span><span class="sxs-lookup"><span data-stu-id="b091e-175">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="b091e-176">Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.</span><span class="sxs-lookup"><span data-stu-id="b091e-176">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-177">`--ignore-columns | -I` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-177">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="b091e-178">Con questo argomento è possibile ignorare le colonne esistenti nel file del set di dati in modo che non vengano caricate e usate dai processi di training.</span><span class="sxs-lookup"><span data-stu-id="b091e-178">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="b091e-179">Specificare i nomi delle colonne da ignorare.</span><span class="sxs-lookup"><span data-stu-id="b091e-179">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="b091e-180">Usare ', ' (virgola seguita da uno spazio) oppure ' ' (spazio) per separare più nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="b091e-180">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="b091e-181">È possibile usare le virgolette per nomi di colonna che contengono uno spazio vuoto (ad esempio, "accesso eseguito").</span><span class="sxs-lookup"><span data-stu-id="b091e-181">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="b091e-182">Esempio:</span><span class="sxs-lookup"><span data-stu-id="b091e-182">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

<span data-ttu-id="b091e-183">`--has-header | -h` (bool)</span><span class="sxs-lookup"><span data-stu-id="b091e-183">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="b091e-184">Specificare se i file di set di dati includono una riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="b091e-184">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="b091e-185">I possibili valori sono:</span><span class="sxs-lookup"><span data-stu-id="b091e-185">Possible values are:</span></span>
- `true`
- `false`

<span data-ttu-id="b091e-186">Il valore predefinito è `true` se questo argomento non viene specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b091e-186">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="b091e-187">Per usare l'argomento `--label-column-name` è necessario che il file del set di dati includa un'intestazione e che `--has-header` sia impostato su `true` (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="b091e-187">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-188">`--max-exploration-time | -x` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-188">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="b091e-189">Per impostazione predefinita, il tempo massimo di esplorazione è 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="b091e-189">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="b091e-190">Questo argomento imposta il tempo massimo (in secondi) per il processo per l'esplorazione di più trainer e configurazioni.</span><span class="sxs-lookup"><span data-stu-id="b091e-190">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="b091e-191">Il tempo configurato può essere superato se il tempo specificato è troppo breve (ad esempio, 2 secondi) per una singola iterazione.</span><span class="sxs-lookup"><span data-stu-id="b091e-191">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="b091e-192">In questo caso, il tempo effettivo corrisponde al tempo necessario per produrre una configurazione di modello in una singola iterazione.</span><span class="sxs-lookup"><span data-stu-id="b091e-192">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="b091e-193">Il tempo necessario per le iterazioni può variare a seconda delle dimensioni del set di dati.</span><span class="sxs-lookup"><span data-stu-id="b091e-193">The needed time for iterations can vary depending on the size of the dataset.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-194">`--cache | -c` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="b091e-195">Se si usa la memorizzazione nella cache, verrà caricato in memoria l'intero training set.</span><span class="sxs-lookup"><span data-stu-id="b091e-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="b091e-196">Per set di dati di piccole e medie dimensioni, l'uso della cache può migliorare nettamente le prestazioni di training riducendo il tempo di training rispetto a quando non si usa la cache.</span><span class="sxs-lookup"><span data-stu-id="b091e-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="b091e-197">Tuttavia, per i set di dati di grandi dimensioni, il caricamento di tutti i dati in memoria può influire negativamente ed esaurire la memoria.</span><span class="sxs-lookup"><span data-stu-id="b091e-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="b091e-198">Quando viene eseguito il training con file di set di dati di grandi dimensioni senza usare la cache, ML.NET esegue lo streaming di blocchi di dati dell'unità quando è necessario caricare più dati durante il training.</span><span class="sxs-lookup"><span data-stu-id="b091e-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="b091e-199">È possibile specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b091e-199">You can specify the following values:</span></span>

<span data-ttu-id="b091e-200">`on`: impone l'uso della cache durante il training.</span><span class="sxs-lookup"><span data-stu-id="b091e-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="b091e-201">`off`: impedisce l'uso della cache durante il training.</span><span class="sxs-lookup"><span data-stu-id="b091e-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="b091e-202">`auto`: l'uso della cache è determinato dalle regole euristiche della funzionalità di Machine Learning automatico.</span><span class="sxs-lookup"><span data-stu-id="b091e-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="b091e-203">In genere i set di dati di piccole e medie dimensioni usano la cache, mentre i set di dati di grandi dimensioni non usano la cache se viene usata l'opzione `auto`.</span><span class="sxs-lookup"><span data-stu-id="b091e-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="b091e-204">Se non si specifica il parametro `--cache`, viene usata la configurazione `auto` della cache per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b091e-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-205">`--name | -N` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-205">`--name | -N` (string)</span></span>

<span data-ttu-id="b091e-206">Nome del progetto di output o della soluzione creata.</span><span class="sxs-lookup"><span data-stu-id="b091e-206">The name for the created output project or solution.</span></span> <span data-ttu-id="b091e-207">Se viene specificato alcun nome, viene usato il nome `sample-{mltask}`.</span><span class="sxs-lookup"><span data-stu-id="b091e-207">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="b091e-208">Verrà assegnato lo stesso nome anche al file di modello di ML.NET (file con estensione zip).</span><span class="sxs-lookup"><span data-stu-id="b091e-208">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-209">`--output-path | -o` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-209">`--output-path | -o` (string)</span></span>

<span data-ttu-id="b091e-210">Percorso o cartella radice in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="b091e-210">Root location/folder to place the generated output.</span></span> <span data-ttu-id="b091e-211">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b091e-211">The default is the current directory.</span></span>

----------------------------------------------------------

<span data-ttu-id="b091e-212">`--verbosity | -V` (string)</span><span class="sxs-lookup"><span data-stu-id="b091e-212">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="b091e-213">Imposta il livello di dettaglio dell'output standard.</span><span class="sxs-lookup"><span data-stu-id="b091e-213">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="b091e-214">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="b091e-214">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="b091e-215">`m[inimal]`  (per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="b091e-215">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="b091e-216">`diag[nostic]` (livello informazioni di registrazione)</span><span class="sxs-lookup"><span data-stu-id="b091e-216">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="b091e-217">Per impostazione predefinita, lo strumento dell'interfaccia della riga di comando dovrebbe visualizzare un feedback minimo, ad esempio indicare che è attivo e se possibile il tempo rimanente o la percentuale di tempo trascorso.</span><span class="sxs-lookup"><span data-stu-id="b091e-217">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

----------------------------------------------------------

`-h|--help`

<span data-ttu-id="b091e-218">Visualizza le informazioni della Guida per il comando con una descrizione per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="b091e-218">Prints out help for the command with a description for each command's parameter.</span></span>

----------------------------------------------------------

## <a name="see-also"></a><span data-ttu-id="b091e-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b091e-219">See also</span></span>

- [<span data-ttu-id="b091e-220">Come installare lo strumento dell'interfaccia della riga comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="b091e-220">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="b091e-221">Automatizzare il training del modello con l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="b091e-221">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="b091e-222">Esercitazione: Generare automaticamente un classificatore binario con l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="b091e-222">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="b091e-223">Telemetria nell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="b091e-223">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
