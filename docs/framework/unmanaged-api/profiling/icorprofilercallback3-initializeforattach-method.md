---
title: Metodo ICorProfilerCallback3::InitializeForAttach
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 124e27e446e129173018aed9d3ab770582342c72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3initializeforattach-method"></a>Metodo ICorProfilerCallback3::InitializeForAttach
Chiamato da Common Language Runtime (CLR) per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pCorProfilerInfoUnk`  
 [in] Puntatore all'interfaccia `ICorProfilerInfo*`.  
  
 `pvClientData`  
 [in] Passato un puntatore ai dati per il [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) metodo nel relativo `pvClientData` parametro. Se questo parametro è null, `cbClientData` sarà 0 (zero). CLR libera questa memoria quando ottiene un risultato da `InitializeForAttach`.  
  
 `cbClientData`  
 [in] Dimensioni in byte dei dati a cui `pvClientData` punta.  
  
## <a name="remarks"></a>Note  
 CLR chiama `InitializeForAttach` per dare al profiler la possibilità di richiedere callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
