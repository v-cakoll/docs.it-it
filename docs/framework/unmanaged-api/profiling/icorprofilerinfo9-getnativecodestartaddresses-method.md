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
ms.openlocfilehash: 8412020fb98fde245b873a2f0c6a355f6436f712
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868278"
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

## <a name="parameters"></a>Parametri

- `functionId`

  \[in] ID della funzione i cui indirizzi di avvio del codice nativo devono essere restituiti.

- `reJitId`

  \[in] identità della funzione ricompilata tramite JIT.

- `cCodeStartAddresses`

  \[in] dimensione massima della matrice di `codeStartAddresses`.

- `pcCodeStartAddresses`

  \[out] numero di indirizzi disponibili.

- `codeStartAddresses`

  \[out] matrice di `UINT_PTR`, ciascuno dei quali è l'indirizzo iniziale per un corpo nativo per la funzione specificata.

## <a name="remarks"></a>Note

Quando è abilitata la compilazione a più livelli, una funzione può avere più di un corpo del codice nativo.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo9](icorprofilerinfo9-interface.md)
