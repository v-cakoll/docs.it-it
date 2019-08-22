---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 9e8e4c7e6c367970100c98dc3dc8237b25f99221
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665608"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a>Metodo ICorProfilerInfo9:: GetILToNativeMapping3

Dato l'indirizzo iniziale del codice nativo, restituisce le informazioni di mapping native a per la versione compilato JIT del codice.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

#### <a name="parameters"></a>Parametri

`pNativeCodeStartAddress` \
in Puntatore all'inizio di una funzione nativa.

`cMap` \
[in] Dimensione massima della matrice `map`.

`pcMap` \
out Numero totale di strutture COR_DEBUG_IL_TO_NATIVE_MAP disponibili.

`map` \
out Matrice di strutture [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , ognuna delle quali specifica gli offset. Dopo il completamento del metodo `GetILToNativeMapping3`, `map` conterrà alcune o tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.

## <a name="remarks"></a>Note

Quando è abilitata la compilazione a più livelli, un metodo può avere più di un corpo del codice nativo. [ICorProfilerInfo9:: GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) restituirà gli indirizzi iniziali per tutti i corpi del codice nativo.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Intestazione:** CorProf. idl, CorProf. h

**Libreria** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
