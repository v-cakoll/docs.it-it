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
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863946"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a>Metodo ICorProfilerInfo::GetCurrentThreadID
Ottiene l'ID del thread corrente, se è un thread gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a>Parametri  
 `pThreadId`  
 out Puntatore all'ID restituito del thread gestito.  
  
## <a name="remarks"></a>Note  
 Se il thread corrente è un thread runtime interno o un altro thread non gestito, `GetCurrentThreadID` restituisce CORPROF_E_NOT_MANAGED_THREAD come HRESULT e il valore restituito del parametro `pThreadId` sarà null.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
