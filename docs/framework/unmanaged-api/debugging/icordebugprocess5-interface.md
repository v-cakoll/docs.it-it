---
title: Interfaccia ICorDebugProcess5
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3aed85e989313e4778e12a6f6bb789ccef49747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess5-interface"></a>Interfaccia ICorDebugProcess5
Estende l'interfaccia ICorDebugProcess per supportare l'accesso all'heap gestito, per fornire informazioni sull'operazione di garbage collection di oggetti gestiti, e per determinare se un debugger carica le immagini dalla cache delle immagini native locali dell'applicazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|Imposta un valore che determina come un'applicazione carica le immagini native durante l'esecuzione in un debugger gestito.|  
|[Metodo EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|Ottiene un enumeratore per tutti gli oggetti che devono essere sottoposto a garbage collection in un processo.|  
|[Metodo EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|Ottiene un enumeratore per gli handle di oggetto in un processo.|  
|[Metodo EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|Ottiene un enumeratore per gli oggetti nell'heap gestito.|  
|[Metodo EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|Ottiene un enumeratore per le aree dell'heap gestito.|  
|[Metodo GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|Ottiene informazioni sul layout di una matrice in memoria.|  
|[Metodo GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|Ottiene un puntatore a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) struttura che contiene informazioni sugli oggetti che devono essere sottoposto a garbage collection nell'heap gestito.|  
|[Metodo GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|Ottiene un puntatore a un oggetto nell'heap gestito.|  
|[Metodo GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|Ottiene un puntatore a una matrice che contiene informazioni sui campi per un tipo in base al relativo identificatore di tipo.|  
|[Metodo GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|Ottiene un oggetto di tipo che fornisce informazioni su un oggetto in base ai relativi identificatori di tipo.|  
|[Metodo GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|Ottiene l'identificatore di tipo per l'oggetto a un indirizzo specificato.|  
|[Metodo GetTypeLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|Ottiene informazioni sul layout di un oggetto in memoria in base al relativo identificatore di tipo.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia estende logicamente l'ICorDebugProcess, ICorDebugProcess2, e [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfacce.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, da un altro computer o da un altro processo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
