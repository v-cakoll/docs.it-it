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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430453"
---
# <a name="runtime-element"></a>\<runtime> Elemento

Fornisce le informazioni utilizzate dal Common Language Runtime per configurare le applicazioni.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<runtime>

## <a name="syntax"></a>Sintassi

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

No.

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
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Specifica che il runtime deve usare il comportamento di ordinamento legacy durante l'esecuzione di confronti tra stringhe.|
|[\<developmentMode>](developmentmode-element.md)|Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Specifica se la memorizzazione nella cache degli errori di associazione, che è il comportamento predefinito in .NET Framework versione 2,0, è disabilitata.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Specifica se viene eseguito il commit dello stack di thread completo quando viene avviato un thread.|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Determina se i metodi di analisi di data e ora usano un set di regole di rettifica per analizzare le stringhe di data che contengono solo un indicatore di giorno, mese, ora e AM/PM.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).|
|[\<etwEnable>](etwenable-element.md)|Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|Nelle piattaforme a 64 bit, abilita le matrici con dimensione totale maggiore di 2 gigabyte (GB).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Specifica se il Common Language Runtime viene eseguito Garbage Collection simultaneamente.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Specifica se Garbage Collection supporta più gruppi di CPU.|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Definisce l'affinità tra Garbage Collection heap e singoli processori.|
|[\<GCHeapCount>](gcheapcount-element.md)|Specifica il numero di heap/thread da usare per il Garbage Collection server.|
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Specifica le dimensioni della soglia che determinano l'inserimento degli oggetti nell'heap degli oggetti grandi da parte del Garbage Collector.|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Specifica se creare affinità tra il server Garbage Collection thread con le CPU.|
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
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|Specifica se la copia shadow usa il comportamento di avvio predefinito introdotto nel .NET Framework 4 o Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework.|
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

## <a name="remarks"></a>Commenti

Gli elementi figlio nella [\<runtime>](runtime-element.md) sezione di un file di configurazione vengono usati dal Common Language Runtime per configurare la modalità di esecuzione di un'applicazione. Ad esempio, l' [\<gcServer>](gcserver-element.md) elemento determina se il Garbage Collector utilizza Garbage Collection workstation o Garbage Collection server, l' [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) elemento determina se il Common Language Runtime calcola i codici hash per la stringa in base all'applicazione o al dominio dell'applicazione e l' `AppContextSwitchOverrides` elemento consente agli utenti della libreria di acconsentire o rifiutare esplicitamente le funzionalità modificate fornite da una libreria.

Gli elementi nella [\<runtime>](runtime-element.md) sezione vengono letti automaticamente dall'Common Language Runtime all'avvio dell'applicazione. È anche possibile definire il file di configurazione per un dominio dell'applicazione non predefinito fornendone il nome alla proprietà. le <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> impostazioni vengono lette automaticamente quando il dominio applicazione viene caricato. Raramente, se mai, è necessario leggere direttamente le impostazioni nella [\<runtime>](runtime-element.md) sezione del file di configurazione dell'applicazione.

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
