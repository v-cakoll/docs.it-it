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
ms.openlocfilehash: 9aadf9701444d215291b6fc19cc8cd61ca832837
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452240"
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

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](icorprofilerinfo10-interface.md)
