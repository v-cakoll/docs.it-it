---
title: Riferimento al comando CLI ML.NET
description: Panoramica, esempi e riferimento per il comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET.
ms.date: 12/18/2019
ms.openlocfilehash: 537f8d361c170378f5fe8cf454320831d7c8cbf2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449699"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="d809f-103">Riferimento ai comandi dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="d809f-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="d809f-104">Il comando `auto-train` è il comando principale dello strumento dell'interfaccia della riga di comando di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d809f-104">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="d809f-105">Il comando consente di generare un modello ML.NET di qualità elevata usando automazione Machine Learning (AutoML), nonché il codice di C# esempio per eseguire/assegnare un punteggio a tale modello.</span><span class="sxs-lookup"><span data-stu-id="d809f-105">The command allows you to generate a good quality ML.NET model using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="d809f-106">Inoltre, il C# codice per eseguire il training del modello viene generato per la ricerca dell'algoritmo e delle impostazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="d809f-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="d809f-107">Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="d809f-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="d809f-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d809f-108">Overview</span></span>

<span data-ttu-id="d809f-109">Sintassi di esempio:</span><span class="sxs-lookup"><span data-stu-id="d809f-109">Example usage:</span></span>

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="d809f-110">Il comando `mlnet auto-train` genera gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="d809f-110">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="d809f-111">Un file di modello serializzato con estensione zip ("miglior modello") pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="d809f-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="d809f-112">C#codice per l'esecuzione o il punteggio del modello generato.</span><span class="sxs-lookup"><span data-stu-id="d809f-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="d809f-113">C#codice con il codice di training utilizzato per generare il modello.</span><span class="sxs-lookup"><span data-stu-id="d809f-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="d809f-114">Le prime due risorse possono essere usate direttamente nelle app per gli utenti finali (ASP.NET Core app Web, servizi, app desktop e altro ancora) per eseguire stime con il modello.</span><span class="sxs-lookup"><span data-stu-id="d809f-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="d809f-115">Il terzo asset, il codice di training, Mostra il codice API ML.NET usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo da poter esaminare l'algoritmo e le impostazioni specifiche del modello.</span><span class="sxs-lookup"><span data-stu-id="d809f-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="d809f-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="d809f-116">Examples</span></span>

<span data-ttu-id="d809f-117">Il comando CLI più semplice per un problema di classificazione binaria (AutoML deduce la maggior parte della configurazione dai dati forniti):</span><span class="sxs-lookup"><span data-stu-id="d809f-117">The simplest CLI command for a binary classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="d809f-118">Un altro comando dell'interfaccia della riga semplice per un problema di regressione:</span><span class="sxs-lookup"><span data-stu-id="d809f-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="d809f-119">Creare ed eseguire il training di un modello di classificazione binaria con un set di dati con training, un set di dati di test e ulteriori argomenti espliciti di personalizzazione:</span><span class="sxs-lookup"><span data-stu-id="d809f-119">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a><span data-ttu-id="d809f-120">Opzioni del comando</span><span class="sxs-lookup"><span data-stu-id="d809f-120">Command options</span></span>

<span data-ttu-id="d809f-121">`mlnet auto-train` esegue il training di più modelli in base al set di dati fornito e infine seleziona il modello migliore, lo salva come file con estensione zip C# serializzato più genera il codice correlato per il punteggio e il training.</span><span class="sxs-lookup"><span data-stu-id="d809f-121">`mlnet auto-train` trains multiple models based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

```console
mlnet auto-train

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

<span data-ttu-id="d809f-122">Opzioni di input non valide. lo strumento dell'interfaccia della riga di comando crea un elenco di input validi e un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d809f-122">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="task"></a><span data-ttu-id="d809f-123">Attività</span><span class="sxs-lookup"><span data-stu-id="d809f-123">Task</span></span>

<span data-ttu-id="d809f-124">`--task | --mltask | -T` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-124">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="d809f-125">Stringa singola che specifica il problema di Machine Learning da risolvere.</span><span class="sxs-lookup"><span data-stu-id="d809f-125">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="d809f-126">Ad esempio, una delle attività seguenti (l'interfaccia della riga di comando supporterà tutte le attività supportate nella funzionalità di Machine Learning automatico):</span><span class="sxs-lookup"><span data-stu-id="d809f-126">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="d809f-127">`regression` - Scegliere se verrà usato il modello di Machine Learning per effettuare la previsione di un valore numerico</span><span class="sxs-lookup"><span data-stu-id="d809f-127">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="d809f-128">`binary-classification` - Scegliere se il risultato del modello di Machine Learning ha due valori booleani categorici possibili (0 o 1).</span><span class="sxs-lookup"><span data-stu-id="d809f-128">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="d809f-129">`multiclass-classification` - Scegliere se il risultato del modello di Machine Learning ha più valori categorici possibili.</span><span class="sxs-lookup"><span data-stu-id="d809f-129">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="d809f-130">In questo argomento è necessario specificare una sola attività di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="d809f-130">Only one ML task should be provided in this argument.</span></span>

## <a name="dataset"></a><span data-ttu-id="d809f-131">Set di dati</span><span class="sxs-lookup"><span data-stu-id="d809f-131">Dataset</span></span>

<span data-ttu-id="d809f-132">`--dataset | -d` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-132">`--dataset | -d` (string)</span></span>

<span data-ttu-id="d809f-133">Questo argomento specifica il percorso file di una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d809f-133">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="d809f-134">*R: l'intero file del set di dati:* Se si usa questa opzione e l'utente non fornisce `--test-dataset` e `--validation-dataset`, la convalida incrociata (k-fold e così via) o gli approcci di suddivisione automatica dei dati verranno usati internamente per la convalida del modello.</span><span class="sxs-lookup"><span data-stu-id="d809f-134">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="d809f-135">In questo caso l'utente dovrà specificare soltanto il percorso file del set di dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-135">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="d809f-136">*B: file del set di dati di training:* Se l'utente fornisce anche set di dati per la convalida del modello (usando `--test-dataset` e, facoltativamente, `--validation-dataset`), l'argomento `--dataset` significa solo il "set di dati di training".</span><span class="sxs-lookup"><span data-stu-id="d809f-136">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="d809f-137">Ad esempio, quando viene usato un approccio 80% - 20% per convalidare la qualità del modello e ottenere le metriche di accuratezza, il "training set" avrà l'80% dei dati, mentre il "set di dati di test" avrà il 20% dei dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-137">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="d809f-138">Set di dati di test</span><span class="sxs-lookup"><span data-stu-id="d809f-138">Test dataset</span></span>

<span data-ttu-id="d809f-139">`--test-dataset | -t` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-139">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="d809f-140">Percorso del file del set di dati di test, ad esempio quando viene usato un approccio 80% - 20% durante le convalide regolari per ottenere le metriche di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="d809f-140">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="d809f-141">Se viene usato `--test-dataset`, è necessario specificare anche `--dataset`.</span><span class="sxs-lookup"><span data-stu-id="d809f-141">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="d809f-142">L'argomento `--test-dataset` è facoltativo, a meno che non venga usato --validation-dataset.</span><span class="sxs-lookup"><span data-stu-id="d809f-142">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="d809f-143">In questo caso, l'utente deve usare i tre argomenti.</span><span class="sxs-lookup"><span data-stu-id="d809f-143">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="d809f-144">Set di dati di convalida</span><span class="sxs-lookup"><span data-stu-id="d809f-144">Validation dataset</span></span>

<span data-ttu-id="d809f-145">`--validation-dataset | -v` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-145">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="d809f-146">Percorso del file del set di dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="d809f-146">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="d809f-147">In tutti i casi il set di dati di convalida è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d809f-147">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="d809f-148">Se si usa `validation dataset`, il comportamento deve essere il seguente:</span><span class="sxs-lookup"><span data-stu-id="d809f-148">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="d809f-149">Anche gli argomenti `test-dataset` e `--dataset` sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="d809f-149">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="d809f-150">Il set di dati `validation-dataset` viene usato per stimare l'errore di previsione per la selezione del modello.</span><span class="sxs-lookup"><span data-stu-id="d809f-150">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="d809f-151">Il set di dati `test-dataset` viene usato per la valutazione dell'errore di generalizzazione del modello selezionato finale.</span><span class="sxs-lookup"><span data-stu-id="d809f-151">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="d809f-152">In teoria, il set di test deve essere conservato in un "vault" e usato solo alla fine dell'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-152">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="d809f-153">In pratica, quando vengono usati `validation dataset` e `test dataset`, la fase di convalida è suddivisa in due parti:</span><span class="sxs-lookup"><span data-stu-id="d809f-153">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="d809f-154">Si esaminano innanzitutto i modelli e si seleziona l'approccio migliore usando i dati di convalida (=validation)</span><span class="sxs-lookup"><span data-stu-id="d809f-154">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="d809f-155">Quindi si valuta l'accuratezza dell'approccio selezionato (=test).</span><span class="sxs-lookup"><span data-stu-id="d809f-155">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="d809f-156">Di conseguenza, la suddivisione dei dati potrebbe essere 80/10/10 o 75/15/10.</span><span class="sxs-lookup"><span data-stu-id="d809f-156">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="d809f-157">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="d809f-157">For example:</span></span>

- <span data-ttu-id="d809f-158">Il file di `training-dataset` deve avere il 75% dei dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-158">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="d809f-159">Il file di `validation-dataset` deve avere il 15% dei dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-159">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="d809f-160">Il file di `test-dataset` deve avere il 10% dei dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-160">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="d809f-161">In ogni caso, queste percentuali verranno decise dall'utente tramite l'interfaccia della riga di comando che fornirà i file già suddivisi.</span><span class="sxs-lookup"><span data-stu-id="d809f-161">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column-name"></a><span data-ttu-id="d809f-162">Nome colonna etichetta</span><span class="sxs-lookup"><span data-stu-id="d809f-162">Label column name</span></span>

<span data-ttu-id="d809f-163">`--label-column-name | -n` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-163">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="d809f-164">Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando il nome della colonna impostato nell'intestazione del set di dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-164">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="d809f-165">Questo argomento viene usato solo per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*.</span><span class="sxs-lookup"><span data-stu-id="d809f-165">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="d809f-166">Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.</span><span class="sxs-lookup"><span data-stu-id="d809f-166">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="label-column-index"></a><span data-ttu-id="d809f-167">Indice colonna etichetta</span><span class="sxs-lookup"><span data-stu-id="d809f-167">Label column index</span></span>

<span data-ttu-id="d809f-168">`--label-column-index | -i` (int)</span><span class="sxs-lookup"><span data-stu-id="d809f-168">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="d809f-169">Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando l'indice numerico della colonna nel file del set di dati (i valori di indice della colonna iniziano da 1).</span><span class="sxs-lookup"><span data-stu-id="d809f-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="d809f-170">*Nota:* Se l'utente usa anche il `--label-column-name`, il `--label-column-name` è quello usato.</span><span class="sxs-lookup"><span data-stu-id="d809f-170">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="d809f-171">Questo argomento viene usato per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*.</span><span class="sxs-lookup"><span data-stu-id="d809f-171">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="d809f-172">Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.</span><span class="sxs-lookup"><span data-stu-id="d809f-172">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="d809f-173">Ignora colonne</span><span class="sxs-lookup"><span data-stu-id="d809f-173">Ignore columns</span></span>

<span data-ttu-id="d809f-174">`--ignore-columns | -I` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-174">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="d809f-175">Con questo argomento è possibile ignorare le colonne esistenti nel file del set di dati in modo che non vengano caricate e usate dai processi di training.</span><span class="sxs-lookup"><span data-stu-id="d809f-175">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="d809f-176">Specificare i nomi delle colonne da ignorare.</span><span class="sxs-lookup"><span data-stu-id="d809f-176">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="d809f-177">Usare ', ' (virgola seguita da uno spazio) oppure ' ' (spazio) per separare più nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="d809f-177">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="d809f-178">È possibile usare le virgolette per nomi di colonna che contengono uno spazio vuoto (ad esempio, "accesso eseguito").</span><span class="sxs-lookup"><span data-stu-id="d809f-178">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="d809f-179">Esempio:</span><span class="sxs-lookup"><span data-stu-id="d809f-179">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="d809f-180">Con intestazione</span><span class="sxs-lookup"><span data-stu-id="d809f-180">Has header</span></span>

<span data-ttu-id="d809f-181">`--has-header | -h` (bool)</span><span class="sxs-lookup"><span data-stu-id="d809f-181">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="d809f-182">Specificare se i file di set di dati includono una riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="d809f-182">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="d809f-183">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="d809f-183">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="d809f-184">Il valore predefinito è `true` se questo argomento non viene specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d809f-184">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="d809f-185">Per usare l'argomento `--label-column-name` è necessario che il file del set di dati includa un'intestazione e che `--has-header` sia impostato su `true` (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="d809f-185">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

## <a name="max-exploration-time"></a><span data-ttu-id="d809f-186">Tempo massimo di esplorazione</span><span class="sxs-lookup"><span data-stu-id="d809f-186">Max exploration time</span></span>

<span data-ttu-id="d809f-187">`--max-exploration-time | -x` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-187">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="d809f-188">Per impostazione predefinita, il tempo massimo di esplorazione è 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="d809f-188">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="d809f-189">Questo argomento imposta il tempo massimo (in secondi) per il processo per l'esplorazione di più trainer e configurazioni.</span><span class="sxs-lookup"><span data-stu-id="d809f-189">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="d809f-190">Il tempo configurato può essere superato se il tempo specificato è troppo breve (ad esempio, 2 secondi) per una singola iterazione.</span><span class="sxs-lookup"><span data-stu-id="d809f-190">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="d809f-191">In questo caso, il tempo effettivo corrisponde al tempo necessario per produrre una configurazione di modello in una singola iterazione.</span><span class="sxs-lookup"><span data-stu-id="d809f-191">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="d809f-192">Il tempo necessario per le iterazioni può variare a seconda delle dimensioni del set di dati.</span><span class="sxs-lookup"><span data-stu-id="d809f-192">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="d809f-193">Cache</span><span class="sxs-lookup"><span data-stu-id="d809f-193">Cache</span></span>

<span data-ttu-id="d809f-194">`--cache | -c` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="d809f-195">Se si usa la memorizzazione nella cache, verrà caricato in memoria l'intero training set.</span><span class="sxs-lookup"><span data-stu-id="d809f-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="d809f-196">Per set di dati di piccole e medie dimensioni, l'uso della cache può migliorare nettamente le prestazioni di training riducendo il tempo di training rispetto a quando non si usa la cache.</span><span class="sxs-lookup"><span data-stu-id="d809f-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="d809f-197">Tuttavia, per i set di dati di grandi dimensioni, il caricamento di tutti i dati in memoria può influire negativamente ed esaurire la memoria.</span><span class="sxs-lookup"><span data-stu-id="d809f-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="d809f-198">Quando viene eseguito il training con file di set di dati di grandi dimensioni senza usare la cache, ML.NET esegue lo streaming di blocchi di dati dell'unità quando è necessario caricare più dati durante il training.</span><span class="sxs-lookup"><span data-stu-id="d809f-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="d809f-199">È possibile specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="d809f-199">You can specify the following values:</span></span>

<span data-ttu-id="d809f-200">`on`: forza la cache da usare durante il training.</span><span class="sxs-lookup"><span data-stu-id="d809f-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="d809f-201">`off`: forza la cache a non essere utilizzata durante il training.</span><span class="sxs-lookup"><span data-stu-id="d809f-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="d809f-202">`auto`: a seconda dell'euristica AutoML, la cache verrà utilizzata o meno.</span><span class="sxs-lookup"><span data-stu-id="d809f-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="d809f-203">In genere i set di dati di piccole e medie dimensioni usano la cache, mentre i set di dati di grandi dimensioni non usano la cache se viene usata l'opzione `auto`.</span><span class="sxs-lookup"><span data-stu-id="d809f-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="d809f-204">Se non si specifica il parametro `--cache`, viene usata la configurazione `auto` della cache per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d809f-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="d809f-205">Name</span><span class="sxs-lookup"><span data-stu-id="d809f-205">Name</span></span>

<span data-ttu-id="d809f-206">`--name | -N` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-206">`--name | -N` (string)</span></span>

<span data-ttu-id="d809f-207">Nome del progetto di output o della soluzione creata.</span><span class="sxs-lookup"><span data-stu-id="d809f-207">The name for the created output project or solution.</span></span> <span data-ttu-id="d809f-208">Se viene specificato alcun nome, viene usato il nome `sample-{mltask}`.</span><span class="sxs-lookup"><span data-stu-id="d809f-208">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="d809f-209">Verrà assegnato lo stesso nome anche al file di modello di ML.NET (file con estensione zip).</span><span class="sxs-lookup"><span data-stu-id="d809f-209">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="d809f-210">Percorso output</span><span class="sxs-lookup"><span data-stu-id="d809f-210">Output path</span></span>

<span data-ttu-id="d809f-211">`--output-path | -o` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-211">`--output-path | -o` (string)</span></span>

<span data-ttu-id="d809f-212">Percorso o cartella radice in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="d809f-212">Root location/folder to place the generated output.</span></span> <span data-ttu-id="d809f-213">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d809f-213">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="d809f-214">Livello di dettaglio</span><span class="sxs-lookup"><span data-stu-id="d809f-214">Verbosity</span></span>

<span data-ttu-id="d809f-215">`--verbosity | -V` (string)</span><span class="sxs-lookup"><span data-stu-id="d809f-215">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="d809f-216">Imposta il livello di dettaglio dell'output standard.</span><span class="sxs-lookup"><span data-stu-id="d809f-216">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="d809f-217">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="d809f-217">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="d809f-218">`m[inimal]`  (per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="d809f-218">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="d809f-219">`diag[nostic]` (livello informazioni di registrazione)</span><span class="sxs-lookup"><span data-stu-id="d809f-219">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="d809f-220">Per impostazione predefinita, lo strumento dell'interfaccia della riga di comando dovrebbe visualizzare un feedback minimo, ad esempio indicare che è attivo e se possibile il tempo rimanente o la percentuale di tempo trascorso.</span><span class="sxs-lookup"><span data-stu-id="d809f-220">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="d809f-221">?</span><span class="sxs-lookup"><span data-stu-id="d809f-221">Help</span></span>

`-h|--help`

<span data-ttu-id="d809f-222">Visualizza le informazioni della Guida per il comando con una descrizione per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="d809f-222">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="d809f-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d809f-223">See also</span></span>

- [<span data-ttu-id="d809f-224">Come installare lo strumento dell'interfaccia della riga comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="d809f-224">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="d809f-225">Panoramica dell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="d809f-225">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="d809f-226">Esercitazione: analizzare i sentimenti usando l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="d809f-226">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="d809f-227">Telemetria nell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="d809f-227">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
