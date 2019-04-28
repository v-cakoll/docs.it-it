---
title: Interfacce di profilatura
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 059fadc5607e76b871083682136fda542ae9bacf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758197"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="abb80-102">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="abb80-102">Profiling Interfaces</span></span>
<span data-ttu-id="abb80-103">Questa sezione descrive le interfacce non gestite che consentono di definire il profilo di un programma eseguito da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="abb80-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abb80-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="abb80-104">In This Section</span></span>  
 [<span data-ttu-id="abb80-105">Interfaccia ICLRProfiling</span><span class="sxs-lookup"><span data-stu-id="abb80-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="abb80-106">Fornisce il [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) metodo, che consente a un profiler di connettersi a un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="abb80-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="abb80-107">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="abb80-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="abb80-108">Consente al profiler di indicare a CLR di riferimenti ad assembly che il profiler aggiungerà nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="abb80-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="abb80-109">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="abb80-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="abb80-110">Fornisce i metodi usati da CLR per indicare a un Code Profiler il verificarsi degli eventi ai quali il profiler ha effettuato la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="abb80-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="abb80-111">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="abb80-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="abb80-112">Estende l'interfaccia `ICorProfilerCallback` con callback supportati in .NET Framework 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="abb80-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="abb80-113">Interfaccia ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="abb80-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="abb80-114">Fornisce metodi di callback usati da CLR per comunicare informazioni sullo stato di connessione e disconnessione al profiler.</span><span class="sxs-lookup"><span data-stu-id="abb80-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="abb80-115">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="abb80-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="abb80-116">Fornisce metodi di callback usati da CLR per comunicare informazioni al profiler.</span><span class="sxs-lookup"><span data-stu-id="abb80-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="abb80-117">Interfaccia ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="abb80-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="abb80-118">Fornisce un metodo che identifica la chiusura transitiva di oggetti a cui fanno riferimento le radici di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="abb80-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="abb80-119">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="abb80-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="abb80-120">Fornisce un metodo di callback usato da CLR per indicare a un profiler che un assembly è in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="abb80-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="abb80-121">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="abb80-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="abb80-122">Fornisce un metodo di callback che usa common language runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="abb80-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="abb80-123">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="abb80-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="abb80-124">Fornisce metodi di callback che usa common language runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è iniziata e terminata.</span><span class="sxs-lookup"><span data-stu-id="abb80-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="abb80-125">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="abb80-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="abb80-126">Fornisce un metodo di callback che usa common language runtime per notificare al profiler che un metodo dinamico viene sottoposto a garbage raccolti e successivamente scaricata.</span><span class="sxs-lookup"><span data-stu-id="abb80-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="abb80-127">Interfaccia ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="abb80-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="abb80-128">Fornisce metodi che consentono a un Code Profiler di comunicare con CLR per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="abb80-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="abb80-129">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="abb80-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="abb80-130">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in CLR.</span><span class="sxs-lookup"><span data-stu-id="abb80-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="abb80-131">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="abb80-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="abb80-132">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="abb80-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="abb80-133">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="abb80-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="abb80-134">Estende l'interfaccia `ICorProfilerInfo` con metodi supportati in .NET Framework 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="abb80-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="abb80-135">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="abb80-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="abb80-136">Estende l'interfaccia `ICorProfilerInfo2` con metodi supportati in [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="abb80-136">Extends the `ICorProfilerInfo2` interface with methods supported in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions.</span></span>  
  
 [<span data-ttu-id="abb80-137">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="abb80-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="abb80-138">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="abb80-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="abb80-139">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="abb80-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="abb80-140">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi.</span><span class="sxs-lookup"><span data-stu-id="abb80-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="abb80-141">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="abb80-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="abb80-142">Fornisce un enumeratore per tutti i metodi che appartengono a un determinato modulo NGen e che vengono inserite nel corpo di un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="abb80-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="abb80-143">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="abb80-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="abb80-144">Fornisce un metodo per applicare appena definito i metadati per un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="abb80-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="abb80-145">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="abb80-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="abb80-146">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.</span><span class="sxs-lookup"><span data-stu-id="abb80-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="abb80-147">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="abb80-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="abb80-148">Fornisce metodi per eseguire l'iterazione sequenziale con una raccolta di oggetti bloccati generati da [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="abb80-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="abb80-149">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="abb80-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="abb80-150">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di thread in CLR.</span><span class="sxs-lookup"><span data-stu-id="abb80-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="abb80-151">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="abb80-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="abb80-152">Fornisce il [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) metodo per allocare memoria per un nuovo corpo di funzione Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="abb80-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="abb80-153">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="abb80-153">Related Sections</span></span>  
 [<span data-ttu-id="abb80-154">Panoramica della profilatura</span><span class="sxs-lookup"><span data-stu-id="abb80-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="abb80-155">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="abb80-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="abb80-156">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="abb80-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="abb80-157">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="abb80-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
