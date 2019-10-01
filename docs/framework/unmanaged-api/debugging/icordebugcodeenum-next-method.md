---
title: Metodo ICorDebugCodeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 076b5d628dfe83decdbbe2f5e74c50e08262c580
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700691"
---
# <a name="icordebugcodeenumnext-method"></a>Metodo ICorDebugCodeEnum::Next

Ottiene il numero specificato di istanze "ICorDebugCode" dall'enumerazione, a partire dalla posizione corrente.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a>Parametri

 `celt`  
 in Numero di istanze di @no__t 0 da recuperare.

 `values`  
 out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugCode`.

 `pceltFetched`  
 out Puntatore al numero di istanze di @no__t 0 effettivamente restituite. Questo valore può essere null se `celt` è uno.

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

 **Intestazione:** CorDebug. idl, CorDebug. h

 **Libreria** CorGuids.lib

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
 
