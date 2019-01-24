---
title: Metodo ICorProfilerInfo::SetEventMask
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34aba20704ff8dc0d699ebee9440745d19c697b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566008"
---
# <a name="icorprofilerinfoseteventmask-method"></a>Metodo ICorProfilerInfo::SetEventMask
Imposta un valore che specifica i tipi di eventi per i quali il profiler richiede la ricezione della notifica da Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwEvents`  
 [in] valore a 4 byte che specifica le categorie di eventi. Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso. I bit sono descritti nel [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  È necessario chiamare il [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo anziché questo metodo. Anche se il `SetEventMask` metodo continua a essere supportato [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) fornisce funzionalità aggiuntive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Metodo SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
