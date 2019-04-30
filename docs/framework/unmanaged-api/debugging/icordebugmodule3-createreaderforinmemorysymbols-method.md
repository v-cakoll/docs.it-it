---
title: Metodo ICorDebugModule3::CreateReaderForInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccfe83707b6354c42a4c3c81e911918b2ea79ec4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942454"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>Metodo ICorDebugModule3::CreateReaderForInMemorySymbols
Crea un lettore di simboli di debug per un modulo dinamico.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a>Parametri  
 riid  
 [in] IID dell'interfaccia COM da restituire. Si tratta in genere un [interfaccia di ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).  
  
 ppObj  
 [out] Puntatore a un puntatore a interfaccia restituito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 È stato creato il lettore.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 Il modulo non è un modulo in memoria o dinamico.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 Simboli non sono stati forniti dall'applicazione o non sono ancora disponibili.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile creare il lettore.  
  
## <a name="remarks"></a>Note  
 Questo metodo può essere anche usati per creare un oggetto lettore di simboli per i moduli (modifikaci nedynamického) in memoria, ma solo dopo che i simboli sono disponibili prima di tutto (indicato dal [metodo UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).  
  
 Questo metodo restituisce una nuova istanza del lettore ogni volta che viene chiamato (ad esempio [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)). Pertanto, il debugger deve memorizzare nella cache il risultato e richiedere una nuova istanza solo quando i dati sottostanti sia stato modificato (ovvero, quando un [LoadClass (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback viene ricevuto).  
  
 I moduli dinamici non sono disponibili eventuali simboli disponibili fino a quando non è stato caricato il primo tipo (come indicato dal [metodo LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
