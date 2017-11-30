---
title: Metodo ICorProfilerInfo2::GetContextStaticAddress
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetContextStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type: apiref
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2d206ca90b2d89ead67f419f0f4511d19d8ce110
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>Metodo ICorProfilerInfo2::GetContextStaticAddress
Ottiene l'indirizzo per il campo statico specificato nell'ambito del contesto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classId`  
 [in] L'ID della classe che contiene il campo statico richiesto.  
  
 `fieldToken`  
 [in] Il token di metadati per il campo statico richiesto.  
  
 `contextId`  
 [in] L'ID del contesto è l'ambito per il campo statico richiesto.  
  
 `ppAddress`  
 [out] Un puntatore all'indirizzo del campo statico è all'interno del contesto specificato.  
  
## <a name="remarks"></a>Note  
 Il `GetContextStaticAddress` metodo può restituire uno dei seguenti:  
  
-   Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico indicato non è stato assegnato un indirizzo nel contesto specificato.  
  
-   Gli indirizzi degli oggetti che possono trovarsi nell'heap di garbage collection. Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, pertanto dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.  
  
 Prima che venga completato il costruttore di classe di una classe, `GetContextStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbe già essere inizializzato e oggetti radice del garbage collection.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
