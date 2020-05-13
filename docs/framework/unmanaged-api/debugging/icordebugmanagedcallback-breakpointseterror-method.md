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
ms.openlocfilehash: 0fa25dd33223ad2a9521aed0917ce35a2a33fa2f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213387"
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
  
## <a name="remarks"></a>Osservazioni  
 Il punto di interruzione specificato non verrà mai raggiunto. Il debugger dovrebbe disattivarlo e riassociarlo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
