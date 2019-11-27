---
title: Metodo ICorProfilerInfo2::GetRVAStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
ms.openlocfilehash: db768c97a2d1a0fd5ee42ecfb121fb96d3092e79
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433018"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>Metodo ICorProfilerInfo2::GetRVAStaticAddress
Ottiene l'indirizzo del campo statico dell'indirizzo RVA (relativo Virtual Address) specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 in ID della classe che contiene il campo RVA-static richiesto.  
  
 `fieldToken`  
 in Token di metadati per il campo RVA-static richiesto.  
  
 `ppAddress`  
 out Puntatore all'indirizzo del campo RVA-static.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetRVAStaticAddress` può restituire uno dei seguenti elementi:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.  
  
- Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection. Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.  
  
 Prima del completamento del costruttore della classe di una classe, `GetRVAStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, sebbene alcuni dei campi statici potrebbero essere già stati inizializzati e potrebbero essere radice Garbage Collection oggetti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
