---
title: <runtime> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime
helpviewer_keywords:
- <runtime> element
- runtime element
- container tags, <runtime> element
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
ms.openlocfilehash: 3825ae7c3e35193cb835981600fe1ef83097cd2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430453"
---
# <a name="runtime-element"></a>\<runtime> Element

Provides information used by the common language runtime to configure applications.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<runtime>

## <a name="syntax"></a>Sintassi

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

The following sections describe child elements and parent elements.

### <a name="attributes"></a>Attributi

Nessuna.

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|Definisce una o più opzioni di compatibilità usate dalla classe <xref:System.AppContext> per fornire un meccanismo di rifiuto esplicito per la nuova funzionalità.|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|Specifica se la verifica del nome sicuro per gli assembly attendibili deve essere ignorata.|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Specifies that the runtime should use legacy sorting behavior when performing string comparisons.|
|[\<developmentMode>](developmentmode-element.md)|Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Specifies whether the caching of binding failures, which is the default behavior in the .NET Framework version 2.0, is disabled.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Specifica se viene eseguito il commit dello stack di thread completo quando viene avviato un thread.|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Determina se i metodi di analisi di data e ora usano un set di regole di rettifica per analizzare le stringhe di data che contengono solo un indicatore di giorno, mese, ora e AM/PM.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).|
|[\<etwEnable>](etwenable-element.md)|Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|Nelle piattaforme a 64 bit, abilita le matrici con dimensione totale maggiore di 2 gigabyte (GB).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Specifies whether the common language runtime runs garbage collection concurrently.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Specifica se Garbage Collection supporta più gruppi di CPU.|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Defines the affinity between garbage collection heaps and individual processors.|
|[\<GCHeapCount>](gcheapcount-element.md)|Specifies the number of heaps/threads to use for server garbage collection.|
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Specifies the threshold size that causes the garbage collector to put objects on the large object heap.|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Specifies whether or not to affinitize server garbage collection threads with CPUs.|
|[\<gcServer>](gcserver-element.md)|Specifica se Common Language Runtime esegue Garbage Collection per server.|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|Specifica se il runtime usa i criteri dell'editore di sicurezza per l'accesso di codice.|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|Specifica se il runtime consente al codice gestito di rilevare violazioni di accesso e altre eccezioni di stato danneggiato.|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|Specifica se gli assembly da origini remote vengono caricati con attendibilità totale.|
|[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)|Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.|
|[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)|Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Specifica se il runtime utilizza una quantità di memoria fissa per calcolare i codici hash per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .|
|[\<PreferComInsteadOfRemoting>](prefercominsteadofmanagedremoting-element.md)|Specifica che il runtime userà l'interoperabilità COM anziché la comunicazione remota tra i limiti del dominio applicazione.|
|[\<relativeBindForResources>](relativebindforresources-element.md)|Ottimizza le ricerche degli assembly satellite.|
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.|
|[\<supportPortability>](supportportability-element.md)|Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Fornisce informazioni sulla configurazione per la cache degli oggetti in memoria predefinita.|
|[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)|Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|Specifica se le eccezioni di attività non gestite devono comportare l'arresto di un processo in esecuzione.|
|[\<TimeSpan_LegacyFormatMode>](timespan-legacyformatmode-element.md)|Specifica se il runtime usa la formattazione legacy per i valori di <xref:System.TimeSpan>.|
|[\<useLegacyJit>](uselegacyjit-element.md)|Determina se Common Language Runtime usa il compilatore JIT a 64 bit legacy per la compilazione JIT.|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|Specifica se il runtime calcola i codici hash per le stringhe in base al dominio applicazione.|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|Richiede al runtime di usare dimensioni dello stack esplicite quando crea determinati thread usati internamente, invece delle dimensioni dello stack predefinite.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|

## <a name="remarks"></a>Note

The child elements in the [\<runtime>](runtime-element.md) section of a configuration file are used by the common language runtime to configure how an application executes. For example, the [\<gcServer>](gcserver-element.md) element determines whether the garbage collector uses workstation garbage collection or server garbage collection, the [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) element determines whether the common language runtime calculates hash codes for string on a per-application or a per-application domain basis, and the `AppContextSwitchOverrides` element allows library users to opt in or opt out of changed  functionality provided by a library.

The elements in the [\<runtime>](runtime-element.md) section are read automatically by the common language runtime at application startup. You can also define the configuration file for a non-default application domain by supplying its name to the <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> property; its settings are read automatically when the application domain is loaded. You should rarely, if ever, have a need to directly read the settings in the [\<runtime>](runtime-element.md) section in your application's configuration file.

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
