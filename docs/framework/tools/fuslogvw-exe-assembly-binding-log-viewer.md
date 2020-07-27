---
title: Fuslogvw.exe (Visualizzatore log associazioni assembly)
description: Utilizzare Fuslogvw.exe, il Visualizzatore log associazioni assembly. Questo visualizzatore mostra i dettagli dell'associazione di assembly, che consentono di diagnosticare il motivo per cui .NET non riesce a trovare un assembly in fase di esecuzione.
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: 949f9cf98d5eb4e100be9837be120038f085cc40
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167118"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a><span data-ttu-id="26579-104">Fuslogvw.exe (Visualizzatore log associazioni assembly)</span><span class="sxs-lookup"><span data-stu-id="26579-104">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>

<span data-ttu-id="26579-105">Il Visualizzatore log associazione assembly consente di visualizzare i dettagli relativi alle associazioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="26579-105">The Assembly Binding Log Viewer displays details for assembly binds.</span></span> <span data-ttu-id="26579-106">Queste informazioni facilitano la diagnosi delle cause dell'impossibilità di individuare un assembly in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="26579-106">This information helps you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span> <span data-ttu-id="26579-107">Questi errori sono generalmente dovuti alla distribuzione di un assembly nel percorso errato, a un'immagine nativa che non è più valida o a una mancata corrispondenza di numeri di versione o impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="26579-107">These failures are usually the result of an assembly deployed to the wrong location, a native image that is no longer valid, or a mismatch in version numbers or cultures.</span></span> <span data-ttu-id="26579-108">L'impossibilità da parte di Common Language Runtime di individuare un assembly produce generalmente un'eccezione <xref:System.TypeLoadException> nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26579-108">The common language runtime's failure to locate an assembly typically shows up as a <xref:System.TypeLoadException> in your application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26579-109">È necessario eseguire fuslogvw.exe con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="26579-109">You must run fuslogvw.exe with administrator privileges.</span></span>

<span data-ttu-id="26579-110">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="26579-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="26579-111">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio o il prompt dei comandi di Visual Studio in Windows 7 con credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="26579-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7) with administrator credentials.</span></span> <span data-ttu-id="26579-112">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="26579-112">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="26579-113">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="26579-113">At the command prompt, type the following:</span></span>

```console
fuslogvw
```

<span data-ttu-id="26579-114">Nel visualizzatore è riportata una voce per ciascuna associazione di assembly non riuscita.</span><span class="sxs-lookup"><span data-stu-id="26579-114">The viewer displays an entry for each failed assembly bind.</span></span> <span data-ttu-id="26579-115">Per ciascun errore vengono descritti l'applicazione che ha avviato l'associazione, l'assembly interessato, inclusi il nome, la versione, le impostazioni cultura e la chiave pubblica, nonché la data e l'ora dell'errore.</span><span class="sxs-lookup"><span data-stu-id="26579-115">For each failure, the viewer describes the application that initiated the bind; the assembly the bind is for, including name, version, culture and public key; and the date and time of the failure.</span></span>

### <a name="to-change-the-log-location-view"></a><span data-ttu-id="26579-116">Per modificare la visualizzazione del percorso del file di log</span><span class="sxs-lookup"><span data-stu-id="26579-116">To change the log location view</span></span>

1. <span data-ttu-id="26579-117">Selezionare il pulsante di opzione **Predefinito** per visualizzare gli errori di associazione per tutti i tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="26579-117">Select the **Default** option button to view bind failures for all application types.</span></span> <span data-ttu-id="26579-118">Per impostazione predefinita, le voci di log vengono archiviate in directory specifiche per utente su disco, nella cache wininet.</span><span class="sxs-lookup"><span data-stu-id="26579-118">By default, log entries are stored in per-user directories on disk in the wininet cache.</span></span>

2. <span data-ttu-id="26579-119">Selezionare il pulsante di opzione **Personalizzato** per visualizzare gli errori di associazione in una directory personalizzata specificata.</span><span class="sxs-lookup"><span data-stu-id="26579-119">Select the **Custom** option button to view bind failures in a custom directory that you specify.</span></span> <span data-ttu-id="26579-120">È necessario specificare il percorso personalizzato in cui il runtime deve archiviare i log impostando il percorso di log personalizzato su un nome di directory valido nella finestra di dialogo **Impostazioni log**.</span><span class="sxs-lookup"><span data-stu-id="26579-120">You must specify the custom location where you want the runtime to store the logs by setting the custom log location in the **Log Settings** dialog to a valid directory name.</span></span> <span data-ttu-id="26579-121">Tale directory deve essere pulita e contenere solo file generati dal runtime.</span><span class="sxs-lookup"><span data-stu-id="26579-121">This directory should be clean, and only contain files that the runtime generates.</span></span> <span data-ttu-id="26579-122">Se contiene un file eseguibile che genera un errore da registrare, l'errore non verrà registrato poiché lo strumento cercherà di creare una directory con lo stesso nome del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="26579-122">If it contains an executable that generates a failure to be logged, the failure will not be logged because the tool tries to create a directory with the same name as the executable.</span></span> <span data-ttu-id="26579-123">Inoltre, il tentativo di esecuzione di un eseguibile dal percorso del log avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="26579-123">In addition, an attempt to run an executable from the log location will fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26579-124">È preferibile usare il percorso di associazione predefinito anziché quello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="26579-124">The default bind location is preferable to the custom bind location.</span></span> <span data-ttu-id="26579-125">Il runtime archivia il percorso di associazione predefinito nella cache WinInet e pertanto lo pulisce automaticamente. Se si specifica un percorso di binding personalizzato, l'utente è responsabile della pulizia.</span><span class="sxs-lookup"><span data-stu-id="26579-125">The runtime stores the default bind location in the wininet cache, and therefore automatically cleans it out. If you specify a custom bind location, you are responsible for cleaning it out.</span></span>

### <a name="to-view-details-about-a-specific-failure"></a><span data-ttu-id="26579-126">Per visualizzare i dettagli relativi a un errore specifico</span><span class="sxs-lookup"><span data-stu-id="26579-126">To view details about a specific failure</span></span>

1. <span data-ttu-id="26579-127">Nel visualizzatore selezionare il nome dell'applicazione dalla voce desiderata.</span><span class="sxs-lookup"><span data-stu-id="26579-127">Select the application name of the desired entry in the viewer.</span></span>

2. <span data-ttu-id="26579-128">Fare clic sul pulsante **Visualizza file di log**.</span><span class="sxs-lookup"><span data-stu-id="26579-128">Click the **View Log** button.</span></span> <span data-ttu-id="26579-129">In alternativa è possibile fare doppio clic sulla voce selezionata.</span><span class="sxs-lookup"><span data-stu-id="26579-129">Alternately, you can double-click the selected entry.</span></span>

    <span data-ttu-id="26579-130">Vengono visualizzati i seguenti dettagli relativi all'errore di associazione selezionato:</span><span class="sxs-lookup"><span data-stu-id="26579-130">The tool displays the following details about the selected bind failure:</span></span>

    - <span data-ttu-id="26579-131">Causa specifica dell'errore, ad esempio irreperibilità del file o versioni non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="26579-131">The specific reason the bind failed, such as "file not found" or "version mismatch".</span></span>

    - <span data-ttu-id="26579-132">Informazioni sull'applicazione con cui è stata avviata l'associazione, inclusi il nome, la directory radice dell'applicazione (AppBase) e una descrizione del percorso di ricerca privato, se presente.</span><span class="sxs-lookup"><span data-stu-id="26579-132">Information about the application that initiated the bind, including its name, the application's root directory (AppBase), and a description of the private search path, if there is one.</span></span>

    - <span data-ttu-id="26579-133">Identità dell'assembly cercato.</span><span class="sxs-lookup"><span data-stu-id="26579-133">The identity of the assembly the tool is looking for.</span></span>

    - <span data-ttu-id="26579-134">Descrizione dei criteri di controllo delle versioni applicati a livello di applicazione, editore o amministratore.</span><span class="sxs-lookup"><span data-stu-id="26579-134">A description of any Application, Publisher, or Administrator version policies that have been applied.</span></span>

    - <span data-ttu-id="26579-135">Provenienza o meno dell'assembly dalla [Global Assembly Cache](../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="26579-135">Whether the assembly was found in the [global assembly cache](../app-domains/gac.md).</span></span>

    - <span data-ttu-id="26579-136">Elenco di tutti gli URL di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="26579-136">A list of all probing URLs.</span></span>

<span data-ttu-id="26579-137">Nell'esempio seguente viene illustrata una voce di log in cui sono visualizzate informazioni dettagliate su un'associazione di assembly non riuscita.</span><span class="sxs-lookup"><span data-stu-id="26579-137">The following sample log entry shows detailed information about a failed assembly bind.</span></span>

```output
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe
--- A detailed error log follows.

=== Pre-bind state information ===
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
 (Fully-specified)
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\
LOG: Initial PrivatePath = NULL
LOG: Dynamic Base = NULL
LOG: Cache Base = NULL
LOG: AppName = NULL
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
===

LOG: Processing DEVPATH.
LOG: DEVPATH is not set. Falling through to regular bind.
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.
LOG: All probing URLs attempted and failed.
```

### <a name="to-delete-a-single-entry-from-the-log"></a><span data-ttu-id="26579-138">Per eliminare una singola voce dal log</span><span class="sxs-lookup"><span data-stu-id="26579-138">To delete a single entry from the log</span></span>

1. <span data-ttu-id="26579-139">Selezionare una voce nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="26579-139">Select an entry in the viewer.</span></span>

2. <span data-ttu-id="26579-140">Fare clic sul pulsante **Elimina voce**.</span><span class="sxs-lookup"><span data-stu-id="26579-140">Click the **Delete Entry** button.</span></span>

### <a name="to-delete-all-entries-from-the-log"></a><span data-ttu-id="26579-141">Per eliminare tutte le voci dal log</span><span class="sxs-lookup"><span data-stu-id="26579-141">To delete all entries from the log</span></span>

- <span data-ttu-id="26579-142">Fare clic sul pulsante **Elimina tutto**.</span><span class="sxs-lookup"><span data-stu-id="26579-142">Click the **Delete All** button.</span></span>

### <a name="to-refresh-the-user-interface"></a><span data-ttu-id="26579-143">Per aggiornare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="26579-143">To refresh the user interface</span></span>

- <span data-ttu-id="26579-144">Fare clic sul pulsante **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="26579-144">Click the **Refresh** button.</span></span> <span data-ttu-id="26579-145">Il visualizzatore non rileva automaticamente le nuove voci di log mentre è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="26579-145">The viewer does not automatically detect new log entries while it is running.</span></span> <span data-ttu-id="26579-146">Per visualizzarle è necessario scegliere il pulsante **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="26579-146">You must use the **Refresh** button to display them.</span></span>

### <a name="to-change-the-log-settings"></a><span data-ttu-id="26579-147">Per modificare le impostazioni di log</span><span class="sxs-lookup"><span data-stu-id="26579-147">To change the log settings</span></span>

- <span data-ttu-id="26579-148">Scegliere il pulsante **Impostazioni** per aprire la finestra di dialogo **Impostazioni log**.</span><span class="sxs-lookup"><span data-stu-id="26579-148">Click the **Settings** button to open the **Log Settings** dialog.</span></span>

### <a name="to-view-the-about-dialog"></a><span data-ttu-id="26579-149">Per visualizzare la finestra di dialogo Informazioni su</span><span class="sxs-lookup"><span data-stu-id="26579-149">To view the About dialog</span></span>

- <span data-ttu-id="26579-150">Fare clic sul pulsante **Informazioni su**.</span><span class="sxs-lookup"><span data-stu-id="26579-150">Click the **About** button.</span></span>

## <a name="binding-logs-for-native-images"></a><span data-ttu-id="26579-151">Log di associazioni per immagini native</span><span class="sxs-lookup"><span data-stu-id="26579-151">Binding Logs for Native Images</span></span>

<span data-ttu-id="26579-152">Per impostazione predefinita, Fuslogvw.exe registra le normali richieste di associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="26579-152">By default, Fuslogvw.exe logs normal assembly bind requests.</span></span> <span data-ttu-id="26579-153">In alternativa, è possibile registrare le associazioni di assembly per le immagini native create usando [Ngen.exe (generatore di immagini native)](ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="26579-153">Alternatively, you can log assembly binds for native images that were created using the [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md).</span></span>

#### <a name="to-log-assembly-binds-for-native-images"></a><span data-ttu-id="26579-154">Per registrare le associazioni di assembly per le immagini native</span><span class="sxs-lookup"><span data-stu-id="26579-154">To log assembly binds for native images</span></span>

- <span data-ttu-id="26579-155">Nel gruppo **Categorie log**, selezionare il pulsante di opzione **Immagini native**.</span><span class="sxs-lookup"><span data-stu-id="26579-155">In the **Log Categories** group, select the **Native Images** option button.</span></span>

<span data-ttu-id="26579-156">Nel log seguente viene riportato un errore causato da una dipendenza inesistente nel momento in cui è stata creata l'immagine nativa per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26579-156">The following log shows a failure caused by a dependency that did not exist when the native image was created for the application.</span></span> <span data-ttu-id="26579-157">Se le dipendenze in fase di esecuzione differiscono dalle dipendenze durante l'esecuzione di Ngen.exe, l'associazione a un'immagine nativa non è consentita.</span><span class="sxs-lookup"><span data-stu-id="26579-157">If the dependencies at run time differ from the dependencies when Ngen.exe is run, binding to a native image is not allowed.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\App.exe
--- A detailed error log follows.

LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\App.exe.
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.
WRN: No matching native image found.
LOG: Bind to native image assembly did not succeed. Use IL image.
```

<span data-ttu-id="26579-158">Nel log seguente viene riportato un errore di associazione dell'immagine nativa che si è verificato perché le impostazioni di sicurezza del computer nel momento in cui è stata eseguita l'applicazione erano diverse da quelle impostate al momento della creazione dell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="26579-158">The following log shows a native image binding failure that occurred because the security settings on the computer when the application was run were different from the security settings at the time the native image was created.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***

The operation failed.
Bind result: hr = 0x80004005. Unspecified error

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\Application101622.exe
--- A detailed error log follows.

LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\Application101622.exe.
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Dependency evaluation succeeded.
LOG: Validation of dependencies succeeded.
LOG: Start loading all the dependencies into load context.
LOG: Loading of dependencies succeeded.
LOG: Bind to native image succeeded.
Native image has correct version information.
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.
Discarding native image.
```

## <a name="the-log-settings-dialog"></a><span data-ttu-id="26579-159">Finestra di dialogo Impostazioni log</span><span class="sxs-lookup"><span data-stu-id="26579-159">The Log Settings Dialog</span></span>

<span data-ttu-id="26579-160">È possibile usare la finestra di dialogo **Impostazioni log** per effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="26579-160">You can use the **Log Settings** dialog to perform the following actions.</span></span>

#### <a name="to-disable-logging"></a><span data-ttu-id="26579-161">Per disabilitare la registrazione</span><span class="sxs-lookup"><span data-stu-id="26579-161">To disable logging</span></span>

- <span data-ttu-id="26579-162">Selezionare il pulsante di opzione **Log disattivato**.</span><span class="sxs-lookup"><span data-stu-id="26579-162">Select the **Log disabled** option button.</span></span>  <span data-ttu-id="26579-163">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="26579-163">Note that this option is selected by default.</span></span>

#### <a name="to-log-assembly-binds-in-exceptions"></a><span data-ttu-id="26579-164">Per registrare le associazioni di assembly in eccezioni</span><span class="sxs-lookup"><span data-stu-id="26579-164">To log assembly binds in exceptions</span></span>

- <span data-ttu-id="26579-165">Selezionare il pulsante di opzione **Registra nel testo dell'eccezione**.</span><span class="sxs-lookup"><span data-stu-id="26579-165">Select the **Log in exception text** option button.</span></span> <span data-ttu-id="26579-166">Solo le informazioni meno dettagliate del log Fusion vengono registrate nel testo dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="26579-166">Only the least detailed fusion log information is logged in exception text.</span></span> <span data-ttu-id="26579-167">Per visualizzare le informazioni complete, usare una delle altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="26579-167">To view full information, use one of the other settings.</span></span>

  <span data-ttu-id="26579-168">Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="26579-168">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-assembly-bind-failures"></a><span data-ttu-id="26579-169">Per registrare gli errori di associazione di assembly</span><span class="sxs-lookup"><span data-stu-id="26579-169">To log assembly bind failures</span></span>

- <span data-ttu-id="26579-170">Selezionare il pulsante di opzione **Registra errori di associazione su disco**.</span><span class="sxs-lookup"><span data-stu-id="26579-170">Select the **Log bind failures to disk** option button.</span></span>

  <span data-ttu-id="26579-171">Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="26579-171">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-all-assembly-binds"></a><span data-ttu-id="26579-172">Per registrare tutte le associazioni di assembly</span><span class="sxs-lookup"><span data-stu-id="26579-172">To log all assembly binds</span></span>

- <span data-ttu-id="26579-173">Selezionare il pulsante di opzione **Registra tutte le associazioni su disco**.</span><span class="sxs-lookup"><span data-stu-id="26579-173">Select the **Log all binds to disk** option button.</span></span>

  <span data-ttu-id="26579-174">Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="26579-174">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26579-175">Quando un assembly viene caricato come indipendente dal dominio, ad esempio impostando la proprietà <xref:System.AppDomainSetup.LoaderOptimization%2A> su <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> o <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, l'abilitazione della registrazione può determinare una perdita di memoria in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="26579-175">When an assembly is loaded as domain neutral, for example by setting the <xref:System.AppDomainSetup.LoaderOptimization%2A> property to <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> or <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, turning on logging might leak memory in some cases.</span></span> <span data-ttu-id="26579-176">Ciò può verificarsi se si crea una voce di log quando in un dominio applicazione viene caricato un modulo indipendente dal dominio e successivamente il dominio applicazione viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="26579-176">This can happen if a log entry is made when a domain-neutral module is loaded into an application domain, and later the application domain is unloaded.</span></span> <span data-ttu-id="26579-177">È possibile che la voce di log non venga rilasciata fino alla fine del processo.</span><span class="sxs-lookup"><span data-stu-id="26579-177">The log entry might not be released until the process ends.</span></span> <span data-ttu-id="26579-178">Alcuni debugger prevedono l'abilitazione automatica della registrazione.</span><span class="sxs-lookup"><span data-stu-id="26579-178">Some debuggers automatically turn on logging.</span></span>

#### <a name="to-enable-a-custom-log-path"></a><span data-ttu-id="26579-179">Per impostare un percorso di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="26579-179">To enable a custom log path</span></span>

1. <span data-ttu-id="26579-180">Selezionare il pulsante di opzione **Attiva percorso personalizzato log**.</span><span class="sxs-lookup"><span data-stu-id="26579-180">Select the **Enable custom log path** option button.</span></span>

2. <span data-ttu-id="26579-181">Immettere il percorso nella casella di testo **Percorso personalizzato log**.</span><span class="sxs-lookup"><span data-stu-id="26579-181">Enter the path into the **Custom log path** text box.</span></span>

> [!NOTE]
> <span data-ttu-id="26579-182">Per l'archiviazione del log associazioni del [visualizzatore log associazioni assembly (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) viene usata la cache di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="26579-182">The [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) uses the Internet Explorer (IE) cache to store its binding log.</span></span> <span data-ttu-id="26579-183">In seguito al danneggiamento occasionale della cache di Internet Explorer, è possibile che nella finestra di visualizzazione del [visualizzatore log associazioni assembly (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) non siano visualizzati i nuovi log associazioni.</span><span class="sxs-lookup"><span data-stu-id="26579-183">Due to occasional corruption in the IE cache, the [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) can sometimes stop showing new binding logs in the viewing window.</span></span> <span data-ttu-id="26579-184">In tali circostanze l'infrastruttura di associazione di .NET (fusion) non è in grado di eseguire operazioni di scrittura o lettura dal log associazioni.</span><span class="sxs-lookup"><span data-stu-id="26579-184">As a result of this corruption, the .NET binding infrastructure (fusion) cannot write to or read from the binding log.</span></span> <span data-ttu-id="26579-185">Questo problema non viene rilevato se si usa un percorso di log personalizzato.  Per correggere il danneggiamento e consentire a Fusion di visualizzare di nuovo i log di binding, deselezionare la cache IE eliminando i file Internet temporanei dall'interno della finestra di dialogo Opzioni Internet di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="26579-185">(This issue is not encountered if you use a custom log path.)  To fix the corruption and allow fusion to show binding logs again, clear the IE cache by deleting temporary internet files from within the IE Internet Options dialog.</span></span>
>
> <span data-ttu-id="26579-186">Se l'applicazione non gestita ospita Common Language Runtime mediante l'implementazione delle interfacce `IHostAssemblyManager` e `IHostAssemblyStore`, le voci di logo non possono essere archiviate nella cache wininet.</span><span class="sxs-lookup"><span data-stu-id="26579-186">If your unmanaged application hosts the common language runtime by implementing the `IHostAssemblyManager` and `IHostAssemblyStore` interfaces, log entries can't be stored in the wininet cache.</span></span>  <span data-ttu-id="26579-187">Per visualizzare le voci di log di host personalizzati che implementano tali interfacce, è necessario specificare un percorso alternativo per il log.</span><span class="sxs-lookup"><span data-stu-id="26579-187">To view log entries for custom hosts that implement these interfaces, you must specify an alternate log path.</span></span>

#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a><span data-ttu-id="26579-188">Per abilitare la registrazione per le app eseguite nel contenitore delle app Windows</span><span class="sxs-lookup"><span data-stu-id="26579-188">To enable logging for apps running in the Windows app container</span></span>

1. <span data-ttu-id="26579-189">Abilitare un percorso di log personalizzato come descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="26579-189">Enable a custom log path, as described in the previous procedure.</span></span> <span data-ttu-id="26579-190">Per impostazione predefinita, le app eseguite nel contenitore delle app Windows dispongono di accesso limitato al disco rigido.</span><span class="sxs-lookup"><span data-stu-id="26579-190">By default, apps that are running in the Windows app container have limited access to the hard disk.</span></span> <span data-ttu-id="26579-191">La directory specificata disporrà di accesso in lettura/scrittura su tutte le app nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="26579-191">The directory you specify will have read/write access for all apps in the app container.</span></span>

2. <span data-ttu-id="26579-192">Selezionare la casella di controllo **Abilita registrazione immersiva**.</span><span class="sxs-lookup"><span data-stu-id="26579-192">Select the **Enable immersive logging** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26579-193">Questa casella è abilitata solo in Windows 8 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="26579-193">This box is enabled only on Windows 8 or later.</span></span>

## <a name="see-also"></a><span data-ttu-id="26579-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26579-194">See also</span></span>

- <xref:System.TypeLoadException>
- [<span data-ttu-id="26579-195">Strumenti</span><span class="sxs-lookup"><span data-stu-id="26579-195">Tools</span></span>](index.md)
- [<span data-ttu-id="26579-196">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="26579-196">Global Assembly Cache</span></span>](../app-domains/gac.md)
- [<span data-ttu-id="26579-197">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="26579-197">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="26579-198">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="26579-198">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
