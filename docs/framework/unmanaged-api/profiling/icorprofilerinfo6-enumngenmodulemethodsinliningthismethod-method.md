---
title: Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67ae413ae8944757fc90bcde752b9a5fe53cc68f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948525"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="af092-102">Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="af092-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="af092-103">Restituisce un enumeratore per tutti i metodi definiti in un determinato modulo NGen e inline un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="af092-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="af092-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af092-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="af092-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af092-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="af092-106">[in] L'identificatore di un modulo NGen.</span><span class="sxs-lookup"><span data-stu-id="af092-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="af092-107">[in] L'identificatore di un modulo che definisce `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="af092-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="af092-108">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="af092-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="af092-109">[in] L'identificatore di un metodo di implementazione inline.</span><span class="sxs-lookup"><span data-stu-id="af092-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="af092-110">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="af092-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="af092-111">[out] Un flag che indica se `ppEnum` contiene tutti i metodi l'incorporamento di un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="af092-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="af092-112">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="af092-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="af092-113">[out] Un puntatore all'indirizzo di un enumeratore</span><span class="sxs-lookup"><span data-stu-id="af092-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="af092-114">Note</span><span class="sxs-lookup"><span data-stu-id="af092-114">Remarks</span></span>

<span data-ttu-id="af092-115">`inlineeModuleId` e `inlineeMethodId` insieme formano l'identificatore completo per il metodo che può essere impostato come inline.</span><span class="sxs-lookup"><span data-stu-id="af092-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="af092-116">Si supponga ad esempio modulo `A` definisce un metodo `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="af092-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="af092-117">e definisce il modulo B `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="af092-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="af092-118">Si supponga anche che `Fancy.AddTwice` inlines la chiamata a `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="af092-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="af092-119">Un profiler può usare l'enumeratore per trovare tutti i metodi definiti nel modulo B che inline `Simple.Add`, e il risultato sarebbe enumerare `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="af092-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="af092-120">`inlineeModuleId` è l'identificatore del modulo `A`, e `inlineeMethodId` è l'identificatore di `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="af092-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="af092-121">Se `incompleteData` è true dopo la funzione termina, l'enumeratore non contiene tutti i metodi inline un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="af092-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="af092-122">Questa situazione può verificarsi quando uno o più dipendenze dirette o indirette di inliners modulo non è stato ancora caricate.</span><span class="sxs-lookup"><span data-stu-id="af092-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="af092-123">Se un profiler deve dati accurati, provare a ripetere in un secondo momento quando vengono caricati più moduli, preferibilmente ogni caricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="af092-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="af092-124">Il `EnumNgenModuleMethodsInliningThisMethod` metodo può essere usato per aggirare le limitazioni nell'incorporamento per ReJIT.</span><span class="sxs-lookup"><span data-stu-id="af092-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="af092-125">ReJIT consente a un profiler di modificare l'implementazione di un metodo e quindi creare di nuovo codice appositamente in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="af092-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="af092-126">Ad esempio, è possibile modificare `Simple.Add` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="af092-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="af092-127">Tuttavia poiché `Fancy.AddTwice` ha già impostato come inline `Simple.Add`, continua ad avere lo stesso comportamento come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="af092-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="af092-128">Per aggirare questa limitazione, il chiamante dispone cercare tutti i metodi in tutti i moduli inline `Simple.Add` e usare `ICorProfilerInfo5::RequestRejit` in ognuno di questi metodi.</span><span class="sxs-lookup"><span data-stu-id="af092-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="af092-129">Quando i metodi sono nuovamente compilati, hanno il nuovo comportamento di `Simple.Add` anziché il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="af092-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="af092-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af092-130">Requirements</span></span>

<span data-ttu-id="af092-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af092-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="af092-132">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="af092-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="af092-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af092-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="af092-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af092-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="af092-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af092-135">See also</span></span>

- [<span data-ttu-id="af092-136">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="af092-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)