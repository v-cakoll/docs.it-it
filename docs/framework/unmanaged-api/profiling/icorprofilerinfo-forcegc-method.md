---
title: Metodo ICorProfilerInfo::ForceGC
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06601b1aa675dd9ecf023a9f83d881ba1591ac52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfoforcegc-method"></a>Metodo ICorProfilerInfo::ForceGC
Forza il garbage collection si verifichi all'interno di common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Note  
 Il `ForceGC` metodo deve essere chiamato solo da un thread che non ha mai eseguito codice gestito e non siano presenti callback del profiler. relativo stack. L'implementazione più semplice consiste nel creare un thread separato all'interno del profiler che chiama `ForceGC` quando riceve un segnale.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
