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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe5e1267b619d5900ed9af55dd6079a8f38d6550
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugblockingreason-enumeration"></a>Enumerazione CorDebugBlockingReason
Specifica i motivi che possono causare il blocco di un thread su un oggetto specifico.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`BLOCKING_NONE`|Solo per uso interno.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Un thread sta tentando di acquisire la sezione critica è associata al blocco di monitoraggio su un oggetto. In genere, questo errore si verifica quando si chiama uno del <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> o <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> metodi.|  
|`BLOCKING_MONITOR_EVENT`|Un thread è in attesa dell'evento associato a un blocco di monitoraggio per un oggetto. In genere, questo errore si verifica quando si chiama uno del <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` metodi.|  
  
## <a name="remarks"></a>Note  
 Quando il `BLOCKING_MONITOR_CRITICAL_SECTION` o `BLOCKING_MONITOR_EVENT` membro viene utilizzato un [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) struttura, il `pBlockingObject` membro della struttura punta a un'interfaccia "ICorDebugValue" che rappresenta l'oggetto in corso di immissione . È inoltre garantito per implementare il [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interfaccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
