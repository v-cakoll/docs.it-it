---
title: Diagnostica degli errori tramite gli assistenti al debug gestito
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
ms.openlocfilehash: 712fbbe9e0ad291385e8eef321c5e8a2fa092a5d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216562"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="8d0a1-102">Diagnosticare gli errori con gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="8d0a1-102">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="8d0a1-103">Gli assistenti al debug gestito sono strumenti per il debug da usare insieme a CLR (Common Language Runtime) per fornire informazioni sullo stato del runtime.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="8d0a1-104">Gli assistenti generano messaggi informativi su eventi di runtime che non possono essere intercettati in altro modo.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="8d0a1-105">È possibile usare gli assistenti al debug gestito per isolare bug di applicazione difficili da individuare, che si verificano durante la transizione tra codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="8d0a1-106">È possibile [abilitare o disabilitare](#enable-and-disable-mdas) tutti i MDA aggiungendo una chiave al registro di sistema di Windows o impostando una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-106">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="8d0a1-107">Le impostazioni di configurazione dell'applicazione permettono di abilitare assistenti al debug gestito specifici.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="8d0a1-108">È possibile definire impostazioni di configurazione aggiuntive per alcuni singoli assistenti al debug gestito nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="8d0a1-109">Poiché questi file di configurazione sono analizzati durante il caricamento del runtime, è necessario abilitare l'assistente al debug gestito prima dell'avvio dell'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="8d0a1-110">Non è possibile abilitarlo per applicazioni già avviate.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-110">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="8d0a1-111">Nella tabella seguente sono elencati i MDA forniti con la .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8d0a1-111">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="8d0a1-112">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="8d0a1-112">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="8d0a1-113">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="8d0a1-113">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="8d0a1-114">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="8d0a1-114">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="8d0a1-115">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="8d0a1-115">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="8d0a1-116">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="8d0a1-116">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="8d0a1-117">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="8d0a1-117">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="8d0a1-118">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="8d0a1-118">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="8d0a1-119">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="8d0a1-119">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="8d0a1-120">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="8d0a1-120">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="8d0a1-121">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="8d0a1-121">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="8d0a1-122">failedQI</span><span class="sxs-lookup"><span data-stu-id="8d0a1-122">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="8d0a1-123">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="8d0a1-123">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="8d0a1-124">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="8d0a1-124">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="8d0a1-125">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="8d0a1-125">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="8d0a1-126">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="8d0a1-126">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="8d0a1-127">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="8d0a1-127">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="8d0a1-128">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="8d0a1-128">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="8d0a1-129">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="8d0a1-129">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="8d0a1-130">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="8d0a1-130">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="8d0a1-131">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="8d0a1-131">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="8d0a1-132">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="8d0a1-132">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="8d0a1-133">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="8d0a1-133">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="8d0a1-134">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="8d0a1-134">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="8d0a1-135">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="8d0a1-135">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="8d0a1-136">loaderLock</span><span class="sxs-lookup"><span data-stu-id="8d0a1-136">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="8d0a1-137">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="8d0a1-137">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="8d0a1-138">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="8d0a1-138">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="8d0a1-139">marshaling</span><span class="sxs-lookup"><span data-stu-id="8d0a1-139">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="8d0a1-140">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="8d0a1-140">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="8d0a1-141">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="8d0a1-141">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="8d0a1-142">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="8d0a1-142">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="8d0a1-143">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="8d0a1-143">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="8d0a1-144">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="8d0a1-144">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="8d0a1-145">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="8d0a1-145">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="8d0a1-146">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="8d0a1-146">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="8d0a1-147">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="8d0a1-147">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="8d0a1-148">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="8d0a1-148">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="8d0a1-149">reentrancy</span><span class="sxs-lookup"><span data-stu-id="8d0a1-149">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="8d0a1-150">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="8d0a1-150">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="8d0a1-151">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="8d0a1-151">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="8d0a1-152">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="8d0a1-152">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="8d0a1-153">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="8d0a1-153">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="8d0a1-154">Per impostazione predefinita, .NET Framework attiva un sottoinsieme di assistenti al debug gestito per tutti i debugger gestiti.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-154">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="8d0a1-155">È possibile visualizzare il set predefinito in Visual Studio scegliendo **Windows** > **Impostazioni eccezioni** dal menu **debug** , quindi espandendo l'elenco **assistenti al debug gestito** .</span><span class="sxs-lookup"><span data-stu-id="8d0a1-155">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Finestra Impostazioni eccezioni in Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="8d0a1-157">Abilitare e disabilitare MDA</span><span class="sxs-lookup"><span data-stu-id="8d0a1-157">Enable and Disable MDAs</span></span>

<span data-ttu-id="8d0a1-158">È possibile abilitare e disabilitare gli assistenti al debug gestito usando una chiave del Registro di sistema, una variabile di ambiente e impostazioni di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-158">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="8d0a1-159">Per usare le impostazioni di configurazione dell'applicazione, è necessario abilitare la chiave del Registro di sistema o la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-159">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="8d0a1-160">Anziché disabilitare MDA, è possibile impedire a Visual Studio di visualizzare la finestra di dialogo MDA ogni volta che viene ricevuta una notifica dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-160">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="8d0a1-161">A tale scopo, scegliere **Windows** > **Impostazioni eccezioni** dal menu **debug** , espandere l'elenco **assistenti al debug gestito** e quindi selezionare o deselezionare la casella di controllo **Interrompi quando viene generata** per il singolo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-161">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="8d0a1-162">Chiave del Registro</span><span class="sxs-lookup"><span data-stu-id="8d0a1-162">Registry Key</span></span>

<span data-ttu-id="8d0a1-163">Per abilitare MDA, aggiungere il **\\HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.** Sottochiave NETFramework\MDA (tipo REG_SZ, valore 1) nel registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-163">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="8d0a1-164">Copiare l'esempio seguente in un file di testo denominato *MDAEnable. reg*. Aprire l'editor del registro di sistema di Windows (RegEdit. exe) e scegliere **Importa**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="8d0a1-164">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="8d0a1-165">Selezionare il file *MDAEnable. reg* per abilitare MDA nel computer.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-165">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="8d0a1-166">Se si imposta la sottochiave sul valore stringa **1** (non DWORD valore **1**), viene abilitata la lettura delle impostazioni dell'assistente al debug gestito dal file *ApplicationName. suffiss*. mda. config.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-166">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="8d0a1-167">Il file di configurazione dell'assistente al debug gestito per il blocco note, ad esempio, è denominato Notepad. exe. mda. config.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-167">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="8d0a1-168">Se il computer esegue un'applicazione a 32 bit in un sistema operativo a 64 bit, la chiave dell'assistente al debug gestito deve essere configurata come segue:</span><span class="sxs-lookup"><span data-stu-id="8d0a1-168">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="8d0a1-169">Per ulteriori informazioni, vedere [impostazioni di configurazione specifiche dell'applicazione](#application-specific-configuration-settings) .</span><span class="sxs-lookup"><span data-stu-id="8d0a1-169">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="8d0a1-170">L'impostazione del Registro di sistema può essere sostituita dalla variabile di ambiente COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-170">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="8d0a1-171">Per ulteriori informazioni, vedere [variabile di ambiente](#environment-variable) .</span><span class="sxs-lookup"><span data-stu-id="8d0a1-171">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="8d0a1-172">Per disabilitare MDA, impostare la sottochiave MDA su **0** (zero) utilizzando l'editor del registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-172">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="8d0a1-173">Per impostazione predefinita, alcuni assistenti al debug gestito sono abilitati quando si esegue un'applicazione associata a un debugger, anche se non si aggiunge la chiave del Registro di sistema,</span><span class="sxs-lookup"><span data-stu-id="8d0a1-173">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="8d0a1-174">È possibile disabilitare questi assistenti eseguendo il file *MDADisable. reg* come descritto in precedenza in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-174">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="8d0a1-175">Variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="8d0a1-175">Environment Variable</span></span>

<span data-ttu-id="8d0a1-176">L'attivazione dell'assistente al debug gestito può essere controllata anche dalla variabile di ambiente COMPLUS_MDA, che sostituisce la chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-176">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="8d0a1-177">La stringa COMPLUS_MDA è un elenco di nomi di assistenti al debug gestito o di altre stringhe di controllo speciali delimitato da punto e virgola e in cui non è applicata la distinzione tra maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-177">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="8d0a1-178">L'avvio con un debugger gestito o non gestito abilita un set di assistenti al debug gestito per impostazione predefinita,</span><span class="sxs-lookup"><span data-stu-id="8d0a1-178">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="8d0a1-179">aggiungendo in modo implicito l'elenco delimitato da punto e virgola di assistenti al debug gestito abilitati per impostazione predefinita con i debugger davanti al valore della variabile di ambiente o della chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-179">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="8d0a1-180">Di seguito sono elencate le stringhe di controllo speciali:</span><span class="sxs-lookup"><span data-stu-id="8d0a1-180">The special control strings are the following:</span></span>

- <span data-ttu-id="8d0a1-181">`0` - Disattiva tutti gli assistenti al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-181">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="8d0a1-182">`1`: legge le impostazioni dell'assistente al debug gestito da *NomeApplicazione*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-182">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="8d0a1-183">`managedDebugger` - Attiva esplicitamente tutti gli assistenti al debug gestito attivati in modo implicito quando si avvia un eseguibile gestito con un debugger.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-183">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="8d0a1-184">`unmanagedDebugger` - Attiva esplicitamente tutti gli assistenti al debug gestito attivati in modo implicito quando si avvia un eseguibile non gestito con un debugger.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-184">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="8d0a1-185">In caso di conflitto, le impostazioni più recenti eseguono l'override di quelle precedenti:</span><span class="sxs-lookup"><span data-stu-id="8d0a1-185">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="8d0a1-186">`COMPLUS_MDA=0` disabilita tutti gli assistenti al debug gestito, inclusi quelli abilitati in modo implicito con un debugger.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-186">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="8d0a1-187">`COMPLUS_MDA=gcUnmanagedToManaged` abilita `gcUnmanagedToManaged`, oltre a eventuali assistenti al debug gestito abilitati in modo implicito con un debugger.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-187">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="8d0a1-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` abilita `gcUnmanagedToManaged` ma disabilita gli assistenti al debug gestito che sarebbero altrimenti abilitati in modo implicito con un debugger.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="8d0a1-189">Impostazioni di configurazione specifiche dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8d0a1-189">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="8d0a1-190">È possibile abilitare, disabilitare e configurare individualmente alcuni assistenti nel file di configurazione MDA per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-190">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="8d0a1-191">Per abilitare l'uso di un file di configurazione dell'applicazione al fine di configurare gli assistenti al debug gestito, è necessario impostare la chiave del Registro di sistema relativa a MDA o la variabile di ambiente COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-191">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="8d0a1-192">Il file di configurazione dell'applicazione si trova in genere nella stessa directory del file eseguibile (con estensione exe) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-192">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="8d0a1-193">Il nome del file assume il formato *ApplicationName*. mda. config; ad esempio, Notepad. exe. mda. config. Gli assistenti abilitati nel file di configurazione dell'applicazione possono disporre di attributi o elementi appositamente progettati per controllare il comportamento dell'assistente.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-193">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="8d0a1-194">Nell'esempio seguente viene illustrato come abilitare e configurare il [marshalling](marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="8d0a1-194">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

<span data-ttu-id="8d0a1-195">L'assistente `Marshaling` emette informazioni sul tipo gestito di cui si sta effettuando il marshalling a un tipo non gestito per ogni transizione da gestito a non gestito nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-195">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="8d0a1-196">Il `Marshaling` MDA consente inoltre di filtrare i nomi dei campi del metodo e della struttura forniti rispettivamente negli elementi figlio **methodFilter** e **fieldFilter** .</span><span class="sxs-lookup"><span data-stu-id="8d0a1-196">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="8d0a1-197">Nell'esempio seguente viene illustrato come abilitare più MDA utilizzando le impostazioni predefinite:</span><span class="sxs-lookup"><span data-stu-id="8d0a1-197">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> <span data-ttu-id="8d0a1-198">Se si specifica più di un assistente in un file di configurazione, è necessario elencarli in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-198">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="8d0a1-199">Ad esempio, per abilitare gli assistenti `virtualCERCall` e `invalidCERCall`, è necessario aggiungere la voce `<invalidCERCall />` prima della voce `<virtualCERCall />`.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-199">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="8d0a1-200">Se le voci non sono in ordine alfabetico, sarà visualizzato un messaggio relativo a un'eccezione non gestita per file di configurazione non valido.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-200">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="8d0a1-201">Eccezioni MDA</span><span class="sxs-lookup"><span data-stu-id="8d0a1-201">MDA exceptions</span></span>

<span data-ttu-id="8d0a1-202">Quando un assistente al debug gestito è abilitato, è attivo anche quando il codice non è in esecuzione in un debugger.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-202">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="8d0a1-203">Se un evento dell'assistente al debug gestito è generato quando non è presente alcun debugger, il messaggio relativo all'evento è visualizzato in una finestra di dialogo per eccezioni non gestite, anche se non si tratta di un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-203">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="8d0a1-204">Per evitare la visualizzazione della finestra di dialogo, rimuovere l'impostazione per l'abilitazione dell'assistente al debug gestito quando il codice non è in esecuzione in un ambiente di debug.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-204">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="8d0a1-205">Quando il codice viene eseguito nell'IDE di Visual Integrated Development Environment studio, è possibile evitare la finestra di dialogo di eccezione visualizzata per eventi di assistente al debug gestito specifici.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-205">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="8d0a1-206">A tale scopo, scegliere **Windows** > **Impostazioni eccezioni**dal menu **debug** .</span><span class="sxs-lookup"><span data-stu-id="8d0a1-206">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="8d0a1-207">Nella finestra **Impostazioni eccezioni** espandere l'elenco **assistenti al debug gestito** , quindi deselezionare la casella di controllo **Interrompi quando generata** per il singolo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-207">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="8d0a1-208">È inoltre possibile utilizzare questa finestra di dialogo per *abilitare* la visualizzazione delle finestre di dialogo delle eccezioni dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-208">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="8d0a1-209">Output degli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="8d0a1-209">MDA Output</span></span>

<span data-ttu-id="8d0a1-210">L'output dell'assistente al debug gestito è simile all'esempio seguente, che mostra l'output del `PInvokeStackImbalance` MDA:</span><span class="sxs-lookup"><span data-stu-id="8d0a1-210">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="8d0a1-211">**Una chiamata alla funzione PInvoke ' MDATest!' MDATest. Program:: StdCall ' ha sbilanciato lo stack. Questa operazione è probabilmente dovuta al fatto che la firma PInvoke gestita non corrisponde alla firma di destinazione non gestita. Verificare che la convenzione di chiamata e i parametri della firma PInvoke corrispondano alla firma non gestita di destinazione.**</span><span class="sxs-lookup"><span data-stu-id="8d0a1-211">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="8d0a1-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d0a1-212">See also</span></span>

- [<span data-ttu-id="8d0a1-213">Debug, analisi e profilatura</span><span class="sxs-lookup"><span data-stu-id="8d0a1-213">Debugging, Tracing, and Profiling</span></span>](index.md)
