---
title: Enumerazioni di debug
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: c37b6ff42b428184d301d63b6dbbd9d80a72bf3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179136"
---
# <a name="debugging-enumerations"></a>Enumerazioni di debug
Questa sezione descrive le enumerazioni non gestite usate dall'API di debug.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Enumerazione CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md)  
 Fornisce i valori utilizzati dal metodo [ICLRDebugging::OpenVirtualProcess.](iclrdebugging-openvirtualprocess-method.md)  
  
 [Enumerazione CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md)  
 Indica quali aree di memoria deve includere una chiamata al metodo [ICLRDataEnumMemoryRegions::EnumMemoryRegions.](iclrdataenummemoryregions-enummemoryregions-method.md)  
  
 [Enumerazione COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md)  
 Identifica il tipo di processo da enumerare.  
  
 [Enumerazione CorDebugBlockingReason](cordebugblockingreason-enumeration.md)  
 Specifica i motivi che possono causare il blocco di un thread su un oggetto specifico.  
  
 CorDebugChainReason  
 Indica i motivi che determinano l'avvio di una catena di chiamate.  
  
 [Enumerazione CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)  
 Descrive in che modo una funzione esportata richiama il codice gestito.  
  
 [Enumerazione CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)  
 Descrive il motivo per cui una funzione esportata chiama il codice gestito.  
  
 CorDebugCreateProcessFlags  
 Fornisce opzioni di debug aggiuntive che possono essere utilizzate in una chiamata al [metodo ICorDebug::CreateProcess](icordebug-createprocess-method.md) .  
  
 [Enumerazione CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md)  
 Indica il tipo di evento le cui informazioni vengono decodificate dal metodo [DecodeEvent.](icordebugprocess6-decodeevent-method.md)  
  
 [Enumerazione CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md)  
 Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.  
  
 CorDebugExceptionCallbackType  
 Indica il tipo di callback eseguito da un [evento ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) .  
  
 [Enumerazione CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md)  
 Offre informazioni aggiuntive su un'eccezione.  
  
 CorDebugExceptionUnwindCallbackType  
 Indica l'evento segnalato dal callback durante la fase di rimozione.  
  
 [Enumerazione CorDebugGCType](cordebuggctype-enumeration.md)  
 Indica se un Garbage Collector è in esecuzione in una workstation o in un server.  
  
 [Enumerazione CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md)  
 Specifica la generazione di un'area di memoria nell'heap gestito.  
  
 CorDebugHandleType  
 Indica il tipo di handle.  
  
 [Enumerazione CorDebugIlToNativeMappingTypes](cordebugiltonativemappingtypes-enumeration.md)  
 Indica se un intervallo specifico di istruzioni native corrisponde a un'area di codice speciale.  
  
 CorDebugIntercept  
 Indica i tipi di codice in cui è possibile eseguire l'istruzione.  
  
 [Enumerazione CorDebugInterfaceVersion](cordebuginterfaceversion-enumeration.md)  
 Specifica una versione di .NET Framework o una versione di .NET Framework in cui è stata introdotta un'interfaccia.  
  
 CorDebugInternalFrameType  
 Identifica il tipo di stack frame.  
  
 [Enumerazione CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)  
 Contiene valori che influenzano il comportamento del compilatore JIT gestito.  
  
 [Enumerazione CorDebugJITCompilerFlagsDeprecated](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Obsoleto. Utilizzare `CORDEBUG_JIT_DEFAULT` invece il membro dell'enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) .  
  
 CorDebugMappingResult  
 Fornisce informazioni su come è stato ottenuto il valore del puntatore dell'istruzione.  
  
 [Enumerazione CorDebugMDAFlags](cordebugmdaflags-enumeration.md)  
 Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.  
  
 [Enumerazione CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md)  
 Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.  
  
 [Enumerazione CorDebugPlatform](cordebugplatform-enumeration.md)  
 Fornisce i valori della piattaforma di destinazione utilizzati dal [metodo ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) .  
  
 [Enumerazione CorDebugRecordFormat](cordebugrecordformat-enumeration.md)  
 Descrive il formato dei dati in una matrice di byte che contiene informazioni su un evento di debug per le eccezioni native.  
  
 CorDebugRegister  
 Specifica i registri associati a un'architettura di processore specifica.  
  
 [Enumerazione CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md)  
 Indica se il contesto proviene dal frame attivo (o foglia) sullo stack o se è stato calcolato dalla rimozione da un altro frame.  
  
 [Enumerazione CorDebugStateChange](cordebugstatechange-enumeration.md)  
 Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.  
  
 CorDebugStepReason  
 Indica l'esito di una singola istruzione.  
  
 CorDebugThreadState  
 Specifica lo stato di un thread per il debug.  
  
 \>CorDebugUnmappedStop  
 Specifica il tipo di codice non mappato che può attivare un arresto nell'esecuzione del codice da parte del gestore di istruzioni.  
  
 CorDebugUserState  
 Indica lo stato utente di un thread.  
  
 [Enumerazione CorGCReferenceType](corgcreferencetype-enumeration.md)  
 Identifica l'origine di un oggetto per la Garbage Collection.  
  
 [Enumerazione ILCodeKind](ilcodekind-enumeration.md)  
 Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.  
  
 [Enumerazione LoggingLevelEnum](logginglevelenum-enumeration.md)  
 Indica il livello di gravità di un messaggio descrittivo scritto nel registro eventi quando un thread gestito registra un evento.  
  
 [Enumerazione LogSwitchCallReason](logswitchcallreason-enumeration.md)  
 Indica l'operazione che è stata eseguita su un'opzione di debug/traccia.  
  
 [Enumerazione VariableLocationType](variablelocationtype-enumeration.md)  
 Indica il tipo di posizione nativo di una variabile.  
  
 [Enumerazione WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md)  
 Fornisce i valori che specificano se gli aggiornamenti in memoria ai metadati sono visibili a un debugger.

 [Enumerazione ClrDataSourceType](clrdatasourcetype-enumeration.md) Fornisce i valori utilizzati dalla struttura CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](debugging-coclasses.md)  
  
 [Interfacce di debug](debugging-interfaces.md)  
  
 [Funzioni statiche globali di debug](debugging-global-static-functions.md)  
  
 [Strutture di debug](debugging-structures.md)
