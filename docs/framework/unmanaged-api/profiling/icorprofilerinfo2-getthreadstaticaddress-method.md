---
title: Metodo ICorProfilerInfo2::GetThreadStaticAddress
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1de945d2e6e0dd1ce3fa2da99e265bc304d4f4fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a>Metodo ICorProfilerInfo2::GetThreadStaticAddress
Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classId`  
 [in] L'ID della classe che contiene il campo statico a livello di thread richiesto.  
  
 `fieldToken`  
 [in] Il token di metadati per il campo statico a livello di thread richiesto.  
  
 `threadId`  
 [in] L'ID del thread che è l'ambito per il campo statico richiesto.  
  
 `ppAddress`  
 [out] Un puntatore all'indirizzo del campo statico che si trova all'interno di thread specificato.  
  
## <a name="remarks"></a>Note  
 Il `GetThreadStaticAddress` metodo può restituire uno dei seguenti:  
  
-   Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico indicato non è stato assegnato un indirizzo nel contesto specificato.  
  
-   Gli indirizzi degli oggetti che possono trovarsi nell'heap di garbage collection. Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, quindi dopo i profiler di garbage collection non devono presupporre che sono validi.  
  
 Prima che venga completato il costruttore di classe di una classe, `GetThreadStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbe già essere inizializzato e oggetti radice del garbage collection.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
