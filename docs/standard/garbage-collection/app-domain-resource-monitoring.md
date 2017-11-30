---
title: Monitoraggio delle risorse del dominio applicazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62a514f94857044af5020d36a1cfd6ce06741ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="application-domain-resource-monitoring"></a>Monitoraggio delle risorse del dominio applicazione
Risorse del dominio applicazione (ARM) di monitoraggio consente agli host di monitorare l'utilizzo della CPU e memoria dal dominio applicazione. Ciò è utile per gli host, ad esempio ASP.NET che utilizzano molti domini applicazione in un processo a esecuzione prolungata. L'host può scaricare il dominio di applicazione di un'applicazione che influisce negativamente sulle prestazioni dell'intero processo, ma solo se è in grado di identificare l'applicazione problematica. ARM fornisce informazioni che possono essere utilizzate per assistere nella creazione di tali decisioni.  
  
 Ad esempio, un servizio di hosting dispone di molte applicazioni in esecuzione in un server ASP.NET. Se un'applicazione nel processo inizia utilizza troppa memoria o troppo tempo processore, il servizio di hosting può utilizzare ARM per identificare il dominio applicazione che ha causato il problema.  
  
 ARM è sufficientemente semplice da utilizzare nelle applicazioni in tempo reale. Le informazioni è possibile accedere tramite traccia eventi per Windows (ETW) o direttamente tramite le API gestite o native.  
  
## <a name="enabling-resource-monitoring"></a>Abilitazione del monitoraggio risorse  
 ARM può essere abilitato in quattro modi: fornendo un file di configurazione all'avvio di common language runtime (CLR), utilizzando una funzione non gestita API di hosting, tramite codice gestito o in attesa di eventi ETW ARM.  
  
 Non appena il monitoraggio viene abilitato, inizia a raccogliere dati su tutti i domini applicazione nel processo. Se un dominio applicazione è stato creato prima che il monitoraggio viene abilitato, dati cumulativi inizia quando il monitoraggio viene abilitato, non quando è stato creato il dominio dell'applicazione. Una volta attivato, ARM non può essere disabilitato.  
  
-   È possibile abilitare ARM all'avvio di CLR aggiungendo il [ \<appDomainResourceMonitoring >](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) elemento per il file di configurazione e l'impostazione di `enabled` attributo `true`. Il valore `false` (il valore predefinito) indica solo che ARM non è abilitato all'avvio, è possibile attivarla in un secondo momento utilizzando uno degli altri meccanismi di attivazione.  
  
-   L'host può abilitare ARM richiedendo il [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaccia di hosting. Una volta questa interfaccia è stata ottenuta correttamente, il monitoraggio viene abilitato.  
  
-   Codice gestito può abilitare ARM impostando statica (`Shared` in Visual Basic) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> proprietà `true`. Non appena la proprietà è impostata, il monitoraggio viene abilitato.  
  
-   È possibile abilitare ARM dopo l'avvio in attesa di eventi ETW. Il monitoraggio è abilitato e inizia a generare eventi per tutti i domini applicazione, quando si abilita il provider pubblico `Microsoft-Windows-DotNETRuntime` utilizzando il `AppDomainResourceManagementKeyword` (parola chiave). Per correlare i dati con i domini applicazione e thread, è necessario abilitare il `Microsoft-Windows-DotNETRuntimeRundown` provider con il `ThreadingKeyword` (parola chiave).  
  
## <a name="using-arm"></a>Utilizzo di ARM  
 ARM fornisce il tempo processore totale utilizzato da un dominio applicazione e tre i tipi di informazioni sull'utilizzo della memoria.  
  
-   **Tempo totale processore per un dominio applicazione, in secondi**: viene calcolata aggiungendo le durate dei thread ha segnalate dal sistema operativo per tutti i thread che è trascorso tempo durante l'esecuzione nel dominio dell'applicazione durante la relativa durata. Bloccato o sospensione di thread non utilizzano tempo processore. Quando un thread esegue chiamate nel codice nativo, il tempo trascorso dal thread in codice nativo è incluso nel conteggio per il dominio applicazione in cui è stata effettuata la chiamata.  
  
    -   API gestita: <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> proprietà.  
  
    -   API di hosting: [GetCurrentCpuTime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md) metodo.  
  
    -   Eventi ETW: `ThreadCreated`, `ThreadAppDomainEnter`, e `ThreadTerminated` eventi. Per informazioni sui provider e le parole chiave, vedere "Eventi di monitoraggio risorse di AppDomain" in [eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md).  
  
-   **Totale gestite allocazioni effettuate da un dominio dell'applicazione durante la sua durata, in byte**: le allocazioni totali non riflettono sempre uso della memoria da un dominio applicazione, poiché gli oggetti allocati potrebbero essere di breve durati. Tuttavia, se un'applicazione alloca e libera grandi quantità di oggetti, il costo delle allocazioni potrebbe essere significativo.  
  
    -   API gestita: <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> proprietà.  
  
    -   API di hosting: [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md) metodo.  
  
    -   Eventi ETW: `AppDomainMemAllocated` evento `Allocated` campo.  
  
-   **Memoria gestita, in byte, che fa riferimento a un dominio applicazione e che è stato raccolto il più recente completa di Garbage collection bloccante**: questo numero è preciso solo dopo una procedura completa di raccolta. (È diversamente dalle raccolte concorrenti, che vengono eseguite in background e non blocca l'applicazione). Ad esempio, il <xref:System.GC.Collect?displayProperty=nameWithType> overload del metodo provoca una procedura completa di Garbage collection bloccante.  
  
    -   API gestita: <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> proprietà.  
  
    -   API di hosting: [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) metodo `pAppDomainBytesSurvived` parametro.  
  
    -   Eventi ETW: `AppDomainMemSurvived` evento `Survived` campo.  
  
-   **Totale di memoria gestita, in byte, a cui fa riferimento il processo e che è stato raccolto il più recente completa di Garbage collection bloccante**: la memoria esclusa per singoli domini applicazione può essere confrontata a questo numero.  
  
    -   API gestita: <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType> proprietà.  
  
    -   API di hosting: [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) metodo `pTotalBytesSurvived` parametro.  
  
    -   Eventi ETW: `AppDomainMemSurvived` evento `ProcessSurvived` campo.  
  
### <a name="determining-when-a-full-blocking-collection-occurs"></a>Determinare se una procedura completa, Garbage Collection bloccante  
 Per determinare se i contatori di memoria esclusa sono accurati, è necessario sapere quando è stata appena eseguita una raccolta completa di. Il metodo per eseguire questa operazione dipende dall'API consentono di esaminare le statistiche ARM.  
  
#### <a name="managed-api"></a>API gestita  
 Se si utilizzano le proprietà del <xref:System.AppDomain> (classe), è possibile utilizzare il <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> metodo di registrazione delle notifiche delle raccolte complete. La soglia che è utilizzare non è importante, poiché si attende il completamento di una raccolta anziché l'approccio di una raccolta. È quindi possibile chiamare il <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType> (metodo), che si blocca fino al completamento di una raccolta completa. È possibile creare un thread che chiama il metodo in un ciclo e non le analisi necessarie ogni volta che il metodo restituisce.  
  
 In alternativa, è possibile chiamare il <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType> metodo periodicamente per verificare se il conteggio delle raccolte di generazione 2 è aumentato. A seconda della frequenza di polling, questa tecnica potrebbe non fornire accurata un'indicazione dell'occorrenza di una raccolta completa.  
  
#### <a name="hosting-api"></a>API di hosting  
 Se si utilizza l'API di hosting non gestita, l'host deve passare CLR un'implementazione del [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md) interfaccia. CLR chiama il [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) metodo quando riprende l'esecuzione di thread che sono state sospese durante una raccolta. CLR passa la generazione di raccolta completata come parametro del metodo, in modo che l'host può determinare se la raccolta è di tipo completo o parziale. L'implementazione del [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) metodo possibile eseguire una query per la memoria esclusa, per garantire che i conteggi vengono recuperati come tali file vengono aggiornati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [ICLRAppDomainResourceMonitor (interfaccia)](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md)
