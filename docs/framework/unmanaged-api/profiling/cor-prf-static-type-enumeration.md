---
title: Enumerazione COR_PRF_STATIC_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 753c3b38187dd69593dcb0520acef9ce4b137039
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751906"
---
# <a name="corprfstatictype-enumeration"></a>Enumerazione COR_PRF_STATIC_TYPE
Indica se un campo è statico e, in tal caso, la qualità statica che si applica al campo. Questi valori possono essere combinati utilizzando l'operatore OR bit per indicare che il campo dispone di più, la qualità statica diverse.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|Il campo non è statico.|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|Il campo è statico dominio applicazione.|  
|`COR_PRF_FIELD_THREAD_STATIC`|Il campo è statico.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|Il campo è statico.|  
|`COR_PRF_FIELD_RVA_STATIC`|Il campo è un indirizzo virtuale relativo (RVA)-statici.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
