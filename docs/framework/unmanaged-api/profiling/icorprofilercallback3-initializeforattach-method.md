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
ms.openlocfilehash: 9bff594d0307153fb468b28c1535977f06997748
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499714"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="9e799-102">Metodo ICorProfilerCallback3::InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="9e799-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="9e799-103">Chiamato da Common Language Runtime (CLR) per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="9e799-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e799-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e799-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e799-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e799-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="9e799-106">[in] Puntatore all'interfaccia `ICorProfilerInfo*`.</span><span class="sxs-lookup"><span data-stu-id="9e799-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="9e799-107">in Puntatore ai dati passati al metodo [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) nel `pvClientData` parametro.</span><span class="sxs-lookup"><span data-stu-id="9e799-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="9e799-108">Se questo parametro è null, `cbClientData` sarà 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="9e799-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="9e799-109">CLR libera questa memoria quando ottiene un risultato da `InitializeForAttach`.</span><span class="sxs-lookup"><span data-stu-id="9e799-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="9e799-110">[in] Dimensioni in byte dei dati a cui `pvClientData` punta.</span><span class="sxs-lookup"><span data-stu-id="9e799-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e799-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9e799-111">Remarks</span></span>  
 <span data-ttu-id="9e799-112">CLR chiama `InitializeForAttach` per dare al profiler la possibilità di richiedere callback.</span><span class="sxs-lookup"><span data-stu-id="9e799-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e799-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e799-113">Requirements</span></span>  
 <span data-ttu-id="9e799-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e799-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e799-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e799-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e799-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e799-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e799-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e799-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e799-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e799-118">See also</span></span>

- [<span data-ttu-id="9e799-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9e799-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9e799-120">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="9e799-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="9e799-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="9e799-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9e799-122">Profilatura</span><span class="sxs-lookup"><span data-stu-id="9e799-122">Profiling</span></span>](index.md)
