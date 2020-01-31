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
ms.openlocfilehash: b855a53c9e4303138d7605bdf108d37bb345b917
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789335"
---
# <a name="cordebugguidtotypemapping-structure"></a>Struttura CorDebugGuidToTypeMapping
Esegue il mapping di un GUID Windows Runtime al relativo oggetto ICorDebugType corrispondente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`iid`|GUID del tipo di Windows Runtime memorizzato nella cache.|  
|`pType`|Puntatore a un oggetto ICorDebugType che fornisce informazioni sul tipo memorizzato nella cache.|  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** Windows Runtime.  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
