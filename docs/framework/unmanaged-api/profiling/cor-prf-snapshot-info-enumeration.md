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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa85fb2cebb47ecbd7b0f091cb79f6ea0936b1cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177840"
---
# <a name="corprfsnapshotinfo-enumeration"></a>Enumerazione COR_PRF_SNAPSHOT_INFO
Specifica quanto nuovamente i dati da passare con uno snapshot dello stack in ogni chiamata a del profiler [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) (funzione).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membri|Descrizione|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, ad eccezione di `context` parametro.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, incluso il `context` parametro.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Indica che verrà utilizzato un algoritmo di analisi dello stack più semplice, alternativo.|  
  
## <a name="remarks"></a>Note  
 Valori forniti per il `COR_PRF_SNAPSHOT_INFO` enumerazione vengono passati come parametri per il [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
