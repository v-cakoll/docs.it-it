---
title: ICorProfilerInfo10::GetLOHObjectSizeThreshold
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 8c9a85e9f00027f597795eea55a9bbb0364790f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661234"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>Metodo ICorProfilerInfo10:: GetLOHObjectSizeThreshold

Ottiene il valore della soglia dell'heap degli oggetti grandi (LOH) configurata.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a>Parametri

`pThreshold` \
out Soglia heap oggetti grandi in byte.

## <a name="remarks"></a>Note

Gli oggetti più grandi della soglia dell'heap degli oggetti grandi verranno allocati nell'heap degli oggetti grandi. A partire da .NET Core 3,0 la soglia dell'heap degli oggetti grandi è `pThreshold` configurabile, conterrà le dimensioni della soglia heap oggetti grandi attive in byte.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Intestazione:** CorProf. idl, CorProf. h

**Libreria** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
