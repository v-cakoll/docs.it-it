---
title: Metodo ICorProfilerCallback::Initialize
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: ea4fc8ab39d616415106150f56f4b7afd5f68237
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500104"
---
# <a name="icorprofilercallbackinitialize-method"></a>Metodo ICorProfilerCallback::Initialize
Chiamato per inizializzare la Code Profiler ogni volta che viene avviata una nuova applicazione di Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parametri

- `pICorProfilerInfoUnk`

  \[in] puntatore a un'interfaccia [IUnknown](/cpp/atl/iunknown) che il profiler deve eseguire una query per un puntatore di interfaccia [ICorProfilerInfo](icorprofilerinfo-interface.md) .  

## <a name="remarks"></a>Osservazioni  
 La `Initialize` chiamata è l'unica opportunità per abilitare (o disabilitare) i callback che non sono modificabili. Quando un callback viene abilitato dalla `Initialize` chiamata, non può essere disabilitato in un secondo momento utilizzando [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Il valore COR_PRF_MONITOR_IMMUTABLE dell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica gli eventi che non sono modificabili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo Shutdown](icorprofilercallback-shutdown-method.md)
