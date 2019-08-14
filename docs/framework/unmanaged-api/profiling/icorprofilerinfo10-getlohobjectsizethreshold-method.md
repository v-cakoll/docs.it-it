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
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="5b1fc-102">Metodo ICorProfilerInfo10:: GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="5b1fc-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>
  
 <span data-ttu-id="5b1fc-103">Ottiene il valore della soglia dell'heap degli oggetti grandi (LOH) configurata.</span><span class="sxs-lookup"><span data-stu-id="5b1fc-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="5b1fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b1fc-104">Syntax</span></span>  
  
```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b1fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b1fc-105">Parameters</span></span>  
 `pThreshold` \
 <span data-ttu-id="5b1fc-106">out Soglia heap oggetti grandi in byte.</span><span class="sxs-lookup"><span data-stu-id="5b1fc-106">[out] The large object heap threshold in bytes.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5b1fc-107">Note</span><span class="sxs-lookup"><span data-stu-id="5b1fc-107">Remarks</span></span>  
 <span data-ttu-id="5b1fc-108">Gli oggetti più grandi della soglia dell'heap degli oggetti grandi verranno allocati nell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="5b1fc-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="5b1fc-109">A partire da .NET Core 3,0 la soglia dell'heap degli oggetti grandi è `pThreshold` configurabile, conterrà le dimensioni della soglia heap oggetti grandi attive in byte.</span><span class="sxs-lookup"><span data-stu-id="5b1fc-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b1fc-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b1fc-110">Requirements</span></span>  
 <span data-ttu-id="5b1fc-111">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="5b1fc-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="5b1fc-112">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="5b1fc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b1fc-113">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b1fc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b1fc-114">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b1fc-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b1fc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b1fc-115">See also</span></span>
- [<span data-ttu-id="5b1fc-116">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="5b1fc-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

