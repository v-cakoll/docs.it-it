---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863309"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>Metodo ICorProfilerInfo10:: EnumerateObjectReferences

Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente).

## <a name="syntax"></a>Sintassi

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>Parametri

- `objectId`

  \[in] oggetto su cui enumerare i riferimenti.

- `callback`

  \[in] funzione che verrà chiamata con i riferimenti per l'oggetto.

- `clientData`

  \[in] dati forniti dal profiler da passare alla funzione di `callback`.

## <a name="remarks"></a>Note

Il metodo `EnumerateObjectReferences` è simile a [ObjectReferences](icorprofilercallback-objectreferences-method.md), ad eccezione del fatto che scorre i riferimenti su richiesta per il profiler anziché pre-allocare una matrice per archiviare i riferimenti.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](icorprofilerinfo10-interface.md)
