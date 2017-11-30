---
title: Interfaccia ICorDebugStackWalk
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk
helpviewer_keywords: ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0c8a4421b716614081368755388bd2ab8d8fe22e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalk-interface"></a>Interfaccia ICorDebugStackWalk
Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetContext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Restituisce il contesto per il fotogramma corrente il `ICorDebugStackWalk` oggetto.|  
|[SetContext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Imposta il `ICorDebugStackWalk` contesto corrente dell'oggetto a un contesto valido per il thread.|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Sposta il `ICorDebugStackWalk` oggetto al frame successivo.|  
|[GetFrame (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Ottiene il frame corrente `ICorDebugStackWalk` oggetto.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
