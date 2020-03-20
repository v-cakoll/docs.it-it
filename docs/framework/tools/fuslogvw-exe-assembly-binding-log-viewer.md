---
title: Fuslogvw.exe (Visualizzatore log associazioni assembly)
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: 2f0018dca6e5add2c5bc531103a4078307a8c8c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73129852"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a><span data-ttu-id="b490f-102">Fuslogvw.exe (Visualizzatore log associazioni assembly)</span><span class="sxs-lookup"><span data-stu-id="b490f-102">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>

<span data-ttu-id="b490f-103">Il Visualizzatore log associazione assembly consente di visualizzare i dettagli relativi alle associazioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="b490f-103">The Assembly Binding Log Viewer displays details for assembly binds.</span></span> <span data-ttu-id="b490f-104">Queste informazioni facilitano la diagnosi delle cause dell'impossibilità di individuare un assembly in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b490f-104">This information helps you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span> <span data-ttu-id="b490f-105">Questi errori sono generalmente dovuti alla distribuzione di un assembly nel percorso errato, a un'immagine nativa che non è più valida o a una mancata corrispondenza di numeri di versione o impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="b490f-105">These failures are usually the result of an assembly deployed to the wrong location, a native image that is no longer valid, or a mismatch in version numbers or cultures.</span></span> <span data-ttu-id="b490f-106">L'impossibilità da parte di Common Language Runtime di individuare un assembly produce generalmente un'eccezione <xref:System.TypeLoadException> nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b490f-106">The common language runtime's failure to locate an assembly typically shows up as a <xref:System.TypeLoadException> in your application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b490f-107">È necessario eseguire fuslogvw.exe con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b490f-107">You must run fuslogvw.exe with administrator privileges.</span></span>

<span data-ttu-id="b490f-108">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b490f-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="b490f-109">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio o il prompt dei comandi di Visual Studio in Windows 7 con credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b490f-109">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7) with administrator credentials.</span></span> <span data-ttu-id="b490f-110">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b490f-110">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="b490f-111">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b490f-111">At the command prompt, type the following:</span></span>

```console
fuslogvw
```

<span data-ttu-id="b490f-112">Nel visualizzatore è riportata una voce per ciascuna associazione di assembly non riuscita.</span><span class="sxs-lookup"><span data-stu-id="b490f-112">The viewer displays an entry for each failed assembly bind.</span></span> <span data-ttu-id="b490f-113">Per ciascun errore vengono descritti l'applicazione che ha avviato l'associazione, l'assembly interessato, inclusi il nome, la versione, le impostazioni cultura e la chiave pubblica, nonché la data e l'ora dell'errore.</span><span class="sxs-lookup"><span data-stu-id="b490f-113">For each failure, the viewer describes the application that initiated the bind; the assembly the bind is for, including name, version, culture and public key; and the date and time of the failure.</span></span>

### <a name="to-change-the-log-location-view"></a><span data-ttu-id="b490f-114">Per modificare la visualizzazione del percorso del file di log</span><span class="sxs-lookup"><span data-stu-id="b490f-114">To change the log location view</span></span>

1. <span data-ttu-id="b490f-115">Selezionare il pulsante di opzione **Predefinito** per visualizzare gli errori di associazione per tutti i tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="b490f-115">Select the **Default** option button to view bind failures for all application types.</span></span> <span data-ttu-id="b490f-116">Per impostazione predefinita, le voci di log vengono archiviate in directory specifiche per utente su disco, nella cache wininet.</span><span class="sxs-lookup"><span data-stu-id="b490f-116">By default, log entries are stored in per-user directories on disk in the wininet cache.</span></span>

2. <span data-ttu-id="b490f-117">Selezionare il pulsante di opzione **Personalizzato** per visualizzare gli errori di associazione in una directory personalizzata specificata.</span><span class="sxs-lookup"><span data-stu-id="b490f-117">Select the **Custom** option button to view bind failures in a custom directory that you specify.</span></span> <span data-ttu-id="b490f-118">È necessario specificare il percorso personalizzato in cui il runtime deve archiviare i log impostando il percorso di log personalizzato su un nome di directory valido nella finestra di dialogo **Impostazioni log**.</span><span class="sxs-lookup"><span data-stu-id="b490f-118">You must specify the custom location where you want the runtime to store the logs by setting the custom log location in the **Log Settings** dialog to a valid directory name.</span></span> <span data-ttu-id="b490f-119">Tale directory deve essere pulita e contenere solo file generati dal runtime.</span><span class="sxs-lookup"><span data-stu-id="b490f-119">This directory should be clean, and only contain files that the runtime generates.</span></span> <span data-ttu-id="b490f-120">Se contiene un file eseguibile che genera un errore da registrare, l'errore non verrà registrato poiché lo strumento cercherà di creare una directory con lo stesso nome del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="b490f-120">If it contains an executable that generates a failure to be logged, the failure will not be logged because the tool tries to create a directory with the same name as the executable.</span></span> <span data-ttu-id="b490f-121">Inoltre, il tentativo di esecuzione di un eseguibile dal percorso del log avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b490f-121">In addition, an attempt to run an executable from the log location will fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b490f-122">È preferibile usare il percorso di associazione predefinito anziché quello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b490f-122">The default bind location is preferable to the custom bind location.</span></span> <span data-ttu-id="b490f-123">Il runtime archivia il percorso di associazione predefinito nella cache wininet e pertanto lo elimina automaticamente. Se si specifica un percorso di associazione personalizzato, si è responsabili della pulizia.</span><span class="sxs-lookup"><span data-stu-id="b490f-123">The runtime stores the default bind location in the wininet cache, and therefore automatically cleans it out. If you specify a custom bind location, you are responsible for cleaning it out.</span></span>

### <a name="to-view-details-about-a-specific-failure"></a><span data-ttu-id="b490f-124">Per visualizzare i dettagli relativi a un errore specifico</span><span class="sxs-lookup"><span data-stu-id="b490f-124">To view details about a specific failure</span></span>

1. <span data-ttu-id="b490f-125">Nel visualizzatore selezionare il nome dell'applicazione dalla voce desiderata.</span><span class="sxs-lookup"><span data-stu-id="b490f-125">Select the application name of the desired entry in the viewer.</span></span>

2. <span data-ttu-id="b490f-126">Fare clic sul pulsante **Visualizza file di log**.</span><span class="sxs-lookup"><span data-stu-id="b490f-126">Click the **View Log** button.</span></span> <span data-ttu-id="b490f-127">In alternativa è possibile fare doppio clic sulla voce selezionata.</span><span class="sxs-lookup"><span data-stu-id="b490f-127">Alternately, you can double-click the selected entry.</span></span>

    <span data-ttu-id="b490f-128">Vengono visualizzati i seguenti dettagli relativi all'errore di associazione selezionato:</span><span class="sxs-lookup"><span data-stu-id="b490f-128">The tool displays the following details about the selected bind failure:</span></span>

    - <span data-ttu-id="b490f-129">Causa specifica dell'errore, ad esempio irreperibilità del file o versioni non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b490f-129">The specific reason the bind failed, such as "file not found" or "version mismatch".</span></span>

    - <span data-ttu-id="b490f-130">Informazioni sull'applicazione con cui è stata avviata l'associazione, inclusi il nome, la directory radice dell'applicazione (AppBase) e una descrizione del percorso di ricerca privato, se presente.</span><span class="sxs-lookup"><span data-stu-id="b490f-130">Information about the application that initiated the bind, including its name, the application's root directory (AppBase), and a description of the private search path, if there is one.</span></span>

    - <span data-ttu-id="b490f-131">Identità dell'assembly cercato.</span><span class="sxs-lookup"><span data-stu-id="b490f-131">The identity of the assembly the tool is looking for.</span></span>

    - <span data-ttu-id="b490f-132">Descrizione dei criteri di controllo delle versioni applicati a livello di applicazione, editore o amministratore.</span><span class="sxs-lookup"><span data-stu-id="b490f-132">A description of any Application, Publisher, or Administrator version policies that have been applied.</span></span>

    - <span data-ttu-id="b490f-133">Provenienza o meno dell'assembly dalla [Global Assembly Cache](../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="b490f-133">Whether the assembly was found in the [global assembly cache](../app-domains/gac.md).</span></span>

    - <span data-ttu-id="b490f-134">Elenco di tutti gli URL di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b490f-134">A list of all probing URLs.</span></span>

<span data-ttu-id="b490f-135">Nell'esempio seguente viene illustrata una voce di log in cui sono visualizzate informazioni dettagliate su un'associazione di assembly non riuscita.</span><span class="sxs-lookup"><span data-stu-id="b490f-135">The following sample log entry shows detailed information about a failed assembly bind.</span></span>

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

### <a name="to-delete-a-single-entry-from-the-log"></a><span data-ttu-id="b490f-136">Per eliminare una singola voce dal log</span><span class="sxs-lookup"><span data-stu-id="b490f-136">To delete a single entry from the log</span></span>

1. <span data-ttu-id="b490f-137">Selezionare una voce nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="b490f-137">Select an entry in the viewer.</span></span>

2. <span data-ttu-id="b490f-138">Fare clic sul pulsante **Elimina voce**.</span><span class="sxs-lookup"><span data-stu-id="b490f-138">Click the **Delete Entry** button.</span></span>

### <a name="to-delete-all-entries-from-the-log"></a><span data-ttu-id="b490f-139">Per eliminare tutte le voci dal log</span><span class="sxs-lookup"><span data-stu-id="b490f-139">To delete all entries from the log</span></span>

- <span data-ttu-id="b490f-140">Fare clic sul pulsante **Elimina tutto**.</span><span class="sxs-lookup"><span data-stu-id="b490f-140">Click the **Delete All** button.</span></span>

### <a name="to-refresh-the-user-interface"></a><span data-ttu-id="b490f-141">Per aggiornare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b490f-141">To refresh the user interface</span></span>

- <span data-ttu-id="b490f-142">Fare clic sul pulsante **Aggiorna.**</span><span class="sxs-lookup"><span data-stu-id="b490f-142">Click the **Refresh** button.</span></span> <span data-ttu-id="b490f-143">Il visualizzatore non rileva automaticamente le nuove voci di log mentre è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b490f-143">The viewer does not automatically detect new log entries while it is running.</span></span> <span data-ttu-id="b490f-144">Per visualizzarle è necessario scegliere il pulsante **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="b490f-144">You must use the **Refresh** button to display them.</span></span>

### <a name="to-change-the-log-settings"></a><span data-ttu-id="b490f-145">Per modificare le impostazioni di log</span><span class="sxs-lookup"><span data-stu-id="b490f-145">To change the log settings</span></span>

- <span data-ttu-id="b490f-146">Scegliere il pulsante **Impostazioni** per aprire la finestra di dialogo **Impostazioni log**.</span><span class="sxs-lookup"><span data-stu-id="b490f-146">Click the **Settings** button to open the **Log Settings** dialog.</span></span>

### <a name="to-view-the-about-dialog"></a><span data-ttu-id="b490f-147">Per visualizzare la finestra di dialogo Informazioni su</span><span class="sxs-lookup"><span data-stu-id="b490f-147">To view the About dialog</span></span>

- <span data-ttu-id="b490f-148">Fare clic sul pulsante **Informazioni su**.</span><span class="sxs-lookup"><span data-stu-id="b490f-148">Click the **About** button.</span></span>

## <a name="binding-logs-for-native-images"></a><span data-ttu-id="b490f-149">Log di associazioni per immagini native</span><span class="sxs-lookup"><span data-stu-id="b490f-149">Binding Logs for Native Images</span></span>

<span data-ttu-id="b490f-150">Per impostazione predefinita, Fuslogvw.exe registra le normali richieste di associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="b490f-150">By default, Fuslogvw.exe logs normal assembly bind requests.</span></span> <span data-ttu-id="b490f-151">In alternativa, è possibile registrare le associazioni di assembly per le immagini native create usando [Ngen.exe (generatore di immagini native)](ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="b490f-151">Alternatively, you can log assembly binds for native images that were created using the [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md).</span></span>

#### <a name="to-log-assembly-binds-for-native-images"></a><span data-ttu-id="b490f-152">Per registrare le associazioni di assembly per le immagini native</span><span class="sxs-lookup"><span data-stu-id="b490f-152">To log assembly binds for native images</span></span>

- <span data-ttu-id="b490f-153">Nel gruppo **Categorie log**, selezionare il pulsante di opzione **Immagini native**.</span><span class="sxs-lookup"><span data-stu-id="b490f-153">In the **Log Categories** group, select the **Native Images** option button.</span></span>

<span data-ttu-id="b490f-154">Nel log seguente viene riportato un errore causato da una dipendenza inesistente nel momento in cui è stata creata l'immagine nativa per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b490f-154">The following log shows a failure caused by a dependency that did not exist when the native image was created for the application.</span></span> <span data-ttu-id="b490f-155">Se le dipendenze in fase di esecuzione differiscono dalle dipendenze durante l'esecuzione di Ngen.exe, l'associazione a un'immagine nativa non è consentita.</span><span class="sxs-lookup"><span data-stu-id="b490f-155">If the dependencies at run time differ from the dependencies when Ngen.exe is run, binding to a native image is not allowed.</span></span>

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

<span data-ttu-id="b490f-156">Nel log seguente viene riportato un errore di associazione dell'immagine nativa che si è verificato perché le impostazioni di sicurezza del computer nel momento in cui è stata eseguita l'applicazione erano diverse da quelle impostate al momento della creazione dell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="b490f-156">The following log shows a native image binding failure that occurred because the security settings on the computer when the application was run were different from the security settings at the time the native image was created.</span></span>

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

## <a name="the-log-settings-dialog"></a><span data-ttu-id="b490f-157">Finestra di dialogo Impostazioni log</span><span class="sxs-lookup"><span data-stu-id="b490f-157">The Log Settings Dialog</span></span>

<span data-ttu-id="b490f-158">È possibile usare la finestra di dialogo **Impostazioni log** per effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="b490f-158">You can use the **Log Settings** dialog to perform the following actions.</span></span>

#### <a name="to-disable-logging"></a><span data-ttu-id="b490f-159">Per disabilitare la registrazione</span><span class="sxs-lookup"><span data-stu-id="b490f-159">To disable logging</span></span>

- <span data-ttu-id="b490f-160">Selezionare il pulsante di opzione **Log disattivato**.</span><span class="sxs-lookup"><span data-stu-id="b490f-160">Select the **Log disabled** option button.</span></span>  <span data-ttu-id="b490f-161">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b490f-161">Note that this option is selected by default.</span></span>

#### <a name="to-log-assembly-binds-in-exceptions"></a><span data-ttu-id="b490f-162">Per registrare le associazioni di assembly in eccezioni</span><span class="sxs-lookup"><span data-stu-id="b490f-162">To log assembly binds in exceptions</span></span>

- <span data-ttu-id="b490f-163">Selezionare il pulsante di opzione **Registra nel testo dell'eccezione**.</span><span class="sxs-lookup"><span data-stu-id="b490f-163">Select the **Log in exception text** option button.</span></span> <span data-ttu-id="b490f-164">Solo le informazioni meno dettagliate del log Fusion vengono registrate nel testo dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b490f-164">Only the least detailed fusion log information is logged in exception text.</span></span> <span data-ttu-id="b490f-165">Per visualizzare le informazioni complete, usare una delle altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b490f-165">To view full information, use one of the other settings.</span></span>

  <span data-ttu-id="b490f-166">Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="b490f-166">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-assembly-bind-failures"></a><span data-ttu-id="b490f-167">Per registrare gli errori di associazione di assembly</span><span class="sxs-lookup"><span data-stu-id="b490f-167">To log assembly bind failures</span></span>

- <span data-ttu-id="b490f-168">Selezionare il pulsante di opzione **Registra errori di associazione su disco**.</span><span class="sxs-lookup"><span data-stu-id="b490f-168">Select the **Log bind failures to disk** option button.</span></span>

  <span data-ttu-id="b490f-169">Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="b490f-169">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-all-assembly-binds"></a><span data-ttu-id="b490f-170">Per registrare tutte le associazioni di assembly</span><span class="sxs-lookup"><span data-stu-id="b490f-170">To log all assembly binds</span></span>

- <span data-ttu-id="b490f-171">Selezionare il pulsante di opzione **Registra tutte le associazioni su disco**.</span><span class="sxs-lookup"><span data-stu-id="b490f-171">Select the **Log all binds to disk** option button.</span></span>

  <span data-ttu-id="b490f-172">Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="b490f-172">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b490f-173">Quando un assembly viene caricato come indipendente dal dominio, ad esempio impostando la proprietà <xref:System.AppDomainSetup.LoaderOptimization%2A> su <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> o <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, l'abilitazione della registrazione può determinare una perdita di memoria in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="b490f-173">When an assembly is loaded as domain neutral, for example by setting the <xref:System.AppDomainSetup.LoaderOptimization%2A> property to <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> or <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, turning on logging might leak memory in some cases.</span></span> <span data-ttu-id="b490f-174">Ciò può verificarsi se si crea una voce di log quando in un dominio applicazione viene caricato un modulo indipendente dal dominio e successivamente il dominio applicazione viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="b490f-174">This can happen if a log entry is made when a domain-neutral module is loaded into an application domain, and later the application domain is unloaded.</span></span> <span data-ttu-id="b490f-175">È possibile che la voce di log non venga rilasciata fino alla fine del processo.</span><span class="sxs-lookup"><span data-stu-id="b490f-175">The log entry might not be released until the process ends.</span></span> <span data-ttu-id="b490f-176">Alcuni debugger prevedono l'abilitazione automatica della registrazione.</span><span class="sxs-lookup"><span data-stu-id="b490f-176">Some debuggers automatically turn on logging.</span></span>

#### <a name="to-enable-a-custom-log-path"></a><span data-ttu-id="b490f-177">Per impostare un percorso di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="b490f-177">To enable a custom log path</span></span>

1. <span data-ttu-id="b490f-178">Selezionare il pulsante di opzione **Attiva percorso personalizzato log**.</span><span class="sxs-lookup"><span data-stu-id="b490f-178">Select the **Enable custom log path** option button.</span></span>

2. <span data-ttu-id="b490f-179">Immettere il percorso nella casella di testo **Percorso personalizzato log**.</span><span class="sxs-lookup"><span data-stu-id="b490f-179">Enter the path into the **Custom log path** text box.</span></span>

> [!NOTE]
> <span data-ttu-id="b490f-180">Per l'archiviazione del log associazioni del [visualizzatore log associazioni assembly (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) viene usata la cache di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b490f-180">The [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) uses the Internet Explorer (IE) cache to store its binding log.</span></span> <span data-ttu-id="b490f-181">In seguito al danneggiamento occasionale della cache di Internet Explorer, è possibile che nella finestra di visualizzazione del [visualizzatore log associazioni assembly (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) non siano visualizzati i nuovi log associazioni.</span><span class="sxs-lookup"><span data-stu-id="b490f-181">Due to occasional corruption in the IE cache, the [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) can sometimes stop showing new binding logs in the viewing window.</span></span> <span data-ttu-id="b490f-182">In tali circostanze l'infrastruttura di associazione di .NET (fusion) non è in grado di eseguire operazioni di scrittura o lettura dal log associazioni.</span><span class="sxs-lookup"><span data-stu-id="b490f-182">As a result of this corruption, the .NET binding infrastructure (fusion) cannot write to or read from the binding log.</span></span> <span data-ttu-id="b490f-183">Questo problema non si verifica se si utilizza un percorso di log personalizzato.  Per correggere il danneggiamento e consentire a Fusion di visualizzare nuovamente i registri di associazione, cancellare la cache di Internet IE eliminando i file Internet temporanei dalla finestra di dialogo Opzioni Internet di Internet Internet.</span><span class="sxs-lookup"><span data-stu-id="b490f-183">(This issue is not encountered if you use a custom log path.)  To fix the corruption and allow fusion to show binding logs again, clear the IE cache by deleting temporary internet files from within the IE Internet Options dialog.</span></span>
>
> <span data-ttu-id="b490f-184">Se l'applicazione non gestita ospita Common Language Runtime mediante l'implementazione delle interfacce `IHostAssemblyManager` e `IHostAssemblyStore`, le voci di logo non possono essere archiviate nella cache wininet.</span><span class="sxs-lookup"><span data-stu-id="b490f-184">If your unmanaged application hosts the common language runtime by implementing the `IHostAssemblyManager` and `IHostAssemblyStore` interfaces, log entries can't be stored in the wininet cache.</span></span>  <span data-ttu-id="b490f-185">Per visualizzare le voci di log di host personalizzati che implementano tali interfacce, è necessario specificare un percorso alternativo per il log.</span><span class="sxs-lookup"><span data-stu-id="b490f-185">To view log entries for custom hosts that implement these interfaces, you must specify an alternate log path.</span></span>

#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a><span data-ttu-id="b490f-186">Per abilitare la registrazione per le app eseguite nel contenitore delle app Windows</span><span class="sxs-lookup"><span data-stu-id="b490f-186">To enable logging for apps running in the Windows app container</span></span>

1. <span data-ttu-id="b490f-187">Abilitare un percorso di log personalizzato come descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="b490f-187">Enable a custom log path, as described in the previous procedure.</span></span> <span data-ttu-id="b490f-188">Per impostazione predefinita, le app eseguite nel contenitore delle app Windows dispongono di accesso limitato al disco rigido.</span><span class="sxs-lookup"><span data-stu-id="b490f-188">By default, apps that are running in the Windows app container have limited access to the hard disk.</span></span> <span data-ttu-id="b490f-189">La directory specificata disporrà di accesso in lettura/scrittura su tutte le app nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="b490f-189">The directory you specify will have read/write access for all apps in the app container.</span></span>

2. <span data-ttu-id="b490f-190">Selezionare la casella di controllo **Abilita registrazione immersiva**.</span><span class="sxs-lookup"><span data-stu-id="b490f-190">Select the **Enable immersive logging** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b490f-191">Questa casella è abilitata solo in Windows 8 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b490f-191">This box is enabled only on Windows 8 or later.</span></span>

## <a name="see-also"></a><span data-ttu-id="b490f-192">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b490f-192">See also</span></span>

- <xref:System.TypeLoadException>
- [<span data-ttu-id="b490f-193">Strumenti</span><span class="sxs-lookup"><span data-stu-id="b490f-193">Tools</span></span>](index.md)
- [<span data-ttu-id="b490f-194">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="b490f-194">Global Assembly Cache</span></span>](../app-domains/gac.md)
- [<span data-ttu-id="b490f-195">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="b490f-195">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="b490f-196">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b490f-196">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
