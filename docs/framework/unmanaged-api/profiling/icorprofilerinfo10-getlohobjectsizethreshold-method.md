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
ms.openlocfilehash: 95473a8ce8d5fd7540228ecd9767448e51b5b326
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868984"
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

## <a name="requirements"></a>Requisiti di

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](icorprofilerinfo10-interface.md)
