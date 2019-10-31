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
ms.openlocfilehash: 04c36d1e5f0e79b71963683a3b613a9ad7392bcf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125522"
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
in Numero di istanze di `ICorDebugCode` da recuperare.

`values`  
out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugCode`.

`pceltFetched`  
out Puntatore al numero di istanze di `ICorDebugCode` restituite effettivamente. Questo valore può essere null se `celt` è uno.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
