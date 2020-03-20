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
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179304"
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`se le strutture di Garbage Collection sono valide e l'heap può essere enumerato; in `false`caso contrario, .|  
|`pointerSize`|Dimensione, in byte, dei puntatori nell'architettura di destinazione.|  
|`numHeaps`|Numero di heap di Garbage Collection logici nel processo.|  
|`concurrent`|`TRUE`se l'operazione di Garbage Collection simultanea (in background) è abilitata; in `FALSE`caso contrario, .|  
|`gcType`|Membro dell'enumerazione [CorDebugGCType](cordebuggctype-enumeration.md) che indica se il Garbage Collector è in esecuzione su una workstation o su un server.|  
  
## <a name="remarks"></a>Osservazioni  
 Un'istanza `COR_HEAPINFO` della struttura viene restituita chiamando il [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) metodo.  
  
 Prima di enumerare gli oggetti nell'heap `areGCStructuresValid` di Garbage Collection, è necessario controllare sempre il campo per assicurarsi che l'heap sia in uno stato enumerabile. Per altre informazioni, vedere il [metodo ICorDebugProcess5::GetGCHeapInformation.For more information, see the ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
