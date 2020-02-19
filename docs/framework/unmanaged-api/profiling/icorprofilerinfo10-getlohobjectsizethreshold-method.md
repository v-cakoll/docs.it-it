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
ms.openlocfilehash: 7a0f6f6bea5bc919ebfe9c9acc3b02a31eaa7cd0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452214"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>Metodo ICorProfilerInfo10:: GetLOHObjectSizeThreshold

Ottiene il valore della soglia dell'heap degli oggetti grandi (LOH) configurata.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a>Parametri

- `pThreshold`

  \[out] soglia heap oggetti grandi in byte.

## <a name="remarks"></a>Note

Gli oggetti più grandi della soglia dell'heap degli oggetti grandi verranno allocati nell'heap degli oggetti grandi. A partire da .NET Core 3,0 la soglia dell'heap degli oggetti grandi è configurabile, `pThreshold` conterrà le dimensioni della soglia heap oggetti grandi attive in byte.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](icorprofilerinfo10-interface.md)
