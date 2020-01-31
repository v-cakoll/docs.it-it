---
title: Metodo ICorProfilerInfo::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
ms.openlocfilehash: f9abb3ae9cd3f9c70485e584399a6ed32b32a572
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870616"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="9eafc-102">Metodo ICorProfilerInfo::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="9eafc-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>
<span data-ttu-id="9eafc-103">Ottiene una mappa dagli offset MSIL (Microsoft Intermediate Language) agli offset nativi per il codice contenuto nella funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="9eafc-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eafc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9eafc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eafc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9eafc-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9eafc-106">[in] ID della funzione che contiene il codice.</span><span class="sxs-lookup"><span data-stu-id="9eafc-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="9eafc-107">[in] Dimensione massima della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="9eafc-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="9eafc-108">[out] Numero complessivo di strutture COR_DEBUG_IL_TO_NATIVE_MAP disponibili.</span><span class="sxs-lookup"><span data-stu-id="9eafc-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="9eafc-109">[out] Matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`, ognuna delle quali specifica gli offset.</span><span class="sxs-lookup"><span data-stu-id="9eafc-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="9eafc-110">Dopo il completamento del metodo `GetILToNativeMapping`, `map` conterrà alcune o tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9eafc-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9eafc-111">Note</span><span class="sxs-lookup"><span data-stu-id="9eafc-111">Remarks</span></span>  
 <span data-ttu-id="9eafc-112">Il metodo `GetILToNativeMapping` restituisce una matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9eafc-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="9eafc-113">Per indicare che determinati intervalli di istruzioni native corrispondono a aree speciali di codice (ad esempio, il prologo), una voce nella matrice può avere il campo `ilOffset` impostato su un valore dell'enumerazione [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="9eafc-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="9eafc-114">Dopo il completamento del metodo `GetILToNativeMapping`, è necessario verificare che il buffer `map` sia abbastanza grande per contenere tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9eafc-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="9eafc-115">A tale scopo, confrontare il valore di `cMap` con il valore del parametro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="9eafc-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="9eafc-116">Se il valore `pcMap`, moltiplicato per la dimensione di una struttura `COR_DEBUG_IL_TO_NATIVE_MAP`, è superiore a `cMap`, allocare un buffer `map` più grande, aggiornare `cMap` con la nuova dimensione e chiamare nuovamente `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="9eafc-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="9eafc-117">In alternativa, è possibile chiamare innanzitutto `GetILToNativeMapping` con un buffer `map` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="9eafc-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="9eafc-118">È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcMap` e chiamare nuovamente `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="9eafc-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eafc-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9eafc-119">Requirements</span></span>  
 <span data-ttu-id="9eafc-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eafc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eafc-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9eafc-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9eafc-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9eafc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9eafc-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eafc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eafc-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eafc-124">See also</span></span>

- [<span data-ttu-id="9eafc-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9eafc-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="9eafc-126">Metodo GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="9eafc-126">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="9eafc-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="9eafc-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9eafc-128">Profilatura</span><span class="sxs-lookup"><span data-stu-id="9eafc-128">Profiling</span></span>](index.md)
