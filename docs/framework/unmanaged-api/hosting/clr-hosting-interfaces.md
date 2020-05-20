---
title: Interfacce di hosting CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: e6913e18a4ff6e616f357a4ef43fb8b892264943
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616840"
---
# <a name="clr-hosting-interfaces"></a>Interfacce di hosting CLR
In questa sezione vengono descritte le interfacce che gli host non gestiti possono utilizzare per integrare il Common Language Runtime (CLR) nelle relative applicazioni. Le informazioni si riferiscono alla versione .NET Framework 2,0 e versioni successive. Queste interfacce consentono all'host di controllare molti più aspetti del runtime rispetto a quanto fosse possibile nelle versioni 1,0 e 1,1 e offrono un'integrazione molto più stretta tra CLR e il modello di esecuzione dell'host.  
  
 In .NET Framework versione 1,0 e 1,1, il modello di hosting ha consentito a un host non gestito di caricare il CLR in un processo, configurare determinate impostazioni e ricevere notifiche degli eventi. Tuttavia, in generale, l'host e CLR venivano eseguiti in modo indipendente in tale processo. In .NET Framework versione 2,0 e versioni successive, i nuovi livelli di astrazione consentono all'host di fornire molte delle risorse attualmente fornite dai tipi nell'assembly Win32 ed estendere il set di funzionalità che l'host è in grado di configurare.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Interfaccia IActionOnCLREvent](iactiononclrevent-interface.md)  
 Fornisce un metodo che esegue un callback per un evento registrato.  
  
 [Interfaccia IApartmentCallback](iapartmentcallback-interface.md)  
 Fornisce metodi per l'esecuzione di callback in un Apartment.  
  
 [Interfaccia IAppDomainBinding](iappdomainbinding-interface.md)  
 Fornisce metodi per l'impostazione della configurazione in fase di esecuzione.  
  
 [Interfaccia ICatalogServices](icatalogservices-interface.md)  
 Fornisce metodi per la catalogazione dei servizi. Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.  
  
 [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)  
 Fornisce metodi che supportano la comunicazione tra l'host e CLR sugli assembly.  
  
 [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)  
 Gestisce un elenco di assembly caricati da CLR e non dall'host.  
  
 [Interfaccia ICLRControl](iclrcontrol-interface.md)  
 Fornisce metodi che consentono all'host di ottenere l'accesso a e configurare diversi aspetti di CLR.  
  
 [Interfaccia ICLRDebugManager](iclrdebugmanager-interface.md)  
 Fornisce metodi che consentono a un host di associare un set di attività con un identificatore e un nome descrittivo.  
  
 [Interfaccia ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)  
 Fornisce metodi che consentono all'host di configurare dump di heap personalizzati per la segnalazione degli errori.  
  
 [Interfaccia ICLRGCManager](iclrgcmanager-interface.md)  
 Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection di CLR.  
  
 [Interfaccia ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)  
 Fornisce metodi che consentono all'host di valutare e comunicare le modifiche nelle informazioni sui criteri per gli assembly.  
  
 [Interfaccia ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)  
 Consente all'host di bloccare le classi, i metodi, le proprietà e i campi gestiti specifici dall'esecuzione in codice parzialmente attendibile.  
  
 [Interfaccia ICLRIoCompletionManager](iclriocompletionmanager-interface.md)  
 Implementa un metodo di callback che consente all'host di notificare a CLR lo stato delle richieste di I/O specificate.  
  
 [Interfaccia ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md)  
 Consente all'host di segnalare le condizioni di utilizzo della memoria utilizzando un approccio simile a quello della `CreateMemoryResourceNotification` funzione Win32.  
  
 [Interfaccia ICLROnEventManager](iclroneventmanager-interface.md)  
 Fornisce metodi che consentono all'host di registrare e annullare la registrazione di callback per gli eventi CLR.  
  
 [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)  
 Fornisce metodi che consentono all'host di specificare le azioni dei criteri da intraprendere in caso di errori e timeout.  
  
 [Interfaccia ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)  
 Fornisce metodi che consentono all'host di ottenere le identità di probe di un assembly usando le informazioni sull'identità dell'assembly interne a CLR, senza dover creare o comprendere tale identità.  
  
 [Interfaccia ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)  
 Fornisce metodi che consentono all'host di modificare il set di assembly a cui fa riferimento un file o un flusso utilizzando i dati di identità dell'assembly interni a CLR, senza dover creare o comprendere tali identità.  
  
 [Interfaccia ICLRRuntimeHost](iclrruntimehost-interface.md)  
 Fornisce funzionalità simili a [ICorRuntimeHost](icorruntimehost-interface.md), con un metodo aggiuntivo per impostare l'interfaccia del controllo host.  
  
 [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)  
 Fornisce metodi per l'host per ottenere informazioni sulle attività richieste e per rilevare i deadlock nell'implementazione della sincronizzazione.  
  
 [Interfaccia ICLRTask](iclrtask-interface.md)  
 Fornisce metodi che consentono all'host di effettuare richieste di CLR o di fornire notifiche a CLR sull'attività associata.  
  
 [Interfaccia ICLRTaskManager](iclrtaskmanager-interface.md)  
 Fornisce metodi che consentono all'host di richiedere in modo esplicito che CLR crei una nuova attività, ottenga l'attività attualmente in esecuzione e imposti la lingua geografica e le impostazioni cultura per l'attività.  
  
 [Interfaccia ICLRValidator](iclrvalidator-interface.md)  
 Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.  
  
 [Interfaccia ICorConfiguration](icorconfiguration-interface.md)  
 Fornisce metodi per la configurazione di CLR.  
  
 [Interfaccia ICorThreadpool](icorthreadpool-interface.md)  
 Fornisce metodi per accedere al pool di thread.  
  
 [Interfaccia IDebuggerInfo](idebuggerinfo-interface.md)  
 Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.  
  
 [Interfaccia IDebuggerThreadControl](idebuggerthreadcontrol-interface.md)  
 Fornisce metodi per notificare all'host informazioni sul blocco e lo sblocco dei thread da parte dei servizi di debug.  
  
 [Interfaccia IGCHost](igchost-interface.md)  
 Fornisce metodi per ottenere informazioni sul sistema Garbage Collection e per controllare alcuni aspetti di Garbage Collection.  
  
 [Interfaccia IGCHost2](igchost2-interface.md)  
 Fornisce il metodo [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) che consente a un host di impostare le dimensioni del segmento Garbage Collection e la dimensione massima della generazione zero del sistema Garbage Collection su valori maggiori di `DWORD` .  
  
 [Interfaccia IGCHostControl](igchostcontrol-interface.md)  
 Fornisce un metodo che consente all'Garbage Collector di richiedere all'host di modificare i limiti della memoria virtuale.  
  
 [Interfaccia IGCThreadControl](igcthreadcontrol-interface.md)  
 Fornisce metodi per partecipare alla pianificazione dei thread che altrimenti verrebbero bloccati per Garbage Collection.  
  
 [Interfaccia IHostAssemblyManager](ihostassemblymanager-interface.md)  
 Fornisce metodi che consentono a un host di specificare set di assembly che devono essere caricati da CLR o dall'host.  
  
 [Interfaccia IHostAssemblyStore](ihostassemblystore-interface.md)  
 Fornisce metodi che consentono a un host di caricare assembly e moduli in modo indipendente da CLR.  
  
 [Interfaccia IHostAutoEvent](ihostautoevent-interface.md)  
 Fornisce una rappresentazione di un evento di reimpostazione automatica implementato dall'host.  
  
 [Interfaccia IHostControl](ihostcontrol-interface.md)  
 Fornisce metodi per la configurazione del caricamento di assembly e per la determinazione delle interfacce di hosting supportate dall'host.  
  
 [Interfaccia IHostCrst](ihostcrst-interface.md)  
 Funge da rappresentazione dell'host di una sezione critica per il Threading.  
  
 [Interfaccia IHostGCManager](ihostgcmanager-interface.md)  
 Fornisce metodi che notificano all'host degli eventi nel meccanismo Garbage Collection implementato da CLR.  
  
 [Interfaccia IHostIoCompletionManager](ihostiocompletionmanager-interface.md)  
 Fornisce metodi che consentono a CLR di interagire con le porte di completamento I/O fornite dall'host.  
  
 [Interfaccia IHostMalloc](ihostmalloc-interface.md)  
 Fornisce metodi che consentono a CLR di richiedere allocazioni con granularità fine dall'heap tramite l'host.  
  
 [Interfaccia IHostManualEvent](ihostmanualevent-interface.md)  
 Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.  
  
 [Interfaccia IHostMemoryManager](ihostmemorymanager-interface.md)  
 Fornisce metodi che consentono a CLR di effettuare richieste di memoria virtuale attraverso l'host anziché utilizzare le funzioni di memoria virtuale Win32 standard.  
  
 [Interfaccia IHostPolicyManager](ihostpolicymanager-interface.md)  
 Fornisce metodi che notificano all'host le azioni eseguite da CLR in caso di interruzioni, timeout o errori.  
  
 [Interfaccia IHostSecurityContext](ihostsecuritycontext-interface.md)  
 Consente a CLR di mantenere le informazioni sul contesto di sicurezza implementate dall'host.  
  
 [Interfaccia IHostSecurityManager](ihostsecuritymanager-interface.md)  
 Fornisce metodi che consentono l'accesso e il controllo del contesto di sicurezza del thread attualmente in esecuzione.  
  
 [Interfaccia IHostSemaphore](ihostsemaphore-interface.md)  
 Fornisce una rappresentazione di un semaforo implementato dall'host.  
  
 [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)  
 Fornisce metodi che consentono a CLR di creare primitive di sincronizzazione chiamando l'host anziché utilizzare le funzioni di sincronizzazione Win32.  
  
 [Interfaccia IHostTask](ihosttask-interface.md)  
 Fornisce metodi che consentono a CLR di comunicare con l'host per gestire le attività.  
  
 [Interfaccia IHostTaskManager](ihosttaskmanager-interface.md)  
 Fornisce metodi che consentono a CLR di utilizzare le attività attraverso l'host anziché utilizzare il threading del sistema operativo standard o le funzioni fiber.  
  
 [Interfaccia IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)  
 Fornisce metodi per CLR per configurare il pool di thread e accodare gli elementi di lavoro al pool di thread.  
  
 [Interfaccia IManagedObject](imanagedobject-interface.md)  
 Fornisce metodi per il controllo di un oggetto gestito.  
  
 IObjectHandle  
 Fornisce un metodo per l'annullamento del wrapping degli oggetti Marshal-by-value da un riferimento indiretto.  
  
 [Interfaccia ITypeName](itypename-interface.md)  
 Fornisce metodi per ottenere informazioni sul nome del tipo. Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.  
  
 [Interfaccia ITypeNameBuilder](itypenamebuilder-interface.md)  
 Fornisce metodi per la compilazione di un nome di tipo. Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.  
  
 [Interfaccia ITypeNameFactory](itypenamefactory-interface.md)  
 Fornisce metodi per la decostruzione di un nome di tipo. Questa interfaccia supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.  
  
 IValidator  
 Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interfacce di hosting CLR deprecate e coclassi](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Sono contenuti argomenti che descrivono le interfacce di hosting disponibili nella .NET Framework versione 1,0 e 1,1.  
  
 [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Sono contenuti argomenti che descrivono le interfacce di hosting fornite nel .NET Framework 4.
