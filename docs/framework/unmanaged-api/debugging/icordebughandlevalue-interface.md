---
title: ICorDebugHandleValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue
helpviewer_keywords: ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b56c23caaaed2bc63c724769db1198fd088f7f1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebughandlevalue-interface1"></a>ICorDebugHandleValue Interface1
Sottoclasse di ICorDebugReferenceValue che rappresenta un valore di riferimento a cui il debugger ha creato un handle di garbage collection.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Dispose (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Rilascia l'handle di cui fa riferimento questo `ICorDebugHandleValue` oggetto senza rilasciare esplicitamente il puntatore di interfaccia.|  
|[GetHandleType (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Ottiene un valore di CorDebugHandleType che descrive il tipo di cui fa riferimento l'handle `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugReferenceValue` oggetto viene invalidato da un'interruzione dell'esecuzione di codice sottoposto a debug. Un `ICorDebugHandleValue` mantiene il riferimento durante le interruzioni e sulle continuazioni, fino a quando non viene rilasciato in modo esplicito.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
