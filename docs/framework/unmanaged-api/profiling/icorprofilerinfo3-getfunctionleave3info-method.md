---
title: Metodo ICorProfilerInfo3::GetFunctionLeave3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d51462017287d42fd468ed0a74a2e83203a3d94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000623"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a>Metodo ICorProfilerInfo3::GetFunctionLeave3Info
Fornisce lo stack frame e il valore restituito della funzione da segnalare al profiler tramite la [funzione FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (funzione). Questo metodo può essere chiamato solo durante il callback `FunctionLeave3WithInfo`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] Il `FunctionID` della funzione che restituisce.  
  
 `eltInfo`  
 [in] Handle opaco che rappresenta le informazioni su un determinato stack frame. Il profiler deve fornire lo stesso `eltInfo` che è stato assegnato al profiler tramite la [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (funzione).  
  
 `pFrameInfo`  
 [out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame. Questo handle è valido solo durante il callback `FunctionLeave3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionLeave3Info`.  
  
 `pRetvalRange`  
 [out] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) struttura che contiene il valore restituito dalla funzione. Per accedere alle informazioni di valore restituito, il `COR_PRF_ENABLE_FUNCTION_RETVAL` flag deve essere impostato. Il profiler può usare la [SetEventMask (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
