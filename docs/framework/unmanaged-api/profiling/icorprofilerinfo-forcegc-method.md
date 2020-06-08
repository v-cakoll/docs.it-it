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
ms.openlocfilehash: 9bc6619f3ef383c7bf60a310a87f056cfc43cddf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498674"
---
# <a name="icorprofilerinfoforcegc-method"></a>Metodo ICorProfilerInfo::ForceGC
Impone la Garbage Collection all'interno del Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Osservazioni  
 Il `ForceGC` metodo deve essere chiamato solo da un thread che non ha mai eseguito codice gestito e che non dispone di callback del profiler nello stack. L'implementazione più semplice consiste nel creare un thread separato all'interno del profiler che chiama `ForceGC` quando segnalato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
