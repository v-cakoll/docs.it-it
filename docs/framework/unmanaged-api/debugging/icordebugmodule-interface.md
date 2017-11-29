---
title: ICorDebugModule Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule
helpviewer_keywords: ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ced01c9c01a32468f371a8e172c878337fb79757
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmodule-interface1"></a>ICorDebugModule Interface1
Rappresenta un modulo common language runtime (CLR), ovvero un file eseguibile o una libreria di collegamento dinamico (DLL).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CreateBreakpoint (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|Non implementato.|  
|[EnableClassLoadCallbacks (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|Determina se il [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.|  
|[EnableJITDebugging (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Determina se il compilatore di just-in-time (JIT) consente di mantenere le informazioni di debug per i metodi all'interno del modulo.|  
|[GetAssembly (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|Ottiene l'assembly per il modulo che lo contiene.|  
|[Metodo GetBaseAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|Ottiene l'indirizzo di base del modulo.|  
|[GetClassFromToken (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|Ottiene l'oggetto ICorDebugClass dai metadati.|  
|[GetEditAndContinueSnapshot (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|Deprecato.|  
|[GetFunctionFromRVA (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|Non implementato.|  
|[GetFunctionFromToken (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|Ottiene la funzione specificata dal token di metadati.|  
|[GetGlobalVariableValue (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|Ottiene un oggetto valore per la variabile globale specificata.|  
|[GetMetaDataInterface (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|Ottiene un puntatore di interfaccia di metadati che può essere utilizzato per esaminare i metadati per il modulo.|  
|[GetName (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|Ottiene il nome del file del modulo.|  
|[GetProcess (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|Ottiene il processo di contenitore per questo modulo.|  
|[GetSize (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|Ottiene le dimensioni del modulo in byte.|  
|[GetToken (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|Ottiene il token per la voce della tabella per questo modulo.|  
|[IsDynamic (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|Indica se il modulo è dinamico.|  
|[IsInMemory (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|Indica se questo modulo esiste solo in memoria.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
