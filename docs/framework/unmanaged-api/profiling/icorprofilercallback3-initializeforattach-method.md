---
title: Metodo ICorProfilerCallback3::InitializeForAttach
ms.date: 03/30/2017
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
ms.openlocfilehash: 9bff594d0307153fb468b28c1535977f06997748
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499714"
---
# <a name="icorprofilercallback3initializeforattach-method"></a>Metodo ICorProfilerCallback3::InitializeForAttach
Chiamato da Common Language Runtime (CLR) per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCorProfilerInfoUnk`  
 [in] Puntatore all'interfaccia `ICorProfilerInfo*`.  
  
 `pvClientData`  
 in Puntatore ai dati passati al metodo [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) nel `pvClientData` parametro. Se questo parametro è null, `cbClientData` sarà 0 (zero). CLR libera questa memoria quando ottiene un risultato da `InitializeForAttach`.  
  
 `cbClientData`  
 [in] Dimensioni in byte dei dati a cui `pvClientData` punta.  
  
## <a name="remarks"></a>Osservazioni  
 CLR chiama `InitializeForAttach` per dare al profiler la possibilità di richiedere callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
