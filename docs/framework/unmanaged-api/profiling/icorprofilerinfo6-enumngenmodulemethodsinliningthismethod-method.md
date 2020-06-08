---
title: Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 8ed3f305deceacb976aeff994db1588f9e1ce1fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495528"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="eab15-102">Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="eab15-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="eab15-103">Restituisce un enumeratore per tutti i metodi definiti in un determinato modulo NGen e incorporano un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="eab15-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="eab15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eab15-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="eab15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eab15-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="eab15-106">in Identificatore di un modulo NGen.</span><span class="sxs-lookup"><span data-stu-id="eab15-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="eab15-107">in Identificatore di un modulo che definisce `inlineeMethodId` .</span><span class="sxs-lookup"><span data-stu-id="eab15-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="eab15-108">Per ulteriori informazioni, vedere le sezione Note.</span><span class="sxs-lookup"><span data-stu-id="eab15-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="eab15-109">in Identificatore di un metodo inline.</span><span class="sxs-lookup"><span data-stu-id="eab15-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="eab15-110">Per ulteriori informazioni, vedere le sezione Note.</span><span class="sxs-lookup"><span data-stu-id="eab15-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="eab15-111">out Flag che indica se `ppEnum` contiene tutti i metodi che incorporano un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="eab15-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="eab15-112">Per ulteriori informazioni, vedere le sezione Note.</span><span class="sxs-lookup"><span data-stu-id="eab15-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="eab15-113">out Puntatore all'indirizzo di un enumeratore</span><span class="sxs-lookup"><span data-stu-id="eab15-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="eab15-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eab15-114">Remarks</span></span>

<span data-ttu-id="eab15-115">`inlineeModuleId``inlineeMethodId`insieme formano l'identificatore completo per il metodo che potrebbe essere inline.</span><span class="sxs-lookup"><span data-stu-id="eab15-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="eab15-116">Si supponga, ad esempio, che il modulo definisca `A` un metodo `Simple.Add` :</span><span class="sxs-lookup"><span data-stu-id="eab15-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="eab15-117">e il modulo B definisce `Fancy.AddTwice` :</span><span class="sxs-lookup"><span data-stu-id="eab15-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="eab15-118">Si supponga inoltre che `Fancy.AddTwice` inline la chiamata a `SimpleAdd` .</span><span class="sxs-lookup"><span data-stu-id="eab15-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="eab15-119">Un profiler può utilizzare questo enumeratore per trovare tutti i metodi definiti nel modulo B che inline `Simple.Add` e il risultato verrebbe enumerato `AddTwice` .</span><span class="sxs-lookup"><span data-stu-id="eab15-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="eab15-120">`inlineeModuleId`è l'identificatore del modulo `A` e `inlineeMethodId` è l'identificatore di `Simple.Add(int a, int b)` .</span><span class="sxs-lookup"><span data-stu-id="eab15-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="eab15-121">Se `incompleteData` è true dopo la restituzione della funzione, l'enumeratore non contiene tutti i metodi che incorporano un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="eab15-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="eab15-122">Questo problema può verificarsi quando una o più dipendenze dirette o indirette del modulo Inliners non sono ancora state caricate.</span><span class="sxs-lookup"><span data-stu-id="eab15-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="eab15-123">Se un profiler richiede dati accurati, è consigliabile riprovare più tardi quando vengono caricati più moduli, preferibilmente a ogni caricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="eab15-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="eab15-124">Il `EnumNgenModuleMethodsInliningThisMethod` metodo può essere usato per aggirare le limitazioni sull'incorporamento di ReJIT.</span><span class="sxs-lookup"><span data-stu-id="eab15-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="eab15-125">ReJIT consente a un profiler di modificare l'implementazione di un metodo e quindi di crearne il nuovo codice in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="eab15-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="eab15-126">Ad esempio, è possibile modificare `Simple.Add` come segue:</span><span class="sxs-lookup"><span data-stu-id="eab15-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="eab15-127">Tuttavia `Fancy.AddTwice` , poiché è già stato inline `Simple.Add` , continua a avere lo stesso comportamento che precede.</span><span class="sxs-lookup"><span data-stu-id="eab15-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="eab15-128">Per ovviare a questa limitazione, il chiamante deve eseguire la ricerca di tutti i metodi in tutti i moduli che inline `Simple.Add` e utilizzano `ICorProfilerInfo5::RequestRejit` su ognuno di questi metodi.</span><span class="sxs-lookup"><span data-stu-id="eab15-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="eab15-129">Quando i metodi vengono nuovamente compilati, avranno il nuovo comportamento di `Simple.Add` anziché il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="eab15-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="eab15-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eab15-130">Requirements</span></span>

<span data-ttu-id="eab15-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eab15-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="eab15-132">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eab15-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="eab15-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eab15-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="eab15-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eab15-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="eab15-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eab15-135">See also</span></span>

- [<span data-ttu-id="eab15-136">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="eab15-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
