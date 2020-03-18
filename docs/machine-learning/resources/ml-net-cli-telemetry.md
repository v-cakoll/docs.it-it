---
title: Raccolta di dati di telemetria dall'interfaccia della riga di comando di ML.NET
description: Informazioni sulle funzionalità di telemetria dell'interfaccia della riga di comando di ML.NET che raccolgono dati di utilizzo per l'analisi, su come disabilitare le funzionalità e sui dati raccolti. Sono inoltre disponibili collegamenti al contratto di licenza di .NET e informazioni sulla conformità a GDPR di Microsoft.
ms.topic: conceptual
ms.date: 09/03/2019
ms.custom: mlnet-tooling
ms.openlocfilehash: 99e11acba343cc689c3219ca9316144fc62cd618
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78849744"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="e5b1d-104">Raccolta di dati di telemetria dall'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="e5b1d-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="e5b1d-105">L'[interfaccia della riga di comando di ML.NET](https://aka.ms/mlnet-cli) include una funzionalità di telemetria che raccoglie dati di utilizzo anonimi che vengono aggregati per l'uso da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-105">The [ML.NET CLI](https://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="e5b1d-106">Come Microsoft usa i dati</span><span class="sxs-lookup"><span data-stu-id="e5b1d-106">How Microsoft uses the data</span></span>

<span data-ttu-id="e5b1d-107">Il team di prodotto usa i dati di telemetria dell'interfaccia della riga di comando di ML.NET per capire come migliorare gli strumenti che propone.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="e5b1d-108">Se i clienti utilizzano raramente una particolare attività di Machine Learning, ad esempio, il team di prodotto indaga sul motivo e usa i risultati per stabilire le priorità delle funzionalità da sviluppare in futuro.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="e5b1d-109">I dati di telemetria dell'interfaccia della riga di comando di ML.NET sono utili anche per il debug dei problemi, ad esempio gli arresti anomali del sistema e le anomalie di codice.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span>

<span data-ttu-id="e5b1d-110">Nonostante il team di prodotto gradisca disporre di questo tipo di informazioni, Microsoft è consapevole che non tutti gli utenti sono disposti a inviare i dati.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="e5b1d-111">Informazioni su come disabilitare i dati di telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="e5b1d-112">Scope</span><span class="sxs-lookup"><span data-stu-id="e5b1d-112">Scope</span></span>

<span data-ttu-id="e5b1d-113">Il comando `mlnet` avvia l'interfaccia della riga di comando di ML.NET, ma non raccoglie i dati di telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="e5b1d-114">La funzionalità di telemetria *non è abilitata* quando si esegue il comando `mlnet` con nessun altro comando collegato.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="e5b1d-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5b1d-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="e5b1d-116">La funzionalità di telemetria *è abilitata* quando si esegue un [comando dell'interfaccia della riga di comando di ML.NET](../reference/ml-net-cli-reference.md), ad esempio `mlnet auto-train`.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet auto-train`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="e5b1d-117">Rifiutare esplicitamente la raccolta dei dati</span><span class="sxs-lookup"><span data-stu-id="e5b1d-117">Opt out of data collection</span></span>

<span data-ttu-id="e5b1d-118">La funzionalità di telemetria dell'interfaccia della riga di comando di ML.NET è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="e5b1d-119">Rifiutare esplicitamente la funzionalità di telemetria impostando la variabile di ambiente `MLDOTNET_CLI_TELEMETRY_OPTOUT` su `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-119">Opt out of the telemetry feature by setting the `MLDOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="e5b1d-120">Questa variabile di ambiente si applica a livello globale allo strumento ML.NET'interfaccia di comando.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-120">This environment variable applies globally to the ML.NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="e5b1d-121">Punti dati raccolti</span><span class="sxs-lookup"><span data-stu-id="e5b1d-121">Data points collected</span></span>

<span data-ttu-id="e5b1d-122">La funzionalità raccoglie i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5b1d-122">The feature collects the following data:</span></span>

- <span data-ttu-id="e5b1d-123">Il comando che è stato richiamato, ad esempio `auto-train`</span><span class="sxs-lookup"><span data-stu-id="e5b1d-123">What command was invoked, such as `auto-train`</span></span>
- <span data-ttu-id="e5b1d-124">Nomi di parametro della riga di comando utilizzati (ovvero, "dataset-name, label-column-name, ml-task, output-path, max-exploration-time, verbosity")</span><span class="sxs-lookup"><span data-stu-id="e5b1d-124">Command-line parameter names used (that is, "dataset-name, label-column-name, ml-task, output-path, max-exploration-time, verbosity")</span></span>
- <span data-ttu-id="e5b1d-125">Indirizzo MAC con hash: ID univoco e anonimo dal punto di vista crittografico (SHA256) per un computer</span><span class="sxs-lookup"><span data-stu-id="e5b1d-125">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="e5b1d-126">Il timestamp di una chiamata</span><span class="sxs-lookup"><span data-stu-id="e5b1d-126">Timestamp of an invocation</span></span>
- <span data-ttu-id="e5b1d-127">Indirizzo IP a tre ottetti (non l'indirizzo IP completo) usato solo per determinare la posizione geografica</span><span class="sxs-lookup"><span data-stu-id="e5b1d-127">Three octet IP address (not full IP address) used only to determine geographical location</span></span>
- <span data-ttu-id="e5b1d-128">Nome di tutti gli argomenti e dei parametri usati.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-128">Name of all arguments/parameters used.</span></span> <span data-ttu-id="e5b1d-129">Non i valori del cliente, ad esempio le stringhe</span><span class="sxs-lookup"><span data-stu-id="e5b1d-129">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="e5b1d-130">Nome di file del set di dati con hash</span><span class="sxs-lookup"><span data-stu-id="e5b1d-130">Hashed dataset filename</span></span>
- <span data-ttu-id="e5b1d-131">Bucket delle dimensioni di file del set di dati</span><span class="sxs-lookup"><span data-stu-id="e5b1d-131">Dataset file-size bucket</span></span>
- <span data-ttu-id="e5b1d-132">Sistema operativo e versione</span><span class="sxs-lookup"><span data-stu-id="e5b1d-132">Operating system and version</span></span>
- <span data-ttu-id="e5b1d-133">Valore del parametro --task: valori categorici, ad `regression`esempio , `binary-classification`, e`multiclass-classification`</span><span class="sxs-lookup"><span data-stu-id="e5b1d-133">Value of --task parameter: Categorical values, such as `regression`, `binary-classification`, and `multiclass-classification`</span></span>
- <span data-ttu-id="e5b1d-134">ML.NET versione CLI (ovvero 0.3.27703.4)</span><span class="sxs-lookup"><span data-stu-id="e5b1d-134">ML.NET CLI version (that is, 0.3.27703.4)</span></span>

<span data-ttu-id="e5b1d-135">I dati vengono inviati ai server Microsoft in modalità protetta grazie alla tecnologia [Azure Application Insights](https://azure.microsoft.com/services/application-insights/), conservati con accesso limitato e usati in base a severi controlli di sicurezza da parte di sistemi di [archiviazione di Azure](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="e5b1d-135">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="e5b1d-136">Punti dati non raccolti</span><span class="sxs-lookup"><span data-stu-id="e5b1d-136">Data points not collected</span></span>

<span data-ttu-id="e5b1d-137">La funzionalità di telemetria *non* raccoglie:</span><span class="sxs-lookup"><span data-stu-id="e5b1d-137">The telemetry feature *doesn't* collect:</span></span>

- <span data-ttu-id="e5b1d-138">dati personali, ad esempio i nomi utente</span><span class="sxs-lookup"><span data-stu-id="e5b1d-138">personal data, such as usernames</span></span>
- <span data-ttu-id="e5b1d-139">nomi dei set di dati</span><span class="sxs-lookup"><span data-stu-id="e5b1d-139">dataset filenames</span></span>
- <span data-ttu-id="e5b1d-140">dati dei set di dati</span><span class="sxs-lookup"><span data-stu-id="e5b1d-140">data from dataset files</span></span>

<span data-ttu-id="e5b1d-141">Se si sospetta che la funzionalità di telemetria dell'interfaccia della riga di comando di ML.NET raccolga dati sensibili o che i dati raccolti siano gestiti in modo inappropriato o non sicuro, segnalare un problema nel repository di [ML.NET](https://github.com/dotnet/machinelearning).</span><span class="sxs-lookup"><span data-stu-id="e5b1d-141">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="e5b1d-142">Licenza</span><span class="sxs-lookup"><span data-stu-id="e5b1d-142">License</span></span>

<span data-ttu-id="e5b1d-143">La distribuzione Microsoft dell'interfaccia della riga di comando di ML.NET è concessa in licenza con le Condizioni di [licenza software Microsoft: Libreria Microsoft .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="e5b1d-143">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="e5b1d-144">Per informazioni dettagliate sulla raccolta e l'elaborazione dei dati, vedere la sezione intitolata "DATA".</span><span class="sxs-lookup"><span data-stu-id="e5b1d-144">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="e5b1d-145">Divulgazione</span><span class="sxs-lookup"><span data-stu-id="e5b1d-145">Disclosure</span></span>

<span data-ttu-id="e5b1d-146">Quando si esegue un [comando dell'interfaccia della riga di comando di ML.NET](../reference/ml-net-cli-reference.md) per la prima volta, ad esempio `mlnet auto-train`, lo strumento dell'interfaccia della riga di comando di ML.NET visualizza un avviso sulla divulgazione di informazioni che spiega come rifiutare esplicitamente la funzionalità di telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-146">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet auto-train`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="e5b1d-147">Il testo potrebbe variare lievemente in funzione della versione dell'interfaccia della riga di comando in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5b1d-147">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5b1d-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5b1d-148">See also</span></span>

- [<span data-ttu-id="e5b1d-149">Riferimento interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="e5b1d-149">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="e5b1d-150">Condizioni di licenza software Microsoft: Libreria Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="e5b1d-150">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- <span data-ttu-id="e5b1d-151">[Privacy at Microsoft](https://www.microsoft.com/trustcenter/privacy/) (La privacy in Microsoft)</span><span class="sxs-lookup"><span data-stu-id="e5b1d-151">[Privacy at Microsoft](https://www.microsoft.com/trustcenter/privacy/)</span></span>
- [<span data-ttu-id="e5b1d-152">Informativa sulla privacy Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5b1d-152">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
