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
ms.openlocfilehash: fc3f77adf33502bfbc3d65ff5131420093fbbec8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097928"
---
# <a name="cordebugmappingresult-enumeration"></a>Enumerazione CorDebugMappingResult
Fornisce informazioni su come è stato ottenuto il valore del puntatore dell'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`MAPPING_PROLOG`|Il codice nativo è nel prologo, quindi il valore dell'indirizzo IP è 0.|  
|`MAPPING_EPILOG`|Il codice nativo si trova in un epilogo, quindi il valore dell'indirizzo IP è l'indirizzo dell'ultima istruzione del metodo.|  
|`MAPPING_NO_INFO`|Non sono disponibili informazioni di mapping per il metodo, quindi il valore dell'indirizzo IP è 0.|  
|`MAPPING_UNMAPPED_ADDRESS`|Sebbene esistano informazioni di mapping per il metodo, non è possibile eseguire il mapping dell'indirizzo corrente al codice MSIL (Microsoft Intermediate Language). Il valore dell'indirizzo IP è 0.|  
|`MAPPING_EXACT`|Il metodo esegue il mapping esatto al codice MSIL o il frame è stato interpretato, quindi il valore dell'indirizzo IP è accurato.|  
|`MAPPING_APPROXIMATE`|Il mapping del metodo è stato eseguito correttamente, ma il valore dell'indirizzo IP potrebbe essere approssimativo.|  
  
## <a name="remarks"></a>Note  
 È possibile usare il metodo [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) per ottenere il valore del puntatore all'istruzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
