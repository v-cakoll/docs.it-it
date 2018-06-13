---
title: Struttura CorDebugGuidToTypeMapping
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c803a805da605bd52fd50eb1e292c0e277143d7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405259"
---
# <a name="cordebugguidtotypemapping-structure"></a>Struttura CorDebugGuidToTypeMapping
Mappe un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID oggetto ICorDebugType corrispondente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`iid`|Il GUID del memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.|  
|`pType`|Un puntatore a un oggetto ICorDebugType che fornisce informazioni relative al tipo memorizzato nella cache.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
