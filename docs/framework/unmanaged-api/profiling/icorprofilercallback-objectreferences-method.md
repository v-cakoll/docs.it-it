---
title: Metodo ICorProfilerCallback::ObjectReferences
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30b8f6b5f424ff81ace36baa8d2ae39e0a2f1d1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a>Metodo ICorProfilerCallback::ObjectReferences
Notifica al profiler gli oggetti in memoria a cui fa riferimento l'oggetto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID dell'oggetto cui fa riferimento a oggetti.  
  
 `classId`  
 [in] L'ID della classe che l'oggetto specificato è un'istanza di.  
  
 `cObjectRefs`  
 [in] Il numero di oggetti a cui fa riferimento l'oggetto specificato (ovvero, il numero di elementi nel `objectRefIds` matrice).  
  
 `objectRefIds`  
 [in] Matrice di ID di oggetti a cui fa riferimento `objectId`.  
  
## <a name="remarks"></a>Note  
 Il `ObjectReferences` metodo viene chiamato per ogni oggetto rimane nell'heap dopo un'operazione di garbage collection è stata completata. Se il profiler restituisce un errore da questo callback, i servizi di profilatura non richiameranno questo callback fino a quando la successiva operazione di garbage collection.  
  
 Il `ObjectReferences` callback può essere usato in combinazione con il [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback per creare un grafico di riferimento di oggetto completo per il runtime. Common language runtime (CLR) garantisce che ogni riferimento all'oggetto venga segnalato solo una volta per il `ObjectReferences` metodo.  
  
 L'ID di oggetto restituito da `ObjectReferences` non validi durante il callback vero e proprio, perché l'operazione di garbage collection potrebbe essere ancora spostando gli oggetti. Di conseguenza, i profiler non devono tentare di controllare gli oggetti durante una `ObjectReferences` chiamare. Quando [ICorProfilerCallback2::](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) viene chiamato, l'operazione di garbage collection è stata completata e l'ispezione può essere eseguita in modo sicuro.  
  
 Un valore null `ClassId` indica che `objectId` dispone di un tipo che lo scaricamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
