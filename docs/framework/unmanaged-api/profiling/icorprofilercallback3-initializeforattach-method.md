---
title: Metodo ICorProfilerCallback3::InitializeForAttach
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: 047516574595f9ffcd61360f51823da73a2f9733
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439525"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="b8102-102">Metodo ICorProfilerCallback3::InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="b8102-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="b8102-103">Chiamato da Common Language Runtime (CLR) per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="b8102-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8102-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8102-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8102-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8102-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="b8102-106">[in] Puntatore all'interfaccia `ICorProfilerInfo*`.</span><span class="sxs-lookup"><span data-stu-id="b8102-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="b8102-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span><span class="sxs-lookup"><span data-stu-id="b8102-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="b8102-108">Se questo parametro è null, `cbClientData` sarà 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b8102-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="b8102-109">CLR libera questa memoria quando ottiene un risultato da `InitializeForAttach`.</span><span class="sxs-lookup"><span data-stu-id="b8102-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="b8102-110">[in] Dimensioni in byte dei dati a cui `pvClientData` punta.</span><span class="sxs-lookup"><span data-stu-id="b8102-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8102-111">Note</span><span class="sxs-lookup"><span data-stu-id="b8102-111">Remarks</span></span>  
 <span data-ttu-id="b8102-112">CLR chiama `InitializeForAttach` per dare al profiler la possibilità di richiedere callback.</span><span class="sxs-lookup"><span data-stu-id="b8102-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8102-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8102-113">Requirements</span></span>  
 <span data-ttu-id="b8102-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8102-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8102-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8102-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8102-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8102-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8102-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8102-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8102-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8102-118">See also</span></span>

- [<span data-ttu-id="b8102-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b8102-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b8102-120">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="b8102-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b8102-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b8102-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b8102-122">Profilatura</span><span class="sxs-lookup"><span data-stu-id="b8102-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
