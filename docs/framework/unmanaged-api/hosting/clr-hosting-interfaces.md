---
title: Interfacce di hosting CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03839a2c6e52f9d2dcdd2e0941ff4fdbeb8a3a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="clr-hosting-interfaces"></a>Interfacce di hosting CLR
In questa sezione vengono descritte le interfacce non gestite host consente di integrare common language runtime (CLR) nelle relative applicazioni. Le informazioni si riferiscono alla versione di .NET Framework 2.0 e versioni successive. Queste interfacce consentono all'host di controllare molti altri aspetti del runtime rispetto a quanto accadeva nelle versioni 1.0 e 1.1 e forniscono più stretta integrazione tra CLR e il modello di esecuzione dell'host.  
  
 In .NET Framework versioni 1.0 e 1.1, il modello di hosting è abilitato un host non gestito caricare CLR in un processo, configurare alcune impostazioni e per ricevere le notifiche degli eventi. Tuttavia, in generale, l'host e Common Language Runtime è stata eseguita in modo indipendente in tale processo. In .NET Framework versione 2.0 e versioni successive, nuovi livelli di astrazione consentono all'host di fornire molte delle risorse attualmente disponibili per i tipi nell'assembly Win32 ed estendere il set di funzionalità che è possibile configurare l'host.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Interfaccia IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Fornisce un metodo che esegue un callback per un evento registrato.  
  
 [Interfaccia IApartmentCallback](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Fornisce metodi per eseguire callback all'interno di un apartment.  
  
 [Interfaccia IAppDomainBinding](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Fornisce metodi per la configurazione delle impostazioni in fase di esecuzione.  
  
 [Interfaccia ICatalogServices](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Fornisce metodi per servizi di catalogazione. (Questa interfaccia supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice).  
  
 [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Fornisce metodi che supportano la comunicazione tra l'host e sugli assembly di Common Language Runtime.  
  
 [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Gestisce un elenco di assembly caricati da Common Language Runtime e non dall'host.  
  
 [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Fornisce metodi per l'host accedere a e configurare diversi aspetti di Common Language Runtime.  
  
 [Interfaccia ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Fornisce metodi che consentono a un host associare un set di attività con un identificatore e un nome descrittivo.  
  
 [Interfaccia ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Fornisce metodi che consentono all'host configurare il dump dell'heap personalizzati per la segnalazione errori.  
  
 [Interfaccia ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Fornisce metodi che consentono a un host di interagire con il sistema di CLR garbage collection.  
  
 [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Fornisce metodi per l'host valutare e notificare le modifiche delle informazioni sui criteri per gli assembly.  
  
 [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Consente all'host di bloccare le classi gestite specifiche, metodi, proprietà e i campi dall'esecuzione di codice parzialmente attendibile.  
  
 [Interfaccia ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Implementa un metodo di callback che consente all'host di notificare al CLR dello stato delle richieste dei / o specificate.  
  
 [Interfaccia ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Consente all'host di pressione della memoria di report con un approccio simile a quello di Win32 `CreateMemoryResourceNotification` (funzione).  
  
 [Interfaccia ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Fornisce metodi che consentono all'host di registrare e annullare la registrazione di callback per gli eventi CLR.  
  
 [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Fornisce metodi che consentono all'host di specificare criteri di azioni da intraprendere in caso di errori o timeout.  
  
 [Interfaccia ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Fornisce metodi che consentono all'host ottenere l'identità di ricerca di un assembly utilizzando informazioni sull'identità dell'assembly all'interni di CLR, senza la necessità di creare o riconoscere l'identità.  
  
 [Interfaccia ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Fornisce metodi che consentono all'host di modificare il set di assembly a cui fa riferimento un file o flusso utilizzando i dati di identità di assembly all'interni di CLR, senza la necessità di creare o conoscere le identità.  
  
 [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Fornisce funzionalità analoghe a [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), con un metodo aggiuntivo per impostare l'interfaccia del controllo host.  
  
 [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Fornisce metodi per l'host per ottenere informazioni sulle attività richieste e di rilevare deadlock nell'implementazione della sincronizzazione.  
  
 [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Fornisce metodi che consentono all'host per effettuare richieste di CLR o per fornire la notifica a CLR sull'attività associata.  
  
 [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Fornisce metodi che consentono all'host di richiedere in modo esplicito che CLR crea una nuova attività, ottenere l'attività attualmente in esecuzione e impostare la lingua geografica per l'attività.  
  
 [Interfaccia ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Fornisce metodi per la convalida (PE) immagini di tipo PE e la segnalazione degli errori di convalida.  
  
 [Interfaccia ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Fornisce metodi per la configurazione di CLR.  
  
 [Interfaccia ICorThreadpool](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Fornisce metodi per l'accesso ai pool di thread.  
  
 [Interfaccia IDebuggerInfo](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.  
  
 [Interfaccia IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Fornisce metodi per notificare all'host di blocco e sblocco dei thread per i servizi di debug.  
  
 [Interfaccia IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.  
  
 [Interfaccia IGCHost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Fornisce il [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo che consente a un host su cui impostare le dimensioni del segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection zero valori maggiore `DWORD`.  
  
 [Interfaccia IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Fornisce un metodo che consente al garbage collector richiedere all'host di modificare i limiti di memoria virtuale.  
  
 [Interfaccia IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Fornisce metodi per partecipare alla pianificazione di thread che altrimenti sarebbero bloccati per l'operazione di garbage collection.  
  
 [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Fornisce metodi che consentono a un host specificare i set di assembly che devono essere caricati da CLR o dall'host.  
  
 [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Fornisce metodi che consentono a un host caricare gli assembly e moduli in modo indipendente da CLR.  
  
 [Interfaccia IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Fornisce una rappresentazione di un evento di reimpostazione automatica implementato dall'host.  
  
 [Interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Fornisce metodi per la configurazione del caricamento degli assembly e per determinare quali hosting interfacce host supporta.  
  
 [Interfaccia IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Serve come rappresentazione dell'host di una sezione critica di threading.  
  
 [Interfaccia IHostGCManager](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Fornisce metodi per notificare all'host gli eventi nel meccanismo di garbage collection implementata da CLR.  
  
 [Interfaccia IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Fornisce metodi che consentono di interagire con le porte di completamento i/o fornite dall'host CLR.  
  
 [Interfaccia IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Fornisce metodi per richiedere di allocare dall'heap tramite l'host che Common Language Runtime.  
  
 [Interfaccia IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.  
  
 [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Fornisce metodi per il CLR può effettuare richieste di memoria virtuale tramite l'host, invece di usare le funzioni di memoria virtuale Win32 standard.  
  
 [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Fornisce metodi per notificare all'host le azioni eseguite da Common Language Runtime in caso di interruzioni, timeout o errori.  
  
 [Interfaccia IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Consente di mantenere le informazioni sul contesto di sicurezza implementate dall'host CLR.  
  
 [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Fornisce metodi che consentono l'accesso a e controllano, il contesto di sicurezza del thread attualmente in esecuzione.  
  
 [Interfaccia IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Fornisce una rappresentazione di un semaforo implementato dall'host.  
  
 [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Fornisce metodi per Common Language Runtime creare le primitive di sincronizzazione chiamando l'host, invece di usare le funzioni di sincronizzazione di Win32.  
  
 [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Fornisce metodi che consentono a CLR comunicare con l'host per le attività di gestione.  
  
 [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Fornisce metodi che consentono di gestire le attività tramite l'host anziché utilizzare le funzioni di sistema operativo standard fiber o thread CLR.  
  
 [Interfaccia IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Fornisce metodi per la configurazione del pool di thread e di accodare gli elementi di lavoro al pool di thread CLR.  
  
 [Interfaccia IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Fornisce metodi per controllare un oggetto gestito.  
  
 "IObjectHandle"  
 Fornisce un metodo per gli oggetti Unwrap effettuare il marshalling in base al valore di riferimento indiretto.  
  
 [Interfaccia ITypeName](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Fornisce metodi per ottenere informazioni sul nome di tipo. (Questa interfaccia supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice).  
  
 [Interfaccia ITypeNameBuilder](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Fornisce metodi per la creazione di un nome di tipo. (Questa interfaccia supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice).  
  
 [Interfaccia ITypeNameFactory](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Fornisce metodi per eliminare un nome di tipo. (Questa interfaccia supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice).  
  
 "IValidator"  
 Fornisce metodi per la convalida (PE) immagini di tipo PE e la segnalazione degli errori di convalida.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interfacce di hosting CLR deprecate e coclassi](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Contiene argomenti che descrivono le interfacce di hosting disponibili in .NET Framework versione 1.0 e 1.1.  
  
 [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Contiene argomenti che descrivono le interfacce di hosting disponibili nel [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].
