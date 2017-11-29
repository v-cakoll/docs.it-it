---
title: Interfacce di profilatura
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
caps.latest.revision: "31"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c0423f9c8b01c1289e1107c0c16c59968a6e2a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-interfaces"></a><span data-ttu-id="4f914-102">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="4f914-102">Profiling Interfaces</span></span>
<span data-ttu-id="4f914-103">Questa sezione descrive le interfacce non gestite che consentono di definire il profilo di un programma eseguito da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4f914-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f914-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4f914-104">In This Section</span></span>  
 [<span data-ttu-id="4f914-105">ICLRProfiling (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="4f914-106">Fornisce il [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) metodo, che consente a un profiler di connettersi a un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4f914-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="4f914-107">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="4f914-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="4f914-108">Consente al profiler di indicare a CLR di riferimenti ad assembly che verranno aggiunti nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="4f914-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="4f914-109">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4f914-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="4f914-110">Fornisce i metodi usati da CLR per indicare a un Code Profiler il verificarsi degli eventi ai quali il profiler ha effettuato la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="4f914-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="4f914-111">ICorProfilerCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="4f914-112">Estende l'interfaccia `ICorProfilerCallback` con callback supportati in .NET Framework 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="4f914-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="4f914-113">ICorProfilerCallback3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="4f914-114">Fornisce metodi di callback usati da CLR per comunicare informazioni sullo stato di connessione e disconnessione al profiler.</span><span class="sxs-lookup"><span data-stu-id="4f914-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="4f914-115">ICorProfilerCallback4 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="4f914-116">Fornisce metodi di callback usati da CLR per comunicare informazioni al profiler.</span><span class="sxs-lookup"><span data-stu-id="4f914-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="4f914-117">ICorProfilerCallback5 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="4f914-118">Fornisce un metodo che identifica la chiusura transitiva di oggetti a cui fanno riferimento le radici di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f914-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="4f914-119">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="4f914-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="4f914-120">Fornisce un metodo di callback usato da CLR per indicare a un profiler che un assembly è in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="4f914-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="4f914-121">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="4f914-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="4f914-122">Fornisce un metodo di callback che usa common language runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="4f914-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
 [<span data-ttu-id="4f914-123">ICorProfilerFunctionControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-123">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="4f914-124">Fornisce metodi che consentono a un Code Profiler di comunicare con CLR per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="4f914-124">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="4f914-125">ICorProfilerFunctionEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-125">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="4f914-126">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in CLR.</span><span class="sxs-lookup"><span data-stu-id="4f914-126">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="4f914-127">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="4f914-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="4f914-128">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="4f914-128">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="4f914-129">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="4f914-129">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="4f914-130">Estende l'interfaccia `ICorProfilerInfo` con metodi supportati in .NET Framework 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="4f914-130">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="4f914-131">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-131">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="4f914-132">Estende l'interfaccia `ICorProfilerInfo2` con metodi supportati in [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="4f914-132">Extends the `ICorProfilerInfo2` interface with methods supported in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions.</span></span>  
  
 [<span data-ttu-id="4f914-133">ICorProfilerInfo4 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-133">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="4f914-134">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="4f914-134">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="4f914-135">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="4f914-135">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="4f914-136">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi.</span><span class="sxs-lookup"><span data-stu-id="4f914-136">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="4f914-137">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="4f914-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="4f914-138">Fornisce un enumeratore per tutti i metodi che appartengono a un determinato modulo NGen e che vengono impostati come inline nel corpo di un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="4f914-138">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="4f914-139">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="4f914-139">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="4f914-140">Fornisce un metodo per applicare appena definito i metadati per un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="4f914-140">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="4f914-141">ICorProfilerModuleEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-141">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="4f914-142">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.</span><span class="sxs-lookup"><span data-stu-id="4f914-142">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="4f914-143">ICorProfilerObjectEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-143">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="4f914-144">Fornisce metodi per scorrere in sequenza una raccolta di oggetti bloccati generati da [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="4f914-144">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="4f914-145">ICorProfilerThreadEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-145">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="4f914-146">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di thread in CLR.</span><span class="sxs-lookup"><span data-stu-id="4f914-146">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="4f914-147">IMethodMalloc (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f914-147">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="4f914-148">Fornisce il [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) per allocare memoria per un nuovo corpo della funzione Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4f914-148">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4f914-149">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4f914-149">Related Sections</span></span>  
 [<span data-ttu-id="4f914-150">Panoramica della profilatura</span><span class="sxs-lookup"><span data-stu-id="4f914-150">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="4f914-151">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="4f914-151">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="4f914-152">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="4f914-152">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="4f914-153">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="4f914-153">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
