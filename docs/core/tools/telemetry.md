---
title: Telemetria di .NET Core SDK
description: Informazioni sulle funzionalità di telemetria degli strumenti di .NET Core SDK che raccolgono informazioni sull'utilizzo per l'analisi, i dati raccolti e il modo in cui disabilitarli.
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 82410863c81faa95edfb120c95ec6bc186ed1328
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751684"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="2ef72-103">Telemetria di .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="2ef72-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="2ef72-104">[.NET Core SDK](index.md) include una [funzionalità di telemetria](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) che raccoglie le informazioni sull'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="2ef72-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) that collects usage information.</span></span> <span data-ttu-id="2ef72-105">È importante che il team di .NET comprenda come vengono usati gli strumenti per consentire a Microsoft di migliorarne le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2ef72-105">It's important that the .NET Team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="2ef72-106">Per ulteriori informazioni, vedere [Nozioni apprese da .NET Core SDK, telemetria](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="2ef72-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="2ef72-107">I dati raccolti sono anonimi e sono pubblicati in forma aggregata per l'uso da parte di Microsoft e della community in base alla [licenza Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="2ef72-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="2ef72-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="2ef72-108">Scope</span></span>

<span data-ttu-id="2ef72-109">Il comando `dotnet` viene usato per avviare sia le applicazioni sia l’interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2ef72-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="2ef72-110">La raccolta dei dati di telemetria non viene eseguita dal comando `dotnet` stesso.</span><span class="sxs-lookup"><span data-stu-id="2ef72-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="2ef72-111">I comandi dell’interfaccia della riga di comando .NET Core eseguiti dal comando `dotnet` raccolgono la telemetria.</span><span class="sxs-lookup"><span data-stu-id="2ef72-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="2ef72-112">La telemetria *non è abilitata* quando si utilizza il comando `dotnet` stesso, con nessun comando collegato:</span><span class="sxs-lookup"><span data-stu-id="2ef72-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="2ef72-113">La telemetria *è abilitata* quando si utilizzano i comandi dell’interfaccia della riga di comando . NET Core[, ](index.md)ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2ef72-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="2ef72-114">Come rifiutare esplicitamente</span><span class="sxs-lookup"><span data-stu-id="2ef72-114">How to opt out</span></span>

<span data-ttu-id="2ef72-115">La funzionalità di telemetria di .NET Core SDK è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2ef72-115">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="2ef72-116">Rifiutare esplicitamente la funzionalità di telemetria impostando la variabile di ambiente `DOTNET_CLI_TELEMETRY_OPTOUT` su `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="2ef72-116">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="2ef72-117">Punti dati</span><span class="sxs-lookup"><span data-stu-id="2ef72-117">Data points</span></span>

<span data-ttu-id="2ef72-118">La funzionalità raccoglie i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ef72-118">The feature collects the following data:</span></span>

- <span data-ttu-id="2ef72-119">Il timestamp della chiamata&#8224;</span><span class="sxs-lookup"><span data-stu-id="2ef72-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="2ef72-120">Comando richiamato (ad esempio, "build")&#8224;</span><span class="sxs-lookup"><span data-stu-id="2ef72-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="2ef72-121">Indirizzo IP di tre ottetti usato per determinare la posizione geografica&#8224;</span><span class="sxs-lookup"><span data-stu-id="2ef72-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="2ef72-122">`ExitCode` del comando</span><span class="sxs-lookup"><span data-stu-id="2ef72-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="2ef72-123">Test Runner usato (per i progetti di test)</span><span class="sxs-lookup"><span data-stu-id="2ef72-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="2ef72-124">Sistema operativo e relativa versione&#8224;</span><span class="sxs-lookup"><span data-stu-id="2ef72-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="2ef72-125">L'eventuale presenza di ID di runtime nel nodo runtimes</span><span class="sxs-lookup"><span data-stu-id="2ef72-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="2ef72-126">.NET core SDK versione&#8224;</span><span class="sxs-lookup"><span data-stu-id="2ef72-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="2ef72-127">&#8224;Questa metrica è pubblicata.</span><span class="sxs-lookup"><span data-stu-id="2ef72-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="2ef72-128">A partire da .NET Core 2.0 SDK, sono raccolti nuovi punti dati:</span><span class="sxs-lookup"><span data-stu-id="2ef72-128">Starting with .NET Core 2.0 SDK, new data points are collected:</span></span>

- <span data-ttu-id="2ef72-129">`dotnet`argomenti e opzioni di comando: sono raccolti solo gli argomenti e le opzioni noti (non stringhe arbitrarie).</span><span class="sxs-lookup"><span data-stu-id="2ef72-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="2ef72-130">Se il SDK è in esecuzione in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ef72-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="2ef72-131">Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ef72-131">Target frameworks.</span></span>
- <span data-ttu-id="2ef72-132">Indirizzo MAC con hash: ID univoco e anonimo dal punto di vista crittografico (SHA256) per uncomputer.</span><span class="sxs-lookup"><span data-stu-id="2ef72-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="2ef72-133">Questa metrica non è pubblicata.</span><span class="sxs-lookup"><span data-stu-id="2ef72-133">This metric isn't published.</span></span>
- <span data-ttu-id="2ef72-134">Directory di lavoro corrente con hash.</span><span class="sxs-lookup"><span data-stu-id="2ef72-134">Hashed current working directory.</span></span>

<span data-ttu-id="2ef72-135">La funzionalità non raccoglie i dati personali, ad esempio i nomi utente o gli indirizzi e-mail.</span><span class="sxs-lookup"><span data-stu-id="2ef72-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="2ef72-136">Non esegue l'analisi del codice e non estrae i dati sensibili a livello di progetto, ad esempio nome, repository o autore.</span><span class="sxs-lookup"><span data-stu-id="2ef72-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="2ef72-137">I dati vengono inviati in modo sicuro ai server Microsoft tramite la tecnologia [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), conservati con accesso limitato e pubblicati sotto rigidi controlli di sicurezza dai sistemi protetti [di archiviazione di Azure](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="2ef72-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="2ef72-138">Il team .NET è interessato a conoscere come vengono usati gli strumenti e se funzionano bene e non i progetti realizzati con gli strumenti.</span><span class="sxs-lookup"><span data-stu-id="2ef72-138">The .NET team wants to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="2ef72-139">Se si ritiene che la telemetria raccolga dati riservati o che i dati siano gestiti in modo non corretto o non protetto, segnalare un problema nel repository [dotnet/cli](https://github.com/dotnet/cli/issues) per un'analisi più approfondita.</span><span class="sxs-lookup"><span data-stu-id="2ef72-139">If you suspect that the telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="2ef72-140">Dati pubblicati</span><span class="sxs-lookup"><span data-stu-id="2ef72-140">Published data</span></span>

<span data-ttu-id="2ef72-141">I dati pubblicati sono disponibili su base trimestrale e sono elencati in [dati di utilizzo di .NET Core SDK](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="2ef72-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="2ef72-142">Le colonne di un file di dati sono:</span><span class="sxs-lookup"><span data-stu-id="2ef72-142">The columns of a data file are:</span></span>

- <span data-ttu-id="2ef72-143">Timestamp</span><span class="sxs-lookup"><span data-stu-id="2ef72-143">Timestamp</span></span>
- <span data-ttu-id="2ef72-144">Occorrenze&#8224;</span><span class="sxs-lookup"><span data-stu-id="2ef72-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="2ef72-145">Comando</span><span class="sxs-lookup"><span data-stu-id="2ef72-145">Command</span></span>
- <span data-ttu-id="2ef72-146">Geografia&#8225;</span><span class="sxs-lookup"><span data-stu-id="2ef72-146">Geography&#8225;</span></span>
- <span data-ttu-id="2ef72-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="2ef72-147">OSFamily</span></span>
- <span data-ttu-id="2ef72-148">IDruntime</span><span class="sxs-lookup"><span data-stu-id="2ef72-148">RuntimeID</span></span>
- <span data-ttu-id="2ef72-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="2ef72-149">OSVersion</span></span>
- <span data-ttu-id="2ef72-150">VersioneSDK</span><span class="sxs-lookup"><span data-stu-id="2ef72-150">SDKVersion</span></span>

<span data-ttu-id="2ef72-151">&#8224; Nella colonna *Occorrenze* è riportato il conteggio in aggregato dell'utilizzo da parte del comando di metriche di tale riga nel giorno in questione.</span><span class="sxs-lookup"><span data-stu-id="2ef72-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span>

<span data-ttu-id="2ef72-152">&#8225; In genere, nella colonna*Geografia* è riportato il nome di un Paese.</span><span class="sxs-lookup"><span data-stu-id="2ef72-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="2ef72-153">In alcuni casi, continente Antartide viene visualizzato in questa colonna, a causa di ricercatori che utilizzano .NET Core in Antartide o dati della posizione non corretti.</span><span class="sxs-lookup"><span data-stu-id="2ef72-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="2ef72-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ef72-154">Example</span></span>

| <span data-ttu-id="2ef72-155">Timestamp</span><span class="sxs-lookup"><span data-stu-id="2ef72-155">Timestamp</span></span>      | <span data-ttu-id="2ef72-156">Occorrenze</span><span class="sxs-lookup"><span data-stu-id="2ef72-156">Occurrences</span></span> | <span data-ttu-id="2ef72-157">Comando</span><span class="sxs-lookup"><span data-stu-id="2ef72-157">Command</span></span> | <span data-ttu-id="2ef72-158">Geografia</span><span class="sxs-lookup"><span data-stu-id="2ef72-158">Geography</span></span> | <span data-ttu-id="2ef72-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="2ef72-159">OSFamily</span></span> | <span data-ttu-id="2ef72-160">IDruntime</span><span class="sxs-lookup"><span data-stu-id="2ef72-160">RuntimeID</span></span>     | <span data-ttu-id="2ef72-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="2ef72-161">OSVersion</span></span> | <span data-ttu-id="2ef72-162">VersioneSDK</span><span class="sxs-lookup"><span data-stu-id="2ef72-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="2ef72-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="2ef72-163">4/16/2017 0:00</span></span> | <span data-ttu-id="2ef72-164">8</span><span class="sxs-lookup"><span data-stu-id="2ef72-164">8</span></span>           | <span data-ttu-id="2ef72-165">run</span><span class="sxs-lookup"><span data-stu-id="2ef72-165">run</span></span>     | <span data-ttu-id="2ef72-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="2ef72-166">Uganda</span></span>    | <span data-ttu-id="2ef72-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="2ef72-167">Darwin</span></span>   | <span data-ttu-id="2ef72-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="2ef72-168">osx.10.12-x64</span></span> | <span data-ttu-id="2ef72-169">10.12</span><span class="sxs-lookup"><span data-stu-id="2ef72-169">10.12</span></span>     | <span data-ttu-id="2ef72-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="2ef72-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="2ef72-171">Dataset</span><span class="sxs-lookup"><span data-stu-id="2ef72-171">Datasets</span></span>

- [<span data-ttu-id="2ef72-172">2016 - 3° trim.</span><span class="sxs-lookup"><span data-stu-id="2ef72-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)
- [<span data-ttu-id="2ef72-173">2016 - 4° trim.</span><span class="sxs-lookup"><span data-stu-id="2ef72-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)
- [<span data-ttu-id="2ef72-174">2017 - 1° trim.</span><span class="sxs-lookup"><span data-stu-id="2ef72-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)
- [<span data-ttu-id="2ef72-175">2017 - 2° trim.</span><span class="sxs-lookup"><span data-stu-id="2ef72-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)
- [<span data-ttu-id="2ef72-176">2017 - 3° trim.</span><span class="sxs-lookup"><span data-stu-id="2ef72-176">2017 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)
- [<span data-ttu-id="2ef72-177">2017 - 4° trim.</span><span class="sxs-lookup"><span data-stu-id="2ef72-177">2017 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)

<span data-ttu-id="2ef72-178">Set di dati aggiuntivi vengono pubblicati con un formato URL standard.</span><span class="sxs-lookup"><span data-stu-id="2ef72-178">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="2ef72-179">Sostituire `<YEAR>` con l'anno e sostituire `<QUARTER>` con il trimestre dell'anno (utilizzare `1`, `2`, `3`, o `4`).</span><span class="sxs-lookup"><span data-stu-id="2ef72-179">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="2ef72-180">I file sono in formato con valori delimitati da tabulazioni (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="2ef72-180">The files are in tab-separated values (*TSV*) format.</span></span>

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a><span data-ttu-id="2ef72-181">Licenza</span><span class="sxs-lookup"><span data-stu-id="2ef72-181">License</span></span>

<span data-ttu-id="2ef72-182">La distribuzione Microsoft di .NET Core è concessa in base alle [condizioni di licenza software Microsoft: Mirosoft .NET Library](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="2ef72-182">The Microsoft distribution of .NET Core is licensed with the [Microsoft Software License Terms: Mirosoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="2ef72-183">Per informazioni dettagliate sulla raccolta e l'elaborazione dei dati, vedere la sezione intitolata "DATA".</span><span class="sxs-lookup"><span data-stu-id="2ef72-183">For details on data collection and processing, see the section entitled "Data."</span></span>

<span data-ttu-id="2ef72-184">Questa licenza viene usata anche dai [pacchetti NuGet .NET](https://www.nuget.org/profiles/dotnetframework) per i quali, tuttavia, la funzionalità di telemetria non è abilitata (vedere la sezione [Ambito](#scope)).</span><span class="sxs-lookup"><span data-stu-id="2ef72-184">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

## <a name="disclosure"></a><span data-ttu-id="2ef72-185">Divulgazione</span><span class="sxs-lookup"><span data-stu-id="2ef72-185">Disclosure</span></span>

<span data-ttu-id="2ef72-186">La prima volta che si esegue uno dei [comandi dell'interfaccia della riga di comando di .NET Core](index.md), ad esempio `dotnet restore`, .NET Core SDK visualizza il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="2ef72-186">The .NET Core SDK displays the following text when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet restore`).</span></span> <span data-ttu-id="2ef72-187">Testo può variare leggermente a seconda della versione del SDK è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2ef72-187">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="2ef72-188">Questa prima esperienza riguarda la modalità di notifica della raccolta dei dati da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef72-188">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a><span data-ttu-id="2ef72-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ef72-189">See also</span></span>

- [<span data-ttu-id="2ef72-190">Nozioni apprese da.NET Core SDK telemetria</span><span class="sxs-lookup"><span data-stu-id="2ef72-190">What we've learned from .NET Core SDK Telemetry</span></span>](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)
- [<span data-ttu-id="2ef72-191">Origine riferimento di telemetria (repository dotnet/cli)</span><span class="sxs-lookup"><span data-stu-id="2ef72-191">Telemetry reference source (dotnet/cli repo)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [<span data-ttu-id="2ef72-192">Dati di utilizzo di .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="2ef72-192">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
