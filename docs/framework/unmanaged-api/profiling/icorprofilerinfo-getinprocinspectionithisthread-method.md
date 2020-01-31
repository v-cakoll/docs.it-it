---
title: Metodo ICorProfilerInfo::GetInprocInspectionIThisThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: 0ab383f0968061667b3580a2058687eecda99dde
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870042"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a>Metodo ICorProfilerInfo::GetInprocInspectionIThisThread
Ottiene un oggetto su cui è possibile eseguire query per l'interfaccia ICorDebugThread. Questo metodo è obsoleto nella versione .NET Framework 2,0.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppicd`  
 oggetto [out su](/cpp/atl/iunknown) cui è possibile eseguire query per l'interfaccia `ICorDebugThread`.  
  
## <a name="remarks"></a>Note  
 I servizi di debug di Common Language Runtime (CLR) supportano il debug in-process limitato nella versione .NET Framework 1,0. Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug. In seguito ai suggerimenti dei clienti, il debug in-process è stato rimosso dal .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versione .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
