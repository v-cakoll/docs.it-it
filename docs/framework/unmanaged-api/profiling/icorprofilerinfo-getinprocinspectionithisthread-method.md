---
title: Metodo ICorProfilerInfo::GetInprocInspectionIThisThread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionIThisThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9a260143e36939f4201d7949f5783f80e5c20ba7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a>Metodo ICorProfilerInfo::GetInprocInspectionIThisThread
Ottiene un oggetto che è possibile eseguire query per l'interfaccia ICorDebugThread. Questo metodo è obsoleto in .NET Framework versione 2.0.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppicd`  
 [out](/cpp/atl/iunknown) oggetto che è possibile eseguire query per il `ICorDebugThread` interfaccia.  
  
## <a name="remarks"></a>Note  
 Servizi di debug di common language runtime (CLR) è supportato il debug in-process limitato in .NET Framework versione 1.0. Debug in-process è abilitato un profiler di usare le parti di verifica dell'API di debug. Come risultato di analisi utilizzo software, debug in-process è stato rimosso da .NET Framework versione 2.0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versione di .NET framework:** 1.0  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
