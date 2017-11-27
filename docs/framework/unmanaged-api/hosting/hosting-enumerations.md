---
title: Enumerazioni di hosting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f415b4f3062a83f97d2bf186981289cf16e555a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-enumerations"></a>Enumerazioni di hosting
In questa sezione descrive le enumerazioni non gestite usate dall'API di hosting.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [CLSID_RESOLUTION_FLAGS (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/clsid-resolution-flags-enumeration.md)  
 Contiene valori che indicano il modo in cui deve risolvere common language runtime (CLR) un `CLSID`.  
  
 [COR_GC_STAT_TYPES (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 Specifica le statistiche devono essere registrati per una garbage collection.  
  
 [COR_GC_THREAD_STATS_TYPES (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-types-enumeration.md)  
 Indica le statistiche per un thread di garbage collection.  
  
 [EApiCategories (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 Vengono descritte le categorie di funzionalità che l'host può impedire l'esecuzione in codice parzialmente attendibile.  
  
 [EBindPolicyLevels (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)  
 Fornisce i flag che specificano il livello in cui applicare o modificare i criteri di assembly.  
  
 [ECLRAssemblyIdentityFlags (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)  
 Indica il tipo di identità di un assembly.  
  
 [Enumerazione EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 Vengono descritti gli eventi CLR per il quale l'host può registrare callback.  
  
 [EClrFailure (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 Descrive il set di errori per il quale un host può impostare le azioni dei criteri.  
  
 [Enumerazione EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 Viene descritto il set di operazioni per il quale un host può applicare le azioni dei criteri.  
  
 [EClrUnhandledException (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 Descrive le opzioni disponibili per la gestione delle eccezioni non gestite nel codice utente.  
  
 [EContextType (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 Descrive il contesto di sicurezza del thread attualmente in esecuzione.  
  
 [ECustomDumpFlavor (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 Contiene valori che indicano gli elementi da includere in un sottoinsieme di un heap personalizzato dump per la segnalazione di errori.  
  
 [ECustomDumpItemKind (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 Riservato per un'estensione futura del [Struttura CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) struttura.  
  
 [EHostApplicationPolicy (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ehostapplicationpolicy-enumeration.md)  
 Indica come modificare un [interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md) oggetto di interfaccia. Questa enumerazione è stata deprecata.  
  
 [EHostBindingPolicyModifyFlags (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)  
 Consente all'host di specificare il tipo di reindirizzamento che CLR deve essere eseguito quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.  
  
 [EInitializeNewDomainFlags (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)  
 Consente all'host di fornire il runtime con informazioni sull'inizializzazione di un dominio applicazione.  
  
 [EMemoryAvailable (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)  
 Contiene valori che indicano la quantità di memoria fisica disponibile nel computer.  
  
 [EMemoryCriticalLevel (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)  
 Contiene valori che indicano l'impatto di un errore quando un'allocazione di memoria specifico è stato richiesto ma non può essere soddisfatta.  
  
 [EPolicyAction (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 Descrive le azioni dei criteri dell'host è possibile impostare per le operazioni specificate da [enumerazione EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) e gli errori indicati da [EClrFailure (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
 [ESymbolReadingPolicy (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)  
 Contiene valori che impostano i criteri per la lettura dei file di programma (PDB) di database.  
  
 [ETaskType (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)  
 Contiene valori che indicano il tipo di attività rappresentata da un [ICLRTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o [IHostTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interfaccia.  
  
 [HOST_TYPE (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)  
 Contiene valori che specificano il tipo di host che esegue un'applicazione.  
  
 [Enumerazione MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md)  
 Contiene valori che specificano le caratteristiche della memoria allocata.  
  
 [METAHOST_CONFIG_FLAGS (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)  
 Vengono descritti i possibili flag restituiti nel `pdwConfigFlags` parametro del [ICLRMetaHostPolicy::](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo.  
  
 [METAHOST_POLICY_FLAGS (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)  
 Fornisce criteri di associazione che sono comuni per la maggior parte degli host di runtime.  
  
 [RUNTIME_INFO_FLAGS (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)  
 Contiene valori che indicano le informazioni relative al CLR devono essere restituite.  
  
 [StackOverflowType (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)  
 Contiene valori che indicano la causa sottostante di un evento di overflow dello stack.  
  
 [Enumerazione STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)  
 Contiene valori che indicano il comportamento di avvio di CLR.  
  
 [ValidatorFlags (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)  
 Contiene valori che indicano il tipo di convalida che deve essere eseguita in una chiamata a [metodo Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md).  
  
 [Enumerazione WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)  
 Indica l'azione di che un host deve intraprendere se l'operazione richiesta da blocchi di CLR.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [Funzioni di Hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
