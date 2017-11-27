---
title: Interfaccia ICorDebugProcess5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5
helpviewer_keywords: ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0f0a46e18121a222ee62fec207dde938d1e967b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5-interface"></a>Interfaccia ICorDebugProcess5
Estende l'interfaccia ICorDebugProcess per supportare l'accesso all'heap gestito, per fornire informazioni sull'operazione di garbage collection di oggetti gestiti, e per determinare se un debugger carica le immagini dalla cache delle immagini native locali dell'applicazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[EnableNGenPolicy (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|Imposta un valore che determina come un'applicazione carica le immagini native durante l'esecuzione in un debugger gestito.|  
|[EnumerateGCReferences (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|Ottiene un enumeratore per tutti gli oggetti che devono essere sottoposto a garbage collection in un processo.|  
|[EnumerateHandles (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|Ottiene un enumeratore per gli handle di oggetto in un processo.|  
|[EnumerateHeap (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|Ottiene un enumeratore per gli oggetti nell'heap gestito.|  
|[EnumerateHeapRegions (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|Ottiene un enumeratore per le aree dell'heap gestito.|  
|[GetArrayLayout (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|Ottiene informazioni sul layout di una matrice in memoria.|  
|[GetGCHeapInformation (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|Ottiene un puntatore a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) struttura che contiene informazioni sugli oggetti che devono essere sottoposto a garbage collection nell'heap gestito.|  
|[GetObject (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|Ottiene un puntatore a un oggetto nell'heap gestito.|  
|[GetTypeFields (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|Ottiene un puntatore a una matrice che contiene informazioni sui campi per un tipo in base al relativo identificatore di tipo.|  
|[GetTypeForTypeID (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|Ottiene un oggetto di tipo che fornisce informazioni su un oggetto in base ai relativi identificatori di tipo.|  
|[GetTypeID (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|Ottiene l'identificatore di tipo per l'oggetto a un indirizzo specificato.|  
|[GetTypeLayout (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|Ottiene informazioni sul layout di un oggetto in memoria in base al relativo identificatore di tipo.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia estende logicamente l'ICorDebugProcess, ICorDebugProcess2, e [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfacce.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, da un altro computer o da un altro processo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
