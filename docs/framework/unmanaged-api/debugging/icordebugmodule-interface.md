---
title: Interfaccia ICorDebugModule
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
ms.openlocfilehash: 105e56f2508eabbb6876a09d35e6abfbfc08950b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212243"
---
# <a name="icordebugmodule-interface"></a>Interfaccia ICorDebugModule

Rappresenta un modulo di Common Language Runtime (CLR), ovvero un file eseguibile o una libreria a collegamento dinamico (DLL).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](icordebugmodule-createbreakpoint-method.md)|Non implementato.|  
|[Metodo EnableClassLoadCallbacks](icordebugmodule-enableclassloadcallbacks-method.md)|Determina se i callback [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.|  
|[Metodo EnableJITDebugging](icordebugmodule-enablejitdebugging-method.md)|Determina se il compilatore JIT (just-in-Time) conserva le informazioni di debug per i metodi all'interno di questo modulo.|  
|[Metodo GetAssembly](icordebugmodule-getassembly-method.md)|Ottiene l'assembly contenitore per questo modulo.|  
|[Metodo GetBaseAddress](icordebugmodule-getbaseaddress-method.md)|Ottiene l'indirizzo di base del modulo.|  
|[Metodo GetClassFromToken](icordebugmodule-getclassfromtoken-method.md)|Ottiene l'oggetto ICorDebugClass dai metadati.|  
|[Metodo GetEditAndContinueSnapshot](icordebugmodule-geteditandcontinuesnapshot-method.md)|Operazione deprecata.|  
|[Metodo GetFunctionFromRVA](icordebugmodule-getfunctionfromrva-method.md)|Non implementato.|  
|[Metodo GetFunctionFromToken](icordebugmodule-getfunctionfromtoken-method.md)|Ottiene la funzione specificata dal token di metadati.|  
|[Metodo GetGlobalVariableValue](icordebugmodule-getglobalvariablevalue-method.md)|Ottiene un oggetto valore per la variabile globale specificata.|  
|[Metodo GetMetaDataInterface](icordebugmodule-getmetadatainterface-method.md)|Ottiene un puntatore a interfaccia dei metadati che può essere utilizzato per esaminare i metadati per il modulo.|  
|[Metodo GetName](icordebugmodule-getname-method.md)|Ottiene il nome file del modulo.|  
|[Metodo GetProcess](icordebugmodule-getprocess-method.md)|Ottiene il processo contenitore per questo modulo.|  
|[Metodo GetSize](icordebugmodule-getsize-method.md)|Ottiene le dimensioni in byte del modulo.|  
|[Metodo GetToken](icordebugmodule-gettoken-method.md)|Ottiene il token per la voce della tabella per questo modulo.|  
|[Metodo IsDynamic](icordebugmodule-isdynamic-method.md)|Indica se il modulo è dinamico.|  
|[Metodo IsInMemory](icordebugmodule-isinmemory-method.md)|Indica se il modulo esiste solo in memoria.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
