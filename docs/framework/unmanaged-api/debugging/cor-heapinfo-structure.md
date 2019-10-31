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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132327"
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` se Garbage Collection strutture sono valide e l'heap può essere enumerato; in caso contrario, `false`.|  
|`pointerSize`|Dimensione, in byte, dei puntatori nell'architettura di destinazione.|  
|`numHeaps`|Numero di heap Garbage Collection logici nel processo.|  
|`concurrent`|`TRUE` se Garbage Collection simultaneo (sfondo) è abilitato; in caso contrario, `FALSE`.|  
|`gcType`|Membro dell'enumerazione [CorDebugGCType](cordebuggctype-enumeration.md) che indica se il Garbage Collector è in esecuzione su una workstation o un server.|  
  
## <a name="remarks"></a>Note  
 Un'istanza della struttura `COR_HEAPINFO` viene restituita chiamando il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .  
  
 Prima di enumerare gli oggetti nell'heap di Garbage Collection, è sempre necessario controllare il campo `areGCStructuresValid` per assicurarsi che l'heap sia in uno stato enumerabile. Per ulteriori informazioni, vedere il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
