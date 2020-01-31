---
title: Metodo ICorProfilerInfo::GetInprocInspectionInterface
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
ms.openlocfilehash: 5c9258126c872bd501b4eebc4698b4dded402dfe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863361"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a>Metodo ICorProfilerInfo::GetInprocInspectionInterface
Ottiene un oggetto su cui è possibile eseguire una query per un'interfaccia "ICorDebugProcess". Questo metodo è obsoleto nella versione .NET Framework 2,0.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppicd`  
 oggetto [out su](/cpp/atl/iunknown) cui è possibile eseguire una query per un'interfaccia `ICorDebugProcess`.  
  
## <a name="remarks"></a>Note  
 L'API di debug di Common Language Runtime (CLR) supportava il debug in-process limitato nella versione .NET Framework 1,0. Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug. In seguito ai suggerimenti dei clienti, il debug in-process è stato rimosso dal .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versione .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
