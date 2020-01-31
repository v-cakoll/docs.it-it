---
title: Metodo ICorDebugManagedCallback::BreakpointSetError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
ms.openlocfilehash: 67d4972ee38a54d43b4a096847cc61fa3402b042
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788441"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a>Metodo ICorDebugManagedCallback::BreakpointSetError
Notifica al debugger che il Common Language Runtime non è stato in grado di associare accuratamente un punto di interruzione impostato prima della compilazione JIT (just-in-Time) di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione non associato.  
  
 `pThread`  
 in Puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione non associato.  
  
 `pBreakpoint`  
 in Puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione non associato.  
  
 `dwError`  
 in Intero che indica l'errore.  
  
## <a name="remarks"></a>Note  
 Il punto di interruzione specificato non verrà mai raggiunto. Il debugger dovrebbe disattivarlo e riassociarlo.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
