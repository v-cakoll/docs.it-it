---
title: Interfaccia ICorDebugHandleValue
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3219554cf953b8de31e236b2f484478172673f7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915011"
---
# <a name="icordebughandlevalue-interface"></a>Interfaccia ICorDebugHandleValue

Sottoclasse di ICorDebugReferenceValue che rappresenta un valore di riferimento al quale il debugger ha creato un handle per Garbage Collection.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|[Metodo Dispose](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Rilascia l'handle a cui fa riferimento `ICorDebugHandleValue` questo oggetto senza rilasciare in modo esplicito il puntatore all'interfaccia.|  
|[Metodo GetHandleType](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Ottiene un valore CorDebugHandleType che descrive il tipo di handle a cui fa riferimento `ICorDebugHandleValue`questo oggetto.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugReferenceValue` oggetto viene invalidato da un'operazione break nell'esecuzione del codice sottoposto a debug. Un `ICorDebugHandleValue` oggetto mantiene il riferimento tramite interruzioni e continuazioni, fino a quando non viene rilasciato in modo esplicito.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
