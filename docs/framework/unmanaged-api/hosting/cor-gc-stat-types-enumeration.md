---
title: Enumerazione COR_GC_STAT_TYPES
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: b0fbc462283ef1577de8100e60fd09caa53db539
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131920"
---
# <a name="cor_gc_stat_types-enumeration"></a>Enumerazione COR_GC_STAT_TYPES
Specifica le statistiche da registrare per un Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>Note  
 Questa enumerazione specifica quali statistiche nella struttura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) devono essere impostate dal metodo [ICLRGCManager:: GetStatistics](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) .  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Registra il numero di operazioni di Garbage Collection eseguite per ogni generazione.|  
|`COR_GC_MEMORYUSAGE`|Registra l'utilizzo della memoria e le statistiche delle dimensioni del Garbage Collection.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost. idl, GCHost. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Struttura COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
