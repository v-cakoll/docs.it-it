---
title: Struttura COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7b340a73aa9eaebca9c0d78563ae298557039b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274183"
---
# <a name="cor_heapinfo-structure"></a>Struttura COR_HEAPINFO
Fornisce informazioni generali sull'heap di Garbage Collection, specificando anche se è enumerabile.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`Se Garbage Collection strutture sono valide e l'heap può essere enumerato; in caso `false`contrario,.|  
|`pointerSize`|Dimensione, in byte, dei puntatori nell'architettura di destinazione.|  
|`numHeaps`|Numero di heap Garbage Collection logici nel processo.|  
|`concurrent`|`TRUE`Se Garbage Collection simultaneo (sfondo) è abilitato; in caso `FALSE`contrario,.|  
|`gcType`|Membro dell'enumerazione [CorDebugGCType](cordebuggctype-enumeration.md) che indica se il Garbage Collector è in esecuzione su una workstation o un server.|  
  
## <a name="remarks"></a>Note  
 Viene restituita un' `COR_HEAPINFO` istanza della struttura chiamando il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .  
  
 Prima di enumerare gli oggetti nell'heap di Garbage Collection, è sempre necessario `areGCStructuresValid` controllare il campo per assicurarsi che l'heap sia in uno stato enumerabile. Per ulteriori informazioni, vedere il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
