---
title: Schema delle impostazioni di runtime
ms.date: 03/30/2017
helpviewer_keywords:
- schema runtime settings
- configuration schema [.NET Framework], runtime settings
- runtime settings schema
ms.assetid: f04816ab-110d-4e28-9283-845d6d9a4a68
ms.openlocfilehash: d5af9f3299b48d431b43566c11610d745167b60b
ms.sourcegitcommit: 0a798a7e9680e2d0a5a81a3eaa203870ea782883
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "74431054"
---
# <a name="run-time-settings-schema"></a>Schema delle impostazioni di runtime

Le impostazioni della fase di esecuzione vengono utilizzate dal Common Language Runtime per configurare le applicazioni destinate al .NET Framework.

## <a name="the-runtime-section-and-its-parent-and-child-elements"></a>La \<runtime> sezione e i relativi elementi padre e figlio

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerType>](appdomainmanagertype-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyBinding>](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<dependentAssembly>](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyIdentity>](assemblyidentity-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<bindingRedirect>](bindingredirect-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<codeBase>](codebase-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<publisherPolicy>](publisherpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<probing>](probing-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<qualifyAssembly>](qualifyassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<supportPortability>](supportportability-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<developmentMode>](developmentmode-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<etwEnable>](etwenable-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcAllowVeryLargeObjects>](gcconcurrent-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcConcurrent>](gcconcurrent-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCCpuGroup>](gccpugroup-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCHeapCount>](gcheapcount-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCLOHThreshold>](gclohthreshold-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCNoAffinitize>](gcnoaffinitize-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcServer>](gcserver-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<generatePublisherEvidence>](generatepublisherevidence-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<loadfromRemoteSources>](loadfromremotesources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<PreferComInsteadOfManagedRemoting>](prefercominsteadofmanagedremoting-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<relativeBindForResources>](relativebindforresources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<TimeSpan_LegacyFormatMode>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<useLegacyJit>](uselegacyjit-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)\
&nbsp;&nbsp;[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<memoryCache>](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<namedCaches>](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<add>](add-element-for-namedcaches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clear>](clear-element-for-namedcaches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<remove>](remove-element-for-namedcaches.md)

## <a name="alphabetical-list-of-runtime-elements"></a>Elenco alfabetico di \<runtime> elementi

|Elemento|Descrizione|
|-------------|-----------------|
|[\<add>](add-element-for-namedcaches.md)|Aggiunge una cache denominata alla raccolta `namedCaches` per una cache in memoria.|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|Definisce una o più opzioni di compatibilità usate dalla classe <xref:System.AppContext> per fornire un meccanismo di rifiuto esplicito per la nuova funzionalità.|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|
|[\<assemblyIdentity>](assemblyidentity-element-for-runtime.md)|Contiene le informazioni di identificazione su un assembly.|
|[\<bindingRedirect>](bindingredirect-element.md)|Reindirizza una versione dell'assembly in un'altra.|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|Specifica se la verifica del nome sicuro per gli assembly attendibili deve essere ignorata.|
|[\<clear>](clear-element-for-namedcaches.md)|Cancella la raccolta `namedCaches` per una cache in memoria.|
|[\<codeBase>](codebase-element.md)|Specifica dove il runtime può trovare un assembly.|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Specifica che il runtime deve usare il comportamento di ordinamento legacy quando si eseguono confronti di stringhe.|
|[\<dependentAssembly>](dependentassembly-element.md)|Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.|
|[\<developmentMode>](developmentmode-element.md)|Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Specifica se la memorizzazione nella cache degli errori di associazione, che è il comportamento predefinito nel .NET Framework 2,0, è disabilitata.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Specifica se viene eseguito il commit dello stack di thread completo all'avvio di un thread.|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Determina se i metodi di analisi di data e ora usano un set di regole di rettifica per analizzare le stringhe di data che contengono solo un indicatore di giorno, mese, ora e AM/PM.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).|
|[\<etwEnable>](etwenable-element.md)|Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|Nelle piattaforme a 64 bit, abilita le matrici con dimensione totale maggiore di 2 gigabyte (GB).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Specifica se Garbage Collection supporta più gruppi di CPU.|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Definisce l'affinità tra heap GC e singoli processori.|
|[\<GCHeapCount>](gcheapcount-element.md)|Specifica il numero di heap/thread da usare per il Garbage Collection server.  |
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Specifica le dimensioni della soglia che determinano l'uso degli oggetti nell'heap degli oggetti grandi (LOH).|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Specifica se creare affinità tra i thread GC del server con CPU.|
|[\<gcServer>](gcserver-element.md)|Specifica se Common Language Runtime esegue Garbage Collection per server.|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|Specifica se il runtime usa i criteri dell'editore di sicurezza per l'accesso di codice.|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|Specifica se il runtime consente al codice gestito di rilevare violazioni di accesso e altre eccezioni di stato danneggiato.|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|Specifica se gli assembly da origini remote vengono caricati con attendibilità totale.|
|[\<memoryCache>](memorycache-element-cache-settings.md)|Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .|
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per l'istanza `namedCache` .|
|[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)|Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.|
|[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)|Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Specifica se il runtime utilizza una quantità di memoria fissa per calcolare i codici hash per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .|
|[\<PreferComInsteadOfManagedRemoting>](prefercominsteadofmanagedremoting-element.md)|Specifica che il runtime userà l'interoperabilità COM anziché la comunicazione remota tra i limiti del dominio applicazione.|
|[\<probing>](probing-element.md)|Specifica le sottodirectory in cui il runtime esegue la ricerca al momento del caricamento degli assembly.|
|[\<publisherPolicy>](publisherpolicy-element.md)|Specifica se il runtime applica i criteri dell'editore.|
|[\<qualifyAssembly>](qualifyassembly-element.md)|Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.|
|[\<relativeBindForResources>](relativebindforresources-element.md)|Ottimizza le ricerche degli assembly satellite.|
|[\<remove>](remove-element-for-namedcaches.md)|Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.|
|[\<runtime>](runtime-element.md)|Contiene informazioni sull'associazione degli assembly e il comportamento di Garbage Collection.|
|[\<shadowCopyTimeStampVerification>](shadowcopyverifybytimestamp-element.md)|Specifica se la copia shadow usa il comportamento di avvio predefinito introdotto nel .NET Framework 4 o Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework.|
|[\<supportPortability>](supportportability-element.md)|Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Fornisce informazioni sulla configurazione per la cache degli oggetti in memoria predefinita.|
|[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)|Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|Specifica se le eccezioni di attività non gestite devono comportare l'arresto di un processo in esecuzione.|
|[\<TimeSpan_LegacyFormatMode>](runtime-element.md)|Specifica se il runtime usa la formattazione legacy per i valori di <xref:System.TimeSpan>.|
|[\<useLegacyJit>](uselegacyjit-element.md)|Determina se Common Language Runtime usa il compilatore JIT a 64 bit legacy per la compilazione JIT.|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|Specifica se il runtime calcola i codici hash per le stringhe in base al dominio applicazione.|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|Richiede al runtime di usare dimensioni dello stack esplicite quando crea determinati thread usati internamente, invece delle dimensioni dello stack predefinite.|

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione](../index.md)
- [Per disabilitare Garbage Collection simultanee](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Reindirizzamento delle versioni di assembly](../../redirect-assembly-versions.md)
