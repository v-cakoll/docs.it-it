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
ms.openlocfilehash: 9a9eb63e681b47f058901b0ff002015baffe6048
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117443"
---
# <a name="icordebughandlevalue-interface"></a>Interfaccia ICorDebugHandleValue

Sottoclasse di interfaccia ICorDebugReferenceValue che rappresenta un valore di riferimento a cui il debugger ha creato un handle di garbage collection.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Dispose](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Rilascia l'handle fa riferimento questo `ICorDebugHandleValue` oggetto senza rilasciare in modo esplicito il puntatore di interfaccia.|  
|[Metodo GetHandleType](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Ottiene un valore CorDebugHandleType che descrive il tipo di handle fa riferimento questo `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugReferenceValue` oggetto viene invalidato da un'interruzione nell'esecuzione del codice sottoposto a debug. Un `ICorDebugHandleValue` mantiene il riferimento durante le interruzioni e sulle continuazioni, fino a quando non viene rilasciato in modo esplicito.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
