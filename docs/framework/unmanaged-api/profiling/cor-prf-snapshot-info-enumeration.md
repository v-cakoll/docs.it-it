---
title: Enumerazione COR_PRF_SNAPSHOT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: 6168c5b27868a261871b292e17ca02b04ae89917
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500780"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>Enumerazione COR_PRF_SNAPSHOT_INFO
Specifica la quantità di dati da passare di nuovo con uno snapshot dello stack in ogni chiamata alla funzione [StackSnapshotCallback](stacksnapshotcallback-function.md) del profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membri|Descrizione|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, ad eccezione del `context` parametro.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, incluso il `context` parametro.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Indica che verrà utilizzato un algoritmo più semplice e alternativo per lo stack.|  
  
## <a name="remarks"></a>Osservazioni  
 I valori forniti dall' `COR_PRF_SNAPSHOT_INFO` enumerazione vengono passati come parametri al metodo [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Enumerazioni di profilatura](profiling-enumerations.md)
