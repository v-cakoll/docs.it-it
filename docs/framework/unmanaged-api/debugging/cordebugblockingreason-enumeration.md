---
title: Enumerazione CorDebugBlockingReason
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: bc488e55bf64468eb62e2dc6eaedca62ebde3310
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098980"
---
# <a name="cordebugblockingreason-enumeration"></a>Enumerazione CorDebugBlockingReason
Specifica i motivi che possono causare il blocco di un thread su un oggetto specifico.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`BLOCKING_NONE`|Solo per uso interno.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Un thread sta tentando di acquisire la sezione critica associata al blocco di monitoraggio su un oggetto. Questa situazione si verifica in genere quando si chiama uno dei metodi <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> o <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>.|  
|`BLOCKING_MONITOR_EVENT`|Un thread è in attesa dell'evento associato a un blocco di monitoraggio per un oggetto. Questa situazione si verifica in genere quando si chiama uno dei metodi di `Wait` <xref:System.Threading.Monitor?displayProperty=nameWithType>.|  
  
## <a name="remarks"></a>Note  
 Quando il `BLOCKING_MONITOR_CRITICAL_SECTION` o il membro `BLOCKING_MONITOR_EVENT` viene usato in una struttura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , il membro `pBlockingObject` della struttura punta a un'interfaccia "ICorDebugValue" che rappresenta l'oggetto immesso. È inoltre garantita l'implementazione dell'interfaccia [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
