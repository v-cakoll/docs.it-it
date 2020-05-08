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
ms.openlocfilehash: 4d69f13d4716b43c815148ff0fe4aa087b57c6e5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892761"
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
  
## <a name="remarks"></a>Osservazioni  
 Un thread viene considerato attivo dopo l'invio del callback [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) e prima dell'invio del callback [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) . Un thread gestito potrebbe non avere necessariamente frame gestiti nello stack. I thread possono essere enumerati anche prima del callback [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . L'enumerazione sarà naturalmente vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
