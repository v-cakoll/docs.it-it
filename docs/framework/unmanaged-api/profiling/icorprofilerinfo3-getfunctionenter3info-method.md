---
title: Metodo ICorProfilerInfo3::GetFunctionEnter3Info
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a75f76af924c3e75d280c36fb5f436498dc6c862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a>Metodo ICorProfilerInfo3::GetFunctionEnter3Info
Fornisce le informazioni sullo stack frame e l'argomento della funzione da segnalare al profiler tramite la [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) (funzione). Questo metodo può essere chiamato solo durante il callback `FunctionEnter3WithInfo`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] `FunctionID` della funzione da immettere.  
  
 `eltInfo`  
 [in] Handle opaco che rappresenta le informazioni su un determinato stack frame. Il profiler deve fornire la stessa `eltInfo` che fornito il [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) (funzione).  
  
 `pFrameInfo`  
 [out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame. Questo handle è valido solo durante il callback `FunctionEnter3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionEnter3Info`.  
  
 `pcbArgumentInfo`  
 [in, out] Un puntatore alla dimensione totale, espressa in byte, del [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) struttura (più eventuali altre [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) strutture per gli intervalli di argomenti a cui puntati `pArgumentInfo`). Se la dimensione specificata non è sufficiente, viene restituito ERROR_INSUFFICIENT_BUFFER e la dimensione prevista viene archiviata in `pcbArgumentInfo`. Per chiamare `GetFunctionEnter3Info` per recuperare il valore previsto per `*pcbArgumentInfo`, impostare `*pcbArgumentInfo`=0 e `pArgumentInfo`=NULL.  
  
 `pArgumentInfo`  
 [out] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) struttura che descrive le posizioni degli argomenti della funzione in memoria, in ordine da sinistra a destra.  
  
## <a name="remarks"></a>Note  
 Il profiler deve allocare spazio sufficiente per la struttura `COR_PRF_FUNCTION_ARGUMENT_INFO` della funzione che viene esaminata e deve indicare la dimensione nel parametro `pcbArgumentInfo`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [ICorProfilerInfo3 (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
