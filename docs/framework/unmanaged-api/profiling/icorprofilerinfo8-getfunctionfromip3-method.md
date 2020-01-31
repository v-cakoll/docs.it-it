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
ms.openlocfilehash: 6d50a5d74eccff6fe39aca111f768bac4d8f2e2e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868330"
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

## <a name="remarks"></a>Note

Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici. Si tratta di un superset di [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), che funziona solo per le funzioni con metadati.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo8](icorprofilerinfo8-interface.md)
