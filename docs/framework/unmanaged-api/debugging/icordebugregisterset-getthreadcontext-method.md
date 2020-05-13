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
ms.openlocfilehash: 04ae3c4dd663351eaf1a58646e24e8ae95aeb9ad
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378287"
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
 in Dimensione, in byte, della `context` matrice.  
  
 `context`  
 [in, out] Matrice di byte che compongono la `CONTEXT` struttura Win32 per la piattaforma corrente.  
  
## <a name="remarks"></a>Osservazioni  
 Il debugger deve chiamare questa funzione al posto della `GetThreadContext` funzione Win32, perché il thread potrebbe trovarsi in uno stato di "Hijack" in cui il contesto è stato modificato temporaneamente. I dati restituiti sono una `CONTEXT` struttura Win32 per la piattaforma corrente.  
  
 Per i frame non foglia, i client devono verificare quali registri sono validi usando [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
