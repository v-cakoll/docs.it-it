---
title: Enumerazioni di hosting
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
ms.openlocfilehash: 8edace3191ee4477b19f199d5db6c891c993dcd5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504303"
---
# <a name="hosting-enumerations"></a>Enumerazioni di hosting
In questa sezione vengono descritte le enumerazioni non gestite utilizzate dall'API di hosting.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Enumerazione CLSID_RESOLUTION_FLAGS](clsid-resolution-flags-enumeration.md)  
 Contiene valori che indicano il modo in cui il Common Language Runtime (CLR) deve risolvere un oggetto `CLSID` .  
  
 [Enumerazione COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md)  
 Specifica le statistiche da registrare per un Garbage Collection.  
  
 [Enumerazione COR_GC_THREAD_STATS_TYPES](cor-gc-thread-stats-types-enumeration.md)  
 Indica le statistiche Garbage Collection per un thread.  
  
 [Enumerazione EApiCategories](eapicategories-enumeration.md)  
 Vengono descritte le categorie di funzionalità che l'host può bloccare dall'esecuzione in codice parzialmente attendibile.  
  
 [Enumerazione EBindPolicyLevels](ebindpolicylevels-enumeration.md)  
 Fornisce i flag che specificano il livello al quale applicare o modificare i criteri di assembly.  
  
 [Enumerazione ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md)  
 Indica il tipo di identità di un assembly.  
  
 [Enumerazione EClrEvent](eclrevent-enumeration.md)  
 Vengono descritti gli eventi CLR per i quali l'host può registrare i callback.  
  
 [Enumerazione EClrFailure](eclrfailure-enumeration.md)  
 Descrive il set di errori per i quali un host può impostare le azioni dei criteri.  
  
 [Enumerazione EClrOperation](eclroperation-enumeration.md)  
 Descrive il set di operazioni per cui un host può applicare le azioni dei criteri.  
  
 [Enumerazione EClrUnhandledException](eclrunhandledexception-enumeration.md)  
 Descrive le opzioni disponibili per la gestione delle eccezioni non gestite nel codice utente.  
  
 [Enumerazione EContextType](econtexttype-enumeration.md)  
 Descrive il contesto di sicurezza del thread attualmente in esecuzione.  
  
 [Enumerazione ECustomDumpFlavor](ecustomdumpflavor-enumeration.md)  
 Contiene valori che indicano quali elementi includere in un subset personalizzato di un dump dell'heap quando si segnalano errori.  
  
 [Enumerazione ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)  
 Riservato per l'estensione futura della struttura della [struttura CustomDumpItem](customdumpitem-structure.md) .  
  
 [Enumerazione EHostApplicationPolicy](ehostapplicationpolicy-enumeration.md)  
 Indica come modificare un oggetto interfaccia [IHostAssemblyManager](ihostassemblymanager-interface.md) . Questa enumerazione è stata deprecata.  
  
 [Enumerazione EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md)  
 Consente all'host di specificare il tipo di reindirizzamento che CLR deve eseguire quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.  
  
 [Enumerazione EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md)  
 Consente all'host di fornire al Runtime informazioni sull'inizializzazione di un dominio applicazione.  
  
 [Enumerazione EMemoryAvailable](ememoryavailable-enumeration.md)  
 Contiene valori che indicano la quantità di memoria fisica disponibile nel computer.  
  
 [Enumerazione EMemoryCriticalLevel](ememorycriticallevel-enumeration.md)  
 Contiene valori che indicano l'effetto di un errore quando un'allocazione di memoria specifica è stata richiesta ma non può essere soddisfatta.  
  
 [Enumerazione EPolicyAction](epolicyaction-enumeration.md)  
 Descrive le azioni dei criteri che l'host può impostare per le operazioni descritte dall' [enumerazione EClrOperation](eclroperation-enumeration.md) e gli errori descritti dall' [Enumerazione EClrFailure](eclrfailure-enumeration.md).  
  
 [Enumerazione ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md)  
 Contiene valori che impostano i criteri per la lettura dei file di database di programma (PDB).  
  
 [Enumerazione ETaskType](etasktype-enumeration.md)  
 Contiene valori che indicano il tipo di attività rappresentata da un'interfaccia [ICLRTask](iclrtask-interface.md) o da un'interfaccia di [interfaccia IHostTask](ihosttask-interface.md) .  
  
 [Enumerazione HOST_TYPE](host-type-enumeration.md)  
 Contiene valori che specificano il tipo di host che avvia un'applicazione.  
  
 [Enumerazione MALLOC_TYPE](malloc-type-enumeration.md)  
 Contiene valori che specificano le caratteristiche della memoria da allocare.  
  
 [Enumerazione METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md)  
 Descrive i flag possibili restituiti nel `pdwConfigFlags` parametro del metodo [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
 [Enumerazione METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md)  
 Fornisce criteri di associazione comuni alla maggior parte degli host di Runtime.  
  
 [Enumerazione RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md)  
 Contiene valori che indicano le informazioni relative a CLR da restituire.  
  
 [Enumerazione StackOverflowType](stackoverflowtype-enumeration.md)  
 Contiene valori che indicano la cause sottostante di un evento di overflow dello stack.  
  
 [Enumerazione STARTUP_FLAGS](startup-flags-enumeration.md)  
 Contiene valori che indicano il comportamento di avvio di CLR.  
  
 [Enumerazione ValidatorFlags](validatorflags-enumeration.md)  
 Contiene valori che indicano il tipo di convalida che deve essere eseguita in una chiamata al [Metodo Validate](iclrvalidator-validate-method.md).  
  
 [Enumerazione WAIT_OPTION](wait-option-enumeration.md)  
 Indica l'azione che un host deve eseguire se un'operazione richiesta da CLR si blocca.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di hosting](hosting-coclasses.md)  
  
 [Interfacce di hosting](hosting-interfaces.md)  
  
 [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)  
  
 [Strutture di hosting](hosting-structures.md)
