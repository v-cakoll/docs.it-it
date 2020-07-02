---
title: 'Procedura: debug dei problemi di attivazione CLR'
description: Vedere come eseguire il debug dei problemi di attivazione di Common Language Runtime (CLR) in .NET. Visualizzare ed eseguire il debug dei log di attivazione CLR, che possono essere utili per determinare le cause principali.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 5215e82aebf93fa8d6d1937563ab348126a01d97
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622614"
---
# <a name="how-to-debug-clr-activation-issues"></a><span data-ttu-id="2db01-104">Procedura: debug dei problemi di attivazione CLR</span><span class="sxs-lookup"><span data-stu-id="2db01-104">How to debug CLR activation issues</span></span>

<span data-ttu-id="2db01-105">Se si verificano problemi nell'eseguire l'applicazione con la versione corretta di Common Language Runtime (CLR), è possibile visualizzare ed eseguire il debug dei log di attivazione CLR.</span><span class="sxs-lookup"><span data-stu-id="2db01-105">If you encounter problems in getting your application to run with the correct version of the common language runtime (CLR), you can view and debug CLR activation logs.</span></span> <span data-ttu-id="2db01-106">Questi log possono essere molto utili nell'individuazione della causa principale di un problema di attivazione quando l'applicazione carica una versione di CLR diversa da quella prevista o non carica CLR.</span><span class="sxs-lookup"><span data-stu-id="2db01-106">These logs can be very useful in determining the root cause of an activation issue, when your application either loads a different CLR version than expected or doesn't load the CLR at all.</span></span> <span data-ttu-id="2db01-107">In [Errori di inizializzazione di .NET Framework: gestione dell'esperienza utente](initialization-errors-managing-the-user-experience.md) è descritto il caso in cui non viene trovato alcun CLR per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2db01-107">The [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) discusses the experience when no CLR is found for an application.</span></span>

<span data-ttu-id="2db01-108">La registrazione dell'attivazione di CLR può essere abilitata a livello di sistema usando una chiave del Registro di sistema HKEY_LOCAL_MACHINE o una variabile di ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="2db01-108">CLR activation logging can be enabled system-wide by using an HKEY_LOCAL_MACHINE registry key or a system environment variable.</span></span> <span data-ttu-id="2db01-109">Il log verrà generato fino a quando la voce del Registro di sistema o la variabile di ambiente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="2db01-109">The log will be generated until the registry entry or the environment variable is removed.</span></span> <span data-ttu-id="2db01-110">In alternativa, è possibile usare una variabile di ambiente a livello locale o una variabile dell'utente per attivare la registrazione con ambito e durata differenti.</span><span class="sxs-lookup"><span data-stu-id="2db01-110">Alternatively, you can use a user or process-local environment variable to enable logging with a different scope and duration.</span></span>

<span data-ttu-id="2db01-111">I log di attivazione CLR non devono essere confusi con i [log associazioni assembly](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) che sono completamente diversi.</span><span class="sxs-lookup"><span data-stu-id="2db01-111">CLR activation logs shouldn't be confused with [assembly binding logs](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), which are entirely different.</span></span>

## <a name="to-enable-clr-activation-logging"></a><span data-ttu-id="2db01-112">Per attivare la registrazione dell'attivazione CLR</span><span class="sxs-lookup"><span data-stu-id="2db01-112">To enable CLR activation logging</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="2db01-113">Usando il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="2db01-113">Using the registry</span></span>

1. <span data-ttu-id="2db01-114">Nell'editor del Registro di sistema passare alla cartella HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (in un computer a 32 bit) o alla cartella HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (in un computer a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="2db01-114">In the Registry Editor, navigate to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (on a 32-bit computer) or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework folder (on a 64-bit computer).</span></span>

2. <span data-ttu-id="2db01-115">Aggiungere un valore stringa denominato `CLRLoadLogDir` e impostarlo sul percorso completo di una directory esistente in cui si vuole archiviare i log di attivazione CLR.</span><span class="sxs-lookup"><span data-stu-id="2db01-115">Add a string value named `CLRLoadLogDir`, and set it to the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

<span data-ttu-id="2db01-116">La registrazione dell'attivazione rimane attiva finché non viene rimosso il valore stringa.</span><span class="sxs-lookup"><span data-stu-id="2db01-116">Activation logging remains enabled until you remove the string value.</span></span>

### <a name="using-an-environment-variable"></a><span data-ttu-id="2db01-117">Usando una variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="2db01-117">Using an environment variable</span></span>

- <span data-ttu-id="2db01-118">Impostare la variabile di ambiente `COMPLUS_CLRLoadLogDir` su una stringa che rappresenta il percorso completo di una directory esistente in cui si vuole archiviare i log di attivazione CLR.</span><span class="sxs-lookup"><span data-stu-id="2db01-118">Set the `COMPLUS_CLRLoadLogDir` environment variable to a string that represents the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

    <span data-ttu-id="2db01-119">La modalità di impostazione della variabile di ambiente ne determina l'ambito:</span><span class="sxs-lookup"><span data-stu-id="2db01-119">How you set the environment variable determines its scope:</span></span>

  - <span data-ttu-id="2db01-120">Se impostata a livello di sistema, l'attività di registrazione dell'attivazione rimane abilitata per tutte le applicazioni .NET Framework nel computer fino a quando non viene rimossa la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="2db01-120">If you set it at the system level, activation logging is enabled for all .NET Framework applications on that computer until the environment variable is removed.</span></span>

  - <span data-ttu-id="2db01-121">Se impostata a livello utente, la registrazione dell'attivazione è abilitata solo per l'account utente corrente.</span><span class="sxs-lookup"><span data-stu-id="2db01-121">If you set it at the user level, activation logging is enabled only for the current user account.</span></span> <span data-ttu-id="2db01-122">La registrazione continua fino a quando non viene rimossa la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="2db01-122">Logging continues until the environment variable is removed.</span></span>

  - <span data-ttu-id="2db01-123">Se impostata dall'interno del processo prima del caricamento di CLR, la registrazione dell'attivazione rimane abilitata fino al termine del processo.</span><span class="sxs-lookup"><span data-stu-id="2db01-123">If you set it from within the process before loading the CLR, activation logging is enabled until the process terminates.</span></span>

  - <span data-ttu-id="2db01-124">Se impostata dal prompt dei comandi prima di eseguire un'applicazione, la registrazione dell'attivazione è abilitata per qualsiasi applicazione eseguita da quel prompt.</span><span class="sxs-lookup"><span data-stu-id="2db01-124">If you set it at a command prompt before you run an application, activation logging is enabled for any application that is run from that command prompt.</span></span>

    <span data-ttu-id="2db01-125">Ad esempio, per archiviare i log di attivazione nella directory c:\clrloadlogs con ambito a livello di processo, aprire una finestra del prompt dei comandi e digitare il codice seguente prima di eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="2db01-125">For example, to store activation logs in the c:\clrloadlogs directory with process-level scope, open a Command Prompt window and type the following before you run the application:</span></span>

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a><span data-ttu-id="2db01-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="2db01-126">Example</span></span>

<span data-ttu-id="2db01-127">I log di attivazione CLR offrono una grande quantità di dati sull'attivazione CLR e sull'uso delle API di hosting CLR.</span><span class="sxs-lookup"><span data-stu-id="2db01-127">CLR activation logs provide a large amount of data about CLR activation and the use of the CLR hosting APIs.</span></span> <span data-ttu-id="2db01-128">La maggior parte di questi dati è usato internamente da Microsoft, ma alcuni dati possono essere utili agli sviluppatori, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2db01-128">Most of this data is used internally by Microsoft, but some of the data can also be useful to developers, as described in this article.</span></span>

<span data-ttu-id="2db01-129">Il log rispecchia l'ordine in cui le API di hosting di CLR sono state chiamate.</span><span class="sxs-lookup"><span data-stu-id="2db01-129">The log reflects the order in which the CLR hosting APIs were called.</span></span> <span data-ttu-id="2db01-130">Include anche dati utili sul set di runtime installati rilevati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2db01-130">It also includes useful data about the set of installed runtimes detected on the computer.</span></span> <span data-ttu-id="2db01-131">Il formato del log di attivazione CLR non è documentato, ma può essere usato dagli sviluppatori che devono risolvere problemi di attivazione CLR.</span><span class="sxs-lookup"><span data-stu-id="2db01-131">The CLR activation log format is not itself documented, but can be used to aid developers who need to resolve CLR activation issues.</span></span>

> [!NOTE]
> <span data-ttu-id="2db01-132">Non è possibile aprire il log di attivazione fino a quando il processo che usa CLR non è terminato.</span><span class="sxs-lookup"><span data-stu-id="2db01-132">You cannot open an activation log until the process that uses the CLR has terminated.</span></span>

> [!NOTE]
> <span data-ttu-id="2db01-133">I log di attivazione CLR non sono localizzati; vengono generati sempre in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="2db01-133">CLR activation logs are not localized; they are always generated in the English language.</span></span>

<span data-ttu-id="2db01-134">Nell'esempio seguente di log di attivazione le informazioni più utili sono evidenziate e descritte dopo il log.</span><span class="sxs-lookup"><span data-stu-id="2db01-134">In the following example of an activation log, the most useful information is highlighted and described after the log.</span></span>

```output
532,205950.367,CLR Loading log for C:\Tests\myapp.exe
532,205950.367,Log started at 4:26:12 PM on 10/6/2011
532,205950.367,-----------------------------------
532,205950.382,FunctionCall: _CorExeMain
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
532,205950.382,Input values for ComputeVersionString follow this line
532,205950.382,-----------------------------------
532,205950.382,Default Application Name: C:\Tests\myapp.exe
532,205950.382,IsLegacyBind is: 0
532,205950.382,IsCapped is 0
532,205950.382,SkuCheckFlags are 0
532,205950.382,ShouldEmulateExeLaunch is 0
532,205950.382,LegacyBindRequired is 0
532,205950.382,-----------------------------------
532,205950.382,Parsing config file: C:\Tests\myapp.exe
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.
532,205950.398,SEM_FAILCRITICALERRORS is set to 0
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
532,205950.398,FunctionCall: RealDllMain. Reason: 0
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0
```

- <span data-ttu-id="2db01-135">Il **log di caricamento CLR** specifica il percorso dell'eseguibile che ha avviato il processo che ha caricato il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2db01-135">**CLR Loading log** provides the path to the executable that started the process that loaded managed code.</span></span> <span data-ttu-id="2db01-136">Si noti che questo potrebbe essere un host nativo.</span><span class="sxs-lookup"><span data-stu-id="2db01-136">Note that this could be a native host.</span></span>

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- <span data-ttu-id="2db01-137">Il **runtime installato** è un insieme di versioni di CLR installate nel computer candidate alla richiesta di attivazione.</span><span class="sxs-lookup"><span data-stu-id="2db01-137">**Installed Runtime** is the set of CLR versions installed on the computer that are candidates for the activation request.</span></span>

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- <span data-ttu-id="2db01-138">**Compilato con la versione** indica la versione di CLR usata per compilare il binario inviato a un metodo come [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="2db01-138">**built with version** is the version of the CLR that was used to build the binary that was provided to a method such as [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).</span></span>

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- <span data-ttu-id="2db01-139">L'**installazione funzionalità su richiesta** fa riferimento all'abilitazione di .NET Framework 3.5 in Windows 8.</span><span class="sxs-lookup"><span data-stu-id="2db01-139">**feature-on-demand installation** refers to enabling the .NET Framework 3.5 on Windows 8.</span></span> <span data-ttu-id="2db01-140">Per altre informazioni su questo scenario, vedere [Errori di inizializzazione di .NET Framework: gestione dell'esperienza utente](initialization-errors-managing-the-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="2db01-140">See [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) for more information about this scenario.</span></span>

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a><span data-ttu-id="2db01-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2db01-141">See also</span></span>

- [<span data-ttu-id="2db01-142">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="2db01-142">Deployment</span></span>](index.md)
- [<span data-ttu-id="2db01-143">Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="2db01-143">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
