---
title: Metodo ICorDebugProcess5::GetGCHeapInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetGCHeapInformation
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da423914d8af20c0f942d53ed6ac9f34ace01ca9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>Metodo ICorDebugProcess5::GetGCHeapInformation
Fornisce informazioni generali sull'heap di garbage collection, ad esempio se è attualmente enumerabile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pHeapInfo`  
 [out] Un puntatore a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) valore che fornisce informazioni generali sull'heap di garbage collection.  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugProcess5::GetGCHeapInformation` metodo deve essere chiamato prima l'enumerazione dell'heap o aree di heap singoli per garantire che le strutture di garbage collection del processo attualmente vengono. Heap di garbage collection non può essere esaminata mentre è in corso una raccolta. In caso contrario, l'enumerazione potrebbe acquisire strutture di garbage collection che non sono validi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugProcess5 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
