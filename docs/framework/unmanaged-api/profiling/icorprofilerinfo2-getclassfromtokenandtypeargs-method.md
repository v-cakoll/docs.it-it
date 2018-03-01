---
title: Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
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
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a459f8e9ec6d63dc42d6a0a8f752c129d278524
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="ab1e6-102">Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="ab1e6-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="ab1e6-103">Ottiene il `ClassID` di un tipo utilizzando il token di metadati specificati e `ClassID` valori di qualsiasi tipo di argomenti.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab1e6-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab1e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab1e6-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="ab1e6-106">[in] L'ID del modulo in cui risiede il tipo.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="ab1e6-107">[in] Un `mdTypeDef` token di metadati che fa riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="ab1e6-108">[in] Il numero di parametri di tipo per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="ab1e6-109">Questo valore deve essere zero per i tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="ab1e6-110">[in] Matrice di `ClassID` valori, ognuno dei quali è un argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="ab1e6-111">Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="ab1e6-112">[out] Un puntatore al `ClassID` del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab1e6-113">Note</span><span class="sxs-lookup"><span data-stu-id="ab1e6-113">Remarks</span></span>  
 <span data-ttu-id="ab1e6-114">La chiamata di `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` anziché un `mdTypeDef` token di metadati possono produrre risultati imprevisti, i chiamanti devono risolvere il `mdTypeRef` per un `mdTypeDef` quando viene passato.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="ab1e6-115">Se il tipo non è già stato caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="ab1e6-116">Ad esempio, questo metodo durante il caricamento dei moduli o altri tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="ab1e6-117">In generale, utilizzare `GetClassFromTokenAndTypeArgs` è sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="ab1e6-118">Se i profiler sono interessati agli eventi per un determinato tipo, archiviano il `ModuleID` e `mdTypeDef` di tale tipo e utilizzare [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="ab1e6-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab1e6-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab1e6-119">Requirements</span></span>  
 <span data-ttu-id="ab1e6-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab1e6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab1e6-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab1e6-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab1e6-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab1e6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab1e6-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab1e6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1e6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab1e6-124">See Also</span></span>  
 [<span data-ttu-id="ab1e6-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ab1e6-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="ab1e6-126">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="ab1e6-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
