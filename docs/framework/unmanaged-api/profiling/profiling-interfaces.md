---
title: Interfacce di profilatura
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: f073794b4fdf89f289b70fed9967ee37b5f4e133
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494033"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="c512b-102">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c512b-102">Profiling Interfaces</span></span>
<span data-ttu-id="c512b-103">Questa sezione descrive le interfacce non gestite che consentono di definire il profilo di un programma eseguito da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c512b-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c512b-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c512b-104">In This Section</span></span>  
 [<span data-ttu-id="c512b-105">Interfaccia ICLRProfiling</span><span class="sxs-lookup"><span data-stu-id="c512b-105">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="c512b-106">Fornisce il metodo [AttachProfiler](iclrprofiling-attachprofiler-method.md) , che consente a un profiler di connettersi a un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c512b-106">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="c512b-107">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="c512b-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="c512b-108">Consente al profiler di indicare a CLR i riferimenti ad assembly che saranno aggiunti dal profiler nel callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c512b-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="c512b-109">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c512b-109">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="c512b-110">Fornisce i metodi usati da CLR per indicare a un Code Profiler il verificarsi degli eventi ai quali il profiler ha effettuato la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="c512b-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="c512b-111">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="c512b-111">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="c512b-112">Estende l'interfaccia `ICorProfilerCallback` con callback supportati in .NET Framework 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c512b-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="c512b-113">Interfaccia ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="c512b-113">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="c512b-114">Fornisce metodi di callback usati da CLR per comunicare informazioni sullo stato di connessione e disconnessione al profiler.</span><span class="sxs-lookup"><span data-stu-id="c512b-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="c512b-115">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="c512b-115">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="c512b-116">Fornisce metodi di callback usati da CLR per comunicare informazioni al profiler.</span><span class="sxs-lookup"><span data-stu-id="c512b-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="c512b-117">Interfaccia ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="c512b-117">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="c512b-118">Fornisce un metodo che identifica la chiusura transitiva di oggetti a cui fanno riferimento le radici di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c512b-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="c512b-119">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="c512b-119">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="c512b-120">Fornisce un metodo di callback usato da CLR per indicare a un profiler che un assembly è in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="c512b-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="c512b-121">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="c512b-121">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="c512b-122">Fornisce un metodo di callback usato dal Common Language Runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c512b-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="c512b-123">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="c512b-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="c512b-124">Fornisce metodi di callback utilizzati dal Common Language Runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è stata avviata e completata.</span><span class="sxs-lookup"><span data-stu-id="c512b-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="c512b-125">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="c512b-125">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="c512b-126">Fornisce un metodo di callback utilizzato dal Common Language Runtime per notificare al profiler che un metodo dinamico viene sottoposta a Garbage Collection e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="c512b-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="c512b-127">Interfaccia ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="c512b-127">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="c512b-128">Fornisce metodi che consentono a un Code Profiler di comunicare con CLR per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="c512b-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="c512b-129">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="c512b-129">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="c512b-130">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in CLR.</span><span class="sxs-lookup"><span data-stu-id="c512b-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="c512b-131">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c512b-131">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="c512b-132">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="c512b-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="c512b-133">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="c512b-133">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="c512b-134">Estende l'interfaccia `ICorProfilerInfo` con metodi supportati in .NET Framework 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c512b-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="c512b-135">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="c512b-135">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="c512b-136">Estende l' `ICorProfilerInfo2` interfaccia con i metodi supportati in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c512b-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="c512b-137">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="c512b-137">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="c512b-138">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="c512b-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="c512b-139">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="c512b-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="c512b-140">Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi.</span><span class="sxs-lookup"><span data-stu-id="c512b-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="c512b-141">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="c512b-141">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="c512b-142">Fornisce un enumeratore per tutti i metodi che appartengono a un modulo NGen specificato e che sono inline nel corpo di un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="c512b-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="c512b-143">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="c512b-143">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="c512b-144">Fornisce un metodo per applicare i metadati appena definiti a un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="c512b-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="c512b-145">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="c512b-145">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="c512b-146">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.</span><span class="sxs-lookup"><span data-stu-id="c512b-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="c512b-147">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c512b-147">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="c512b-148">Fornisce metodi per scorrere in sequenza una raccolta di oggetti bloccati generati da [NGen. exe (Generatore di immagini native)](../../tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="c512b-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="c512b-149">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="c512b-149">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="c512b-150">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di thread in CLR.</span><span class="sxs-lookup"><span data-stu-id="c512b-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="c512b-151">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="c512b-151">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="c512b-152">Fornisce il metodo [Alloc](imethodmalloc-alloc-method.md) per allocare memoria per un nuovo corpo della funzione MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="c512b-152">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c512b-153">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c512b-153">Related Sections</span></span>  
 [<span data-ttu-id="c512b-154">Panoramica della profilatura</span><span class="sxs-lookup"><span data-stu-id="c512b-154">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="c512b-155">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="c512b-155">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="c512b-156">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="c512b-156">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="c512b-157">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="c512b-157">Profiling Structures</span></span>](profiling-structures.md)
