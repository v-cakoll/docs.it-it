---
title: Metodo ICorDebugHeapEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 5d0b231b4014e60a9e8778c6b9d6ed7758b2d8c5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208473"
---
# <a name="icordebugheapenumnext-method"></a>Metodo ICorDebugHeapEnum::Next
Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametri  
 celt  
 [in] Numero di oggetti da recuperare.  
  
 oggetti  
 out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_HEAPOBJECT](cor-heapobject-structure.md) che fornisce informazioni su un oggetto nell'heap gestito.  
  
 pceltFetched  
 out Puntatore al numero di oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) effettivamente restituiti in `objects` . Questo valore può essere `null` se `celt` è 1.  
  
## <a name="remarks"></a>Osservazioni  
 Il campo `COR_HEAPOBJECT.type` è l'identificatore di un'interfaccia COM con conteggio dei riferimenti annidati. Questo riferimento deve essere rilasciato dal chiamante di `ICorDebugHeapEnum::Next`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugHeapEnum](icordebugheapenum-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
