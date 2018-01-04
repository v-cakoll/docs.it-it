---
title: Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b225b87eab6e65055618c8b6659459637e8a01be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="308b2-102">Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="308b2-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="308b2-103">Ottiene il `FunctionID` di una funzione con il token di metadati specificato, contenente (classe), e `ClassID` valori di qualsiasi tipo di argomenti.</span><span class="sxs-lookup"><span data-stu-id="308b2-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="308b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="308b2-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="308b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="308b2-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="308b2-106">[in] L'ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="308b2-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="308b2-107">[in] Un `mdMethodDef` token di metadati che fa riferimento alla funzione.</span><span class="sxs-lookup"><span data-stu-id="308b2-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="308b2-108">[in] ID della classe contenitore della funzione.</span><span class="sxs-lookup"><span data-stu-id="308b2-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="308b2-109">[in] Il numero di parametri di tipo per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="308b2-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="308b2-110">Questo valore deve essere zero per le funzioni non generica.</span><span class="sxs-lookup"><span data-stu-id="308b2-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="308b2-111">[in] Matrice di `ClassID` valori, ognuno dei quali è un argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="308b2-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="308b2-112">Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="308b2-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="308b2-113">[out] Un puntatore al `FunctionID` della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="308b2-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="308b2-114">Note</span><span class="sxs-lookup"><span data-stu-id="308b2-114">Remarks</span></span>  
 <span data-ttu-id="308b2-115">La chiamata di `GetFunctionFromTokenAndTypeArgs` metodo con un `mdMethodRef` metadati anziché un `mdMethodDef` token di metadati possono produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="308b2-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="308b2-116">I chiamanti devono risolvere il `mdMethodRef` per un `mdMethodDef` momento del passaggio.</span><span class="sxs-lookup"><span data-stu-id="308b2-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="308b2-117">Se la funzione non è già stata caricata, la chiamata `GetFunctionFromTokenAndTypeArgs` causerà luogo al caricamento, operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="308b2-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="308b2-118">Ad esempio, questo metodo durante il caricamento di moduli o tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="308b2-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="308b2-119">In generale, utilizzare `GetFunctionFromTokenAndTypeArgs` è sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="308b2-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="308b2-120">Se i profiler sono interessati agli eventi per una determinata funzione, devono archiviare il `ModuleID` e `mdMethodDef` di tale funzione e utilizzare [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) per verificare se un determinato `FunctionID` è quello della funzione desiderata.</span><span class="sxs-lookup"><span data-stu-id="308b2-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="308b2-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="308b2-121">Requirements</span></span>  
 <span data-ttu-id="308b2-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="308b2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="308b2-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="308b2-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="308b2-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="308b2-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="308b2-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="308b2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="308b2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="308b2-126">See Also</span></span>  
 [<span data-ttu-id="308b2-127">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="308b2-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="308b2-128">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="308b2-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
