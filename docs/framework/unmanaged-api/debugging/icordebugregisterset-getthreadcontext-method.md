---
title: Metodo ICorDebugRegisterSet::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1ee576f41d20fdf4523fb4b566c3f2ce870d62c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469092"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>Metodo ICorDebugRegisterSet::GetThreadContext
Ottiene il contesto del thread corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `contextSize`  
 [in] Le dimensioni, in byte, del `context` matrice.  
  
 `context`  
 [in, out] Una matrice di byte che compongono Win32 `CONTEXT` struttura per la piattaforma corrente.  
  
## <a name="remarks"></a>Note  
 Il debugger deve chiamare questa funzione anziché Win32 `GetThreadContext` funzionare, perché il thread potrebbe essere in uno stato "cui" in cui il contesto è stato modificato temporaneamente. I dati restituiti sono Win32 `CONTEXT` struttura per la piattaforma corrente.  
  
 Per i frame foglia, i client devono controllare i registri che sono validi con [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
