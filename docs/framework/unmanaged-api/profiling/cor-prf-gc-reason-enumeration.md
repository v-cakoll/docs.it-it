---
title: Enumerazione COR_PRF_GC_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13740920e8db5d44b71cd3c324742945c64b3e59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498960"
---
# <a name="corprfgcreason-enumeration"></a>Enumerazione COR_PRF_GC_REASON
Indica il motivo per cui è in corso la Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|L'operazione di garbage collection è stata causata da un <xref:System.GC.Collect%2A> (metodo).|  
|`COR_PRF_GC_OTHER`|Il motivo è specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
