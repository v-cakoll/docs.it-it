---
title: Metodo ICorDebugController::EnumerateThreads
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 291f6c05171b5e507afaa70537aafdc9002a506e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125403"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>Metodo ICorDebugController::EnumerateThreads
Ottiene un enumeratore per i thread gestiti attivi nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppThreads`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugThreadEnum" che rappresenta un enumeratore per tutti i thread gestiti attivi nel processo.  
  
## <a name="remarks"></a>Note  
 Un thread viene considerato attivo dopo l'invio del callback [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) e prima dell'invio del callback [ICorDebugManagedCallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) . Un thread gestito potrebbe non avere necessariamente frame gestiti nello stack. I thread possono essere enumerati anche prima del callback [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) . L'enumerazione sarà naturalmente vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
