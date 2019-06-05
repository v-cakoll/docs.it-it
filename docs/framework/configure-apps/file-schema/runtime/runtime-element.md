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
ms.openlocfilehash: ea9dfd00590aff9c1a882480c76ef5c9f6afc6ec
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689754"
---
# <a name="runtime-element"></a>\<runtime > elemento

Fornisce informazioni usate da common language runtime per configurare le applicazioni.

\<configuration>\
\<runtime>

## <a name="syntax"></a>Sintassi

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Le sezioni seguenti descrivono gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

Nessuno.

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<alwaysFlowImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.|
|[\<AppContextSwitchOverrides>](../../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)|Definisce una o più opzioni di compatibilità usate dalla classe <xref:System.AppContext> per fornire un meccanismo di rifiuto esplicito per la nuova funzionalità.|
|[\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.|
|[\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.|
|[\<appDomainResourceMonitoring>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.|
|[\<assemblyBinding>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|
|[\<bypassTrustedAppStrongNames>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Specifica se la verifica del nome sicuro per gli assembly attendibili deve essere ignorata.|
|[\<CompatSortNLSVersion>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Specifica che il runtime deve utilizzare il comportamento di ordinamento legacy quando si eseguono confronti di stringhe.|
|[\<developmentMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.|
|[\<disableCachingBindingFailures>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Specifica se la memorizzazione nella cache di errori di associazione, ovvero il comportamento predefinito in .NET Framework versione 2.0, è disabilitato.|
|[\<disableCommitThreadStack>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Specifica se viene eseguito il commit dello stack di thread completo quando viene avviato un thread.|
|[\<disableFusionUpdatesFromADManager>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.|
|[\<EnableAmPmParseAdjustment>](../../../../../docs/framework/configure-apps/file-schema/runtime/enableampmparseadjustment-element.md)|Determina se i metodi di analisi di data e ora usano un set di regole di rettifica per analizzare le stringhe di data che contengono solo un indicatore di giorno, mese, ora e AM/PM.|
|[\<enforceFIPSPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).|
|[\<etwEnable>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.|
|[\<gcAllowVeryLargeObjects>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|Nelle piattaforme a 64 bit, abilita le matrici con dimensione totale maggiore di 2 gigabyte (GB).|
|[\<gcConcurrent>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Specifica se common language runtime esegue garbage collection simultanea.|
|[\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Specifica se Garbage Collection supporta più gruppi di CPU.|
|[\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Specifica se Common Language Runtime esegue Garbage Collection per server.|
|[\<generatePublisherEvidence>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Specifica se il runtime usa i criteri dell'editore di sicurezza per l'accesso di codice.|
|[\<legacyCorruptedStateExceptionsPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Specifica se il runtime consente al codice gestito di rilevare violazioni di accesso e altre eccezioni di stato danneggiato.|
|[\<legacyImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.|
|[\<loadfromRemoteSources>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Specifica se gli assembly da origini remote vengono caricati con attendibilità totale.|
|[\<NetFx40_LegacySecurityPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.|
|[\<NetFx40_PInvokeStackResilience>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Specifica se il runtime utilizza una quantità di memoria fissa per calcolare i codici hash per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .|
|[\<PreferComInsteadOfRemoting>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Specifica che il runtime userà l'interoperabilità COM anziché la comunicazione remota tra i limiti del dominio applicazione.|
|[\<relativeBindForResources>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Ottimizza le ricerche degli assembly satellite.|
|[\<shadowCopyVerifyByTimeStamp>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Specifica se la copia shadow Usa il comportamento di avvio predefinito introdotto in .NET Framework 4 o Ripristina il comportamento di avvio delle versioni precedenti di .NET Framework.|
|[\<supportPortability>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.|
|[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Fornisce informazioni sulla configurazione per la cache degli oggetti in memoria predefinita.|
|[\<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.|
|[\<ThrowUnobservedTaskExceptions>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Specifica se le eccezioni di attività non gestite devono comportare l'arresto di un processo in esecuzione.|
|[\<TimeSpan_LegacyFormatMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/timespan-legacyformatmode-element.md)|Specifica se il runtime usa la formattazione legacy per i valori di <xref:System.TimeSpan>.|
|[\<useLegacyJit>](../../../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)|Determina se Common Language Runtime usa il compilatore JIT a 64 bit legacy per la compilazione JIT.|
|[\<UseRandomizedStringHashAlgorithm>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Specifica se il runtime calcola i codici hash per le stringhe in base al dominio applicazione.|
|[\<UseSmallInternalThreadStacks>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Richiede al runtime di usare dimensioni dello stack esplicite quando crea determinati thread usati internamente, invece delle dimensioni dello stack predefinite.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|

## <a name="remarks"></a>Note

Gli elementi figlio di [ \<runtime >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione di un file di configurazione vengono usati da common language runtime per configurare la modalità di esecuzione di un'applicazione. Ad esempio, il [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento determina se il garbage collector Usa garbage collection per workstation o garbage collection per server, il [ \< UseRandomizedStringHashAlgorithm >](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md) elemento determina se common language runtime calcola i codici hash per la stringa in un'applicazione o una singola operazione di dominio per ogni applicazione e il `AppContextSwitchOverrides` elemento consente agli utenti della libreria per acconsentire o rifiutare esplicitamente la funzionalità modificate fornita da una libreria.

Gli elementi di [ \<runtime >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione vengono letti automaticamente dal common language runtime all'avvio dell'applicazione. È anche possibile definire il file di configurazione per un dominio dell'applicazione non predefinito specificando il nome per il <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> proprietà; le relative impostazioni vengono lette automaticamente quando viene caricato il dominio dell'applicazione. Si dovrebbe raramente, se mai, ha l'esigenza di leggere direttamente le impostazioni nel [ \<runtime >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione nel file di configurazione dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
