---
title: Metodo ICorDebugILCode2::GetInstrumentedILMap
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4197b018ea85402762a8591b40f3503c02af3974
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673129"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="61f8a-102">Metodo ICorDebugILCode2::GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="61f8a-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="61f8a-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="61f8a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="61f8a-104">Restituisce una mappa dagli offset di linguaggio intermedio (IL) instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="61f8a-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f8a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61f8a-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61f8a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="61f8a-106">Parameters</span></span>  
 <span data-ttu-id="61f8a-107">cMap</span><span class="sxs-lookup"><span data-stu-id="61f8a-107">cMap</span></span>  
 <span data-ttu-id="61f8a-108">[in] Capacità di memoria della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="61f8a-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="61f8a-109">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="61f8a-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="61f8a-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="61f8a-110">pcMap</span></span>  
 <span data-ttu-id="61f8a-111">[out] Il numero di valori COR_IL_MAP scritti nella matrice map.</span><span class="sxs-lookup"><span data-stu-id="61f8a-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="61f8a-112">map</span><span class="sxs-lookup"><span data-stu-id="61f8a-112">map</span></span>  
 <span data-ttu-id="61f8a-113">[out] Matrice di valori COR_IL_MAP che fornisce informazioni sui mapping dal linguaggio intermedio instrumentato del profiler per il linguaggio intermedio del metodo originale.</span><span class="sxs-lookup"><span data-stu-id="61f8a-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61f8a-114">Note</span><span class="sxs-lookup"><span data-stu-id="61f8a-114">Remarks</span></span>  
 <span data-ttu-id="61f8a-115">Se il profiler imposta il mapping chiamando il [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) metodo, il debugger può chiamare questo metodo per recuperare il mapping e usarlo internamente per IL calcolo degli offset per lo stack le tracce e durata delle variabili.</span><span class="sxs-lookup"><span data-stu-id="61f8a-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="61f8a-116">Se `cMap` è 0 e `pcMap` è diverso da**null**, `pcMap` è impostato sul numero di valori COR_IL_MAP disponibili.</span><span class="sxs-lookup"><span data-stu-id="61f8a-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="61f8a-117">Se `cMap` è diverso da zero, rappresenta la capacità di memoria della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="61f8a-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="61f8a-118">Quando termina, il metodo `map` contiene un massimo di `cMap` gli elementi, e `pcMap` è impostato sul numero di valori COR_IL_MAP effettivamente scritti i `map` matrice.</span><span class="sxs-lookup"><span data-stu-id="61f8a-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="61f8a-119">Se il linguaggio intermedio (IL) non è instrumentato o il profiler non ha fornito un mapping, il metodo restituisce `S_OK` e imposta `pcMap` su 0.</span><span class="sxs-lookup"><span data-stu-id="61f8a-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61f8a-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61f8a-120">Requirements</span></span>  
 <span data-ttu-id="61f8a-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61f8a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61f8a-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61f8a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61f8a-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61f8a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61f8a-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61f8a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f8a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61f8a-125">See also</span></span>

- [<span data-ttu-id="61f8a-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="61f8a-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="61f8a-127">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="61f8a-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="61f8a-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="61f8a-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
