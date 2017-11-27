---
title: Interfaccia ICorDebugComObjectValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugComObjectValue
helpviewer_keywords: ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d339d3146a8a9214c3518eac6c31ed5222f9b31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvalue-interface"></a>Interfaccia ICorDebugComObjectValue
Fornisce metodi per recuperare le informazioni associate a un runtime callable wrapper (RCW).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetCachedInterfacePointers (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Ottiene i puntatori a interfaccia raw memorizzati nella cache su RCW corrente.|  
|[Metodo GetCachedInterfaceTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato in maiuscole per o utilizzato come.|  
  
## <a name="remarks"></a>Note  
 Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un RCW, un debugger chiama `QueryInterface` su "ICorDebugValue" con `IID_ICorDebugComObjectValue`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
