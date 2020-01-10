---
title: Ngen.exe (generatore di immagini native)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Native Image Generator
- images [.NET Framework], native
- side-by-side execution, native images
- assemblies [.NET Framework], native image
- Ngen.exe
- native image generation
- native image cache
- publisher policy applied for native images
- invalid images
- BypassNGenAttribute
- System.Runtime.BypassNGenAttribute
ms.assetid: 44bf97aa-a9a4-4eba-9a0d-cfaa6fc53a66
ms.openlocfilehash: 297bc3f9182e76523eda4d4be3112f4d1d7e3fee
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741799"
---
# <a name="ngenexe-native-image-generator"></a><span data-ttu-id="8e6ab-102">Ngen.exe (generatore di immagini native)</span><span class="sxs-lookup"><span data-stu-id="8e6ab-102">Ngen.exe (Native Image Generator)</span></span>

<span data-ttu-id="8e6ab-103">Il generatore di immagini native (Ngen.exe) consente di migliorare le prestazioni delle applicazioni gestite.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-103">The Native Image Generator (Ngen.exe) is a tool that improves the performance of managed applications.</span></span> <span data-ttu-id="8e6ab-104">Questo strumento crea immagini native, ovvero file contenenti codice macchina compilato specifico del processore, e le installa nella cache delle immagini native del computer locale.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-104">Ngen.exe creates native images, which are files containing compiled processor-specific machine code, and installs them into the native image cache on the local computer.</span></span> <span data-ttu-id="8e6ab-105">Il runtime può usare le immagini native della cache anziché il compilatore Just-In-Time (JIT) per compilare l'assembly originale.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-105">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-106">Ngen.exe compila le immagini native solo per gli assembly la cui destinazione è .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-106">Ngen.exe compiles native images for assemblies that target the .NET Framework only.</span></span> <span data-ttu-id="8e6ab-107">Il generatore di immagini native equivalente per .NET Core è [CrossGen](https://github.com/dotnet/runtime/blob/master/docs/workflow/building/coreclr/crossgen.md).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-107">The equivalent native image generator for .NET Core is [CrossGen](https://github.com/dotnet/runtime/blob/master/docs/workflow/building/coreclr/crossgen.md).</span></span>

<span data-ttu-id="8e6ab-108">Modifiche apportate a Ngen.exe in .NET Framework 4:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-108">Changes to Ngen.exe in the .NET Framework 4:</span></span>

- <span data-ttu-id="8e6ab-109">Ngen.exe ora compila assembly con attendibilità totale e i criteri di sicurezza dall'accesso di codice non vengono più valutati.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-109">Ngen.exe now compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

- <span data-ttu-id="8e6ab-110">Le immagini native generate con Ngen.exe non possono più essere caricate in applicazioni in modalità di esecuzione parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-110">Native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span>

<span data-ttu-id="8e6ab-111">Modifiche apportate a Ngen.exe in .NET Framework versione 2.0:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-111">Changes to Ngen.exe in the .NET Framework version 2.0:</span></span>

- <span data-ttu-id="8e6ab-112">Insieme a un assembly vengono installate anche le relative dipendenze. In questo modo la sintassi di Ngen.exe risulta semplificata.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-112">Installing an assembly also installs its dependencies, simplifying the syntax of Ngen.exe.</span></span>

- <span data-ttu-id="8e6ab-113">È ora possibile condividere le immagini native in più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-113">Native images can now be shared across application domains.</span></span>

- <span data-ttu-id="8e6ab-114">È ora disponibile una nuova azione, `update`, che consente di ricreare le immagini invalidate.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-114">A new action, `update`, re-creates images that have been invalidated.</span></span>

- <span data-ttu-id="8e6ab-115">È possibile rinviare l'esecuzione delle azioni affidandola a un servizio che usa il tempo di inattività sul computer per generare e installare le immagini.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-115">Actions can be deferred for execution by a service that uses idle time on the computer to generate and install images.</span></span>

- <span data-ttu-id="8e6ab-116">Alcune cause di invalidamento delle immagini sono state eliminate.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-116">Some causes of image invalidation have been eliminated.</span></span>

<span data-ttu-id="8e6ab-117">In Windows 8 vedere [Attività di immagini native](#native-image-task).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-117">On Windows 8, see [Native Image Task](#native-image-task).</span></span>

<span data-ttu-id="8e6ab-118">Per altre informazioni sull'uso di Ngen.exe e del servizio immagini native, vedere [Servizio immagini native](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-118">For additional information on using Ngen.exe and the native image service, see [Native Image Service](#native-image-service).</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-119">Per la sintassi di Ngen.exe per le versioni 1.0 e 1.1 di .NET Framework, vedere [Sintassi legacy del generatore di immagini native (Ngen.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-119">Ngen.exe syntax for versions 1.0 and 1.1 of the .NET Framework can be found in [Native Image Generator (Ngen.exe) Legacy Syntax](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span></span>

<span data-ttu-id="8e6ab-120">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-120">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="8e6ab-121">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-121">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="8e6ab-122">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-122">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="8e6ab-123">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-123">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="8e6ab-124">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e6ab-124">Syntax</span></span>

```console
ngen action [options]
```

```console
ngen /? | /help
```

## <a name="actions"></a><span data-ttu-id="8e6ab-125">Azioni</span><span class="sxs-lookup"><span data-stu-id="8e6ab-125">Actions</span></span>

<span data-ttu-id="8e6ab-126">Nella tabella riportata di seguito viene illustrata la sintassi di ciascuna `action`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-126">The following table shows the syntax of each `action`.</span></span> <span data-ttu-id="8e6ab-127">Per le descrizioni delle singole parti di `action`, vedere le tabelle [Argomenti](#ArgumentTable), [Livelli di priorità](#PriorityTable), [Scenari](#ScenarioTable) e [Configurazione](#ConfigTable).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-127">For descriptions of the individual parts of an `action`, see the [Arguments](#ArgumentTable), [Priority Levels](#PriorityTable), [Scenarios](#ScenarioTable), and [Config](#ConfigTable) tables.</span></span> <span data-ttu-id="8e6ab-128">Nella tabella [Opzioni](#OptionTable) vengono descritte le `options` e le opzioni della Guida.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-128">The [Options](#OptionTable) table describes the `options` and the help switches.</span></span>

|<span data-ttu-id="8e6ab-129">Azione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-129">Action</span></span>|<span data-ttu-id="8e6ab-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-130">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="8e6ab-131">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span><span class="sxs-lookup"><span data-stu-id="8e6ab-131">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span></span>|<span data-ttu-id="8e6ab-132">Genera le immagini native per un assembly e le relative dipendenze e installa le immagini nella cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-132">Generate native images for an assembly and its dependencies and install the images in the native image cache.</span></span><br /><br /> <span data-ttu-id="8e6ab-133">Se si specifica l'opzione `/queue`, l'azione viene accodata per il servizio immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-133">If `/queue` is specified, the action is queued for the native image service.</span></span> <span data-ttu-id="8e6ab-134">La priorità predefinita è 3.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-134">The default priority is 3.</span></span> <span data-ttu-id="8e6ab-135">Vedere la tabella [Livelli di priorità](#PriorityTable).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-135">See the [Priority Levels](#PriorityTable) table.</span></span>|
|<span data-ttu-id="8e6ab-136">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span><span class="sxs-lookup"><span data-stu-id="8e6ab-136">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span></span>|<span data-ttu-id="8e6ab-137">Elimina le immagini native di un assembly e le relative dipendenze dalla cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-137">Delete the native images of an assembly and its dependencies from the native image cache.</span></span><br /><br /> <span data-ttu-id="8e6ab-138">Per disinstallare una singola immagine e le relative dipendenze, ricorrere agli stessi argomenti della riga di comando usati per l'installazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-138">To uninstall a single image and its dependencies, use the same command-line arguments that were used to install the image.</span></span> <span data-ttu-id="8e6ab-139">**Nota:**  A partire da .NET Framework 4, l'azione `uninstall` \* non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-139">**Note:**  Starting with the .NET Framework 4, the action `uninstall` \* is no longer supported.</span></span>|
|<span data-ttu-id="8e6ab-140">`update` [`/queue`]</span><span class="sxs-lookup"><span data-stu-id="8e6ab-140">`update` [`/queue`]</span></span>|<span data-ttu-id="8e6ab-141">Aggiorna le immagini native diventate non valide.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-141">Update native images that have become invalid.</span></span><br /><br /> <span data-ttu-id="8e6ab-142">Se si specifica l'opzione `/queue`, gli aggiornamenti vengono accodati per il servizio immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-142">If `/queue` is specified, the updates are queued for the native image service.</span></span> <span data-ttu-id="8e6ab-143">Gli aggiornamenti vengono sempre pianificati con priorità 3, in modo da essere eseguiti durante i periodi di inattività del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-143">Updates are always scheduled at priority 3, so they run when the computer is idle.</span></span>|
|<span data-ttu-id="8e6ab-144">`display` [`assemblyName` &#124; `assemblyPath`]</span><span class="sxs-lookup"><span data-stu-id="8e6ab-144">`display` [`assemblyName` &#124; `assemblyPath`]</span></span>|<span data-ttu-id="8e6ab-145">Visualizza lo stato delle immagini native di un assembly e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-145">Display the state of the native images for an assembly and its dependencies.</span></span><br /><br /> <span data-ttu-id="8e6ab-146">Se non viene fornito alcun argomento, verrà visualizzato l'intero contenuto della cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-146">If no argument is supplied, everything in the native image cache is displayed.</span></span>|
|<span data-ttu-id="8e6ab-147">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span><span class="sxs-lookup"><span data-stu-id="8e6ab-147">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span></span><br /><br /> <span data-ttu-id="8e6ab-148">oppure</span><span class="sxs-lookup"><span data-stu-id="8e6ab-148">-or-</span></span><br /><br /> <span data-ttu-id="8e6ab-149">`eqi` [1&#124;2&#124;3]</span><span class="sxs-lookup"><span data-stu-id="8e6ab-149">`eqi` [1&#124;2&#124;3]</span></span>|<span data-ttu-id="8e6ab-150">Esegue i processi di compilazione accodati.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-150">Execute queued compilation jobs.</span></span><br /><br /> <span data-ttu-id="8e6ab-151">Se è specificata una priorità, verranno eseguiti i processi di compilazione che hanno un livello di priorità maggiore o uguale a quello specificato.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-151">If a priority is specified, compilation jobs with greater or equal priority are executed.</span></span> <span data-ttu-id="8e6ab-152">Se non è specificata alcuna priorità, verranno eseguiti tutti i processi di compilazione accodati.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-152">If no priority is specified, all queued compilation jobs are executed.</span></span>|
|<span data-ttu-id="8e6ab-153">`queue` {`pause` &#124; `continue` &#124; `status`}</span><span class="sxs-lookup"><span data-stu-id="8e6ab-153">`queue` {`pause` &#124; `continue` &#124; `status`}</span></span>|<span data-ttu-id="8e6ab-154">Sospende il servizio immagini native, riprende il servizio sospeso o esegue una query sullo stato del servizio.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-154">Pause the native image service, allow the paused service to continue, or query the status of the service.</span></span>|

<a name="ArgumentTable"></a>

## <a name="arguments"></a><span data-ttu-id="8e6ab-155">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8e6ab-155">Arguments</span></span>

|<span data-ttu-id="8e6ab-156">Argomento</span><span class="sxs-lookup"><span data-stu-id="8e6ab-156">Argument</span></span>|<span data-ttu-id="8e6ab-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-157">Description</span></span>|
|--------------|-----------------|
|`assemblyName`|<span data-ttu-id="8e6ab-158">Nome visualizzato completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-158">The full display name of the assembly.</span></span> <span data-ttu-id="8e6ab-159">Ad esempio `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-159">For example, `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span></span> <span data-ttu-id="8e6ab-160">**Nota:** è possibile fornire un nome parziale di assembly, ad esempio `myAssembly`, per le azioni `display` e `uninstall`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-160">**Note:**  You can supply a partial assembly name, such as `myAssembly`, for the `display` and `uninstall` actions.</span></span> <br /><br /> <span data-ttu-id="8e6ab-161">È possibile specificare un solo assembly per ogni riga di comando di Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-161">Only one assembly can be specified per Ngen.exe command line.</span></span>|
|`assemblyPath`|<span data-ttu-id="8e6ab-162">Percorso esplicito dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-162">The explicit path of the assembly.</span></span> <span data-ttu-id="8e6ab-163">È possibile specificare un percorso completo o relativo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-163">You can specify a full or relative path.</span></span><br /><br /> <span data-ttu-id="8e6ab-164">Se si specifica un nome di file senza percorso, l'assembly deve trovarsi nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-164">If you specify a file name without a path, the assembly must be located in the current directory.</span></span><br /><br /> <span data-ttu-id="8e6ab-165">È possibile specificare un solo assembly per ogni riga di comando di Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-165">Only one assembly can be specified per Ngen.exe command line.</span></span>|

<a name="PriorityTable"></a>

## <a name="priority-levels"></a><span data-ttu-id="8e6ab-166">Livelli di priorità</span><span class="sxs-lookup"><span data-stu-id="8e6ab-166">Priority Levels</span></span>

|<span data-ttu-id="8e6ab-167">Priority</span><span class="sxs-lookup"><span data-stu-id="8e6ab-167">Priority</span></span>|<span data-ttu-id="8e6ab-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-168">Description</span></span>|
|--------------|-----------------|
|`1`|<span data-ttu-id="8e6ab-169">Le immagini native vengono generate e installate immediatamente, senza attendere il tempo di inattività.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-169">Native images are generated and installed immediately, without waiting for idle time.</span></span>|
|`2`|<span data-ttu-id="8e6ab-170">Le immagini native vengono generate e installate senza attendere il tempo di inattività, ma dopo il completamento di tutte le azioni con priorità 1 (e delle relative dipendenze).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-170">Native images are generated and installed without waiting for idle time, but after all priority 1 actions (and their dependencies) have completed.</span></span>|
|`3`|<span data-ttu-id="8e6ab-171">Le immagini native vengono installate quando il relativo servizio rileva lo stato di inattività del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-171">Native images are installed when the native image service detects that the computer is idle.</span></span> <span data-ttu-id="8e6ab-172">Vedere [Servizio immagini native](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-172">See [Native Image Service](#native-image-service).</span></span>|

<a name="ScenarioTable"></a>

## <a name="scenarios"></a><span data-ttu-id="8e6ab-173">Scenari</span><span class="sxs-lookup"><span data-stu-id="8e6ab-173">Scenarios</span></span>

|<span data-ttu-id="8e6ab-174">Scenario</span><span class="sxs-lookup"><span data-stu-id="8e6ab-174">Scenario</span></span>|<span data-ttu-id="8e6ab-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-175">Description</span></span>|
|--------------|-----------------|
|`/Debug`|<span data-ttu-id="8e6ab-176">Genera immagini native utilizzabili con un debugger.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-176">Generate native images that can be used under a debugger.</span></span>|
|`/Profile`|<span data-ttu-id="8e6ab-177">Genera immagini native utilizzabili con un profiler.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-177">Generate native images that can be used under a profiler.</span></span>|
|`/NoDependencies`|<span data-ttu-id="8e6ab-178">Genera il numero minimo di immagini native richiesto dalle opzioni dello scenario specificato.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-178">Generate the minimum number of native images required by the specified scenario options.</span></span>|

<a name="ConfigTable"></a>

## <a name="config"></a><span data-ttu-id="8e6ab-179">Config</span><span class="sxs-lookup"><span data-stu-id="8e6ab-179">Config</span></span>

|<span data-ttu-id="8e6ab-180">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="8e6ab-180">Configuration</span></span>|<span data-ttu-id="8e6ab-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-181">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="8e6ab-182">`/ExeConfig:` `exePath`</span><span class="sxs-lookup"><span data-stu-id="8e6ab-182">`/ExeConfig:` `exePath`</span></span>|<span data-ttu-id="8e6ab-183">Usa la configurazione dell'assembly eseguibile specificato.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-183">Use the configuration of the specified executable assembly.</span></span><br /><br /> <span data-ttu-id="8e6ab-184">Al momento dell'associazione alle dipendenze, le decisioni di Ngen.exe devono coincidere con quelle del caricatore.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-184">Ngen.exe needs to make the same decisions as the loader when binding to dependencies.</span></span> <span data-ttu-id="8e6ab-185">Quando un componente condiviso viene caricato in fase di esecuzione, mediante il metodo <xref:System.Reflection.Assembly.Load%2A>, il file di configurazione dell'applicazione determina le dipendenze che devono essere caricate per il componente condiviso, ad esempio la versione di una dipendenza caricata.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-185">When a shared component is loaded at run time, using the <xref:System.Reflection.Assembly.Load%2A> method, the application's configuration file determines the dependencies that are loaded for the shared component — for example, the version of a dependency that is loaded.</span></span> <span data-ttu-id="8e6ab-186">L'opzione `/ExeConfig` indica a Ngen.exe le dipendenze che verranno caricate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-186">The `/ExeConfig` switch gives Ngen.exe guidance on which dependencies would be loaded at run time.</span></span>|
|<span data-ttu-id="8e6ab-187">`/AppBase:` `directoryPath`</span><span class="sxs-lookup"><span data-stu-id="8e6ab-187">`/AppBase:` `directoryPath`</span></span>|<span data-ttu-id="8e6ab-188">Al momento dell'individuazione delle dipendenze, la directory specificata viene usata come base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-188">When locating dependencies, use the specified directory as the application base.</span></span>|

<a name="OptionTable"></a>

## <a name="options"></a><span data-ttu-id="8e6ab-189">Options</span><span class="sxs-lookup"><span data-stu-id="8e6ab-189">Options</span></span>

|<span data-ttu-id="8e6ab-190">Opzione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-190">Option</span></span>|<span data-ttu-id="8e6ab-191">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-191">Description</span></span>|
|------------|-----------------|
|`/nologo`|<span data-ttu-id="8e6ab-192">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-192">Suppress the Microsoft startup banner display.</span></span>|
|`/silent`|<span data-ttu-id="8e6ab-193">Evita la visualizzazione dei messaggi di operazione riuscita.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-193">Suppress the display of success messages.</span></span>|
|`/verbose`|<span data-ttu-id="8e6ab-194">Visualizza informazioni dettagliate per il debug.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-194">Display detailed information for debugging.</span></span> <span data-ttu-id="8e6ab-195">**Nota:** a causa di limitazioni del sistema operativo, in Windows 98 e Windows Millennium Edition viene visualizzata una quantità ridotta di informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-195">**Note:**  Due to operating system limitations, this option does not display as much additional information on Windows 98 and Windows Millennium Edition.</span></span>|
|<span data-ttu-id="8e6ab-196">`/help`, `/?`</span><span class="sxs-lookup"><span data-stu-id="8e6ab-196">`/help`, `/?`</span></span>|<span data-ttu-id="8e6ab-197">Visualizza la sintassi e le opzioni di comando della versione corrente.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-197">Display command syntax and options for the current release.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8e6ab-198">Note</span><span class="sxs-lookup"><span data-stu-id="8e6ab-198">Remarks</span></span>

<span data-ttu-id="8e6ab-199">Per eseguire Ngen.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-199">To run Ngen.exe, you must have administrative privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="8e6ab-200">Non eseguire Ngen.exe su assembly che non sono completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-200">Do not run Ngen.exe on assemblies that are not fully trusted.</span></span> <span data-ttu-id="8e6ab-201">A partire da .NET Framework 4, Ngen.exe compila assembly con attendibilità totale e i criteri di sicurezza dall'accesso di codice non vengono più valutati.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-201">Starting with the .NET Framework 4, Ngen.exe compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

<span data-ttu-id="8e6ab-202">A partire da .NET Framework 4, le immagini native generate con Ngen.exe non possono più essere caricate in applicazioni in modalità di esecuzione parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-202">Starting with the .NET Framework 4, the native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span> <span data-ttu-id="8e6ab-203">Viene invece richiamato il compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-203">Instead, the just-in-time (JIT) compiler is invoked.</span></span>

<span data-ttu-id="8e6ab-204">Ngen.exe genera immagini native per l'assembly specificato dall'argomento `assemblyname` di `install` e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-204">Ngen.exe generates native images for the assembly specified by the `assemblyname` argument to the `install` action and all its dependencies.</span></span> <span data-ttu-id="8e6ab-205">Le dipendenze vengono determinate in base ai riferimenti presenti nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-205">Dependencies are determined from references in the assembly manifest.</span></span> <span data-ttu-id="8e6ab-206">L'unico scenario in cui è necessario installare separatamente una dipendenza si verifica quando l'applicazione ne esegue il caricamento tramite reflection, ad esempio chiamando il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-206">The only scenario in which you need to install a dependency separately is when the application loads it using reflection, for example by calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e6ab-207">Non usare il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> con le immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-207">Do not use the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method with native images.</span></span> <span data-ttu-id="8e6ab-208">Un'immagine caricata con questo metodo non può essere usata da altri assembly nel contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-208">An image loaded with this method cannot be used by other assemblies in the execution context.</span></span>

<span data-ttu-id="8e6ab-209">Lo strumento Ngen.exe gestisce un conteggio delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-209">Ngen.exe maintains a count on dependencies.</span></span> <span data-ttu-id="8e6ab-210">Si supponga, ad esempio, che `MyAssembly.exe` e `YourAssembly.exe` siano installati nella cache delle immagini native e che entrambi contengano riferimenti a `OurDependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-210">For example, suppose `MyAssembly.exe` and `YourAssembly.exe` are both installed in the native image cache, and both have references to `OurDependency.dll`.</span></span> <span data-ttu-id="8e6ab-211">Se `MyAssembly.exe` viene disinstallato, `OurDependency.dll` non verrà disinstallato.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-211">If `MyAssembly.exe` is uninstalled, `OurDependency.dll` is not uninstalled.</span></span> <span data-ttu-id="8e6ab-212">Quest'ultimo verrà rimosso soltanto dopo la disinstallazione di `YourAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-212">It is only removed when `YourAssembly.exe` is also uninstalled.</span></span>

<span data-ttu-id="8e6ab-213">Se si sta generando un'immagine nativa per un assembly nella Global Assembly Cache, è necessario specificare il relativo nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-213">If you are generating a native image for an assembly in the global assembly cache, specify its display name.</span></span> <span data-ttu-id="8e6ab-214">Vedere <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-214">See <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="8e6ab-215">Le immagini native generate da Ngen.exe possono essere condivise tra più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-215">The native images that Ngen.exe generates can be shared across application domains.</span></span> <span data-ttu-id="8e6ab-216">È pertanto possibile usare Ngen.exe in scenari di applicazioni che richiedono la condivisione di assembly tra più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-216">This means you can use Ngen.exe in application scenarios that require assemblies to be shared across application domains.</span></span> <span data-ttu-id="8e6ab-217">Per specificare l'indipendenza dal dominio, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-217">To specify domain neutrality:</span></span>

- <span data-ttu-id="8e6ab-218">Applicare l'attributo <xref:System.LoaderOptimizationAttribute> all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-218">Apply the <xref:System.LoaderOptimizationAttribute> attribute to your application.</span></span>

- <span data-ttu-id="8e6ab-219">Impostare la proprietà <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> quando si creano le informazioni di impostazione di un nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-219">Set the <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> property when you create setup information for a new application domain.</span></span>

<span data-ttu-id="8e6ab-220">Per il caricamento dello stesso assembly in più domini applicazione si consiglia di usare sempre codice indipendente dal dominio.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-220">Always use domain-neutral code when loading the same assembly into multiple application domains.</span></span> <span data-ttu-id="8e6ab-221">Un'immagine nativa caricata in un dominio applicazione non condiviso dopo essere stata caricata in un dominio condiviso non può essere usata.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-221">If a native image is loaded into a nonshared application domain after having been loaded into a shared domain, it cannot be used.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-222">Il codice indipendente dal dominio non può essere scaricato e le prestazioni potranno risultare leggermente inferiori, in particolare durante l'accesso ai membri statici.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-222">Domain-neutral code cannot be unloaded, and performance may be slightly slower, particularly when accessing static members.</span></span>

<span data-ttu-id="8e6ab-223">Nella sezione Osservazioni:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-223">In this Remarks section:</span></span>

- [<span data-ttu-id="8e6ab-224">Generazione delle immagini per scenari diversi</span><span class="sxs-lookup"><span data-stu-id="8e6ab-224">Generating images for different scenarios</span></span>](#Scenarios)

- [<span data-ttu-id="8e6ab-225">Uso delle immagini native</span><span class="sxs-lookup"><span data-stu-id="8e6ab-225">Determining when to Use native images</span></span>](#WhenToUse)

  - [<span data-ttu-id="8e6ab-226">Uso più efficiente della memoria</span><span class="sxs-lookup"><span data-stu-id="8e6ab-226">Improved memory use</span></span>](#Memory)

  - [<span data-ttu-id="8e6ab-227">Avvio più rapido delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="8e6ab-227">Faster application startup</span></span>](#Startup)

  - [<span data-ttu-id="8e6ab-228">Riepilogo delle considerazioni sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="8e6ab-228">Summary of usage considerations</span></span>](#UsageSummary)

- [<span data-ttu-id="8e6ab-229">Importanza degli indirizzi di base degli assembly</span><span class="sxs-lookup"><span data-stu-id="8e6ab-229">Importance of assembly base addresses</span></span>](#BaseAddresses)

- [<span data-ttu-id="8e6ab-230">Hard binding</span><span class="sxs-lookup"><span data-stu-id="8e6ab-230">Hard binding</span></span>](#HardBinding)

  - [<span data-ttu-id="8e6ab-231">Specifica di un suggerimento di binding per una dipendenza</span><span class="sxs-lookup"><span data-stu-id="8e6ab-231">Specifying a binding hint for a dependency</span></span>](#DependencyHint)

  - [<span data-ttu-id="8e6ab-232">Specifica di un suggerimento di binding predefinito per un assembly</span><span class="sxs-lookup"><span data-stu-id="8e6ab-232">Specifying a default binding hint for an assembly</span></span>](#AssemblyHint)

- [<span data-ttu-id="8e6ab-233">Rinvio dell'elaborazione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-233">Deferred processing</span></span>](#Deferred)

- [<span data-ttu-id="8e6ab-234">Immagini native e compilazione JIT</span><span class="sxs-lookup"><span data-stu-id="8e6ab-234">Native images and JIT compilation</span></span>](#JITCompilation)

  - [<span data-ttu-id="8e6ab-235">Immagini non valide</span><span class="sxs-lookup"><span data-stu-id="8e6ab-235">Invalid images</span></span>](#InvalidImages)

- [<span data-ttu-id="8e6ab-236">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="8e6ab-236">Troubleshooting</span></span>](#Troubleshooting)

  - [<span data-ttu-id="8e6ab-237">Visualizzatore log binding assembly</span><span class="sxs-lookup"><span data-stu-id="8e6ab-237">Assembly Binding Log Viewer</span></span>](#Fusion)

  - [<span data-ttu-id="8e6ab-238">Assistente al debug gestito JITCompilationStart</span><span class="sxs-lookup"><span data-stu-id="8e6ab-238">The JITCompilationStart managed debugging assistant</span></span>](#MDA)

  - [<span data-ttu-id="8e6ab-239">Rifiuto esplicito della generazione di immagini native</span><span class="sxs-lookup"><span data-stu-id="8e6ab-239">Opting out of native image generation</span></span>](#OptOut)

<a name="Scenarios"></a>

## <a name="generating-images-for-----different-scenarios"></a><span data-ttu-id="8e6ab-240">Generazione delle immagini per scenari diversi</span><span class="sxs-lookup"><span data-stu-id="8e6ab-240">Generating images for     different scenarios</span></span>

<span data-ttu-id="8e6ab-241">Una volta generata l'immagine nativa di un assembly, il runtime tenta automaticamente di individuarla e usarla ogni volta che viene eseguito l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-241">After you have generated a native image for an assembly, the runtime automatically attempts to locate and use this native   image each time it runs the assembly.</span></span> <span data-ttu-id="8e6ab-242">Possono essere generate più immagini, a seconda degli scenari di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-242">Multiple images can be generated, depending on usage scenarios.</span></span>

<span data-ttu-id="8e6ab-243">Se ad esempio si esegue un assembly in uno scenario di debug o di profilatura, il runtime cercherà un'immagine nativa generata con le opzioni `/Debug` o `/Profile`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-243">For example, if you run an assembly in a debugging or profiling scenario, the runtime looks for a native image that was generated with the `/Debug` or `/Profile` options.</span></span> <span data-ttu-id="8e6ab-244">Se non è possibile individuare un'immagine nativa corrispondente, verrà ripristinata la compilazione JIT standard.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-244">If it is unable to find a matching native image, the runtime reverts to standard JIT compilation.</span></span> <span data-ttu-id="8e6ab-245">L'unico modo per eseguire il debug delle immagini native consiste nel creare un'immagine nativa con l'opzione `/Debug`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-245">The only way to debug native images is to create a native image with the `/Debug` option.</span></span>

<span data-ttu-id="8e6ab-246">Poiché anche l'azione `uninstall` supporta gli scenari, è possibile disinstallare tutti gli scenari o solo quelli selezionati.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-246">The `uninstall` action also recognize scenarios, so you can uninstall all scenarios or only selected scenarios.</span></span>

<a name="WhenToUse"></a>

## <a name="determining-when-to-use-native-images"></a><span data-ttu-id="8e6ab-247">Uso delle immagini native</span><span class="sxs-lookup"><span data-stu-id="8e6ab-247">Determining when to Use native images</span></span>

<span data-ttu-id="8e6ab-248">Le immagini native offrono i seguenti vantaggi prestazionali: utilizzo migliore della memoria e riduzione del tempo di avvio.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-248">Native images can provide performance improvements in two areas: improved memory use and reduced startup time.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-249">Le prestazioni delle immagini native dipendono da diversi fattori che possono risultare difficili da analizzare, ad esempio i modelli di accesso a dati e codice, il numero delle chiamate effettuate tra i vari moduli e il numero delle dipendenze già caricate da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-249">Performance of native images depends on a number of factors that make analysis difficult, such as code and data access patterns, how many calls are made across module boundaries, and how many dependencies have already been loaded by other applications.</span></span> <span data-ttu-id="8e6ab-250">L'unico modo per determinare se l'applicazione può trarre benefici dall'utilizzo delle immagini native consiste nell'eseguire un'attenta valutazione delle prestazioni negli scenari di distribuzione chiave.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-250">The only way to determine whether native images benefit your application is by careful performance measurements in your key deployment scenarios.</span></span>

<a name="Memory"></a>

### <a name="improved-memory-use"></a><span data-ttu-id="8e6ab-251">Uso più efficiente della memoria</span><span class="sxs-lookup"><span data-stu-id="8e6ab-251">Improved memory use</span></span>

<span data-ttu-id="8e6ab-252">Le immagini native possono migliorare in modo significativo l'utilizzo della memoria quando il codice è condiviso tra più processi.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-252">Native images can significantly improve memory use when code is shared between processes.</span></span> <span data-ttu-id="8e6ab-253">Poiché le immagini native sono file Windows di tipo PE, una singola copia di un file DLL può essere condivisa tra più processi. Il codice nativo prodotto dal compilatore JIT, invece, viene archiviato nella memoria privata e non può essere condiviso.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-253">Native images are Windows PE files, so a single copy of a .dll file can be shared by multiple processes; by contrast, native code produced by the JIT compiler is stored in private memory and cannot be shared.</span></span>

<span data-ttu-id="8e6ab-254">Anche le applicazioni che vengono eseguite in Servizi terminal possono ottenere vantaggi dall'utilizzo di tabelle codici condivise.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-254">Applications that are run under terminal services can also benefit from shared code pages.</span></span>

<span data-ttu-id="8e6ab-255">Inoltre, il mancato caricamento del compilatore JIT consente di risparmiare una quantità fissa di memoria per ciascuna istanza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-255">In addition, not loading the JIT compiler saves a fixed amount of memory for each application instance.</span></span>

<a name="Startup"></a>

### <a name="faster-application-startup"></a><span data-ttu-id="8e6ab-256">Avvio più rapido delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="8e6ab-256">Faster application startup</span></span>

<span data-ttu-id="8e6ab-257">La precompilazione degli assembly con Ngen.exe consente di ridurre il tempo di avvio di alcune applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-257">Precompiling assemblies with Ngen.exe can improve the startup time for some applications.</span></span> <span data-ttu-id="8e6ab-258">In generale, i maggiori vantaggi si ottengono con le applicazioni che condividono assembly di componenti. In questo caso, infatti, una volta avviata la prima applicazione, i componenti condivisi risulteranno già caricati per le applicazioni successive.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-258">In general, gains can be made when applications share component assemblies because after the first application has been started the shared components are already loaded for subsequent applications.</span></span> <span data-ttu-id="8e6ab-259">In caso di avvio a freddo, in cui tutti gli assembly di un'applicazione devono essere caricati dal disco rigido, le immagini native non offrono molti vantaggi poiché il tempo di accesso al disco rigido svolge un ruolo predominante.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-259">Cold startup, in which all the assemblies in an application must be loaded from the hard disk, does not benefit as much from native images because the hard disk access time predominates.</span></span>

<span data-ttu-id="8e6ab-260">L'associazione forte può influire negativamente sul tempo di avvio, poiché tutte le immagini associate in maniera forte all'assembly principale dell'applicazione devono essere caricate simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-260">Hard binding can affect startup time, because all images that are hard bound to the main application assembly must be loaded at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-261">Per le versioni precedenti a .NET Framework 3.5 Service Pack 1 è opportuno inserire i componenti condivisi con nome sicuro nella Global Assembly Cache, perché il caricatore esegue un ulteriore controllo di convalida sugli assembly con nome sicuro che non si trovano nella Global Assembly Cache, annullando quindi qualsiasi miglioramento a livello di tempo di avvio ottenuto grazie alle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-261">Before the .NET Framework 3.5 Service Pack 1, you should put shared, strong-named components in the global assembly cache, because the loader performs extra validation on strong-named assemblies that are not in the global assembly cache, effectively eliminating any improvement in startup time gained by using native images.</span></span> <span data-ttu-id="8e6ab-262">Con le ottimizzazioni introdotte in .NET Framework 3.5 SP1 è stata rimossa la convalida aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-262">Optimizations that were introduced in the .NET Framework 3.5 SP1 removed the extra validation.</span></span>

<a name="UsageSummary"></a>

### <a name="summary-of-usage-considerations"></a><span data-ttu-id="8e6ab-263">Riepilogo delle considerazioni sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="8e6ab-263">Summary of usage considerations</span></span>

<span data-ttu-id="8e6ab-264">Di seguito sono riportate alcune considerazioni di carattere generale e specifiche per le applicazioni che possono aiutare a decidere se l'utilizzo delle immagini native può essere una soluzione vantaggiosa per la propria applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-264">The following general considerations and application considerations may assist you in deciding whether to undertake the effort of evaluating native images for your application:</span></span>

- <span data-ttu-id="8e6ab-265">Le immagini native vengono caricate più rapidamente rispetto al codice MSIL, poiché eliminano la necessità di eseguire molte attività di avvio, ad esempio la compilazione JIT e la verifica dell'indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-265">Native images load faster than MSIL because they eliminate the need for many startup activities, such as JIT compilation and type-safety verification.</span></span>

- <span data-ttu-id="8e6ab-266">Le immagini native richiedono un working set iniziale più piccolo, poiché il compilatore JIT non è necessario.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-266">Native images require a smaller initial working set because there is no need for the JIT compiler.</span></span>

- <span data-ttu-id="8e6ab-267">Le immagini native consentono di condividere il codice tra più processi.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-267">Native images enable code sharing between processes.</span></span>

- <span data-ttu-id="8e6ab-268">Le immagini native occupano una quantità di spazio su disco maggiore rispetto agli assembly MSIL e possono richiedere molto tempo per la generazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-268">Native images require more hard disk space than MSIL assemblies and may require considerable time to generate.</span></span>

- <span data-ttu-id="8e6ab-269">Per le immagini native sono necessarie alcune attività di gestione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-269">Native images must be maintained.</span></span>

  - <span data-ttu-id="8e6ab-270">Le immagini devono essere rigenerate quando vengono apportate delle modifiche all'assembly originale o a una delle relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-270">Images need to be regenerated when the original assembly or one of its dependencies is serviced.</span></span>

  - <span data-ttu-id="8e6ab-271">È possibile che uno stesso assembly richieda più immagini native da usare in applicazioni o scenari differenti.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-271">A single assembly may need multiple native images for use in different applications or different scenarios.</span></span> <span data-ttu-id="8e6ab-272">Ad esempio, le informazioni di configurazione in due applicazioni potrebbero comportare decisioni di associazione diverse per lo stesso assembly dipendente.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-272">For example, the configuration information in two applications might result in different binding decisions for the same dependent assembly.</span></span>

  - <span data-ttu-id="8e6ab-273">Le immagini native devono essere generate da un amministratore, ovvero da un account Windows del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-273">Native images must be generated by an administrator; that is, from a Windows account in the Administrators group.</span></span>

<span data-ttu-id="8e6ab-274">Oltre a queste considerazioni generali, per determinare se le immagini native possono offrire vantaggi in termini di prestazioni occorre valutare anche la natura dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-274">In addition to these general considerations, the nature of your application must be considered when determining whether native images might provide a performance benefit:</span></span>

- <span data-ttu-id="8e6ab-275">Se l'applicazione viene eseguita in un ambiente che usa molti componenti condivisi, le immagini native consentiranno di condividere tali componenti tra più processi.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-275">If your application runs in an environment that uses many shared components, native images allow the components to be shared by multiple processes.</span></span>

- <span data-ttu-id="8e6ab-276">Se l'applicazione usa più domini applicazione, le immagini native consentiranno di condividere le tabelle codici tra più domini.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-276">If your application uses multiple application domains, native images allow code pages to be shared across domains.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8e6ab-277">In .NET Framework versioni 1.0 e 1.1, le immagini native non possono essere condivise tra più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-277">In the .NET Framework versions 1.0 and 1.1, native images cannot be shared across application domains.</span></span> <span data-ttu-id="8e6ab-278">Questa limitazione è stata rimossa nella versione 2.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-278">This is not the case in version 2.0 or later.</span></span>

- <span data-ttu-id="8e6ab-279">Se l'applicazione verrà eseguita in Terminal Server, le immagini native consentiranno di condividere le tabelle codici.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-279">If your application will be run under Terminal Server, native images allow sharing of code pages.</span></span>

- <span data-ttu-id="8e6ab-280">La compilazione in immagini native in genere comporta un miglioramento delle prestazioni per le applicazioni di grandi dimensioni,</span><span class="sxs-lookup"><span data-stu-id="8e6ab-280">Large applications generally benefit from compilation to native images.</span></span> <span data-ttu-id="8e6ab-281">ma non per quelle di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-281">Small applications generally do not benefit.</span></span>

- <span data-ttu-id="8e6ab-282">Per le applicazioni a esecuzione prolungata, la compilazione JIT in fase di esecuzione offre prestazioni leggermente migliori rispetto alle immagini native,</span><span class="sxs-lookup"><span data-stu-id="8e6ab-282">For long-running applications, run-time JIT compilation performs slightly better than native images.</span></span> <span data-ttu-id="8e6ab-283">anche se tale differenza può comunque essere ridotta mediante l'utilizzo dell'associazione forte.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-283">(Hard binding can mitigate this performance difference to some degree.)</span></span>

<a name="BaseAddresses"></a>

## <a name="importance-of-assembly-base-addresses"></a><span data-ttu-id="8e6ab-284">Importanza degli indirizzi di base degli assembly</span><span class="sxs-lookup"><span data-stu-id="8e6ab-284">Importance of assembly base addresses</span></span>

<span data-ttu-id="8e6ab-285">Poiché sono file Windows di tipo PE, le immagini native sono soggette agli stessi problemi di rilocazione degli altri file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-285">Because native images are Windows PE files, they are subject to the same rebasing issues as other executable files.</span></span> <span data-ttu-id="8e6ab-286">L'impatto della rilocazione sulle prestazioni risulta ancora più accentuato in caso di utilizzo dell'associazione forte.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-286">The performance cost of relocation is even more pronounced if hard binding is employed.</span></span>

<span data-ttu-id="8e6ab-287">Per impostare l'indirizzo di base di un'immagine nativa, usare l'opzione appropriata del compilatore per impostare l'indirizzo di base dell'assembly,</span><span class="sxs-lookup"><span data-stu-id="8e6ab-287">To set the base address for a native image, use the appropriate option of your compiler to set the base address for the assembly.</span></span> <span data-ttu-id="8e6ab-288">che verrà quindi usato da Ngen.exe come indirizzo di base dell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-288">Ngen.exe uses this base address for the native image.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-289">Le immagini native sono più grandi rispetto agli assembly gestiti da cui sono state create.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-289">Native images are larger than the managed assemblies from which they were created.</span></span> <span data-ttu-id="8e6ab-290">Gli indirizzi di base devono quindi essere calcolati tenendo conto di queste dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-290">Base addresses must be calculated to allow for these larger sizes.</span></span>

<span data-ttu-id="8e6ab-291">Per visualizzare l'indirizzo di base preferenziale di un'immagine nativa è possibile usare uno strumento quale dumpbin.exe.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-291">You can use a tool such as dumpbin.exe to view the preferred base address of a native image.</span></span>

<a name="HardBinding"></a>

## <a name="hard-binding"></a><span data-ttu-id="8e6ab-292">Hard binding</span><span class="sxs-lookup"><span data-stu-id="8e6ab-292">Hard binding</span></span>

<span data-ttu-id="8e6ab-293">L'associazione forte consente di aumentare la velocità effettiva e ridurre la dimensione del working set per le immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-293">Hard binding increases throughput and reduces working set size for native images.</span></span> <span data-ttu-id="8e6ab-294">Lo svantaggio consiste nel fatto che tutte le immagini associate in maniera forte a un assembly devono essere caricate al momento del caricamento dell'assembly,</span><span class="sxs-lookup"><span data-stu-id="8e6ab-294">The disadvantage of hard binding is that all the images that are hard bound to an assembly must be loaded when the assembly is loaded.</span></span> <span data-ttu-id="8e6ab-295">cosa che può provocare un aumento significativo del tempo di avvio per un'applicazione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-295">This can significantly increase startup time for a large application.</span></span>

<span data-ttu-id="8e6ab-296">L'associazione forte è appropriata per le dipendenze che vengono caricate in tutti gli scenari dell'applicazione in cui è fondamentale che le prestazioni siano elevate.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-296">Hard binding is appropriate for dependencies that are loaded in all your application's performance-critical scenarios.</span></span> <span data-ttu-id="8e6ab-297">Come accade con qualsiasi altro aspetto relativo all'utilizzo delle immagini native, l'unico modo per determinare se l'associazione forte è in grado di migliorare le prestazioni dell'applicazione consiste in un'attenta valutazione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-297">As with any aspect of native image use, careful performance measurements are the only way to determine whether hard binding improves your application's performance.</span></span>

<span data-ttu-id="8e6ab-298">Gli attributi <xref:System.Runtime.CompilerServices.DependencyAttribute> e <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> consentono di fornire a Ngen.exe alcuni suggerimenti per l'utilizzo dell'associazione forte.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-298">The <xref:System.Runtime.CompilerServices.DependencyAttribute> and <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> attributes allow you to provide hard binding hints to Ngen.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-299">Questi attributi non sono comandi ma semplici suggerimenti</span><span class="sxs-lookup"><span data-stu-id="8e6ab-299">These attributes are hints to Ngen.exe, not commands.</span></span> <span data-ttu-id="8e6ab-300">e il loro utilizzo non garantisce l'associazione forte.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-300">Using them does not guarantee hard binding.</span></span> <span data-ttu-id="8e6ab-301">Il significato di questi attributi potrebbe cambiare nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-301">The meaning of these attributes may change in future releases.</span></span>

<a name="DependencyHint"></a>

### <a name="specifying-a-binding-hint-for-a-dependency"></a><span data-ttu-id="8e6ab-302">Specifica di un suggerimento di binding per una dipendenza</span><span class="sxs-lookup"><span data-stu-id="8e6ab-302">Specifying a binding hint for a dependency</span></span>

<span data-ttu-id="8e6ab-303">Applicare <xref:System.Runtime.CompilerServices.DependencyAttribute> a un assembly per indicare la probabilità che una dipendenza specificata venga caricata.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-303">Apply the <xref:System.Runtime.CompilerServices.DependencyAttribute> to an assembly to indicate the likelihood that a specified dependency will be loaded.</span></span> <span data-ttu-id="8e6ab-304"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indica che l'associazione forte è appropriata, <xref:System.Runtime.CompilerServices.LoadHint.Default> indica che deve essere usato il valore predefinito per la dipendenza e <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indica che l'associazione forte non è appropriata.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-304"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indicates that hard binding is appropriate, <xref:System.Runtime.CompilerServices.LoadHint.Default> indicates that the default for the dependency should be used, and <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indicates that hard binding is not appropriate.</span></span>

<span data-ttu-id="8e6ab-305">Nell'esempio di codice riportato di seguito vengono illustrati gli attributi per un assembly con due dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-305">The following code shows the attributes for an assembly that has two dependencies.</span></span> <span data-ttu-id="8e6ab-306">La prima dipendenza (Assembly1) è un candidato appropriato per l'associazione forte, al contrario della seconda (Assembly2).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-306">The first dependency (Assembly1) is an appropriate candidate for hard binding, and the second (Assembly2) is not.</span></span>

```vb
Imports System.Runtime.CompilerServices
<Assembly:DependencyAttribute("Assembly1", LoadHint.Always)>
<Assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)>
```

```csharp
using System.Runtime.CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)]
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)]
```

```cpp
using namespace System::Runtime::CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)];
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)];
```

<span data-ttu-id="8e6ab-307">Il nome dell'assembly non include l'estensione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-307">The assembly name does not include the file name extension.</span></span> <span data-ttu-id="8e6ab-308">ed è possibile usare i nomi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-308">Display names can be used.</span></span>

<a name="AssemblyHint"></a>

### <a name="specifying-a-default-binding-hint-for-an-assembly"></a><span data-ttu-id="8e6ab-309">Specifica di un suggerimento di binding predefinito per un assembly</span><span class="sxs-lookup"><span data-stu-id="8e6ab-309">Specifying a default binding hint for an assembly</span></span>

<span data-ttu-id="8e6ab-310">I suggerimenti di associazione predefinita sono necessari solo per gli assembly che verranno usati immediatamente e di frequente da una qualsiasi applicazione che prevede una dipendenza da tali assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-310">Default binding hints are only needed for assemblies that will be used immediately and frequently by any application that has a dependency on them.</span></span> <span data-ttu-id="8e6ab-311">Applicare <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> con <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> a tali assembly per specificare che deve essere usata l'associazione forte.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-311">Apply the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> with <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> to such assemblies to specify that hard binding should be used.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-312">Non esiste alcun motivo per applicare <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> agli assembly DLL che non rientrano in questa categoria, poiché l'applicazione dell'attributo con un qualsiasi valore diverso da <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> equivale a non applicare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-312">There is no reason to apply <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to .dll assemblies that do not fall into this category, because applying the attribute with any value other than <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> has the same effect as not applying the attribute at all.</span></span>

<span data-ttu-id="8e6ab-313">Microsoft usa <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> per specificare che l'associazione forte è l'impostazione predefinita per un numero molto piccolo di assembly in .NET Framework, ad esempio mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-313">Microsoft uses the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to specify that hard binding is the default for a very small number of assemblies in the .NET Framework, such as mscorlib.dll.</span></span>

<a name="Deferred"></a>

## <a name="deferred-processing"></a><span data-ttu-id="8e6ab-314">Rinvio dell'elaborazione</span><span class="sxs-lookup"><span data-stu-id="8e6ab-314">Deferred processing</span></span>

<span data-ttu-id="8e6ab-315">La generazione delle immagini native per un'applicazione di grandi dimensioni può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-315">Generation of native images for a very large application can take considerable time.</span></span> <span data-ttu-id="8e6ab-316">In modo analogo, le modifiche a un componente condiviso o alle impostazioni del computer potrebbero richiedere l'aggiornamento di numerose immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-316">Similarly, changes to a shared component or changes to computer settings might require many native images to be updated.</span></span> <span data-ttu-id="8e6ab-317">Per le azioni `install` e `update` è disponibile un'opzione `/queue` che accoda l'operazione per rinviare l'esecuzione tramite il servizio immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-317">The `install` and `update` actions have a `/queue` option that queues the operation for deferred execution by the native image service.</span></span> <span data-ttu-id="8e6ab-318">Inoltre, Ngen.exe include le azioni `queue` e `executeQueuedItems` che forniscono un certo grado di controllo sul servizio.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-318">In addition, Ngen.exe has `queue` and `executeQueuedItems` actions that provide some control over the service.</span></span> <span data-ttu-id="8e6ab-319">Per altre informazioni, vedere [Servizio immagini native](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-319">For more information, see [Native Image Service](#native-image-service).</span></span>

<a name="JITCompilation"></a>

## <a name="native-images-and-jit-compilation"></a><span data-ttu-id="8e6ab-320">Immagini native e compilazione JIT</span><span class="sxs-lookup"><span data-stu-id="8e6ab-320">Native images and JIT compilation</span></span>

<span data-ttu-id="8e6ab-321">Se Ngen.exe individua in un assembly metodi che non possono essere generati, li esclude dall'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-321">If Ngen.exe encounters any methods in an assembly that it cannot generate, it excludes them from the native image.</span></span> <span data-ttu-id="8e6ab-322">Quando il runtime eseguirà questo assembly, utilizzerà la compilazione JIT per i metodi che non sono stati inclusi nell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-322">When the runtime executes this assembly, it reverts to JIT compilation for the methods that were not included in the native image.</span></span>

<span data-ttu-id="8e6ab-323">Inoltre, le immagini native non vengono usate se l'assembly è stato aggiornato o se l'immagine è stata invalidata per qualche motivo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-323">In addition, native images are not used if the assembly has been upgraded, or if the image has been invalidated for any reason.</span></span>

<a name="InvalidImages"></a>

### <a name="invalid-images"></a><span data-ttu-id="8e6ab-324">Immagini non valide</span><span class="sxs-lookup"><span data-stu-id="8e6ab-324">Invalid images</span></span>

<span data-ttu-id="8e6ab-325">Quando si usa Ngen.exe per creare un'immagine nativa di un assembly, l'output dipenderà dalle opzioni della riga di comando specificate e da alcune impostazioni del computer,</span><span class="sxs-lookup"><span data-stu-id="8e6ab-325">When you use Ngen.exe to create a native image of an assembly, the output depends upon the command-line options that you specify and certain settings on your computer.</span></span> <span data-ttu-id="8e6ab-326">incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-326">These settings include the following:</span></span>

- <span data-ttu-id="8e6ab-327">Versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-327">The version of the .NET Framework.</span></span>

- <span data-ttu-id="8e6ab-328">Versione del sistema operativo, se si è passati dalla famiglia Windows 9x alla famiglia Windows NT.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-328">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

- <span data-ttu-id="8e6ab-329">Identità esatta dell'assembly (l'identità cambia ad ogni ricompilazione).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-329">The exact identity of the assembly (recompilation changes identity).</span></span>

- <span data-ttu-id="8e6ab-330">Identità esatta di tutti gli assembly a cui l'assembly fa riferimento (l'identità cambia ad ogni ricompilazione).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-330">The exact identity of all assemblies that the assembly references (recompilation changes identity).</span></span>

- <span data-ttu-id="8e6ab-331">Fattori di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-331">Security factors.</span></span>

<span data-ttu-id="8e6ab-332">Quando genera un'immagine nativa, Ngen.exe registra queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-332">Ngen.exe records this information when it generates a native image.</span></span> <span data-ttu-id="8e6ab-333">Quando si esegue un assembly, il runtime cerca l'immagine nativa generata con le opzioni e le impostazioni che corrispondono all'ambiente corrente del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-333">When you execute an assembly, the runtime looks for the native image generated with options and settings that match the computer's current environment.</span></span> <span data-ttu-id="8e6ab-334">Se non viene individuata un'immagine nativa corrispondente, viene ripristinata la compilazione JIT di un assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-334">The runtime reverts to JIT compilation of an assembly if it cannot find a matching native image.</span></span> <span data-ttu-id="8e6ab-335">Le modifiche alle impostazioni e all'ambiente di un computer che rendono non valide le immagini native sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-335">The following changes to a computer's settings and environment cause native images to become invalid:</span></span>

- <span data-ttu-id="8e6ab-336">Versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-336">The version of the .NET Framework.</span></span>

     <span data-ttu-id="8e6ab-337">Se viene eseguito un aggiornamento di .NET Framework, tutte le immagini native create usando Ngen.exe non saranno più valide.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-337">If you apply an update to the .NET Framework, all native images that you have created using Ngen.exe become invalid.</span></span> <span data-ttu-id="8e6ab-338">Per questo motivo, tutti gli aggiornamenti di .NET Framework eseguono il comando `Ngen Update` per assicurare che tutte le immagini native vengano rigenerate.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-338">For this reason, all updates of the .NET Framework execute the `Ngen Update` command, to ensure that all native images are regenerated.</span></span> <span data-ttu-id="8e6ab-339">.NET Framework crea automaticamente nuove immagini native per le librerie di .NET Framework installate.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-339">The .NET Framework automatically creates new native images for the .NET Framework libraries that it installs.</span></span>

- <span data-ttu-id="8e6ab-340">Versione del sistema operativo, se si è passati dalla famiglia Windows 9x alla famiglia Windows NT.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-340">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

     <span data-ttu-id="8e6ab-341">Se ad esempio la versione del sistema operativo in esecuzione su un computer passa da Windows 98 a Windows XP, tutte le immagini native archiviate nella cache delle immagini native non sono più valide.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-341">For example, if the version of the operating system running on a computer changes from Windows 98 to Windows XP, all native images stored in the native image cache become invalid.</span></span> <span data-ttu-id="8e6ab-342">Tuttavia, se si passa da Windows 2000 a Windows XP, le immagini continuano a essere valide.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-342">However, if the operating system changes from Windows 2000 to Windows XP, the images are not invalidated.</span></span>

- <span data-ttu-id="8e6ab-343">Identità esatta dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-343">The exact identity of the assembly.</span></span>

     <span data-ttu-id="8e6ab-344">Se si ricompila un assembly, l'immagine nativa corrispondente diventerà non valida.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-344">If you recompile an assembly, the assembly's corresponding native image becomes invalid.</span></span>

- <span data-ttu-id="8e6ab-345">Identità esatta di tutti gli assembly a cui fa riferimento l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-345">The exact identity of any assemblies the assembly references.</span></span>

     <span data-ttu-id="8e6ab-346">Se si aggiorna un assembly gestito, tutte le immagini native che dipendono direttamente o indirettamente dall'assembly in questione diventano non valide e devono essere rigenerate.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-346">If you update a managed assembly, all native images that directly or indirectly depend on that assembly become invalid and need to be regenerated.</span></span> <span data-ttu-id="8e6ab-347">Sono inclusi in tal senso i riferimenti ordinari e le dipendenze con associazione forte.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-347">This includes both ordinary references and hard-bound dependencies.</span></span> <span data-ttu-id="8e6ab-348">Ogni volta che viene applicato un aggiornamento software, il programma di installazione dovrebbe eseguire un comando `Ngen Update` per assicurare le rigenerazione di tutte le immagini native dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-348">Whenever a software update is applied, the installation program should execute an `Ngen Update` command to ensure that all dependent native images are regenerated.</span></span>

- <span data-ttu-id="8e6ab-349">Fattori di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-349">Security factors.</span></span>

     <span data-ttu-id="8e6ab-350">La modifica dei criteri di sicurezza del computer per limitare le autorizzazioni concesse in precedenza a un assembly può rendere non valida un'immagine nativa compilata in precedenza per l'assembly in questione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-350">Changing machine security policy to restrict permissions previously granted to an assembly can cause a previously compiled native image for that assembly to become invalid.</span></span>

     <span data-ttu-id="8e6ab-351">Per informazioni dettagliate sulla gestione della sicurezza dall'accesso di codice in Common Language Runtime e sull'uso delle autorizzazioni, vedere [Sicurezza dall'accesso di codice](../misc/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-351">For detailed information about how the common language runtime administers code access security and how to use permissions, see [Code Access Security](../misc/code-access-security.md).</span></span>

<a name="Troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="8e6ab-352">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="8e6ab-352">Troubleshooting</span></span>

<span data-ttu-id="8e6ab-353">Gli argomenti seguenti per la risoluzione dei problemi consentono di vedere quali immagini native vengono usate dall'applicazione e quali non possono essere usate da questa per determinare quando il compilatore JIT inizia a compilare un metodo. Illustrano anche come rifiutare esplicitamente la compilazione di immagini native di metodi specificati.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-353">The following troubleshooting topics allow you to see which native images are being used and which cannot be used by your application, to determine when the JIT compiler starts to compile a method, and shows how to opt out of native image compilation of specified methods.</span></span>

<a name="Fusion"></a>

### <a name="assembly-binding-log-viewer"></a><span data-ttu-id="8e6ab-354">Visualizzatore registro associazione assembly</span><span class="sxs-lookup"><span data-stu-id="8e6ab-354">Assembly Binding Log Viewer</span></span>

<span data-ttu-id="8e6ab-355">Per assicurarsi che le immagini native vengano usate dall'applicazione, è possibile usare lo strumento [Fuslogvw.exe (Visualizzatore log binding assembly)](fuslogvw-exe-assembly-binding-log-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-355">To confirm that native images are being used by your application, you can use the [Fuslogvw.exe (Assembly Binding Log Viewer)](fuslogvw-exe-assembly-binding-log-viewer.md).</span></span> <span data-ttu-id="8e6ab-356">Selezionare **Immagini native** nella casella **Categorie log** della finestra del visualizzatore dei log di binding.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-356">Select **Native Images** in the **Log Categories** box on the binding log viewer window.</span></span> <span data-ttu-id="8e6ab-357">Questo strumento fornisce informazioni sul motivo del rifiuto di un'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-357">Fuslogvw.exe provides information about why a native image was rejected.</span></span>

<a name="MDA"></a>

### <a name="the-jitcompilationstart-managed-debugging-assistant"></a><span data-ttu-id="8e6ab-358">Assistente al debug gestito JITCompilationStart</span><span class="sxs-lookup"><span data-stu-id="8e6ab-358">The JITCompilationStart managed debugging assistant</span></span>

<span data-ttu-id="8e6ab-359">È possibile usare l'assistente al debug gestito [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) per determinare quando il compilatore JIT inizia a compilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-359">You can use the [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) managed debugging assistant (MDA) to determine when the JIT compiler starts to compile a function.</span></span>

<a name="OptOut"></a>

### <a name="opting-out-of-native-image-generation"></a><span data-ttu-id="8e6ab-360">Rifiuto esplicito della generazione di immagini native</span><span class="sxs-lookup"><span data-stu-id="8e6ab-360">Opting out of native image generation</span></span>

<span data-ttu-id="8e6ab-361">In alcuni casi, NGen.exe può incontrare difficoltà nella generazione di un'immagine nativa per un metodo specifico oppure può essere preferibile compilare il metodo tramite JIT anziché compilarlo in un'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-361">In some cases, NGen.exe may have difficulty generating a native image for a specific method, or you may prefer that the method be JIT compiled rather then compiled to a native image.</span></span> <span data-ttu-id="8e6ab-362">In questo caso, è possibile usare l'attributo `System.Runtime.BypassNGenAttribute` per evitare che NGen.exe generi un'immagine nativa per un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-362">In this case, you can use the `System.Runtime.BypassNGenAttribute` attribute to prevent NGen.exe from generating a native image for a particular method.</span></span> <span data-ttu-id="8e6ab-363">L'attributo deve essere applicato singolarmente a ogni metodo di cui non si vuole includere il codice nell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-363">The attribute must be applied individually to each method whose code you do not want to include in the native image.</span></span> <span data-ttu-id="8e6ab-364">NGen.exe riconosce l'attributo e per il metodo corrispondente non genera codice nell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-364">NGen.exe recognizes the attribute and does not generate code in the native image for the corresponding method.</span></span>

<span data-ttu-id="8e6ab-365">Si noti tuttavia che `BypassNGenAttribute` non è definito come tipo nella libreria di classi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-365">Note, however, that `BypassNGenAttribute` is not defined as a type in the .NET Framework Class Library.</span></span> <span data-ttu-id="8e6ab-366">Per utilizzare l'attributo nel codice, è prima necessario definirlo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-366">In order to consume the attribute in your code, you must first define it as follows:</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#1)]
[!code-vb[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#1)]

<span data-ttu-id="8e6ab-367">È quindi possibile applicare l'attributo sulla base di ciascun metodo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-367">You can then apply the attribute on a per-method basis.</span></span> <span data-ttu-id="8e6ab-368">L'esempio seguente indica al generatore di immagini native di non generare un'immagine nativa per il metodo `ExampleClass.ToJITCompile`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-368">The following example instructs the Native Image Generator that it should not generate a native image for the `ExampleClass.ToJITCompile` method.</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#2)]
[!code-vb[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#2)]

## <a name="examples"></a><span data-ttu-id="8e6ab-369">Esempi</span><span class="sxs-lookup"><span data-stu-id="8e6ab-369">Examples</span></span>

<span data-ttu-id="8e6ab-370">Il comando che segue genera un'immagine nativa per `ClientApp.exe`, situato nella directory corrente, e la installa nella cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-370">The following command generates a native image for `ClientApp.exe`, located in the current directory, and installs the image in the native image cache.</span></span> <span data-ttu-id="8e6ab-371">Se esiste un file di configurazione per l'assembly, tale file verrà usato da Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-371">If a configuration file exists for the assembly, Ngen.exe uses it.</span></span> <span data-ttu-id="8e6ab-372">Vengono inoltre generate immagini native per gli eventuali file DLL a cui fa riferimento `ClientApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-372">In addition, native images are generated for any .dll files that `ClientApp.exe` references.</span></span>

```console
ngen install ClientApp.exe
```

<span data-ttu-id="8e6ab-373">Un'immagine installata con Ngen.exe viene anche detta radice.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-373">An image installed with Ngen.exe is also called a root.</span></span> <span data-ttu-id="8e6ab-374">Una radice può essere un'applicazione o un componente condiviso.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-374">A root can be an application or a shared component.</span></span>

<span data-ttu-id="8e6ab-375">Il comando che segue genera un'immagine nativa per `MyAssembly.exe` con il percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-375">The following command generates a native image for `MyAssembly.exe` with the specified path.</span></span>

```console
ngen install c:\myfiles\MyAssembly.exe
```

<span data-ttu-id="8e6ab-376">Per l'individuazione degli assembly e delle relative dipendenze, Ngen.exe usa la stessa logica di sondaggio usata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-376">When locating assemblies and their dependencies, Ngen.exe uses the same probing logic used by the common language runtime.</span></span> <span data-ttu-id="8e6ab-377">Per impostazione predefinita, la directory contenente `ClientApp.exe` viene usata come directory di base dell'applicazione e il sondaggio alla ricerca degli assembly inizia in questa directory.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-377">By default, the directory that contains `ClientApp.exe` is used as the application base directory, and all assembly probing begins in this directory.</span></span> <span data-ttu-id="8e6ab-378">È possibile sostituire questo comportamento usando l'opzione `/AppBase`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-378">You can override this behavior by using the `/AppBase` option.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-379">Si tratta di una variazione rispetto al comportamento di Ngen.exe in .NET Framework versioni 1.0 e 1.1, in cui la base dell'applicazione viene impostata sulla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-379">This is a change from Ngen.exe behavior in the .NET Framework versions 1.0 and 1.1, where the application base is set to the current directory.</span></span>

<span data-ttu-id="8e6ab-380">Un assembly può avere una dipendenza senza un riferimento, ad esempio se carica un file DLL usando il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-380">An assembly can have a dependency without a reference, for example if it loads a .dll file by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="8e6ab-381">È possibile creare un'immagine nativa per tale file usando le informazioni di configurazione dell'assembly dell'applicazione, con l'opzione `/ExeConfig`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-381">You can create a native image for such a .dll file by using configuration information for the application assembly, with the `/ExeConfig` option.</span></span> <span data-ttu-id="8e6ab-382">Il comando che segue genera un'immagine nativa per `MyLib.dll,` usando le informazioni di configurazione di `MyApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-382">The following command generates a native image for `MyLib.dll,` using the configuration information from `MyApp.exe`.</span></span>

```console
ngen install c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="8e6ab-383">Gli assembly installati con questa modalità non vengono rimossi se l'applicazione viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-383">Assemblies installed in this way are not removed when the application is removed.</span></span>

<span data-ttu-id="8e6ab-384">Per disinstallare una dipendenza, è necessario usare le stesse opzioni della riga di comando usate per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-384">To uninstall a dependency, use the same command-line options that were used to install it.</span></span> <span data-ttu-id="8e6ab-385">Il comando che segue disinstalla il file `MyLib.dll` dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-385">The following command uninstalls the `MyLib.dll` from the previous example.</span></span>

```console
ngen uninstall c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="8e6ab-386">Per creare un'immagine nativa per un assembly nella Global Assembly Cache, usare il nome visualizzato dell'assembly,</span><span class="sxs-lookup"><span data-stu-id="8e6ab-386">To create a native image for an assembly in the global assembly cache, use the display name of the assembly.</span></span> <span data-ttu-id="8e6ab-387">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-387">For example:</span></span>

```console
ngen install "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
```

<span data-ttu-id="8e6ab-388">Ngen.exe genera un set di immagini separato per ciascuno scenario installato.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-388">NGen.exe generates a separate set of images for each scenario you install.</span></span> <span data-ttu-id="8e6ab-389">I comandi che seguono, ad esempio, installano un set completo di immagini native per le normali operazioni, un altro set completo per il debug e un terzo per la profilatura:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-389">For example, the following commands install a complete set of native images for normal operation, another complete set for debugging, and a third for profiling:</span></span>

```console
ngen install MyApp.exe
ngen install MyApp.exe /debug
ngen install MyApp.exe /profile
```

### <a name="displaying-the-native-image-cache"></a><span data-ttu-id="8e6ab-390">Visualizzazione della cache delle immagini native</span><span class="sxs-lookup"><span data-stu-id="8e6ab-390">Displaying the Native Image Cache</span></span>

<span data-ttu-id="8e6ab-391">Una volta installate immagini native nella cache, è possibile visualizzarle usando Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-391">Once native images are installed in the cache, they can be displayed using Ngen.exe.</span></span> <span data-ttu-id="8e6ab-392">Il comando che segue visualizza tutte le immagini native presenti nella cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-392">The following command displays all native images in the native image cache.</span></span>

```console
ngen display
```

<span data-ttu-id="8e6ab-393">L'azione `display` elenca tutti gli assembly radice seguiti da un elenco di tutte le immagini native presenti sul computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-393">The `display` action lists all the root assemblies first, followed by a list of all the native images on the computer.</span></span>

<span data-ttu-id="8e6ab-394">Usare il nome semplice di un assembly per visualizzare soltanto le informazioni relative a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-394">Use the simple name of an assembly to display information only for that assembly.</span></span> <span data-ttu-id="8e6ab-395">Il comando che segue visualizza tutte le immagini native contenute nella cache delle immagini native corrispondenti al nome parziale `MyAssembly`, tutte le relative dipendenze e tutte le radici che dipendono da `MyAssembly`:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-395">The following command displays all native images in the native image cache that match the partial name `MyAssembly`, their dependencies, and all roots that have a dependency on `MyAssembly`:</span></span>

```console
ngen display MyAssembly
```

<span data-ttu-id="8e6ab-396">La possibilità di sapere quali radici dipendono da un assembly di un componente condiviso risulta utile per la valutazione dell'impatto di un'azione `update` dopo l'aggiornamento del componente condiviso.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-396">Knowing what roots depend on a shared component assembly is useful in gauging the impact of an `update` action after the shared component is upgraded.</span></span>

<span data-ttu-id="8e6ab-397">Se si specifica l'estensione di file di un assembly, è necessario specificare il percorso o eseguire Ngen.exe dalla directory contenente l'assembly:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-397">If you specify an assembly's file extension, you must either specify the path or execute Ngen.exe from the directory containing the assembly:</span></span>

```console
ngen display c:\myApps\MyAssembly.exe
```

<span data-ttu-id="8e6ab-398">Il comando che segue visualizza tutte le immagini native contenute nella cache delle immagini native con nome `MyAssembly` e versione 1.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-398">The following command displays all native images in the native image cache with the name `MyAssembly` and the version 1.0.0.0.</span></span>

```console
ngen display "myAssembly, version=1.0.0.0"
```

### <a name="updating-images"></a><span data-ttu-id="8e6ab-399">Aggiornamento delle immagini</span><span class="sxs-lookup"><span data-stu-id="8e6ab-399">Updating Images</span></span>

<span data-ttu-id="8e6ab-400">Le immagini in genere vengono aggiornate dopo l'aggiornamento di un componente condiviso.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-400">Images are typically updated after a shared component has been upgraded.</span></span> <span data-ttu-id="8e6ab-401">Per aggiornare tutte le immagini native modificate, o le cui dipendenze sono state modificate, usare l'azione `update` senza alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-401">To update all native images that have changed, or whose dependencies have changed, use the `update` action with no arguments.</span></span>

```console
ngen update
```

<span data-ttu-id="8e6ab-402">L'aggiornamento di tutte le immagini può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-402">Updating all images can be a lengthy process.</span></span> <span data-ttu-id="8e6ab-403">Per questo motivo, è possibile usare l'opzione `/queue` per accodare gli aggiornamenti in modo che vengano eseguiti dal servizio immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-403">You can queue the updates for execution by the native image service by using the `/queue` option.</span></span> <span data-ttu-id="8e6ab-404">Per altre informazioni sull'opzione `/queue` e sulle priorità di installazione, vedere [Servizio immagini native](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-404">For more information on the `/queue` option and installation priorities, see [Native Image Service](#native-image-service).</span></span>

```console
ngen update /queue
```

### <a name="uninstalling-images"></a><span data-ttu-id="8e6ab-405">Disinstallazione delle immagini</span><span class="sxs-lookup"><span data-stu-id="8e6ab-405">Uninstalling Images</span></span>

<span data-ttu-id="8e6ab-406">Poiché Ngen.exe mantiene un elenco di dipendenze, i componenti condivisi verranno rimossi solo quando saranno stati rimossi tutti gli assembly che dipendono da tali componenti.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-406">Ngen.exe maintains a list of dependencies, so that shared components are removed only when all assemblies that depend on them have been removed.</span></span> <span data-ttu-id="8e6ab-407">Inoltre, un componente condiviso installato come radice non verrà mai rimosso.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-407">In addition, a shared component is not removed if it has been installed as a root.</span></span>

<span data-ttu-id="8e6ab-408">Il comando che segue disinstalla tutti gli scenari per la radice `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-408">The following command uninstalls all scenarios for the root `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp
```

<span data-ttu-id="8e6ab-409">L'azione `uninstall` può essere usata per rimuovere scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-409">The `uninstall` action can be used to remove specific scenarios.</span></span> <span data-ttu-id="8e6ab-410">Il comando che segue disinstalla tutti gli scenari di debug per `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-410">The following command uninstalls all debug scenarios for `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp /debug
```

> [!NOTE]
> <span data-ttu-id="8e6ab-411">La disinstallazione degli scenari `/debug` non comporta la disinstallazione di uno scenario che include sia `/profile` che `/debug.`</span><span class="sxs-lookup"><span data-stu-id="8e6ab-411">Uninstalling `/debug` scenarios does not uninstall a scenario that includes both `/profile` and `/debug.`</span></span>

<span data-ttu-id="8e6ab-412">Il comando che segue disinstalla tutti gli scenari per una versione specifica di `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-412">The following command uninstalls all scenarios for a specific version of `ClientApp.exe`:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0"
```

<span data-ttu-id="8e6ab-413">I comandi che seguono disinstallano tutti gli scenari per `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` o semplicemente lo scenario di debug per tale assembly:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-413">The following commands uninstall all scenarios for `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` or just the debug scenario for that assembly:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL" /debug
```

<span data-ttu-id="8e6ab-414">Come con l'azione `install`, l'eventuale presenza dell'estensione richiede l'esecuzione di Ngen.exe dalla directory contenente l'assembly o la specifica di un percorso completo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-414">As with the `install` action, supplying an extension requires either executing Ngen.exe from the directory containing the assembly or specifying a full path.</span></span>

<span data-ttu-id="8e6ab-415">Per esempi relativi al servizio immagini native, vedere [Servizio immagini native](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-415">For examples relating to the native image service, see [Native Image Service](#native-image-service).</span></span>

## <a name="native-image-task"></a><span data-ttu-id="8e6ab-416">Attività di immagini native</span><span class="sxs-lookup"><span data-stu-id="8e6ab-416">Native Image Task</span></span>

<span data-ttu-id="8e6ab-417">L'attività di immagini native è un'attività di Windows che esegue automaticamente la generazione e la gestione delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-417">The native image task is a Windows task that generates and maintains native images.</span></span> <span data-ttu-id="8e6ab-418">L'attività di immagini native genera e recupera le immagini native automaticamente per gli scenari supportati</span><span class="sxs-lookup"><span data-stu-id="8e6ab-418">The native image task generates and reclaims native images automatically for supported scenarios.</span></span> <span data-ttu-id="8e6ab-419">Consente inoltre ai programmi di installazione di usare [NGen. exe (Generatore di immagini native)](ngen-exe-native-image-generator.md) per creare e aggiornare le immagini native a un'ora posticipata.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-419">It also enables installers to use [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md) to create and update native images at a deferred time.</span></span>

<span data-ttu-id="8e6ab-420">L'attività di immagini native viene registrata una volta per ogni architettura della CPU supportata in un computer, per consentire la compilazione di applicazioni destinate a ogni architettura:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-420">The native image task is registered once for each CPU architecture supported on a computer, to allow compilation for applications that target each architecture:</span></span>

|<span data-ttu-id="8e6ab-421">Nome dell'attività</span><span class="sxs-lookup"><span data-stu-id="8e6ab-421">Task name</span></span>|<span data-ttu-id="8e6ab-422">Computer a 32 bit</span><span class="sxs-lookup"><span data-stu-id="8e6ab-422">32-bit computer</span></span>|<span data-ttu-id="8e6ab-423">Computer a 64 bit</span><span class="sxs-lookup"><span data-stu-id="8e6ab-423">64-bit computer</span></span>|
|---------------|----------------------|----------------------|
|<span data-ttu-id="8e6ab-424">NET Framework NGEN v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="8e6ab-424">NET Framework NGEN v4.0.30319</span></span>|<span data-ttu-id="8e6ab-425">Sì</span><span class="sxs-lookup"><span data-stu-id="8e6ab-425">Yes</span></span>|<span data-ttu-id="8e6ab-426">Sì</span><span class="sxs-lookup"><span data-stu-id="8e6ab-426">Yes</span></span>|
|<span data-ttu-id="8e6ab-427">NET Framework NGEN v4.0.30319 64</span><span class="sxs-lookup"><span data-stu-id="8e6ab-427">NET Framework NGEN v4.0.30319 64</span></span>|<span data-ttu-id="8e6ab-428">No</span><span class="sxs-lookup"><span data-stu-id="8e6ab-428">No</span></span>|<span data-ttu-id="8e6ab-429">Sì</span><span class="sxs-lookup"><span data-stu-id="8e6ab-429">Yes</span></span>|

<span data-ttu-id="8e6ab-430">L'attività di immagine nativa è disponibile in .NET Framework 4.5 e versioni successive, se in esecuzione in Windows 8 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-430">The native image task is available in the .NET Framework 4.5 and later versions, when running on Windows 8 or later.</span></span> <span data-ttu-id="8e6ab-431">Nelle versioni precedenti di Windows, .NET Framework usa il [Servizio immagini native](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="8e6ab-431">On earlier versions of Windows, the .NET Framework uses the [Native Image Service](#native-image-service).</span></span>

### <a name="task-lifetime"></a><span data-ttu-id="8e6ab-432">Durata delle attività</span><span class="sxs-lookup"><span data-stu-id="8e6ab-432">Task Lifetime</span></span>

<span data-ttu-id="8e6ab-433">L'utilità di pianificazione di Windows avvia, in genere, l'attività delle immagini native ogni notte quando il computer è inattivo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-433">In general, the Windows Task Scheduler starts the native image task every night when the computer is idle.</span></span> <span data-ttu-id="8e6ab-434">L'attività controlla ogni lavoro posticipato che viene accodato dai programmi di installazione, eventuali richieste di aggiornamento di immagine nativa posticipate ed eventuali creazioni automatiche di immagini.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-434">The task checks for any deferred work that is queued by application installers, any deferred native image update requests, and any automatic image creation.</span></span> <span data-ttu-id="8e6ab-435">L'attività completa gli elementi di lavoro in sospeso e quindi viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-435">The task completes outstanding work items and then shuts down.</span></span> <span data-ttu-id="8e6ab-436">Se il computer diviene attivo mentre l'attività è in esecuzione, l'attività viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-436">If the computer stops being idle while the task is running, the task stops.</span></span>

<span data-ttu-id="8e6ab-437">È anche possibile avviare l'attività dell'immagine nativa manualmente tramite l'interfaccia utente dell'utilità di pianificazione o con chiamate manuali a NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-437">You can also start the native image task manually through the Task Scheduler UI or through manual calls to NGen.exe.</span></span> <span data-ttu-id="8e6ab-438">Se l'attività viene avviata con uno di questi metodi, essa continuerà l'esecuzione quando il computer non è più inattivo.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-438">If the task is started through either of these methods, it will continue running when the computer is no longer idle.</span></span> <span data-ttu-id="8e6ab-439">Le immagini create manualmente usando NGen.exe hanno priorità maggiore per abilitare il comportamento prevedibile dei programmi di installazione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-439">Images created manually by using NGen.exe are prioritized to enable predictable behavior for application installers.</span></span>

## <a name="native-image-service"></a><span data-ttu-id="8e6ab-440">Servizio immagini native</span><span class="sxs-lookup"><span data-stu-id="8e6ab-440">Native Image Service</span></span>

<span data-ttu-id="8e6ab-441">Il servizio immagini native è un servizio Windows che esegue automaticamente la generazione e la gestione delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-441">The native image service is a Windows service that generates and maintains native images.</span></span> <span data-ttu-id="8e6ab-442">Questo servizio consente allo sviluppatore di differire le azioni di installazione e aggiornamento delle immagini native in modo che vengano eseguite nei periodi di inattività del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-442">The native image service allows the developer to defer the installation and update of native images to periods when the computer is idle.</span></span>

<span data-ttu-id="8e6ab-443">Il servizio immagini native viene in genere avviato dal programma di installazione di un'applicazione o di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-443">Normally, the native image service is initiated by the installation program (installer) for an application or update.</span></span> <span data-ttu-id="8e6ab-444">Per le azioni con priorità 3, il servizio viene eseguito durante il periodo di inattività del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-444">For priority 3 actions, the service executes during idle time on the computer.</span></span> <span data-ttu-id="8e6ab-445">Lo stato del servizio viene salvato automaticamente e, se necessario, l'esecuzione può riprendere anche dopo il riavvio del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-445">The service saves its state and is capable of continuing through multiple reboots if necessary.</span></span> <span data-ttu-id="8e6ab-446">È supportato l'accodamento di più compilazioni di immagini.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-446">Multiple image compilations can be queued.</span></span>

<span data-ttu-id="8e6ab-447">Il servizio interagisce anche con il comando Ngen.exe manuale.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-447">The service also interacts with the manual Ngen.exe command.</span></span> <span data-ttu-id="8e6ab-448">I comandi manuali hanno priorità sull'attività in background.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-448">Manual commands take precedence over background activity.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ab-449">In Windows Vista il nome visualizzato per il servizio immagini native è "Microsoft.NET Framework NGEN v2.0.50727_X86" o "Microsoft.NET Framework NGEN v2.0.50727_X64".</span><span class="sxs-lookup"><span data-stu-id="8e6ab-449">On Windows Vista, the name displayed for the native image service is "Microsoft.NET Framework NGEN v2.0.50727_X86" or "Microsoft.NET Framework NGEN v2.0.50727_X64".</span></span> <span data-ttu-id="8e6ab-450">In tutte le versioni precedenti di Microsoft Windows il nome è ".NET Runtime Optimization Service v2.0.50727_X86" o ".NET Runtime Optimization Service v2.0.50727_X64".</span><span class="sxs-lookup"><span data-stu-id="8e6ab-450">On all earlier versions of Microsoft Windows, the name is ".NET Runtime Optimization Service v2.0.50727_X86" or ".NET Runtime Optimization Service v2.0.50727_X64".</span></span>

### <a name="launching-deferred-operations"></a><span data-ttu-id="8e6ab-451">Avvio delle azioni differite</span><span class="sxs-lookup"><span data-stu-id="8e6ab-451">Launching Deferred Operations</span></span>

<span data-ttu-id="8e6ab-452">Prima di iniziare un'azione di installazione o aggiornamento, è opportuno sospendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-452">Before beginning an installation or upgrade, pausing the service is recommended.</span></span> <span data-ttu-id="8e6ab-453">In questo modo si ha la garanzia che il servizio non venga eseguito durante la copia dei file o l'inserimento degli assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-453">This ensures that the service does not execute while the installer is copying files or putting assemblies in the global assembly cache.</span></span> <span data-ttu-id="8e6ab-454">Per sospendere l'esecuzione, usare il seguente comando di Ngen.exe:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-454">The following Ngen.exe command line pauses the service:</span></span>

```console
ngen queue pause
```

<span data-ttu-id="8e6ab-455">Quando tutte le azioni differite sono state accodate, il seguente comando consente di riprendere l'esecuzione del servizio:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-455">When all deferred operations have been queued, the following command allows the service to resume:</span></span>

```console
ngen queue continue
```

<span data-ttu-id="8e6ab-456">Per differire la generazione delle immagini native durante l'installazione di una nuova applicazione o l'aggiornamento di un componente condiviso, usare l'opzione `/queue` con le azioni `install` o `update`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-456">To defer native image generation when installing a new application or when updating a shared component, use the `/queue` option with the `install` or `update` actions.</span></span> <span data-ttu-id="8e6ab-457">Le seguenti stringhe di comando Ngen.exe determinano l'installazione di un'immagine nativa per un componente condiviso e l'esecuzione di un aggiornamento di tutte le radici che possono essere state modificate:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-457">The following Ngen.exe command lines install a native image for a shared component and perform an update of all roots that may have been affected:</span></span>

```console
ngen install MyComponent /queue
ngen update /queue
```

<span data-ttu-id="8e6ab-458">L'azione `update` rigenera tutte le immagini native che sono state invalidate, non solo quelle che usano `MyComponent`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-458">The `update` action regenerates all native images that have been invalidated, not just those that use `MyComponent`.</span></span>

<span data-ttu-id="8e6ab-459">Se l'applicazione è costituita da più radici, è possibile controllare la priorità delle azioni differite.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-459">If your application consists of many roots, you can control the priority of the deferred actions.</span></span> <span data-ttu-id="8e6ab-460">I comandi riportati di seguito consentono di accodare l'installazione di tre radici.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-460">The following commands queue the installation of three roots.</span></span> <span data-ttu-id="8e6ab-461">`Assembly1` viene installata per prima, senza attendere l'inattività del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-461">`Assembly1` is installed first, without waiting for idle time.</span></span> <span data-ttu-id="8e6ab-462">Anche `Assembly2` viene installata senza attendere l'inattività, ma dopo il completamento delle azioni con priorità 1.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-462">`Assembly2` is also installed without waiting for idle time, but after all priority 1 actions have completed.</span></span> <span data-ttu-id="8e6ab-463">`Assembly3` viene invece installata quando il servizio rileva lo stato di inattività del computer.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-463">`Assembly3` is installed when the service detects that the computer is idle.</span></span>

```console
ngen install Assembly1 /queue:1
ngen install Assembly2 /queue:2
ngen install Assembly3 /queue:3
```

<span data-ttu-id="8e6ab-464">È possibile imporre l'esecuzione simultanea delle azioni accodate usando `executeQueuedItems`.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-464">You can force queued actions to occur synchronously by using the `executeQueuedItems` action.</span></span> <span data-ttu-id="8e6ab-465">Se si specifica la priorità facoltativa, l'esecuzione simultanea ha effetto sulle azioni accodate con priorità uguale o inferiore.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-465">If you supply the optional priority, this action affects only the queued actions that have equal or lower priority.</span></span> <span data-ttu-id="8e6ab-466">La priorità predefinita è 3. Di conseguenza, il comando Ngen.exe riportato di seguito elabora immediatamente tutte le azioni accodate e non restituisce il controllo finché non sono completate:</span><span class="sxs-lookup"><span data-stu-id="8e6ab-466">The default priority is 3, so the following Ngen.exe command processes all queued actions immediately, and does not return until they are finished:</span></span>

```console
ngen executeQueuedItems
```

<span data-ttu-id="8e6ab-467">I comandi sincroni vengono eseguiti da Ngen.exe e non usano il servizio immagini native.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-467">Synchronous commands are executed by Ngen.exe and do not use the native image service.</span></span> <span data-ttu-id="8e6ab-468">È possibile eseguire azioni mediante Ngen.exe mentre il servizio immagini native è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-468">You can execute actions using Ngen.exe while the native image service is running.</span></span>

### <a name="service-shutdown"></a><span data-ttu-id="8e6ab-469">Chiusura del servizio</span><span class="sxs-lookup"><span data-stu-id="8e6ab-469">Service Shutdown</span></span>

<span data-ttu-id="8e6ab-470">Dopo l'avvio mediante l'esecuzione di un comando Ngen.exe con l'opzione `/queue`, il servizio viene eseguito in background finché tutte le azioni non sono state completate.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-470">After being initiated by the execution of an Ngen.exe command that includes the `/queue` option, the service runs in the background until all actions have been completed.</span></span> <span data-ttu-id="8e6ab-471">Lo stato del servizio viene salvato, in modo che l'esecuzione possa riprendere anche dopo vari riavvii del computer, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-471">The service saves its state so that it can continue through multiple reboots if necessary.</span></span> <span data-ttu-id="8e6ab-472">Quando viene rilevato che non sono più presenti azioni accodate, lo stato del servizio viene ripristinato per evitare che venga riavviato al successivo avvio del computer, quindi il servizio viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-472">When the service detects that there are no more actions queued, it resets its status so that it will not restart the next time the computer is booted, and then it shuts itself down.</span></span>

### <a name="service-interaction-with-clients"></a><span data-ttu-id="8e6ab-473">Interazione del servizio con i client</span><span class="sxs-lookup"><span data-stu-id="8e6ab-473">Service Interaction with Clients</span></span>

<span data-ttu-id="8e6ab-474">In .NET Framework versione 2.0 l'interazione con il servizio immagini native avviene solo tramite lo strumento da riga di comando Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-474">In the .NET Framework version 2.0, the only interaction with the native image service is through the command-line tool Ngen.exe.</span></span> <span data-ttu-id="8e6ab-475">Usare questo strumento negli script di installazione per accodare le azioni per il servizio immagini native e interagire con il servizio.</span><span class="sxs-lookup"><span data-stu-id="8e6ab-475">Use the command-line tool in installation scripts to queue actions for the native image service and to interact with the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e6ab-476">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e6ab-476">See also</span></span>

- [<span data-ttu-id="8e6ab-477">Strumenti</span><span class="sxs-lookup"><span data-stu-id="8e6ab-477">Tools</span></span>](index.md)
- [<span data-ttu-id="8e6ab-478">Processo di esecuzione gestita</span><span class="sxs-lookup"><span data-stu-id="8e6ab-478">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="8e6ab-479">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="8e6ab-479">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="8e6ab-480">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="8e6ab-480">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
