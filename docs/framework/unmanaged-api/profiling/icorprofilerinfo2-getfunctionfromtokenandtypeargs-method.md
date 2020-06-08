---
title: Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 7f1276e1adeece086ca7b6791eb6e870faf4d010
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502873"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="c5a2f-102">Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="c5a2f-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="c5a2f-103">Ottiene l'oggetto `FunctionID` di una funzione utilizzando il token di metadati specificato, la classe contenente e `ClassID` i valori di qualsiasi argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a2f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5a2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5a2f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5a2f-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c5a2f-106">in ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="c5a2f-107">in `mdMethodDef`Token di metadati che fa riferimento alla funzione.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="c5a2f-108">in ID della classe che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="c5a2f-109">in Numero di parametri di tipo per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="c5a2f-110">Questo valore deve essere zero per le funzioni non generiche.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="c5a2f-111">in Matrice di `ClassID` valori, ognuno dei quali è un argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="c5a2f-112">Il valore di `typeArgs` può essere null se `cTypeArgs` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="c5a2f-113">out Puntatore alla `FunctionID` della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5a2f-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c5a2f-114">Remarks</span></span>  
 <span data-ttu-id="c5a2f-115">La chiamata al `GetFunctionFromTokenAndTypeArgs` metodo con i `mdMethodRef` metadati anziché un `mdMethodDef` token di metadati può avere risultati imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="c5a2f-116">I chiamanti devono risolvere `mdMethodRef` in un oggetto `mdMethodDef` quando lo passano.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="c5a2f-117">Se la funzione non è già caricata, la chiamata a provocherà il `GetFunctionFromTokenAndTypeArgs` caricamento, che è un'operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="c5a2f-118">Ad esempio, la chiamata di questo metodo durante il caricamento di moduli o tipi può causare un ciclo infinito perché il runtime tenta di caricare elementi in modo circolare.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="c5a2f-119">In generale, l'uso di `GetFunctionFromTokenAndTypeArgs` è sconsigliato.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="c5a2f-120">Se i profiler sono interessati agli eventi per una funzione specifica, devono archiviare `ModuleID` e `mdMethodDef` della funzione e usare [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) per verificare se un dato `FunctionID` è quello della funzione desiderata.</span><span class="sxs-lookup"><span data-stu-id="c5a2f-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5a2f-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5a2f-121">Requirements</span></span>  
 <span data-ttu-id="c5a2f-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5a2f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5a2f-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5a2f-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5a2f-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5a2f-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5a2f-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5a2f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a2f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5a2f-126">See also</span></span>

- [<span data-ttu-id="c5a2f-127">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c5a2f-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c5a2f-128">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="c5a2f-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
