---
title: Metodo ICorProfilerInfo::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8be698d27ce69f955e5c1f17f5258602880c4021
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618698"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a>Metodo ICorProfilerInfo::GetCurrentThreadID
Ottiene l'ID del thread corrente, se si tratta di un thread gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pThreadId`  
 [out] Un puntatore all'ID restituito del thread gestito.  
  
## <a name="remarks"></a>Note  
 Se il thread corrente è un thread di runtime interno o un altro thread non gestito, `GetCurrentThreadID` restituisce CORPROF_E_NOT_MANAGED_THREAD come il valore HRESULT e il valore restituito del `pThreadId` parametro sarà null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
