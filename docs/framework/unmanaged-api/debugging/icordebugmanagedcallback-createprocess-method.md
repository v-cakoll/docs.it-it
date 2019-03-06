---
title: Metodo ICorDebugManagedCallback::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36e26101a21471fd840a07deef9f5085a88f2730
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487031"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a>Metodo ICorDebugManagedCallback::CreateProcess
Quando un processo è stato collegato o avviato per la prima volta, invia una notifica del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 [in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo di cui è stato collegato o avviato.  
  
## <a name="remarks"></a>Note  
 Questo metodo non viene chiamato fino a quando non viene inizializzato in common language runtime. La maggior parte delle [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) metodi restituiranno CORDBG_E_NOTREADY prima il `CreateProcess` callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
