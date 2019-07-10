---
title: Metodo ICorDebugTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5efc83152763c5ef8b65a1fad33460c5354c0dc5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772422"
---
# <a name="icordebugtypeenumnext-method"></a>Metodo ICorDebugTypeEnum::Next
Ottiene il numero di istanze di "ICorDebugType" specificate da `celt` dall'enumerazione, iniziando in corrispondenza della posizione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
 [in] Il numero di `ICorDebugType` istanze da recuperare.  
  
 `values`  
 [out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugType` oggetto.  
  
 `pceltFetched`  
 [out] Puntatore al numero di `ICorDebugType` istanze effettivamente restituite. Questo valore può essere null se `celt` è uno.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
