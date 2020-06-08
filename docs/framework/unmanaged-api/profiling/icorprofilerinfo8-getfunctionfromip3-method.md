---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 6822757608429ca5f4ef9520ab7574d440b67b26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495256"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>Metodo ICorProfilerInfo8:: GetFunctionFromIP3

Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID. Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a>Parametri

- `ip`

  \[in] puntatore all'istruzione nel codice gestito.

- `pFunctionId`

  \[out] ID funzione.

- `pReJitId`

  \[out] identità della versione ricompilata in JIT della funzione.

## <a name="remarks"></a>Osservazioni

Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici. Si tratta di un superset di [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), che funziona solo per le funzioni con metadati.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo8](icorprofilerinfo8-interface.md)
