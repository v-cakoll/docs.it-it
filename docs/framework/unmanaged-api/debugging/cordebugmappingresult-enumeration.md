---
title: Enumerazione CorDebugMappingResult
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMappingResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMappingResult
helpviewer_keywords: CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 793158ef63a0de27786dc8bd9b306f10c228054e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MAPPING_PROLOG`|Il codice nativo è nel prologo, pertanto il valore dell'indirizzo IP è 0.|  
|`MAPPING_EPILOG`|Il codice nativo è un epilogo, pertanto il valore dell'indirizzo IP è l'indirizzo dell'ultima istruzione del metodo.|  
|`MAPPING_NO_INFO`|Le informazioni di mapping non sono disponibile per il metodo, pertanto il valore dell'indirizzo IP è 0.|  
|`MAPPING_UNMAPPED_ADDRESS`|Anche se le informazioni di mapping per il metodo non è presente, l'indirizzo corrente non può essere mappato a codice Microsoft intermediate language (MSIL). Il valore dell'indirizzo IP è 0.|  
|`MAPPING_EXACT`|Il metodo viene eseguito il mapping esattamente al codice MSIL o il frame è stato interpretato, pertanto il valore dell'indirizzo IP è accurato.|  
|`MAPPING_APPROXIMATE`|Il metodo è stato mappato correttamente, ma il valore dell'indirizzo IP può essere approssimativo.|  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare il [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) metodo per ottenere il valore del puntatore all'istruzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
