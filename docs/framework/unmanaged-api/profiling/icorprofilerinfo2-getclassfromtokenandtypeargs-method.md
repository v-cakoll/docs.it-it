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
ms.openlocfilehash: e0663ff122397ba639a0a219e513be2f3f0cbbef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862763"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="1cc7e-102">Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="1cc7e-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="1cc7e-103">Ottiene l'`ClassID` di un tipo utilizzando il token di metadati specificato e i valori di `ClassID` di qualsiasi argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cc7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cc7e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1cc7e-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="1cc7e-106">in ID del modulo in cui risiede il tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="1cc7e-107">in Token di metadati `mdTypeDef` che fa riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="1cc7e-108">in Numero di parametri di tipo per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="1cc7e-109">Questo valore deve essere zero per i tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="1cc7e-110">in Matrice di valori di `ClassID`, ognuno dei quali è un argomento del tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="1cc7e-111">Se `cTypeArgs` è impostato su zero, il valore di `typeArgs` può essere NULL.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="1cc7e-112">out Puntatore al `ClassID` del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cc7e-113">Note</span><span class="sxs-lookup"><span data-stu-id="1cc7e-113">Remarks</span></span>  
 <span data-ttu-id="1cc7e-114">La chiamata al metodo `GetClassFromTokenAndTypeArgs` con un `mdTypeRef` anziché un token di metadati `mdTypeDef` può avere risultati imprevedibili. i chiamanti devono risolvere il `mdTypeRef` in un `mdTypeDef` quando viene passato.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="1cc7e-115">Se il tipo non è già caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, che è un'operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="1cc7e-116">Ad esempio, la chiamata di questo metodo durante il caricamento di moduli o altri tipi può causare un ciclo infinito, perché il runtime tenta di caricare elementi in modo circolare.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="1cc7e-117">In generale, l'uso di `GetClassFromTokenAndTypeArgs` è sconsigliato.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="1cc7e-118">Se i profiler sono interessati a eventi per un determinato tipo, devono archiviare il `ModuleID` e `mdTypeDef` di quel tipo e usare [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="1cc7e-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc7e-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1cc7e-119">Requirements</span></span>  
 <span data-ttu-id="1cc7e-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cc7e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc7e-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1cc7e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1cc7e-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cc7e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cc7e-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cc7e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc7e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cc7e-124">See also</span></span>

- [<span data-ttu-id="1cc7e-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1cc7e-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1cc7e-126">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="1cc7e-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
