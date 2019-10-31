---
title: Interfacce di hosting CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 66fdd97d101f5ea53a96b996a2a60e5ed65a2701
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131961"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="23694-102">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="23694-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="23694-103">In questa sezione vengono descritte le interfacce che gli host non gestiti possono utilizzare per integrare il Common Language Runtime (CLR) nelle relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="23694-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="23694-104">Le informazioni si riferiscono alla versione .NET Framework 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="23694-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="23694-105">Queste interfacce consentono all'host di controllare molti più aspetti del runtime rispetto a quanto fosse possibile nelle versioni 1,0 e 1,1 e offrono un'integrazione molto più stretta tra CLR e il modello di esecuzione dell'host.</span><span class="sxs-lookup"><span data-stu-id="23694-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="23694-106">In .NET Framework versione 1,0 e 1,1, il modello di hosting ha consentito a un host non gestito di caricare il CLR in un processo, configurare determinate impostazioni e ricevere notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="23694-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="23694-107">Tuttavia, in generale, l'host e CLR venivano eseguiti in modo indipendente in tale processo.</span><span class="sxs-lookup"><span data-stu-id="23694-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="23694-108">In .NET Framework versione 2,0 e versioni successive, i nuovi livelli di astrazione consentono all'host di fornire molte delle risorse attualmente fornite dai tipi nell'assembly Win32 ed estendere il set di funzionalità che l'host è in grado di configurare.</span><span class="sxs-lookup"><span data-stu-id="23694-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23694-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="23694-109">In This Section</span></span>  
 [<span data-ttu-id="23694-110">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="23694-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="23694-111">Fornisce un metodo che esegue un callback per un evento registrato.</span><span class="sxs-lookup"><span data-stu-id="23694-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="23694-112">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="23694-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="23694-113">Fornisce metodi per l'esecuzione di callback in un Apartment.</span><span class="sxs-lookup"><span data-stu-id="23694-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="23694-114">Interfaccia IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="23694-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="23694-115">Fornisce metodi per l'impostazione della configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="23694-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="23694-116">Interfaccia ICatalogServices</span><span class="sxs-lookup"><span data-stu-id="23694-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="23694-117">Fornisce metodi per la catalogazione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="23694-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="23694-118">Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="23694-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="23694-119">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="23694-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="23694-120">Fornisce metodi che supportano la comunicazione tra l'host e CLR sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="23694-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="23694-121">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="23694-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="23694-122">Gestisce un elenco di assembly caricati da CLR e non dall'host.</span><span class="sxs-lookup"><span data-stu-id="23694-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="23694-123">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="23694-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="23694-124">Fornisce metodi che consentono all'host di ottenere l'accesso a e configurare diversi aspetti di CLR.</span><span class="sxs-lookup"><span data-stu-id="23694-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="23694-125">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="23694-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="23694-126">Fornisce metodi che consentono a un host di associare un set di attività con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="23694-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="23694-127">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="23694-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="23694-128">Fornisce metodi che consentono all'host di configurare dump di heap personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="23694-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="23694-129">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="23694-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="23694-130">Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection di CLR.</span><span class="sxs-lookup"><span data-stu-id="23694-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="23694-131">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="23694-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="23694-132">Fornisce metodi che consentono all'host di valutare e comunicare le modifiche nelle informazioni sui criteri per gli assembly.</span><span class="sxs-lookup"><span data-stu-id="23694-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="23694-133">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="23694-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="23694-134">Consente all'host di bloccare le classi, i metodi, le proprietà e i campi gestiti specifici dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="23694-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="23694-135">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="23694-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="23694-136">Implementa un metodo di callback che consente all'host di notificare a CLR lo stato delle richieste di I/O specificate.</span><span class="sxs-lookup"><span data-stu-id="23694-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="23694-137">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="23694-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="23694-138">Consente all'host di segnalare le condizioni di utilizzo della memoria utilizzando un approccio simile a quello della funzione Win32 `CreateMemoryResourceNotification`.</span><span class="sxs-lookup"><span data-stu-id="23694-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="23694-139">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="23694-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="23694-140">Fornisce metodi che consentono all'host di registrare e annullare la registrazione di callback per gli eventi CLR.</span><span class="sxs-lookup"><span data-stu-id="23694-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="23694-141">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="23694-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="23694-142">Fornisce metodi che consentono all'host di specificare le azioni dei criteri da intraprendere in caso di errori e timeout.</span><span class="sxs-lookup"><span data-stu-id="23694-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="23694-143">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="23694-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="23694-144">Fornisce metodi che consentono all'host di ottenere le identità di probe di un assembly usando le informazioni sull'identità dell'assembly interne a CLR, senza dover creare o comprendere tale identità.</span><span class="sxs-lookup"><span data-stu-id="23694-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="23694-145">Interfaccia ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="23694-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="23694-146">Fornisce metodi che consentono all'host di modificare il set di assembly a cui fa riferimento un file o un flusso utilizzando i dati di identità dell'assembly interni a CLR, senza dover creare o comprendere tali identità.</span><span class="sxs-lookup"><span data-stu-id="23694-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="23694-147">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="23694-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="23694-148">Fornisce funzionalità simili a [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), con un metodo aggiuntivo per impostare l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="23694-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="23694-149">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="23694-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="23694-150">Fornisce metodi per l'host per ottenere informazioni sulle attività richieste e per rilevare i deadlock nell'implementazione della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="23694-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="23694-151">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="23694-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="23694-152">Fornisce metodi che consentono all'host di effettuare richieste di CLR o di fornire notifiche a CLR sull'attività associata.</span><span class="sxs-lookup"><span data-stu-id="23694-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="23694-153">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="23694-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="23694-154">Fornisce metodi che consentono all'host di richiedere in modo esplicito che CLR crei una nuova attività, ottenga l'attività attualmente in esecuzione e imposti la lingua geografica e le impostazioni cultura per l'attività.</span><span class="sxs-lookup"><span data-stu-id="23694-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="23694-155">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="23694-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="23694-156">Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="23694-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="23694-157">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="23694-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="23694-158">Fornisce metodi per la configurazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="23694-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="23694-159">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="23694-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="23694-160">Fornisce metodi per accedere al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="23694-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="23694-161">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="23694-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="23694-162">Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="23694-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="23694-163">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="23694-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="23694-164">Fornisce metodi per notificare all'host informazioni sul blocco e lo sblocco dei thread da parte dei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="23694-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="23694-165">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="23694-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="23694-166">Fornisce metodi per ottenere informazioni sul sistema Garbage Collection e per controllare alcuni aspetti di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="23694-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="23694-167">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="23694-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="23694-168">Fornisce il metodo [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) che consente a un host di impostare le dimensioni del segmento Garbage Collection e la dimensione massima della generazione zero del sistema Garbage Collection su valori maggiori di `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="23694-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="23694-169">Interfaccia IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="23694-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="23694-170">Fornisce un metodo che consente all'Garbage Collector di richiedere all'host di modificare i limiti della memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="23694-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="23694-171">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="23694-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="23694-172">Fornisce metodi per partecipare alla pianificazione dei thread che altrimenti verrebbero bloccati per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="23694-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="23694-173">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="23694-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="23694-174">Fornisce metodi che consentono a un host di specificare set di assembly che devono essere caricati da CLR o dall'host.</span><span class="sxs-lookup"><span data-stu-id="23694-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="23694-175">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="23694-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="23694-176">Fornisce metodi che consentono a un host di caricare assembly e moduli in modo indipendente da CLR.</span><span class="sxs-lookup"><span data-stu-id="23694-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="23694-177">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="23694-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="23694-178">Fornisce una rappresentazione di un evento di reimpostazione automatica implementato dall'host.</span><span class="sxs-lookup"><span data-stu-id="23694-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="23694-179">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="23694-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="23694-180">Fornisce metodi per la configurazione del caricamento di assembly e per la determinazione delle interfacce di hosting supportate dall'host.</span><span class="sxs-lookup"><span data-stu-id="23694-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="23694-181">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="23694-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="23694-182">Funge da rappresentazione dell'host di una sezione critica per il Threading.</span><span class="sxs-lookup"><span data-stu-id="23694-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="23694-183">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="23694-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="23694-184">Fornisce metodi che notificano all'host degli eventi nel meccanismo Garbage Collection implementato da CLR.</span><span class="sxs-lookup"><span data-stu-id="23694-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="23694-185">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="23694-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="23694-186">Fornisce metodi che consentono a CLR di interagire con le porte di completamento I/O fornite dall'host.</span><span class="sxs-lookup"><span data-stu-id="23694-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="23694-187">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="23694-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="23694-188">Fornisce metodi che consentono a CLR di richiedere allocazioni con granularità fine dall'heap tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="23694-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="23694-189">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="23694-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="23694-190">Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="23694-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="23694-191">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="23694-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="23694-192">Fornisce metodi che consentono a CLR di effettuare richieste di memoria virtuale attraverso l'host anziché utilizzare le funzioni di memoria virtuale Win32 standard.</span><span class="sxs-lookup"><span data-stu-id="23694-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="23694-193">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="23694-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="23694-194">Fornisce metodi che notificano all'host le azioni eseguite da CLR in caso di interruzioni, timeout o errori.</span><span class="sxs-lookup"><span data-stu-id="23694-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="23694-195">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="23694-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="23694-196">Consente a CLR di mantenere le informazioni sul contesto di sicurezza implementate dall'host.</span><span class="sxs-lookup"><span data-stu-id="23694-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="23694-197">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="23694-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="23694-198">Fornisce metodi che consentono l'accesso e il controllo del contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="23694-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="23694-199">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="23694-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="23694-200">Fornisce una rappresentazione di un semaforo implementato dall'host.</span><span class="sxs-lookup"><span data-stu-id="23694-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="23694-201">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="23694-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="23694-202">Fornisce metodi che consentono a CLR di creare primitive di sincronizzazione chiamando l'host anziché utilizzare le funzioni di sincronizzazione Win32.</span><span class="sxs-lookup"><span data-stu-id="23694-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="23694-203">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="23694-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="23694-204">Fornisce metodi che consentono a CLR di comunicare con l'host per gestire le attività.</span><span class="sxs-lookup"><span data-stu-id="23694-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="23694-205">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="23694-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="23694-206">Fornisce metodi che consentono a CLR di utilizzare le attività attraverso l'host anziché utilizzare il threading del sistema operativo standard o le funzioni fiber.</span><span class="sxs-lookup"><span data-stu-id="23694-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="23694-207">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="23694-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="23694-208">Fornisce metodi per CLR per configurare il pool di thread e accodare gli elementi di lavoro al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="23694-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="23694-209">Interfaccia IManagedObject</span><span class="sxs-lookup"><span data-stu-id="23694-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="23694-210">Fornisce metodi per il controllo di un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="23694-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="23694-211">IObjectHandle</span><span class="sxs-lookup"><span data-stu-id="23694-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="23694-212">Fornisce un metodo per l'annullamento del wrapping degli oggetti Marshal-by-value da un riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="23694-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="23694-213">Interfaccia ITypeName</span><span class="sxs-lookup"><span data-stu-id="23694-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="23694-214">Fornisce metodi per ottenere informazioni sul nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="23694-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="23694-215">Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="23694-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="23694-216">Interfaccia ITypeNameBuilder</span><span class="sxs-lookup"><span data-stu-id="23694-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="23694-217">Fornisce metodi per la compilazione di un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="23694-217">Provides methods for building a type name.</span></span> <span data-ttu-id="23694-218">Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="23694-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="23694-219">Interfaccia ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="23694-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="23694-220">Fornisce metodi per la decostruzione di un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="23694-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="23694-221">Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="23694-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="23694-222">IValidator</span><span class="sxs-lookup"><span data-stu-id="23694-222">"IValidator"</span></span>  
 <span data-ttu-id="23694-223">Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="23694-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="23694-224">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="23694-224">Related Sections</span></span>  
 [<span data-ttu-id="23694-225">Interfacce di hosting CLR deprecate e coclassi</span><span class="sxs-lookup"><span data-stu-id="23694-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="23694-226">Sono contenuti argomenti che descrivono le interfacce di hosting disponibili nella .NET Framework versione 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="23694-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="23694-227">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="23694-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="23694-228">Sono contenuti argomenti che descrivono le interfacce di hosting fornite nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="23694-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
