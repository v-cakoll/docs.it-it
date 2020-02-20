---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 99b6893854c358720259095bf3c0270cb3676483
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452175"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="0f6c7-102">Metodo ICorProfilerInfo10:: RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="0f6c7-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="0f6c7-103">ReJITs i metodi richiesti, nonché tutti gli inliner dei metodi richiesti.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f6c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f6c7-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="0f6c7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f6c7-105">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="0f6c7-106">\[in] maschera di [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0f6c7-106">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="0f6c7-107">\[in] numero di funzioni da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-107">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="0f6c7-108">\[in] specifica la parte `moduleId` delle coppie (`module``methodDef`) che identificano le funzioni da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-108">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="0f6c7-109">\[in] specifica la parte `methodId` delle coppie (`module``methodDef`) che identificano le funzioni da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-109">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f6c7-110">Note</span><span class="sxs-lookup"><span data-stu-id="0f6c7-110">Remarks</span></span>

<span data-ttu-id="0f6c7-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) non esegue alcun rilevamento dei metodi inline.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="0f6c7-112">Il profiler avrebbe dovuto bloccare l'incorporamento o tenere traccia dell'incorporamento e chiamare `RequestReJIT` per tutti gli Inliners per assicurarsi che ogni istanza di un metodo reso inline fosse ReJITted.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="0f6c7-113">Si è verificato un problema con ReJIT durante l'associazione, poiché il profiler non è presente per il monitoraggio dell'incorporamento.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="0f6c7-114">Questo metodo può essere chiamato per garantire che anche il set completo di inliner sarà ReJITted.</span><span class="sxs-lookup"><span data-stu-id="0f6c7-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f6c7-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f6c7-115">Requirements</span></span>

<span data-ttu-id="0f6c7-116">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="0f6c7-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="0f6c7-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f6c7-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="0f6c7-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f6c7-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0f6c7-119">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f6c7-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0f6c7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f6c7-120">See also</span></span>

- [<span data-ttu-id="0f6c7-121">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="0f6c7-121">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
