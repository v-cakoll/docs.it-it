---
title: Metodo ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: 3a8e967a3ecc452ebda08872d8bcd9e9d08c766f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777698"
---
# <a name="icordebuggcreferenceenumnext-method"></a>Metodo ICorDebugGCReferenceEnum::Next
Ottiene il numero specificato di istanze di [COR_GC_REFERENCE](cor-gc-reference-structure.md) che contengono informazioni sugli oggetti che verranno sottoposti a Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametri  
 celt  
 in Numero di radici da recuperare.  
  
 radici  
 out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_GC_REFERENCE](cor-gc-reference-structure.md) che rappresenta la radice di un oggetto da sottoporre a Garbage Collection.  
  
 pceltFetched  
 out Puntatore al numero di oggetti di [COR_GC_REFERENCE](cor-gc-reference-structure.md) restituiti effettivamente nella `roots`. Questo valore può essere `null` se `celt` è 1.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
