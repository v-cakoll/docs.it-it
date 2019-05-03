---
title: Enumerazioni di debug
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5edd6dfb3dac05ce4614c43949f2ec4c19b5f742
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698512"
---
# <a name="debugging-enumerations"></a>Enumerazioni di debug
Questa sezione descrive le enumerazioni non gestite usate dall'API di debug.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Enumerazione CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 Fornisce i valori utilizzati per il [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) (metodo).  
  
 [Enumerazione CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 Indica una chiamata a quali aree di memoria di [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) deve includere (metodo).  
  
 [Enumerazione COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 Identifica il tipo di processo da enumerare.  
  
 [Enumerazione CorDebugBlockingReason](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 Specifica i motivi che possono causare il blocco di un thread su un oggetto specifico.  
  
 CorDebugChainReason  
 Indica i motivi che determinano l'avvio di una catena di chiamate.  
  
 [Enumerazione CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 Descrive in che modo una funzione esportata richiama il codice gestito.  
  
 [Enumerazione CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 Descrive il motivo per cui una funzione esportata chiama il codice gestito.  
  
 CorDebugCreateProcessFlags  
 Fornisce opzioni aggiuntive di debug che possono essere utilizzate in una chiamata ai [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) (metodo).  
  
 [Enumerazione CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 Indica il tipo di evento le cui informazioni sono decodificate dal [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) (metodo).  
  
 [Enumerazione CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.  
  
 CorDebugExceptionCallbackType  
 Indica il tipo di callback che viene eseguita da un [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) evento.  
  
 [Enumerazione CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 Offre informazioni aggiuntive su un'eccezione.  
  
 CorDebugExceptionUnwindCallbackType  
 Indica l'evento segnalato dal callback durante la fase di rimozione.  
  
 [Enumerazione CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 Indica se un Garbage Collector è in esecuzione in una workstation o in un server.  
  
 [Enumerazione CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 Specifica la generazione di un'area di memoria nell'heap gestito.  
  
 CorDebugHandleType  
 Indica il tipo di handle.  
  
 [Enumerazione CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 Indica se un intervallo specifico di istruzioni native corrisponde a un'area di codice speciale.  
  
 CorDebugIntercept  
 Indica i tipi di codice in cui è possibile eseguire l'istruzione.  
  
 [Enumerazione CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 Specifica una versione di .NET Framework o una versione di .NET Framework in cui è stata introdotta un'interfaccia.  
  
 CorDebugInternalFrameType  
 Identifica il tipo di stack frame.  
  
 [Enumerazione CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 Contiene valori che influenzano il comportamento del compilatore JIT gestito.  
  
 [Enumerazione CorDebugJITCompilerFlagsDeprecated](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Obsoleta. Usare la `CORDEBUG_JIT_DEFAULT` membro della [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione invece.  
  
 CorDebugMappingResult  
 Fornisce informazioni su come è stato ottenuto il valore del puntatore dell'istruzione.  
  
 [Enumerazione CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.  
  
 [Enumerazione CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.  
  
 [Enumerazione CorDebugPlatform](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 Fornisce i valori di piattaforma di destinazione utilizzati per il [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) (metodo).  
  
 [Enumerazione CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 Descrive il formato dei dati in una matrice di byte che contiene informazioni su un evento di debug per le eccezioni native.  
  
 CorDebugRegister  
 Specifica i registri associati a un'architettura di processore specifica.  
  
 [Enumerazione CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 Indica se il contesto proviene dal frame attivo (o foglia) sullo stack o se è stato calcolato dalla rimozione da un altro frame.  
  
 [Enumerazione CorDebugStateChange](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.  
  
 CorDebugStepReason  
 Indica l'esito di una singola istruzione.  
  
 CorDebugThreadState  
 Specifica lo stato di un thread per il debug.  
  
 \>CorDebugUnmappedStop  
 Specifica il tipo di codice non mappato che può attivare un arresto nell'esecuzione del codice da parte del gestore di istruzioni.  
  
 CorDebugUserState  
 Indica lo stato utente di un thread.  
  
 [Enumerazione CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 Identifica l'origine di un oggetto per la Garbage Collection.  
  
 [Enumerazione ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.  
  
 [Enumerazione LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 Indica il livello di gravità di un messaggio descrittivo scritto nel registro eventi quando un thread gestito registra un evento.  
  
 [Enumerazione LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 Indica l'operazione che è stata eseguita su un'opzione di debug/traccia.  
  
 [Enumerazione VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 Indica il tipo di percorso nativo di una variabile.  
  
 [Enumerazione WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 Fornisce i valori che specificano se gli aggiornamenti in memoria ai metadati sono visibili a un debugger. 

 [Enumerazione ClrDataSourceType](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) fornisce valori utilizzati dalla struttura CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
