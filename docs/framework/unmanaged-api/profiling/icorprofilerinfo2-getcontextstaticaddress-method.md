---
title: Metodo ICorProfilerInfo2::GetContextStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02694933aca160e1f2c28554eb6758163ed8efc8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619934"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>Metodo ICorProfilerInfo2::GetContextStaticAddress
Ottiene l'indirizzo per il campo statico di contesto specificato che si trova nell'ambito del contesto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 [in] ID della classe che contiene il campo statico di contesto richiesto.  
  
 `fieldToken`  
 [in] Il token di metadati per il campo statico di contesto richiesto.  
  
 `contextId`  
 [in] L'ID del contesto che è l'ambito per il campo statico di contesto richiesto.  
  
 `ppAddress`  
 [out] Un puntatore all'indirizzo del campo statico è all'interno del contesto specificato.  
  
## <a name="remarks"></a>Note  
 Il `GetContextStaticAddress` metodo può restituire uno dei seguenti:  
  
- Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.  
  
- Gli indirizzi di oggetti che possono trovarsi nell'heap di garbage collection. Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, in modo che dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.  
  
 Prima del completamento, il costruttore di classe della classe `GetContextStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i relativi campi statici, anche se alcuni dei campi statici potrebbero essere già stato inizializzato e oggetti radice del garbage collection.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
