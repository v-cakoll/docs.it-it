---
title: Metodo ICorDebugManagedCallback::UpdateModuleSymbols
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 2b64122489481c6b0fde605015720d0a56ba8fe2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788320"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a>Metodo ICorDebugManagedCallback::UpdateModuleSymbols
Notifica al debugger che i simboli per un modulo Common Language Runtime sono stati modificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il modulo in cui sono stati modificati i simboli.  
  
 `pModule`  
 in Puntatore a un oggetto ICorDebugModule che rappresenta il modulo in cui sono stati modificati i simboli.  
  
 `pSymbolStream`  
 in Puntatore a un oggetto `IStream` COM Win32 che contiene i simboli modificati.  
  
## <a name="remarks"></a>Note  
 Questo metodo offre la possibilità di aggiornare la visualizzazione del debugger dei simboli di un modulo chiamando [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).  
  
 Questo callback può essere eseguito più volte per lo stesso modulo.  
  
 Un debugger deve tentare di associare i punti di interruzione a livello di origine non associati.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
