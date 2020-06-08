---
title: Metodo ICorProfilerInfo4::GetILToNativeMapping2
ms.date: 03/30/2017
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
ms.openlocfilehash: 9a6ee58cda5e0b673b3ff1378240f89323e30194
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496061"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="a1180-102">Metodo ICorProfilerInfo4::GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="a1180-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="a1180-103">Ottiene una mappa dagli offset MSIL (Microsoft Intermediate Language) agli offset nativi per il codice contenuto nella versione ricompilata in JIT della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="a1180-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1180-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1180-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1180-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1180-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a1180-106">[in] ID della funzione che contiene il codice.</span><span class="sxs-lookup"><span data-stu-id="a1180-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="a1180-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="a1180-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="a1180-108">L'identità deve essere zero nella .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="a1180-108">The identity must be zero in the .NET Framework 4.5.</span></span>  
  
 `cMap`  
 <span data-ttu-id="a1180-109">[in] Dimensione massima della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="a1180-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="a1180-110">[out] Numero complessivo di strutture COR_DEBUG_IL_TO_NATIVE_MAP disponibili.</span><span class="sxs-lookup"><span data-stu-id="a1180-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="a1180-111">[out] Matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`, ognuna delle quali specifica gli offset.</span><span class="sxs-lookup"><span data-stu-id="a1180-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="a1180-112">Dopo il completamento del metodo `GetILToNativeMapping2`, `map` conterrà alcune o tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="a1180-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1180-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a1180-113">Remarks</span></span>  
 <span data-ttu-id="a1180-114">`GetILToNativeMapping2`è simile al metodo [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) , con la differenza che consente al profiler di specificare l'ID della funzione ricompilata nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="a1180-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1180-115">Il metodo [ICorProfilerFunctionControl:: SetILInstrumentedCodeMap](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) non è implementato nel .NET Framework 4,5, pertanto le funzioni che sono state ricompilate tramite JIT non possono avere un mapping da il a nativo che differisce dalla funzione originariamente compilata.</span><span class="sxs-lookup"><span data-stu-id="a1180-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the .NET Framework 4.5, so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="a1180-116">Di conseguenza, `GetILToNativeMapping2` non può essere chiamato con un ID ricompilato JIT diverso da zero nel .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="a1180-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="a1180-117">Il metodo `GetILToNativeMapping2` restituisce una matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="a1180-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="a1180-118">Per indicare che determinati intervalli di istruzioni native corrispondono a aree speciali di codice (ad esempio, il prologo), una voce nella matrice può avere il `ilOffset` campo impostato su un valore dell'enumerazione [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="a1180-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="a1180-119">Dopo il completamento del metodo `GetILToNativeMapping2`, è necessario verificare che il buffer `map` sia abbastanza grande per contenere tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="a1180-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="a1180-120">A tale scopo, confrontare il valore di `cMap` con il valore del parametro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="a1180-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="a1180-121">Se il valore `pcMap`, moltiplicato per la dimensione di una struttura `COR_DEBUG_IL_TO_NATIVE_MAP`, è superiore a `cMap`, allocare un buffer `map` più grande, aggiornare `cMap` con la nuova dimensione e chiamare nuovamente `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="a1180-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="a1180-122">In alternativa, è possibile chiamare innanzitutto `GetILToNativeMapping2` con un buffer `map` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="a1180-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="a1180-123">È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcMap` e chiamare nuovamente `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="a1180-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1180-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1180-124">Requirements</span></span>  
 <span data-ttu-id="a1180-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1180-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1180-126">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1180-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1180-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1180-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1180-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1180-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1180-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1180-129">See also</span></span>

- [<span data-ttu-id="a1180-130">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="a1180-130">GetILToNativeMapping Method</span></span>](icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="a1180-131">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="a1180-131">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="a1180-132">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a1180-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a1180-133">Profilatura</span><span class="sxs-lookup"><span data-stu-id="a1180-133">Profiling</span></span>](index.md)
