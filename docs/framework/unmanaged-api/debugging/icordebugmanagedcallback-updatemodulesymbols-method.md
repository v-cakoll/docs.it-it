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
ms.openlocfilehash: 9ee6f43c94b8ff2e765d2a0dde0697c4c895a94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212373"
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
 in Puntatore a un oggetto COM Win32 `IStream` che contiene i simboli modificati.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo offre la possibilità di aggiornare la visualizzazione del debugger dei simboli di un modulo chiamando [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).  
  
 Questo callback può essere eseguito più volte per lo stesso modulo.  
  
 Un debugger deve tentare di associare i punti di interruzione a livello di origine non associati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
