---
title: "Telemetria degli strumenti dell’interfaccia della riga di comando di .NET Core"
description: "Informazioni sulle funzionalità di telemetria degli strumenti di .NET Core che raccolgono informazioni sull'utilizzo per l'analisi, i dati raccolti e il modo in cui disabilitarli."
keywords: .NET,.NET Core,telemetria
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.workload:
- dotnetcore
ms.openlocfilehash: 9a78ec370fd53260f26a5d8c15707a5d611e458f
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2018
---
# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="138f2-104">Telemetria degli strumenti dell’interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="138f2-104">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="138f2-105">[.NET Core SDK](index.md) include una [funzionalità di telemetria](https://github.com/dotnet/cli/pull/2145) che raccoglie le informazioni sull'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="138f2-105">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="138f2-106">È importante che il team di .NET comprenda come vengono usati gli strumenti per consentire a Microsoft di migliorarne le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="138f2-106">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="138f2-107">Per ulteriori informazioni, vedere [Nozioni apprese da .NET Core SDK, telemetria](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="138f2-107">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="138f2-108">I dati raccolti sono anonimi e sono pubblicati in forma aggregata per l'uso da parte di Microsoft e della community in base alla [licenza Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="138f2-108">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="138f2-109">Ambito</span><span class="sxs-lookup"><span data-stu-id="138f2-109">Scope</span></span>

<span data-ttu-id="138f2-110">Il comando `dotnet` viene usato per avviare sia le applicazioni sia l’interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="138f2-110">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="138f2-111">La raccolta dei dati di telemetria non viene eseguita dal comando `dotnet` stesso.</span><span class="sxs-lookup"><span data-stu-id="138f2-111">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="138f2-112">I comandi dell’interfaccia della riga di comando .NET Core eseguiti dal comando `dotnet` raccolgono la telemetria.</span><span class="sxs-lookup"><span data-stu-id="138f2-112">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="138f2-113">La telemetria *non è abilitata* quando si utilizza il comando `dotnet` stesso, con nessun comando collegato:</span><span class="sxs-lookup"><span data-stu-id="138f2-113">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="138f2-114">La telemetria *è abilitata* quando si utilizzano i comandi dell’interfaccia della riga di comando . NET Core[, ](index.md)ad esempio:</span><span class="sxs-lookup"><span data-stu-id="138f2-114">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a><span data-ttu-id="138f2-115">Comportamento</span><span class="sxs-lookup"><span data-stu-id="138f2-115">Behavior</span></span>

<span data-ttu-id="138f2-116">La funzionalità di telemetria degli strumenti dell’interfaccia della riga di comando di .NET Core è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="138f2-116">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="138f2-117">Rifiutare esplicitamente la funzionalità di telemetria impostando la variabile di ambiente `DOTNET_CLI_TELEMETRY_OPTOUT` su `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="138f2-117">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="138f2-118">Punti dati</span><span class="sxs-lookup"><span data-stu-id="138f2-118">Data points</span></span>

<span data-ttu-id="138f2-119">La funzionalità raccoglie i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="138f2-119">The feature collects the following data:</span></span>

- <span data-ttu-id="138f2-120">Il timestamp della chiamata&#8224;</span><span class="sxs-lookup"><span data-stu-id="138f2-120">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="138f2-121">Comando richiamato (ad esempio, "build") &#8224;</span><span class="sxs-lookup"><span data-stu-id="138f2-121">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="138f2-122">Indirizzo IP di tre ottetti usato per determinare la posizione geografica&#8224;</span><span class="sxs-lookup"><span data-stu-id="138f2-122">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="138f2-123">`ExitCode` del comando</span><span class="sxs-lookup"><span data-stu-id="138f2-123">`ExitCode` of the command</span></span>
- <span data-ttu-id="138f2-124">Test Runner usato (per i progetti di test)</span><span class="sxs-lookup"><span data-stu-id="138f2-124">Test runner (for test projects)</span></span>
- <span data-ttu-id="138f2-125">Sistema operativo e relativa versione&#8224;</span><span class="sxs-lookup"><span data-stu-id="138f2-125">Operating system and version&#8224;</span></span>
- <span data-ttu-id="138f2-126">L'eventuale presenza di ID di runtime nel nodo runtimes</span><span class="sxs-lookup"><span data-stu-id="138f2-126">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="138f2-127">.NET core SDK versione&#8224;</span><span class="sxs-lookup"><span data-stu-id="138f2-127">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="138f2-128">&#8224;Questa metrica è pubblicata.</span><span class="sxs-lookup"><span data-stu-id="138f2-128">&#8224;This metric is published.</span></span>

<span data-ttu-id="138f2-129">A partire da .NET Core SDK 2.0, sono raccolti nuovi punti dati:</span><span class="sxs-lookup"><span data-stu-id="138f2-129">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="138f2-130">`dotnet`argomenti e opzioni di comando: sono raccolti solo gli argomenti e le opzioni noti (non stringhe arbitrarie).</span><span class="sxs-lookup"><span data-stu-id="138f2-130">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="138f2-131">Se il SDK è in esecuzione in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="138f2-131">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="138f2-132">Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="138f2-132">Target frameworks.</span></span>
- <span data-ttu-id="138f2-133">Indirizzo MAC con hash: ID univoco e anonimo dal punto di vista crittografico (SHA256) per uncomputer.</span><span class="sxs-lookup"><span data-stu-id="138f2-133">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="138f2-134">Questa metrica non è pubblicata.</span><span class="sxs-lookup"><span data-stu-id="138f2-134">This metric is not published.</span></span>
- <span data-ttu-id="138f2-135">Directory di lavoro corrente con hash.</span><span class="sxs-lookup"><span data-stu-id="138f2-135">Hashed current working directory.</span></span>

<span data-ttu-id="138f2-136">La funzionalità non raccoglie i dati personali, ad esempio i nomi utente o gli indirizzi e-mail.</span><span class="sxs-lookup"><span data-stu-id="138f2-136">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="138f2-137">Non esegue l'analisi del codice e non estrae i dati sensibili a livello di progetto, ad esempio nome, repository o autore.</span><span class="sxs-lookup"><span data-stu-id="138f2-137">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="138f2-138">I dati vengono inviati in modo sicuro ai server Microsoft tramite la tecnologia [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), conservati con accesso limitato e pubblicati sotto rigidi controlli di sicurezza dai sistemi protetti [di archiviazione di Azure](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="138f2-138">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="138f2-139">Microsoft è interessata a conoscere come vengono usati gli strumenti e se funzionano bene e non i progetti realizzati con gli strumenti.</span><span class="sxs-lookup"><span data-stu-id="138f2-139">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="138f2-140">Se si ritiene che la telemetria raccolta dati riservati o che i dati non siano gestiti in modo corretto o non protetto, archiviare [un problema nel repository di risoluzione dei problemi dotnet/cli](https://github.com/dotnet/cli/issues) per analisi più approfondita.</span><span class="sxs-lookup"><span data-stu-id="138f2-140">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="138f2-141">Dati pubblicati</span><span class="sxs-lookup"><span data-stu-id="138f2-141">Published data</span></span>

<span data-ttu-id="138f2-142">I dati pubblicati sono disponibili su base trimestrale e sono elencati in [dati di utilizzo di .NET Core SDK](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="138f2-142">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="138f2-143">Le colonne di un file di dati sono:</span><span class="sxs-lookup"><span data-stu-id="138f2-143">The columns of a data file are:</span></span>
- <span data-ttu-id="138f2-144">Timestamp</span><span class="sxs-lookup"><span data-stu-id="138f2-144">Timestamp</span></span>
- <span data-ttu-id="138f2-145">Occorrenze&#8224;</span><span class="sxs-lookup"><span data-stu-id="138f2-145">Occurrences&#8224;</span></span>
- <span data-ttu-id="138f2-146">Comando</span><span class="sxs-lookup"><span data-stu-id="138f2-146">Command</span></span>
- <span data-ttu-id="138f2-147">Geografia&#8225;</span><span class="sxs-lookup"><span data-stu-id="138f2-147">Geography&#8225;</span></span>
- <span data-ttu-id="138f2-148">OSFamily</span><span class="sxs-lookup"><span data-stu-id="138f2-148">OSFamily</span></span>
- <span data-ttu-id="138f2-149">IDruntime</span><span class="sxs-lookup"><span data-stu-id="138f2-149">RuntimeID</span></span>
- <span data-ttu-id="138f2-150">OSVersion</span><span class="sxs-lookup"><span data-stu-id="138f2-150">OSVersion</span></span>
- <span data-ttu-id="138f2-151">VersioneSDK</span><span class="sxs-lookup"><span data-stu-id="138f2-151">SDKVersion</span></span>

<span data-ttu-id="138f2-152">&#8224; Nella colonna *Occorrenze* è riportato il conteggio in aggregato dell'utilizzo da parte del comando di metriche di tale riga nel giorno in questione.</span><span class="sxs-lookup"><span data-stu-id="138f2-152">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="138f2-153">&#8225; In genere, nella colonna*Geografia* è riportato il nome di un Paese.</span><span class="sxs-lookup"><span data-stu-id="138f2-153">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="138f2-154">In alcuni casi, continente Antartide viene visualizzato in questa colonna, a causa di ricercatori che utilizzano .NET Core in Antartide o dati della posizione non corretti.</span><span class="sxs-lookup"><span data-stu-id="138f2-154">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="138f2-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="138f2-155">Example</span></span>

| <span data-ttu-id="138f2-156">Timestamp</span><span class="sxs-lookup"><span data-stu-id="138f2-156">Timestamp</span></span>      | <span data-ttu-id="138f2-157">Occorrenze</span><span class="sxs-lookup"><span data-stu-id="138f2-157">Occurrences</span></span> | <span data-ttu-id="138f2-158">Comando</span><span class="sxs-lookup"><span data-stu-id="138f2-158">Command</span></span> | <span data-ttu-id="138f2-159">Geografia</span><span class="sxs-lookup"><span data-stu-id="138f2-159">Geography</span></span> | <span data-ttu-id="138f2-160">OSFamily</span><span class="sxs-lookup"><span data-stu-id="138f2-160">OSFamily</span></span> | <span data-ttu-id="138f2-161">IDruntime</span><span class="sxs-lookup"><span data-stu-id="138f2-161">RuntimeID</span></span>     | <span data-ttu-id="138f2-162">OSVersion</span><span class="sxs-lookup"><span data-stu-id="138f2-162">OSVersion</span></span> | <span data-ttu-id="138f2-163">VersioneSDK</span><span class="sxs-lookup"><span data-stu-id="138f2-163">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="138f2-164">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="138f2-164">4/16/2017 0:00</span></span> | <span data-ttu-id="138f2-165">8</span><span class="sxs-lookup"><span data-stu-id="138f2-165">8</span></span>           | <span data-ttu-id="138f2-166">run</span><span class="sxs-lookup"><span data-stu-id="138f2-166">run</span></span>     | <span data-ttu-id="138f2-167">Uganda</span><span class="sxs-lookup"><span data-stu-id="138f2-167">Uganda</span></span>    | <span data-ttu-id="138f2-168">Darwin</span><span class="sxs-lookup"><span data-stu-id="138f2-168">Darwin</span></span>   | <span data-ttu-id="138f2-169">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="138f2-169">osx.10.12-x64</span></span> | <span data-ttu-id="138f2-170">10.12</span><span class="sxs-lookup"><span data-stu-id="138f2-170">10.12</span></span>     | <span data-ttu-id="138f2-171">1.0.1</span><span class="sxs-lookup"><span data-stu-id="138f2-171">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="138f2-172">Dataset</span><span class="sxs-lookup"><span data-stu-id="138f2-172">Datasets</span></span>

[<span data-ttu-id="138f2-173">2016 - 3° trim.</span><span class="sxs-lookup"><span data-stu-id="138f2-173">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="138f2-174">2016 - 4° trim.</span><span class="sxs-lookup"><span data-stu-id="138f2-174">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="138f2-175">2017 - 1° trim.</span><span class="sxs-lookup"><span data-stu-id="138f2-175">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="138f2-176">2017 - 2° trim.</span><span class="sxs-lookup"><span data-stu-id="138f2-176">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="138f2-177">Set di dati aggiuntivi vengono pubblicati con un formato URL standard.</span><span class="sxs-lookup"><span data-stu-id="138f2-177">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="138f2-178">Sostituire `<YEAR>` con l'anno e sostituire `<QUARTER>` con il trimestre dell'anno (utilizzare `1`, `2`, `3`, o `4`).</span><span class="sxs-lookup"><span data-stu-id="138f2-178">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="138f2-179">I file sono in formato con valori delimitati da tabulazioni (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="138f2-179">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="138f2-180">Licenza</span><span class="sxs-lookup"><span data-stu-id="138f2-180">License</span></span>

<span data-ttu-id="138f2-181">La distribuzione Microsoft di .NET Core è concessa in base alle [condizioni di licenza di MICROSOFT .NET LIBRARY](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="138f2-181">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="138f2-182">Nelle condizioni è inclusa la sezione "DATA", per l'abilitazione della telemetria (riportata di seguito).</span><span class="sxs-lookup"><span data-stu-id="138f2-182">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="138f2-183">Questa licenza viene usata anche dai [pacchetti NuGet .NET](https://www.nuget.org/profiles/dotnetframework) per i quali, tuttavia, la funzionalità di telemetria non è abilitata (vedere la sezione [Ambito](#scope)).</span><span class="sxs-lookup"><span data-stu-id="138f2-183">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="138f2-184">DATI.</span><span class="sxs-lookup"><span data-stu-id="138f2-184">DATA.</span></span> <span data-ttu-id="138f2-185">Il software può raccogliere informazioni sull'utente e sull'uso del software e inviarle a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="138f2-185">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="138f2-186">Microsoft può usare queste informazioni per migliorare i prodotti e i servizi.</span><span class="sxs-lookup"><span data-stu-id="138f2-186">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="138f2-187">Per altre informazioni sulla raccolta dei dati, sull'uso nella documentazione della Guida e sull'informativa sulla privacy, vedere http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="138f2-187">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="138f2-188">L'uso del software viene considerato come autorizzazione all'applicazione di queste pratiche.</span><span class="sxs-lookup"><span data-stu-id="138f2-188">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="138f2-189">Divulgazione</span><span class="sxs-lookup"><span data-stu-id="138f2-189">Disclosure</span></span>

<span data-ttu-id="138f2-190">La prima volta che si esegue uno dei comandi, ad esempio `dotnet restore`, gli strumenti dell’interfaccia della riga di comando di .NET Core visualizzano il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="138f2-190">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="138f2-191">Testo può variare leggermente a seconda della versione del SDK è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="138f2-191">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="138f2-192">Questa prima esperienza riguarda la modalità di notifica della raccolta dei dati da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="138f2-192">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a><span data-ttu-id="138f2-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="138f2-193">See also</span></span>

[<span data-ttu-id="138f2-194">Nozioni apprese da.NET Core SDK telemetria</span><span class="sxs-lookup"><span data-stu-id="138f2-194">What we've learned from .NET Core SDK Telemetry</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
<span data-ttu-id="138f2-195">[Origine riferimento di telemetria (repository dotnet/cli; versione/ ramo 2.0.0)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span><span class="sxs-lookup"><span data-stu-id="138f2-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span></span>  
[<span data-ttu-id="138f2-196">Dati di utilizzo di .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="138f2-196">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
