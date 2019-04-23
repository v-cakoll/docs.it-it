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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7525d107fec7229d9b86eee63bde2aaf2d701b1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190301"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a>Metodo ICorProfilerInfo3::EnumJITedFunctions
Restituisce un enumeratore per tutte le funzioni che erano in precedenza a compilazione JIT.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEnum`  
 [out] Un puntatore per il [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumeratore.  
  
## <a name="remarks"></a>Note  
 Questo metodo potrebbe sovrapporsi `JITCompilation` callback, ad esempio il [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) (metodo). Enumeratore restituito da questo metodo non include le funzioni caricate da immagini native generate con Ngen.exe.  
  
> [!NOTE]
>  Enumerazione restituita include solo "0" per il valore della `COR_PRF_FUNCTION::reJitId` campo.  Se è necessario validi `COR_PRF_FUNCTION::reJitId` valori, usare il [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
