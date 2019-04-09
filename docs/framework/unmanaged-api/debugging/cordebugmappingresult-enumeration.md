---
title: Enumerazione CorDebugMappingResult
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2fecc7160cb41e31bf88f1a461265ad8fdce166
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170391"
---
# <a name="cordebugmappingresult-enumeration"></a>Enumerazione CorDebugMappingResult
Fornisce informazioni su come è stato ottenuto il valore del puntatore dell'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`MAPPING_PROLOG`|Il codice nativo è nel prologo, pertanto il valore dell'indirizzo IP è 0.|  
|`MAPPING_EPILOG`|Il codice nativo è incluso un epilogo, pertanto il valore dell'indirizzo IP è l'indirizzo dell'ultima istruzione del metodo.|  
|`MAPPING_NO_INFO`|Nessuna informazione di mapping è disponibile per il metodo, pertanto il valore dell'indirizzo IP è 0.|  
|`MAPPING_UNMAPPED_ADDRESS`|Anche se sono le informazioni di mapping per il metodo, l'indirizzo corrente non è possibile eseguire il mapping al codice Microsoft intermediate language (MSIL). Il valore dell'indirizzo IP è 0.|  
|`MAPPING_EXACT`|Il metodo esegue il mapping di esattamente in codice MSIL o il frame è stato interpretato, pertanto il valore dell'indirizzo IP è accurato.|  
|`MAPPING_APPROXIMATE`|Il metodo è stato mappato correttamente, ma il valore dell'indirizzo IP può essere approssimativo.|  
  
## <a name="remarks"></a>Note  
 È possibile usare la [GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) metodo per ottenere il valore del puntatore dell'istruzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
