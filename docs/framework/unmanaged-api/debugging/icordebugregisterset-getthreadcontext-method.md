---
title: Metodo ICorDebugRegisterSet::GetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 910bb09aa011efc9f81cf5c62a58d39236d723de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
  
#### <a name="parameters"></a>Parametri  
 `contextSize`  
 [in] Le dimensioni, in byte, del `context` matrice.  
  
 `context`  
 [in, out] Una matrice di byte che costituiscono Win32 `CONTEXT` struttura per la piattaforma corrente.  
  
## <a name="remarks"></a>Note  
 Il debugger deve chiamare questa funzione anziché Win32 `GetThreadContext` funzione, perché il thread potrebbe essere in uno stato "fraudolente" il contesto in cui è cambiato temporaneamente. I dati restituiti sono Win32 `CONTEXT` struttura per la piattaforma corrente.  
  
 Per il frame non foglia, i client devono controllare quali registri sono validi con [GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugRegisterSet (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
