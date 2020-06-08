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
ms.openlocfilehash: 702c5f9f2bc08c824bdc0607741a6afd65a3e89b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497257"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="b6c77-102">Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="b6c77-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="b6c77-103">Ottiene l'oggetto `ClassID` di un tipo utilizzando il token di metadati specificato e i `ClassID` valori di qualsiasi argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="b6c77-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c77-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6c77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6c77-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6c77-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="b6c77-106">in ID del modulo in cui risiede il tipo.</span><span class="sxs-lookup"><span data-stu-id="b6c77-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="b6c77-107">in `mdTypeDef`Token di metadati che fa riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="b6c77-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="b6c77-108">in Numero di parametri di tipo per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="b6c77-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="b6c77-109">Questo valore deve essere zero per i tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="b6c77-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="b6c77-110">in Matrice di `ClassID` valori, ognuno dei quali è un argomento del tipo.</span><span class="sxs-lookup"><span data-stu-id="b6c77-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="b6c77-111">Il valore di `typeArgs` può essere null se `cTypeArgs` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="b6c77-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="b6c77-112">out Puntatore all'oggetto `ClassID` del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="b6c77-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6c77-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b6c77-113">Remarks</span></span>  
 <span data-ttu-id="b6c77-114">La chiamata al `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` anziché un `mdTypeDef` token di metadati può avere risultati imprevedibili; i chiamanti devono risolvere l'oggetto `mdTypeRef` in un oggetto `mdTypeDef` quando lo passano.</span><span class="sxs-lookup"><span data-stu-id="b6c77-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="b6c77-115">Se il tipo non è già caricato, la chiamata di attiverà il `GetClassFromTokenAndTypeArgs` caricamento, che è un'operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="b6c77-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="b6c77-116">Ad esempio, la chiamata di questo metodo durante il caricamento di moduli o altri tipi può causare un ciclo infinito, perché il runtime tenta di caricare elementi in modo circolare.</span><span class="sxs-lookup"><span data-stu-id="b6c77-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="b6c77-117">In generale, l'uso di `GetClassFromTokenAndTypeArgs` è sconsigliato.</span><span class="sxs-lookup"><span data-stu-id="b6c77-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="b6c77-118">Se i profiler sono interessati a eventi per un determinato tipo, devono archiviare `ModuleID` e `mdTypeDef` di quel tipo e usare [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un dato `ClassID` è quello del tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="b6c77-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c77-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6c77-119">Requirements</span></span>  
 <span data-ttu-id="b6c77-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6c77-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c77-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6c77-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6c77-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6c77-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6c77-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c77-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c77-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6c77-124">See also</span></span>

- [<span data-ttu-id="b6c77-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b6c77-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b6c77-126">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="b6c77-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
