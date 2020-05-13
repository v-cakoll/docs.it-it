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
ms.openlocfilehash: c901e21521e941c51939958175a5316808890e9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208616"
---
# <a name="icordebughandlevalue-interface"></a>Interfaccia ICorDebugHandleValue

Sottoclasse di ICorDebugReferenceValue che rappresenta un valore di riferimento al quale il debugger ha creato un handle per Garbage Collection.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Dispose](icordebughandlevalue-dispose-method.md)|Rilascia l'handle a cui fa riferimento questo `ICorDebugHandleValue` oggetto senza rilasciare in modo esplicito il puntatore all'interfaccia.|  
|[Metodo GetHandleType](icordebughandlevalue-gethandletype-method.md)|Ottiene un valore CorDebugHandleType che descrive il tipo di handle a cui fa riferimento questo oggetto `ICorDebugHandleValue` .|  
  
## <a name="remarks"></a>Osservazioni  
 Un `ICorDebugReferenceValue` oggetto viene invalidato da un'operazione break nell'esecuzione del codice sottoposto a debug. Un oggetto `ICorDebugHandleValue` mantiene il riferimento tramite interruzioni e continuazioni, fino a quando non viene rilasciato in modo esplicito.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
