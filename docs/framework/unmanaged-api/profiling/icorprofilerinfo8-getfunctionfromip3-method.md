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
ms.openlocfilehash: df9ecc9bc355c12f993763820eb5065ba8bcc36b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855912"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>Metodo ICorProfilerInfo8:: GetFunctionFromIP3

Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID. Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

#### <a name="parameters"></a>Parametri

`ip` \
in Puntatore all'istruzione nel codice gestito.

`pFunctionId` \
out ID funzione.

`pReJitId` \
out Identità della versione ricompilata in JIT della funzione.

## <a name="remarks"></a>Note

Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici. Si tratta di un superset di [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), che funziona solo per le funzioni con metadati.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorProf. idl, CorProf. h

**Libreria** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
