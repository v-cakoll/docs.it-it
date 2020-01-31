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
ms.openlocfilehash: 8070b0693b5718ad8b4cbeb9bf5792cb7f4a0a85
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792397"
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
 out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) che è un enumeratore per gli intervalli di memoria in cui gli oggetti si trovano nell'heap gestito.  
  
## <a name="remarks"></a>Note  
 Prima di chiamare il metodo `ICorDebugProcess5::EnumerateHeapRegions`, è necessario chiamare il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) ed esaminare il valore del campo `areGCStructuresValid` dell'oggetto [COR_HEAPINFO](cor-heapinfo-structure.md) restituito per assicurarsi che l'heap Garbage Collection nello stato corrente sia enumerabile. Inoltre, il metodo `ICorDebugProcess5::EnumerateHeapRegions` restituisce `E_FAIL` se ci si connette troppo presto nella durata del processo, prima che vengano create le aree di memoria.  
  
 Questo metodo garantisce l'enumerazione di tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree. L'oggetto raccolta [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) può includere aree di memoria vuote o riservate.  
  
 L'oggetto interfaccia [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_SEGMENT](cor-segment-structure.md) oggetti. Ogni oggetto [COR_SEGMENT](cor-segment-structure.md) fornisce informazioni sull'intervallo di memoria di un determinato segmento, insieme alla generazione degli oggetti in tale segmento.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
