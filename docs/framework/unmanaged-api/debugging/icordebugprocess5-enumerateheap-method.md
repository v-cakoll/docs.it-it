---
title: Metodo ICorDebugProcess5::EnumerateHeap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fabe3d70b493427f3845b5752946b00097c1e78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerateheap-method"></a>Metodo ICorDebugProcess5::EnumerateHeap
Ottiene un enumeratore per gli oggetti nell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppObject`  
 [out] Un puntatore all'indirizzo di un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto dell'interfaccia che è un enumeratore per gli oggetti che risiedono nell'heap gestito.  
  
## <a name="remarks"></a>Note  
 Prima di chiamare il `ICorDebugProcess5::EnumerateHeap` (metodo), è necessario chiamare il [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) metodo ed esaminare il valore del `areGCStructuresValid` campo dell'oggetto restituito [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) oggetto per garantire che l'heap di garbage collection nello stato corrente è enumerabile. Inoltre, il `ICorDebugProcess5::EnumerateHeap` restituisce `E_FAIL` se si collega troppo presto nel corso della durata del processo, prima di memoria per l'heap gestito viene allocato.  
  
 Il [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto dell'interfaccia è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetti. Questo metodo consente di popolare il [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto insieme con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che forniscono informazioni su tutti gli oggetti. La raccolta può includere anche [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che forniscono informazioni sugli oggetti che non contiene una radice da qualsiasi oggetto, ma non sono stati ancora raccolti dal garbage collector.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
