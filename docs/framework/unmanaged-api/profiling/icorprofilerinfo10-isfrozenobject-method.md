---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 21f9cb415f913a9c865a487f6e80523344db811e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452188"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a>Metodo ICorProfilerInfo10:: IsFrozenObject

Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a>Parametri

- `objectId`

  \[in] oggetto da esaminare.

- `pbFrozen`

  \[out] `BOOL` che indica se l'oggetto si trova in un segmento di sola lettura.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](icorprofilerinfo10-interface.md)
