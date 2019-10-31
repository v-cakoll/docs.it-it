---
title: Metodo ICorDebugProcess5::EnumerateHeapRegions
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 3ab4da3fcf43731587dae6f3a8e82ea48c5ee1ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129634"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>Metodo ICorDebugProcess5::EnumerateHeapRegions
Ottiene un enumeratore per gli intervalli di memoria dell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppRegions`  
 out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) che è un enumeratore per gli intervalli di memoria in cui gli oggetti si trovano nell'heap gestito.  
  
## <a name="remarks"></a>Note  
 Prima di chiamare il metodo `ICorDebugProcess5::EnumerateHeapRegions`, è necessario chiamare il metodo [ICorDebugProcess5:: GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) ed esaminare il valore del campo `areGCStructuresValid` dell'oggetto [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) restituito per assicurarsi che l'heap Garbage Collection nel relativo lo stato corrente è enumerabile. Inoltre, il metodo `ICorDebugProcess5::EnumerateHeapRegions` restituisce `E_FAIL` se ci si connette troppo presto nella durata del processo, prima che vengano create le aree di memoria.  
  
 Questo metodo garantisce l'enumerazione di tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree. L'oggetto raccolta [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) può includere aree di memoria vuote o riservate.  
  
 L'oggetto interfaccia [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare gli oggetti [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) . Ogni oggetto [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) fornisce informazioni sull'intervallo di memoria di un determinato segmento, insieme alla generazione degli oggetti in tale segmento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
