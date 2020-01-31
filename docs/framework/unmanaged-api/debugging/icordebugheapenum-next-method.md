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
ms.openlocfilehash: 2c84112984e9cb7dec2a492ac16af00e14770806
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782488"
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
  
 Azure  
 out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_HEAPOBJECT](cor-heapobject-structure.md) che fornisce informazioni su un oggetto nell'heap gestito.  
  
 pceltFetched  
 out Puntatore al numero di oggetti di [COR_HEAPOBJECT](cor-heapobject-structure.md) restituiti effettivamente nella `objects`. Questo valore può essere `null` se `celt` è 1.  
  
## <a name="remarks"></a>Note  
 Il campo `COR_HEAPOBJECT.type` è l'identificatore di un'interfaccia COM con conteggio dei riferimenti annidati. Questo riferimento deve essere rilasciato dal chiamante di `ICorDebugHeapEnum::Next`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugHeapEnum](icordebugheapenum-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
