---
title: Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04be252092732296354cfec102cf8fe648ed2dd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456638"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="95b0b-102">Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="95b0b-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="95b0b-103">Ottiene il `ClassID` di un tipo utilizzando il token di metadati specificati e `ClassID` valori di qualsiasi tipo di argomenti.</span><span class="sxs-lookup"><span data-stu-id="95b0b-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95b0b-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95b0b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95b0b-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="95b0b-106">[in] L'ID del modulo in cui risiede il tipo.</span><span class="sxs-lookup"><span data-stu-id="95b0b-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="95b0b-107">[in] Un `mdTypeDef` token di metadati che fa riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="95b0b-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="95b0b-108">[in] Il numero di parametri di tipo per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="95b0b-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="95b0b-109">Questo valore deve essere zero per i tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="95b0b-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="95b0b-110">[in] Matrice di `ClassID` valori, ognuno dei quali è un argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="95b0b-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="95b0b-111">Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="95b0b-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="95b0b-112">[out] Un puntatore al `ClassID` del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="95b0b-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95b0b-113">Note</span><span class="sxs-lookup"><span data-stu-id="95b0b-113">Remarks</span></span>  
 <span data-ttu-id="95b0b-114">La chiamata di `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` anziché un `mdTypeDef` token di metadati possono produrre risultati imprevisti, i chiamanti devono risolvere il `mdTypeRef` per un `mdTypeDef` quando viene passato.</span><span class="sxs-lookup"><span data-stu-id="95b0b-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="95b0b-115">Se il tipo non è già stato caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="95b0b-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="95b0b-116">Ad esempio, questo metodo durante il caricamento dei moduli o altri tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="95b0b-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="95b0b-117">In generale, utilizzare `GetClassFromTokenAndTypeArgs` è sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="95b0b-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="95b0b-118">Se i profiler sono interessati agli eventi per un determinato tipo, archiviano il `ModuleID` e `mdTypeDef` di tale tipo e utilizzare [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="95b0b-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95b0b-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95b0b-119">Requirements</span></span>  
 <span data-ttu-id="95b0b-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95b0b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95b0b-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95b0b-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95b0b-122">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="95b0b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95b0b-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95b0b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b0b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95b0b-124">See Also</span></span>  
 [<span data-ttu-id="95b0b-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="95b0b-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="95b0b-126">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="95b0b-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
