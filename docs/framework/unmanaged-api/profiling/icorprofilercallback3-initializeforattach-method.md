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
ms.openlocfilehash: d0219751987b1f2d78ee37a1553b323014c1ccfe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865688"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="25cd0-102">Metodo ICorProfilerCallback3::InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="25cd0-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="25cd0-103">Chiamato da Common Language Runtime (CLR) per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="25cd0-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25cd0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25cd0-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25cd0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25cd0-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="25cd0-106">[in] Puntatore all'interfaccia `ICorProfilerInfo*`.</span><span class="sxs-lookup"><span data-stu-id="25cd0-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="25cd0-107">in Puntatore ai dati passati al metodo [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) nel parametro `pvClientData`.</span><span class="sxs-lookup"><span data-stu-id="25cd0-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="25cd0-108">Se questo parametro è null, `cbClientData` sarà 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="25cd0-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="25cd0-109">CLR libera questa memoria quando ottiene un risultato da `InitializeForAttach`.</span><span class="sxs-lookup"><span data-stu-id="25cd0-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="25cd0-110">[in] Dimensioni in byte dei dati a cui `pvClientData` punta.</span><span class="sxs-lookup"><span data-stu-id="25cd0-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25cd0-111">Note</span><span class="sxs-lookup"><span data-stu-id="25cd0-111">Remarks</span></span>  
 <span data-ttu-id="25cd0-112">CLR chiama `InitializeForAttach` per dare al profiler la possibilità di richiedere callback.</span><span class="sxs-lookup"><span data-stu-id="25cd0-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25cd0-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="25cd0-113">Requirements</span></span>  
 <span data-ttu-id="25cd0-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25cd0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25cd0-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25cd0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25cd0-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25cd0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25cd0-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25cd0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cd0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25cd0-118">See also</span></span>

- [<span data-ttu-id="25cd0-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="25cd0-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="25cd0-120">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="25cd0-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="25cd0-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="25cd0-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="25cd0-122">Profilatura</span><span class="sxs-lookup"><span data-stu-id="25cd0-122">Profiling</span></span>](index.md)
