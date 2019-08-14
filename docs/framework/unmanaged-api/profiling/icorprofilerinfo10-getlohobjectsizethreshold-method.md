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
ms.openlocfilehash: d6b6575cf04635b40b504b11bc415f61f05b4205
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974021"
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

