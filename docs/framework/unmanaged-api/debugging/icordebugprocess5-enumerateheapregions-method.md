---
title: Metodo ICorDebugProcess5::EnumerateHeapRegions
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeapRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 478a8490e57946a08670d9f86e1f6ebcc67703a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>Metodo ICorDebugProcess5::EnumerateHeapRegions
Ottiene un enumeratore per gli intervalli di memoria dell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppRegions`  
 [out] Un puntatore all'indirizzo di un [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto dell'interfaccia che è un enumeratore per gli intervalli di memoria in cui si trovano gli oggetti nell'heap gestito.  
  
## <a name="remarks"></a>Note  
 Prima di chiamare il `ICorDebugProcess5::EnumerateHeapRegions` (metodo), è necessario chiamare il [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) metodo ed esaminare il valore del `areGCStructuresValid` campo dell'oggetto restituito [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) oggetto per garantire che l'heap di garbage collection nello stato corrente è enumerabile. Inoltre, il `ICorDebugProcess5::EnumerateHeapRegions` restituisce `E_FAIL` se si collega troppo presto nel corso della durata del processo, le aree vengono create prima di memoria.  
  
 Questo metodo è garantito per enumerare tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti che risiedono nel tali aree. Il [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto della raccolta può includere le aree di memoria riservata o vuoto.  
  
 Il [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto dell'interfaccia è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) oggetti. Ogni [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) oggetto fornisce informazioni sull'intervallo di memoria di un particolare segmento, con la generazione degli oggetti nel segmento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
