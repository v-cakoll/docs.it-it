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
ms.openlocfilehash: 3d4e44eefaf99a40b9c4f1c45e7dd81192f8b607
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904273"
---
# <a name="icordebugheapsegmentenumnext-method"></a>Metodo ICorDebugHeapSegmentEnum::Next
Ottiene il numero specificato di istanze di [COR_SEGMENT](cor-segment-structure.md) che contengono informazioni sulle aree di memoria dell'heap gestito.  
  
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
 out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_SEGMENT](cor-segment-structure.md) che fornisce informazioni su un'area di memoria nell'heap gestito.  
  
 pceltFetched  
 out Puntatore al numero di oggetti [COR_SEGMENT](cor-segment-structure.md) effettivamente restituiti in `segments` . Questo valore può essere `null` se `celt` è 1.  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
