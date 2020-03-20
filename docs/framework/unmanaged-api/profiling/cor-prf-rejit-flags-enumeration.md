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
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177093"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>Enumerazione COR_PRF_REJIT_FLAGS
Contiene valori che indicano il funzionamento dell'API [ICorProfilerInfo10::RequestReJITWithInliners.](icorprofilerinfo10-requestrejitwithinliners-method.md)  
  
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
|`COR_PRF_REJIT_BLOCK_INLINING`| I metodi ReJITted non verranno bloccati inline in altri metodi. |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| Ricevere `GetFunctionParameters` callback per tutti i metodi che inline i metodi richiesti per essere ReJITted. |  

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Consultate [Sistemi operativi supportati da .NET Core.](../../../core/install/dependencies.md?pivots=os-windows)  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](profiling-enumerations.md)
