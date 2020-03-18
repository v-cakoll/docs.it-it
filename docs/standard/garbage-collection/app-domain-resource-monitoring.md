---
title: Monitoraggio delle risorse del dominio applicazione
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
ms.openlocfilehash: 54e300bef1818fd08f27d7920eec68ee1f2c45bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141387"
---
# <a name="application-domain-resource-monitoring"></a>Monitoraggio delle risorse del dominio applicazione

Il monitoraggio delle risorse del dominio applicazione permette agli host di monitorare l'utilizzo di CPU e memoria da parte del dominio applicazione. Ciò risulta utile per gli host, come ASP.NET, che usano molti domini applicazione in un processo a esecuzione prolungata. L'host può scaricare il dominio applicazione di un'applicazione che influisce negativamente sulle prestazioni dell'intero processo, ma solo se è in grado di identificare l'applicazione problematica. Il monitoraggio delle risorse del dominio applicazione fornisce informazioni che possono essere usate per prendere questo tipo di decisioni.

Ad esempio, un servizio di hosting potrebbe avere molte applicazioni in esecuzione in un server ASP.NET. Se un'applicazione nel processo inizia a utilizzare troppa memoria o troppo tempo del processore, il servizio di hosting può usare il monitoraggio delle risorse del dominio applicazione per identificare il dominio applicazione che causa il problema.

Il monitoraggio delle risorse del dominio applicazione è sufficientemente leggero da essere usato nelle applicazioni attive. Le informazioni sono accessibili tramite Event Tracing for Windows (ETW) o direttamente tramite le API gestite o native.

## <a name="enabling-resource-monitoring"></a>Abilitazione del monitoraggio delle risorse

Il monitoraggio delle risorse del dominio applicazione può essere abilitato in quattro modi: fornendo un file di configurazione all'avvio di Common Language Runtime (CLR), usando un'API di hosting non gestita, tramite codice gestito o attivando l'ascolto di eventi ETW di monitoraggio delle risorse del dominio applicazione.

Non appena il monitoraggio viene abilitato, inizia a raccogliere dati su tutti i domini applicazione nel processo. Se un dominio applicazione è stato creato prima dell'abilitazione del monitoraggio, l'accumulo dei dati inizia quando viene abilitato il monitoraggio e non quando è stato creato il dominio dell'applicazione. Una volta attivato, il monitoraggio delle risorse del dominio applicazione non può essere disabilitato.

- È possibile abilitare ARM all'avvio di CLR aggiungendo l'elemento `enabled` `true` [ \<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) al file di configurazione e impostando l'attributo su . Il valore `false` (predefinito) indica solo che il monitoraggio non viene abilitato all'avvio. È possibile attivarlo in un secondo momento usando uno degli altri meccanismi di attivazione.

- L'host può abilitare il monitoraggio richiedendo l'interfaccia di hosting [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md). Dopo aver ottenuto correttamente questa interfaccia, il monitoraggio viene abilitato.

- È possibile abilitare il monitoraggio delle risorse del dominio applicazione da codice gestito impostando la proprietà statica (`Shared` in Visual Basic) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> su `true`. Il monitoraggio viene abilitato subito dopo aver impostato la proprietà.

- È possibile abilitare il monitoraggio all'avvio, attivando l'ascolto di eventi ETW. Il monitoraggio viene abilitato e inizia a generare eventi per tutti i domini applicazione, quando si abilita il provider pubblico `Microsoft-Windows-DotNETRuntime` tramite la parola chiave `AppDomainResourceManagementKeyword`. Per correlare i dati con domini applicazione e thread, è necessario abilitare anche il provider `Microsoft-Windows-DotNETRuntimeRundown` con la parola chiave `ThreadingKeyword`.

## <a name="using-arm"></a>Uso del monitoraggio delle risorse del dominio applicazione

Il monitoraggio delle risorse del dominio applicazione fornisce il tempo totale del processore usato da un dominio applicazione e tre tipi di informazioni sull'uso della memoria.

- **Tempo totale del processore per un dominio applicazione, in secondi**: viene calcolato sommando la durata dei thread segnalata dal sistema operativo per tutti i thread che hanno dedicato tempo all'esecuzione nel dominio applicazione durante la relativa durata. I thread bloccati o sospeso non usano tempo del processore. Quando un thread esegue chiamate nel codice nativo, il tempo trascorso dal thread nel codice nativo viene incluso nel conteggio per il dominio applicazione in cui è stata effettuata la chiamata.

  - API gestita: proprietà <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>.

  - API di hosting: metodo [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md).

  - Eventi ETW: eventi `ThreadCreated`, `ThreadAppDomainEnter` e `ThreadTerminated`. Per informazioni sui provider e le parole chiave, vedere "Eventi di monitoraggio risorse di AppDomain" in [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md).

- **Totale delle allocazioni gestite effettuate da un dominio applicazione durante la sua durata, in byte**: le allocazioni totali non riflettono sempre l'uso della memoria da parte di un dominio applicazione, perché gli oggetti allocati potrebbero avere breve durata. Tuttavia, se un'applicazione alloca e libera grandi quantità di oggetti, il costo delle allocazioni potrebbe essere significativo.

  - API gestita: proprietà <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>.

  - API di hosting: metodo [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md).

  - Eventi ETW: evento `AppDomainMemAllocated`, campo `Allocated`.

- **Memoria gestita, in byte, a cui fa riferimento un dominio applicazione ed esclusa dalla Garbage Collection di blocco completa più recente**: questo numero è preciso solo dopo una Garbage Collection di blocco completa. Ciò è in contrasto con le raccolte simultanee, che si verificano in background e non bloccano l'applicazione. Ad esempio, <xref:System.GC.Collect?displayProperty=nameWithType> l'overload del metodo causa una raccolta completa di blocco.

  - API gestita: proprietà <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>.

  - API di hosting: metodo [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md), parametro `pAppDomainBytesSurvived`.

  - Eventi ETW: evento `AppDomainMemSurvived`, campo `Survived`.

- **Totale di memoria gestita, in byte, a cui fa riferimento il processo ed esclusa dalla Garbage Collection di blocco completa più recente**: la memoria esclusa per i singoli domini applicazione può essere confrontata con questo numero.

  - API gestita: proprietà <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>.

  - API di hosting: metodo [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md), parametro `pTotalBytesSurvived`.

  - Eventi ETW: evento `AppDomainMemSurvived`, campo `ProcessSurvived`.

### <a name="determining-when-a-full-blocking-collection-occurs"></a>Determinare quando viene eseguita una Garbage Collection di blocco completa

Per determinare se i conteggi della memoria esclusa sono accurati, è necessario sapere quando è stata eseguita una Garbage Collection di blocco completa. Il metodo per eseguire questa operazione dipende dall'API usata per esaminare le statistiche di monitoraggio delle risorse del dominio applicazione.

#### <a name="managed-api"></a>API gestita

Se si usano le proprietà della classe <xref:System.AppDomain>, è possibile usare il metodo <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> per registrarsi per ricevere notifica dell'esecuzione di raccolte complete. La soglia usata non è importante, perché si attende il completamento di un'operazione di Garbage Collection, anziché l'avvicinarsi di questa operazione. È quindi possibile chiamare il metodo <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType> che attiva il blocco fino al completamento di una Garbage Collection completa. È possibile creare un thread che chiama il metodo in un ciclo ed esegue eventuali analisi necessarie ogni volta che il metodo restituisce il controllo.

In alternativa, è possibile chiamare il metodo <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType> periodicamente per verificare se il conteggio delle raccolte di generazione 2 è aumentato. A seconda della frequenza di polling, questa tecnica potrebbe non fornire un'indicazione accurata dell'esecuzione di una Garbage Collection completa.

#### <a name="hosting-api"></a>API di hosting

Se si usa l'API di hosting non gestita, l'host deve passare a CLR un'implementazione dell'interfaccia [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md). CLR chiama il metodo [IHostGCManager::SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) quando riprende l'esecuzione di thread sospesi durante l'esecuzione di una Garbage Collection. CLR passa la generazione della raccolta completata come parametro del metodo, in modo che l'host possa determinare se la raccolta è stata completa o parziale. L'implementazione personalizzata del metodo [IHostGCManager::SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) può eseguire una query per ottenere la memoria esclusa, per assicurarsi che i conteggi vengono recuperati non appena vengono aggiornati.

## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Interfaccia ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [\<>appDomainResourceMonitoring](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md)
