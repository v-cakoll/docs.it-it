---
title: ICorProfilerInfo8::GetDynamicFunctionInfo
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d59de04e6af6cfec473899e0a3edadcb3257d385
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665687"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>Metodo ICorProfilerInfo8:: GetDynamicFunctionInfo

Recupera informazioni sui metodi dinamici.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

#### <a name="parameters"></a>Parametri

`functionId` \
in ID della funzione per la quale recuperare le informazioni.

`moduleId` \
in Puntatore al modulo in cui è definita la classe padre della funzione.

`ppvSig` \
out Puntatore alla firma della funzione.

`pbSig` \
out Puntatore al numero di byte per la firma della funzione.

`cchName` \
[in] Dimensione massima della matrice `wszName`.

`pcchName` \
out Numero di caratteri nella `wszName` matrice.

`wszName` \
out Matrice di `WCHAR` che rappresenta il nome della funzione, se disponibile.

## <a name="remarks"></a>Note

Alcuni metodi come gli stub IL o LCG non dispongono di metadati associati che possono essere recuperati tramite le API [IMetaDataImport](../metadata/imetadataimport-interface.md) e [IMetaDataImport2](../metadata/imetadataimport2-interface.md) . Questi metodi possono essere rilevati dai profiler tramite i puntatori all'istruzione oppure ascoltando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

Questa API può essere usata per recuperare informazioni sui metodi dinamici, incluso un nome descrittivo, se disponibile.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorProf. idl, CorProf. h

**Libreria** CorGuids.lib

**Versioni .NET Framework:** [! INCLUDi[net_current_v472plus](../../../../includes/net-current-v472plus.md)

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
