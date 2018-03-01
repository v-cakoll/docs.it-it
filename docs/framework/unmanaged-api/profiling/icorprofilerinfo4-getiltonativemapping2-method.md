---
title: Metodo ICorProfilerInfo4::GetILToNativeMapping2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d5ce076ad66214f786f7e221a0443edf7986c5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="9ef10-102">Metodo ICorProfilerInfo4::GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="9ef10-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="9ef10-103">Ottiene una mappa dagli offset MSIL (Microsoft Intermediate Language) agli offset nativi per il codice contenuto nella versione ricompilata in JIT della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="9ef10-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef10-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ef10-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ef10-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ef10-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9ef10-106">[in] ID della funzione che contiene il codice.</span><span class="sxs-lookup"><span data-stu-id="9ef10-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="9ef10-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="9ef10-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="9ef10-108">L'identità deve essere uguale a zero in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ef10-108">The identity must be zero in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 `cMap`  
 <span data-ttu-id="9ef10-109">[in] Dimensione massima della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="9ef10-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="9ef10-110">[out] Numero totale di strutture COR_DEBUG_IL_TO_NATIVE_MAP disponibili.</span><span class="sxs-lookup"><span data-stu-id="9ef10-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="9ef10-111">[out] Matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`, ognuna delle quali specifica gli offset.</span><span class="sxs-lookup"><span data-stu-id="9ef10-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="9ef10-112">Dopo il completamento del metodo `GetILToNativeMapping2`, `map` conterrà alcune o tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9ef10-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ef10-113">Note</span><span class="sxs-lookup"><span data-stu-id="9ef10-113">Remarks</span></span>  
 <span data-ttu-id="9ef10-114">`GetILToNativeMapping2`è simile al [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) rilascia metodo, ad eccezione del fatto che consentirà al profiler di specificare l'ID della funzione ricompilata in futuro.</span><span class="sxs-lookup"><span data-stu-id="9ef10-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ef10-115">Il [icorprofilerfunctioncontrol:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) metodo non è implementato nel [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], pertanto le funzioni che sono stati ricompilata in JIT non possono avere un mapping per IL codice nativo che differisce dall'originariamente funzione compilata.</span><span class="sxs-lookup"><span data-stu-id="9ef10-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="9ef10-116">Di conseguenza, `GetILToNativeMapping2` non può essere chiamato con un ID ricompilato in JIT diverso da zero in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ef10-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 <span data-ttu-id="9ef10-117">Il metodo `GetILToNativeMapping2` restituisce una matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9ef10-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="9ef10-118">Per indicare che determinati intervalli di istruzioni native corrispondono ad aree speciali del codice, ad esempio, il prologo, una voce nella matrice può avere il `ilOffset` campo impostato su un valore di [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9ef10-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="9ef10-119">Dopo il completamento del metodo `GetILToNativeMapping2`, è necessario verificare che il buffer `map` sia abbastanza grande per contenere tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9ef10-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="9ef10-120">A tale scopo, confrontare il valore di `cMap` con il valore del parametro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="9ef10-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="9ef10-121">Se il valore `pcMap`, moltiplicato per la dimensione di una struttura `COR_DEBUG_IL_TO_NATIVE_MAP`, è superiore a `cMap`, allocare un buffer `map` più grande, aggiornare `cMap` con la nuova dimensione e chiamare nuovamente `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="9ef10-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="9ef10-122">In alternativa, è possibile chiamare innanzitutto `GetILToNativeMapping2` con un buffer `map` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="9ef10-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="9ef10-123">È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcMap` e chiamare nuovamente `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="9ef10-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ef10-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ef10-124">Requirements</span></span>  
 <span data-ttu-id="9ef10-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ef10-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ef10-126">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ef10-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ef10-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ef10-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ef10-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ef10-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef10-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ef10-129">See Also</span></span>  
 [<span data-ttu-id="9ef10-130">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="9ef10-130">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [<span data-ttu-id="9ef10-131">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="9ef10-131">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="9ef10-132">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="9ef10-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="9ef10-133">Profilatura</span><span class="sxs-lookup"><span data-stu-id="9ef10-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
