---
title: Metodo ICorDebugManagedCallback2::FunctionRemapComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: d49992b1f4b25586f6171a51b351a25d453560f2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212152"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a>Metodo ICorDebugManagedCallback2::FunctionRemapComplete
Notifica al debugger che l'esecuzione del codice è cambiata a una nuova versione di una funzione modificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene la funzione modificata.  
  
 `pThread`  
 in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato rilevato il punto di interruzione del mapping.  
  
 `pFunction`  
 in Puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione nel thread.  
  
## <a name="remarks"></a>Osservazioni  
 Questo callback offre al debugger un'opportunità per ricreare eventuali stepper che in precedenza erano disponibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
