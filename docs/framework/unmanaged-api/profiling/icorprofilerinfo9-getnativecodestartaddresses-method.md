---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 80571933bc8d91c074dbee62aad50cece6277d51
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665496"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>Metodo ICorProfilerInfo9:: GetNativeCodeStartAddresses

Dato un functionId e rejitId, enumera l'indirizzo iniziale del codice nativo di tutte le versioni compilato JIT del codice attualmente esistente.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

#### <a name="parameters"></a>Parametri

`functionId` \
in ID della funzione i cui indirizzi di avvio del codice nativo devono essere restituiti.

`reJitId` \
[in] Identità della funzione ricompilata in JIT.

`cCodeStartAddresses` \
[in] Dimensione massima della matrice `codeStartAddresses`.

`pcCodeStartAddresses` \
out Numero di indirizzi disponibili.

`codeStartAddresses` \
out Matrice di `UINT_PTR`, ciascuno dei quali è l'indirizzo iniziale per un corpo nativo per la funzione specificata.

## <a name="remarks"></a>Note

Quando è abilitata la compilazione a più livelli, una funzione può avere più di un corpo del codice nativo.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Intestazione:** CorProf. idl, CorProf. h

**Libreria** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
