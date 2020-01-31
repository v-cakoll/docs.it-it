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
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792084"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>Metodo ICorDebugRegisterSet::GetThreadContext
Ottiene il contesto del thread corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `contextSize`  
 in Dimensione, in byte, della matrice `context`.  
  
 `context`  
 [in, out] Matrice di byte che compongono la struttura di `CONTEXT` Win32 per la piattaforma corrente.  
  
## <a name="remarks"></a>Note  
 Il debugger deve chiamare questa funzione al posto della funzione Win32 `GetThreadContext`, perché il thread potrebbe trovarsi in uno stato di "Hijack" in cui il contesto è stato modificato temporaneamente. I dati restituiti sono una struttura di `CONTEXT` Win32 per la piattaforma corrente.  
  
 Per i frame non foglia, i client devono verificare quali registri sono validi usando [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
