---
title: Metodo ICorDebugHeapSegmentEnum::Next
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: c9999961ec20a31cf82d5ad60104bcdd04c340d1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210176"
---
# <a name="icordebugheapsegmentenumnext-method"></a>Metodo ICorDebugHeapSegmentEnum::Next
Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sulle aree di memoria dell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametri  
 celt  
 in Numero di segmenti da recuperare.  
  
 segmenti  
 out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_HEAPOBJECT](cor-heapobject-structure.md) che fornisce informazioni su un'area di memoria nell'heap gestito.  
  
 pceltFetched  
 out Puntatore al numero di oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) effettivamente restituiti in `segments` . Questo valore può essere `null` se `celt` è 1.  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
