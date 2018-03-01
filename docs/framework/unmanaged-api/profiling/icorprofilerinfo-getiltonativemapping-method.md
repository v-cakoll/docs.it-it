---
title: Metodo ICorProfilerInfo::GetILToNativeMapping
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 89ccfcbf69a0d3907ec244d7a214d6f4a5766767
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="cf044-102">Metodo ICorProfilerInfo::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="cf044-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>
<span data-ttu-id="cf044-103">Ottiene una mappa dagli offset MSIL (Microsoft Intermediate Language) agli offset nativi per il codice contenuto nella funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="cf044-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf044-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf044-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf044-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf044-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="cf044-106">[in] ID della funzione che contiene il codice.</span><span class="sxs-lookup"><span data-stu-id="cf044-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="cf044-107">[in] Dimensione massima della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="cf044-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="cf044-108">[out] Numero totale di strutture COR_DEBUG_IL_TO_NATIVE_MAP disponibili.</span><span class="sxs-lookup"><span data-stu-id="cf044-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="cf044-109">[out] Matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`, ognuna delle quali specifica gli offset.</span><span class="sxs-lookup"><span data-stu-id="cf044-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="cf044-110">Dopo il completamento del metodo `GetILToNativeMapping`, `map` conterrà alcune o tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="cf044-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf044-111">Note</span><span class="sxs-lookup"><span data-stu-id="cf044-111">Remarks</span></span>  
 <span data-ttu-id="cf044-112">Il metodo `GetILToNativeMapping` restituisce una matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="cf044-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="cf044-113">Per indicare che determinati intervalli di istruzioni native corrispondono ad aree speciali del codice, ad esempio, il prologo, una voce nella matrice può avere il `ilOffset` campo impostato su un valore di [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="cf044-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="cf044-114">Dopo il completamento del metodo `GetILToNativeMapping`, è necessario verificare che il buffer `map` sia abbastanza grande per contenere tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="cf044-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="cf044-115">A tale scopo, confrontare il valore di `cMap` con il valore del parametro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="cf044-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="cf044-116">Se il valore `pcMap`, moltiplicato per la dimensione di una struttura `COR_DEBUG_IL_TO_NATIVE_MAP`, è superiore a `cMap`, allocare un buffer `map` più grande, aggiornare `cMap` con la nuova dimensione e chiamare nuovamente `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="cf044-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="cf044-117">In alternativa, è possibile chiamare innanzitutto `GetILToNativeMapping` con un buffer `map` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="cf044-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="cf044-118">È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcMap` e chiamare nuovamente `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="cf044-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf044-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf044-119">Requirements</span></span>  
 <span data-ttu-id="cf044-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf044-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf044-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf044-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf044-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf044-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf044-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf044-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf044-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf044-124">See Also</span></span>  
 [<span data-ttu-id="cf044-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cf044-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="cf044-126">Metodo GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="cf044-126">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)  
 [<span data-ttu-id="cf044-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="cf044-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="cf044-128">Profilatura</span><span class="sxs-lookup"><span data-stu-id="cf044-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
