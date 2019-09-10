---
title: ICorProfilerInfo8::IsFunctionDynamic
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 01aa1df27dccf41060083333588e04bc5ea88520
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855935"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>Metodo ICorProfilerInfo8:: IsFunctionDynamic

Determina se una funzione non dispone di metadati associati.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a>Parametri

`functionId` \
in  Oggetto `FunctionID` che identifica la funzione in questione.

`isDynamic` \
out Puntatore a un oggetto `BOOL` che conterrà un valore che indica se la funzione non dispone di metadati.

## <a name="remarks"></a>Note

Una funzione è considerata dinamica se non dispone di metadati. Alcuni metodi come gli stub IL o i metodi LCG non dispongono di metadati associati che possono essere recuperati tramite le API IMetaDataImport. Questi metodi possono essere rilevati dai profiler tramite i puntatori all'istruzione oppure ascoltando [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorProf. idl, CorProf. h

**Libreria** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
