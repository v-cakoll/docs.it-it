---
title: Enumerazione COR_PRF_TRANSITION_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: e890c62a54654e86bb4a825613807efe142c8d5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500741"
---
# <a name="cor_prf_transition_reason-enumeration"></a>Enumerazione COR_PRF_TRANSITION_REASON
Indica il motivo di una transizione da codice gestito a codice non gestito o viceversa.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|La transizione è dovuta a una chiamata in una funzione.|  
|`COR_PRF_TRANSITION_RETURN`|La transizione è dovuta a un ritorno da una funzione.|  
  
## <a name="remarks"></a>Osservazioni  
 Quando si verifica una transizione, il profiler riceve un callback [ICorProfilerCallback:: ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) , uno dei quali fornisce un valore dell' `COR_PRF_TRANSITION_REASON` enumerazione per indicare il motivo della transizione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
