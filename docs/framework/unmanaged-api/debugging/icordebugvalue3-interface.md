---
title: Interfaccia ICorDebugValue3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3
helpviewer_keywords: ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3948a4c404036235767f8de6747966709b75bc4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3-interface"></a>Interfaccia ICorDebugValue3
Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici maggiori di 2 GB.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetSize64 (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|Ottiene le dimensioni, in byte, di questo `ICorDebugValue3` oggetto.|  
  
## <a name="remarks"></a>Note  
 Il [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo restituisce una dimensioni dell'oggetto che va da 0 a 2.147.483.647 byte. Nel [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], le dimensioni delle matrici possono superare i 2 GB. Il `ICorDebugValue3` interfaccia consente di determinare le dimensioni di queste matrici.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
    
    
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
