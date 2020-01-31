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
ms.openlocfilehash: 406468fc6e2b68e8c8e1dfbd0f0f18cce3f013ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794450"
---
# <a name="icordebughandlevalue-interface"></a>Interfaccia ICorDebugHandleValue

Sottoclasse di ICorDebugReferenceValue che rappresenta un valore di riferimento al quale il debugger ha creato un handle per Garbage Collection.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Dispose](icordebughandlevalue-dispose-method.md)|Rilascia l'handle a cui fa riferimento questo oggetto `ICorDebugHandleValue` senza rilasciare esplicitamente il puntatore all'interfaccia.|  
|[Metodo GetHandleType](icordebughandlevalue-gethandletype-method.md)|Ottiene un valore CorDebugHandleType che descrive il tipo di handle a cui fa riferimento questo `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Note  
 Un oggetto `ICorDebugReferenceValue` viene invalidato da un'operazione break nell'esecuzione del codice sottoposto a debug. Un `ICorDebugHandleValue` mantiene il riferimento tramite interruzioni e continuazioni, fino a quando non viene rilasciato in modo esplicito.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
