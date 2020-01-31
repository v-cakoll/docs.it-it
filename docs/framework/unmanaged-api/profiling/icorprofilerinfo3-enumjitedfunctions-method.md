---
title: Metodo ICorProfilerInfo3::EnumJITedFunctions
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: a22a0de9a20f32ce1c9818bbcf29222a4b331420
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862425"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a>Metodo ICorProfilerInfo3::EnumJITedFunctions
Restituisce un enumeratore per tutte le funzioni precedentemente compilate tramite JIT.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEnum`  
 out Puntatore all'enumeratore [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .  
  
## <a name="remarks"></a>Note  
 Questo metodo può sovrapporsi a `JITCompilation` callback, ad esempio il metodo [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) . L'enumeratore restituito da questo metodo non include le funzioni caricate da immagini native generate con Ngen. exe.  
  
> [!NOTE]
> L'enumerazione restituita include solo "0" per il valore del campo `COR_PRF_FUNCTION::reJitId`.  Se sono necessari valori di `COR_PRF_FUNCTION::reJitId` validi, usare il metodo [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
