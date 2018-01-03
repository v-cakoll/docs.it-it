---
title: Enumerazione CorDebugExceptionFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionFlags
helpviewer_keywords: CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b25211c8e7f03cc09e8729abc44af39f0c84259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugexceptionflags-enumeration"></a>Enumerazione CorDebugExceptionFlags
Offre informazioni aggiuntive su un'eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|Nessuna eccezione.|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|L'eccezione è intercettabile.<br /><br /> È possibile che la temporizzazione dell'eccezione non consenta al debugger di intercettarla. Ad esempio, in assenza di codice gestito sotto il callback corrente o se l'evento di eccezione è stato generato da un allegato JIT, non è possibile intercettare l'eccezione.|  
  
## <a name="remarks"></a>Note  
 È possibile che nelle versioni successive vengano aggiunti nuovi valori a questa enumerazione, quindi è necessario predisporre codice che usa `CorDebugExceptionFlags` per i valori non previsti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
