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
ms.openlocfilehash: a88a6c19a5c8b45576dd6f632adf70f7ec2eed55
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751870"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="f1482-102">Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="f1482-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="f1482-103">Ottiene il `ClassID` di un tipo usando il token di metadati specificati e il `ClassID` valori di qualsiasi tipo di argomenti.</span><span class="sxs-lookup"><span data-stu-id="f1482-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1482-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1482-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1482-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1482-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="f1482-106">[in] L'ID del modulo in cui si trova il tipo.</span><span class="sxs-lookup"><span data-stu-id="f1482-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="f1482-107">[in] Un `mdTypeDef` token di metadati che fa riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="f1482-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="f1482-108">[in] Il numero di parametri di tipo per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="f1482-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="f1482-109">Questo valore deve essere zero per i tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="f1482-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="f1482-110">[in] Matrice di `ClassID` valori, ognuno dei quali è un argomento del tipo.</span><span class="sxs-lookup"><span data-stu-id="f1482-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="f1482-111">Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="f1482-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="f1482-112">[out] Un puntatore al `ClassID` del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="f1482-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1482-113">Note</span><span class="sxs-lookup"><span data-stu-id="f1482-113">Remarks</span></span>  
 <span data-ttu-id="f1482-114">Chiama il `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` invece di un `mdTypeDef` token di metadati possono produrre risultati imprevisti; i chiamanti devono risolvere il `mdTypeRef` a un `mdTypeDef` quando viene passato.</span><span class="sxs-lookup"><span data-stu-id="f1482-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="f1482-115">Se il tipo non è già stato caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, che è un'operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="f1482-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="f1482-116">Ad esempio, si chiama questo metodo durante il caricamento dei moduli o altri tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare le cose.</span><span class="sxs-lookup"><span data-stu-id="f1482-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="f1482-117">In generale, usare di `GetClassFromTokenAndTypeArgs` è sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="f1482-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="f1482-118">Se profiler sono interessati agli eventi per un determinato tipo, è consigliabile archiviare il `ModuleID` e `mdTypeDef` di quel tipo e usare [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="f1482-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1482-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1482-119">Requirements</span></span>  
 <span data-ttu-id="f1482-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1482-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1482-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1482-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1482-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1482-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1482-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1482-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1482-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1482-124">See also</span></span>

- [<span data-ttu-id="f1482-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f1482-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="f1482-126">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="f1482-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
