---
title: Metodo ICorProfilerInfo::GetEventMask
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
ms.openlocfilehash: 7faa4a5f7b1ca1fbf165c40eb3a3cb32a42a21a4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498336"
---
# <a name="icorprofilerinfogeteventmask-method"></a>Metodo ICorProfilerInfo::GetEventMask
Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwEvents`  
 [out] Puntatore a un valore a 4 byte che specifica le categorie di eventi. Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso. I bit sono descritti nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> È necessario chiamare il metodo [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) anziché questo metodo. Anche se il `SetEventMask` Metodo continua a essere supportato, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) fornisce funzionalità aggiuntive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)
- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
