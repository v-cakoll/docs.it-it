---
title: Metodo ICorDebugILCode2::GetInstrumentedILMap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetInstrumentedILMap
api_location: mscordbi.dll
api_type: COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0499813bc2192d419dc21d9dbb84aff17894544f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="787fa-102">Metodo ICorDebugILCode2::GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="787fa-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="787fa-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="787fa-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="787fa-104">Restituisce una mappa dagli offset di linguaggio intermedio (IL) instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="787fa-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787fa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="787fa-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="787fa-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="787fa-106">Parameters</span></span>  
 <span data-ttu-id="787fa-107">cMap</span><span class="sxs-lookup"><span data-stu-id="787fa-107">cMap</span></span>  
 <span data-ttu-id="787fa-108">[in] Capacità di memoria della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="787fa-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="787fa-109">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="787fa-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="787fa-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="787fa-110">pcMap</span></span>  
 <span data-ttu-id="787fa-111">[out] Il numero di valori COR_IL_MAP scritti nella matrice map.</span><span class="sxs-lookup"><span data-stu-id="787fa-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="787fa-112">map</span><span class="sxs-lookup"><span data-stu-id="787fa-112">map</span></span>  
 <span data-ttu-id="787fa-113">[out] Una matrice di valori COR_IL_MAP che forniscono informazioni sui mapping dal linguaggio intermedio instrumentato del profiler per il linguaggio intermedio del metodo originale.</span><span class="sxs-lookup"><span data-stu-id="787fa-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="787fa-114">Note</span><span class="sxs-lookup"><span data-stu-id="787fa-114">Remarks</span></span>  
 <span data-ttu-id="787fa-115">Se il profiler imposta il mapping chiamando il [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) metodo, il debugger può chiamare questo metodo per recuperare il mapping e utilizzare il mapping internamente durante IL calcolo degli offset per stack le tracce e durata delle variabili.</span><span class="sxs-lookup"><span data-stu-id="787fa-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="787fa-116">Se `cMap` è 0 e `pcMap` è non**null**, `pcMap` è impostato sul numero di valori COR_IL_MAP disponibili.</span><span class="sxs-lookup"><span data-stu-id="787fa-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="787fa-117">Se `cMap` è diverso da zero, rappresenta la capacità di memoria della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="787fa-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="787fa-118">Quando termina, il metodo `map` contiene un massimo di `cMap` elementi, e `pcMap` è impostato per il numero di valori COR_IL_MAP effettivamente scritti il `map` matrice.</span><span class="sxs-lookup"><span data-stu-id="787fa-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="787fa-119">Se il linguaggio intermedio (IL) non è instrumentato o il profiler non ha fornito un mapping, il metodo restituisce `S_OK` e imposta `pcMap` su 0.</span><span class="sxs-lookup"><span data-stu-id="787fa-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="787fa-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="787fa-120">Requirements</span></span>  
 <span data-ttu-id="787fa-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="787fa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="787fa-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="787fa-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="787fa-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="787fa-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="787fa-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="787fa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787fa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="787fa-125">See Also</span></span>  
 [<span data-ttu-id="787fa-126">ICorProfilerInfo:: SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="787fa-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [<span data-ttu-id="787fa-127">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="787fa-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="787fa-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="787fa-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
