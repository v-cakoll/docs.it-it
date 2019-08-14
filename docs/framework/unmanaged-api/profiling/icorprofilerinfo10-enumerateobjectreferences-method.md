---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 4b13659f7c9909e9795caee1eace8da8092c5b9a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974031"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="7a1f0-102">Metodo ICorProfilerInfo10:: EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="7a1f0-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>
  
 <span data-ttu-id="7a1f0-103">Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente).</span><span class="sxs-lookup"><span data-stu-id="7a1f0-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="7a1f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a1f0-104">Syntax</span></span>  
  
```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a1f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a1f0-105">Parameters</span></span>  

 `objectId` \
 <span data-ttu-id="7a1f0-106">in Oggetto su cui enumerare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="7a1f0-106">[in] The object to enumerate references on.</span></span>

 `callback` \
 <span data-ttu-id="7a1f0-107">in Funzione che verrà chiamata con i riferimenti per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7a1f0-107">[in] The function that will be called with the references for the object.</span></span>

 `clientData` \
 <span data-ttu-id="7a1f0-108">in Dati forniti dal `callback` Profiler da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="7a1f0-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7a1f0-109">Note</span><span class="sxs-lookup"><span data-stu-id="7a1f0-109">Remarks</span></span>  
 <span data-ttu-id="7a1f0-110">Il `EnumerateObjectReferences` metodo è simile a [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), ad eccezione del fatto che scorre i riferimenti su richiesta per il profiler anziché pre-allocare una matrice per archiviare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="7a1f0-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>  

## <a name="requirements"></a><span data-ttu-id="7a1f0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a1f0-111">Requirements</span></span>  
 <span data-ttu-id="7a1f0-112">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="7a1f0-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="7a1f0-113">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="7a1f0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a1f0-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a1f0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a1f0-115">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a1f0-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a1f0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a1f0-116">See also</span></span>
- [<span data-ttu-id="7a1f0-117">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="7a1f0-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

