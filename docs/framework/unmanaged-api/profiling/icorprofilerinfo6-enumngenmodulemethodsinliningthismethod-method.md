---
title: Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cf0bccebbfe5620ef329cc8c6f72582a7afe85a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="a94ff-102">Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="a94ff-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>
<span data-ttu-id="a94ff-103">[Supportato in .NET Framework 4.6 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="a94ff-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="a94ff-104">Restituisce un enumeratore per tutti i metodi definiti in un modulo NGen specificato e un determinato metodo inline.</span><span class="sxs-lookup"><span data-stu-id="a94ff-104">Returns an enumerator to all the methods that          are defined in  a given NGen module and          inline a given method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a94ff-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a94ff-105">Syntax</span></span>  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a94ff-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a94ff-106">Parameters</span></span>  
 `inlinersModuleId`  
 <span data-ttu-id="a94ff-107">[in] L'identificatore di un modulo NGen.</span><span class="sxs-lookup"><span data-stu-id="a94ff-107">[in] The identifier of an NGen module.</span></span>  
  
 `inlineeModuleId`  
 <span data-ttu-id="a94ff-108">[in] L'identificatore di un modulo che definisce `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="a94ff-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="a94ff-109">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="a94ff-109">See the Remarks section for more information.</span></span>  
  
 `inlineeMethodId`  
 <span data-ttu-id="a94ff-110">[in] L'identificatore di un metodo inline.</span><span class="sxs-lookup"><span data-stu-id="a94ff-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="a94ff-111">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="a94ff-111">See the Remarks section for more information.</span></span>  
  
 `incompleteData`  
 <span data-ttu-id="a94ff-112">[out] Un flag che indica se `ppEnum` contiene tutti i metodi di incorporamento di un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="a94ff-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="a94ff-113">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="a94ff-113">See the Remarks section for more information.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="a94ff-114">[out] Un puntatore all'indirizzo di un enumeratore</span><span class="sxs-lookup"><span data-stu-id="a94ff-114">[out] A pointer to the address of an enumerator</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a94ff-115">Note</span><span class="sxs-lookup"><span data-stu-id="a94ff-115">Remarks</span></span>  
 <span data-ttu-id="a94ff-116">`inlineeModuleId`e `inlineeMethodId` insieme formano l'identificatore completo per il metodo che può essere resa inline.</span><span class="sxs-lookup"><span data-stu-id="a94ff-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="a94ff-117">Si supponga ad esempio modulo `A` definisce un metodo `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="a94ff-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 <span data-ttu-id="a94ff-118">modulo Bdefines e `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="a94ff-118">and module Bdefines `Fancy.AddTwice`:</span></span>  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 <span data-ttu-id="a94ff-119">Si supponga inoltre che `Fancy.AddTwice` incorpora la chiamata a `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="a94ff-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="a94ff-120">Un profiler potrebbe utilizzare l'enumeratore per trovare tutti i metodi definiti nel modulo B quali inline `Simple.Add`, e il risultato sarebbe enumerare `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="a94ff-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="a94ff-121">`inlineeModuleId`è l'identificatore del modulo `A`, e `inlineeeMethodId` è l'identificatore di `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="a94ff-121">`inlineeModuleId` is the identifier of module `A`,   and `inlineeeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>  
  
 <span data-ttu-id="a94ff-122">Se `incompleteData` è true, dopo la funzione restituisce un risultato, l'enumeratore non contiene tutti i metodi inline un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="a94ff-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="a94ff-123">Questa situazione può verificarsi quando uno o più dipendenze dirette o indirette di inliners modulo non è stato ancora caricate.</span><span class="sxs-lookup"><span data-stu-id="a94ff-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="a94ff-124">Se un profiler dati accurati, deve riprovare in seguito quando vengono caricati altri moduli, preferibilmente in ogni caricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="a94ff-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>  
  
 <span data-ttu-id="a94ff-125">Il `EnumNgenModuleMethodsInliningThisMethod` metodo può essere utilizzato per aggirare le limitazioni in inline per ReJIT.</span><span class="sxs-lookup"><span data-stu-id="a94ff-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="a94ff-126">ReJIT consente a un profiler di modificare l'implementazione di un metodo e quindi creare di nuovo codice per tale in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="a94ff-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="a94ff-127">Ad esempio, è possibile modificare `Simple.Add` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a94ff-127">For example, we could change `Simple.Add` as follows:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 <span data-ttu-id="a94ff-128">Tuttavia poiché `Fancy.AddTwice` ha già resa inline `Simple.Add`, continua ad avere lo stesso comportamento come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a94ff-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="a94ff-129">Per aggirare questa limitazione, il chiamante dispone cercare tutti i metodi in tutti i moduli che inline `Simple.Add` e utilizzare `ICorProfilerInfo5::RequestRejit` in ognuno di questi metodi.</span><span class="sxs-lookup"><span data-stu-id="a94ff-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="a94ff-130">Quando i metodi sono ricompilati, avranno il nuovo comportamento di `Simple.Add` anziché il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="a94ff-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a94ff-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a94ff-131">Requirements</span></span>  
 <span data-ttu-id="a94ff-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a94ff-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a94ff-133">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a94ff-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a94ff-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a94ff-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a94ff-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a94ff-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94ff-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a94ff-136">See Also</span></span>  
 [<span data-ttu-id="a94ff-137">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="a94ff-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
