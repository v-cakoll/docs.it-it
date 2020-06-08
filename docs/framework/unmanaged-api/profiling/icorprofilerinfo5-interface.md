---
title: Interfaccia ICorProfilerInfo5
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: 82f6262c2c576b49be4e7fcaa14043950df4c67a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495627"
---
# <a name="icorprofilerinfo5-interface"></a>Interfaccia ICorProfilerInfo5
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Sottoclasse di [ICorProfilerInfo4](icorprofilerinfo4-interface.md) che fornisce i metodi per l'uso da parte dei profiler del codice per comunicare con il Common Language Runtime (CLR) per controllare il monitoraggio degli eventi.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)|Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da CLR.|  
|[Metodo SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)|Imposta un valore che specifica i tipi di eventi per i quali il profiler richiede la ricezione della notifica da CLR.|  
  
## <a name="remarks"></a>Osservazioni  
 I metodi disponibili in questa interfaccia hanno lo scopo di sostituire i metodi [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
