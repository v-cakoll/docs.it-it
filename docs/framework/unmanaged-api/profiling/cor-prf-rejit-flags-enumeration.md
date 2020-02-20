---
title: Enumerazione COR_PRF_REJIT_FLAGS
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 3b4f85072b9dcf87d696b979fa6cbf4e59393f82
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453039"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>Enumerazione COR_PRF_REJIT_FLAGS
Contiene valori che indicano il comportamento dell'API [ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| I metodi ReJITted verranno bloccati in altri metodi. |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| Ricevere `GetFunctionParameters` callback per qualsiasi metodo che inline i metodi richiesti come ReJITted. |  

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](profiling-enumerations.md)
