---
title: Metodo ICorDebugManagedCallback2::ExceptionUnwind
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
ms.openlocfilehash: 8f66369d3ac5ddcfe38fe579cac728eb3a250165
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205631"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a>Metodo ICorDebugManagedCallback2::ExceptionUnwind
Fornisce una notifica di stato durante il processo di rimozione dell'eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stata generata l'eccezione.  
  
 `pThread`  
 in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.  
  
 `dwEventType`  
 in Valore dell'enumerazione CorDebugExceptionUnwindCallbackType che specifica l'evento che viene segnalato dal callback durante la fase di rimozione.  
  
 `dwFlags`  
 in Valore dell'enumerazione [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) che specifica informazioni aggiuntive sull'eccezione.  
  
## <a name="remarks"></a>Osservazioni  
 `ExceptionUnwind`viene chiamato in diversi punti durante la fase di rimozione del processo di gestione delle eccezioni. `ExceptionUnwind`può essere chiamato più volte durante la rimozione di una singola eccezione.  
  
 Se `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, il puntatore all'istruzione si troverà nel frame foglia del thread, in corrispondenza del punto di sequenza precedente, che può essere costituito da diverse istruzioni prima, dall'istruzione che ha generato l'eccezione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
