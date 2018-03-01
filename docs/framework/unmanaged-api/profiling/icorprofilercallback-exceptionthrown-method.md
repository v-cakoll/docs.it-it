---
title: Metodo ICorProfilerCallback::ExceptionThrown
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
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65fdd8f2912dc2854ba7801244ba489426d05e47
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionthrown-method"></a>Metodo ICorProfilerCallback::ExceptionThrown
Notifica al profiler che è stata generata un'eccezione.  
  
> [!NOTE]
>  Questa funzione viene chiamata solo se l'eccezione raggiunge il codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `thrownObjectId`  
 [in] L'ID dell'oggetto che ha causato l'eccezione generata.  
  
## <a name="remarks"></a>Note  
 Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection. Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.  
  
 Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
