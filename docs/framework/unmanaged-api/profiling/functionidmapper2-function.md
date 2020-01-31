---
title: Funzione FunctionIDMapper2
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: af0ef412395394bb660ae6ed64fb154caef41655
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866918"
---
# <a name="functionidmapper2-function"></a>Funzione FunctionIDMapper2
Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da usare nei callback [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) per tale funzione. `FunctionIDMapper2` consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcId`

  \[in] identificatore di funzione di cui eseguire il mapping.

- `clientData`

  \[in] puntatore ai dati utilizzati per evitare ambiguità tra i Runtime.

- `pbHookFunction`

  \[out] puntatore a un valore che il profiler imposta `true` se desidera ricevere i callback `FunctionEnter3`, `FunctionLeave3`e `FunctionTailcall3`o `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`e `FunctionTailcall3WithInfo`; in caso contrario, imposta questo valore su `false`.

## <a name="return-value"></a>Valore restituito  
 Il profiler restituisce un valore che il motore di esecuzione usa come identificatore alternativo della funzione. Il valore restituito non può essere null a meno che non sia restituito `false` in `pbHookFunction`. In caso contrario, un valore restituito null produrrà risultati imprevedibili, compresa la possibilità di un arresto del processo.  
  
## <a name="remarks"></a>Note  
 Questo metodo estende la funzione [FunctionIDMapper](functionidmapper-function.md) con un parametro aggiuntivo usato per passare i dati del client. I dati del client vengono usati per distinguere tra runtime.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3::SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
