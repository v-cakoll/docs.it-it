---
title: Metodo ICorProfilerInfo5::GetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: 758e5b71443b127c80c820eb8531056530e81b13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495697"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>Metodo ICorProfilerInfo5::GetEventMask2
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da Common Language Runtime (CLR).  Fornisce funzionalità non fornite dal metodo [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwEventsLow`  
 [out] Puntatore a un valore a 4 byte che specifica le categorie di eventi. Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso. I bit sono descritti nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 `pdwEventsHigh`  
 [out] Puntatore a un valore a 4 byte che specifica le categorie di eventi.  Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso. I bit sono descritti nell'enumerazione [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo `GetEventMask2` consente di determinare i callback a cui il profiler ha eseguito la sottoscrizione. In genere, si esegue un OR logico dei `pdwEventsLow` `pdwEventsHigh` valori e e i nuovi bit che si desidera impostare, quindi si chiama il metodo [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
 Questo metodo è l'alternativa consigliata al metodo [GetEventMask](icorprofilerinfo-geteventmask-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo5](icorprofilerinfo5-interface.md)
- [Metodo SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)
