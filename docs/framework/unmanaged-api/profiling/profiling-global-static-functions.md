---
title: Funzioni statiche globali di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 20ee2a9e045d839aa8ac043e035c438986b987ef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860866"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="d0bff-102">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="d0bff-102">Profiling Global Static Functions</span></span>
<span data-ttu-id="d0bff-103">Questa sezione descrive le funzioni API non gestite utilizzate dall'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="d0bff-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0bff-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d0bff-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="d0bff-105">Funzioni di profilatura .NET Framework versione 1</span><span class="sxs-lookup"><span data-stu-id="d0bff-105">.NET Framework version 1 Profiling Functions</span></span>  
 [<span data-ttu-id="d0bff-106">Funzione FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="d0bff-106">FunctionEnter Function</span></span>](functionenter-function.md)  
 <span data-ttu-id="d0bff-107">Notifica al profiler che il controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="d0bff-108">Deprecato nella .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d0bff-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="d0bff-109">Funzione FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="d0bff-109">FunctionLeave Function</span></span>](functionleave-function.md)  
 <span data-ttu-id="d0bff-110">Notifica al profiler che una funzione sta per tornare al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d0bff-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="d0bff-111">Deprecato nella .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d0bff-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="d0bff-112">Funzione FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="d0bff-112">FunctionTailcall Function</span></span>](functiontailcall-function.md)  
 <span data-ttu-id="d0bff-113">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="d0bff-114">Deprecato nella .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d0bff-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="d0bff-115">Funzioni di profilatura .NET Framework versione 2</span><span class="sxs-lookup"><span data-stu-id="d0bff-115">.NET Framework version 2 Profiling Functions</span></span>  
 [<span data-ttu-id="d0bff-116">Funzione FunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d0bff-116">FunctionIDMapper Function</span></span>](functionidmapper-function.md)  
 <span data-ttu-id="d0bff-117">Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da usare nei callback [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)e [FunctionTailcall2](functiontailcall2-function.md) per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="d0bff-118">Consente inoltre al profiler di indicare se si desidera ricevere callback per tale funzione</span><span class="sxs-lookup"><span data-stu-id="d0bff-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="d0bff-119">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="d0bff-119">FunctionEnter2 Function</span></span>](functionenter2-function.md)  
 <span data-ttu-id="d0bff-120">Notifica al profiler che il controllo viene passato a una funzione e fornisce informazioni sugli stack frame e sugli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="d0bff-121">Deprecato nell'.NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d0bff-121">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d0bff-122">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="d0bff-122">FunctionLeave2 Function</span></span>](functionleave2-function.md)  
 <span data-ttu-id="d0bff-123">Notifica al profiler che una funzione sta per tornare al chiamante e fornisce informazioni sull'stack frame e sul valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="d0bff-124">Deprecato nell'.NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d0bff-124">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d0bff-125">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="d0bff-125">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)  
 <span data-ttu-id="d0bff-126">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sul stack frame.</span><span class="sxs-lookup"><span data-stu-id="d0bff-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="d0bff-127">Deprecato nell'.NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d0bff-127">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d0bff-128">Funzione StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="d0bff-128">StackSnapshotCallback Function</span></span>](stacksnapshotcallback-function.md)  
 <span data-ttu-id="d0bff-129">Fornisce al profiler informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti nello stack durante un percorso stack, avviato dal metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d0bff-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="d0bff-130">Funzioni di profilatura .NET Framework versione 4</span><span class="sxs-lookup"><span data-stu-id="d0bff-130">.NET Framework version 4 Profiling Functions</span></span>  
 [<span data-ttu-id="d0bff-131">Funzione FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="d0bff-131">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)  
 <span data-ttu-id="d0bff-132">Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da usare nei callback [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="d0bff-133">Consente inoltre al profiler di indicare se si desidera ricevere callback per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="d0bff-134">`FunctionIDMapper2` estende la funzione [FunctionIDMapper](functionidmapper-function.md) con un parametro `clientData`, che i profiler possono usare per evitare ambiguità tra i Runtime.</span><span class="sxs-lookup"><span data-stu-id="d0bff-134">`FunctionIDMapper2` extends the [FunctionIDMapper](functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="d0bff-135">Funzione FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="d0bff-135">FunctionEnter3 Function</span></span>](functionenter3-function.md)  
 <span data-ttu-id="d0bff-136">Notifica al profiler che il controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="d0bff-137">Funzione FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0bff-137">FunctionEnter3WithInfo Function</span></span>](functionenter3withinfo-function.md)  
 <span data-ttu-id="d0bff-138">Notifica al profiler che il controllo viene passato a una funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare gli argomenti della funzione e del stack frame.</span><span class="sxs-lookup"><span data-stu-id="d0bff-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="d0bff-139">Funzione FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="d0bff-139">FunctionLeave3 Function</span></span>](functionleave3-function.md)  
 <span data-ttu-id="d0bff-140">Notifica al profiler che il controllo viene restituito da una funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="d0bff-141">Funzione FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0bff-141">FunctionLeave3WithInfo Function</span></span>](functionleave3withinfo-function.md)  
 <span data-ttu-id="d0bff-142">Notifica al profiler che il controllo viene restituito da una funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) per recuperare il stack frame e il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="d0bff-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="d0bff-143">Funzione FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="d0bff-143">FunctionTailcall3 Function</span></span>](functiontailcall3-function.md)  
 <span data-ttu-id="d0bff-144">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="d0bff-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="d0bff-145">Funzione FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0bff-145">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)  
 <span data-ttu-id="d0bff-146">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) per recuperare il stack frame.</span><span class="sxs-lookup"><span data-stu-id="d0bff-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d0bff-147">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d0bff-147">Related Sections</span></span>  
 [<span data-ttu-id="d0bff-148">Panoramica della profilatura</span><span class="sxs-lookup"><span data-stu-id="d0bff-148">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="d0bff-149">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="d0bff-149">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="d0bff-150">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="d0bff-150">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="d0bff-151">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="d0bff-151">Profiling Structures</span></span>](profiling-structures.md)
