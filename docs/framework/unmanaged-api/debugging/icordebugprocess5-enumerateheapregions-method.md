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
ms.openlocfilehash: 50b0859d6727a25906f2c8b0f3fe96da228ab886
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213556"
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
  
## <a name="remarks"></a>Osservazioni  
 Prima di chiamare il `ICorDebugProcess5::EnumerateHeapRegions` metodo, è necessario chiamare il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) ed esaminare il valore del `areGCStructuresValid` campo dell'oggetto [COR_HEAPINFO](cor-heapinfo-structure.md) restituito per assicurarsi che l'heap Garbage Collection nello stato corrente sia enumerabile. Inoltre, il `ICorDebugProcess5::EnumerateHeapRegions` metodo restituisce `E_FAIL` se ci si connette troppo presto alla durata del processo, prima che vengano create le aree di memoria.  
  
 Questo metodo garantisce l'enumerazione di tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree. L'oggetto raccolta [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) può includere aree di memoria vuote o riservate.  
  
 L'oggetto interfaccia [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_SEGMENT](cor-segment-structure.md) oggetti. Ogni oggetto [COR_SEGMENT](cor-segment-structure.md) fornisce informazioni sull'intervallo di memoria di un determinato segmento, insieme alla generazione degli oggetti in tale segmento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
