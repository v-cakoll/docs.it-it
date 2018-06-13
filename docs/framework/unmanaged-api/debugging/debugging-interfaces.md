---
title: Interfacce di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 991e333c53101a2be2a8a19d3960c3d0879619be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409932"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="ac6a8-102">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ac6a8-102">Debugging Interfaces</span></span>
<span data-ttu-id="ac6a8-103">Questa sezione descrive le interfacce non gestite che gestiscono il debug di un programma in esecuzione in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac6a8-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ac6a8-104">In This Section</span></span>  
 [<span data-ttu-id="ac6a8-105">Interfaccia ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="ac6a8-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="ac6a8-106">Fornisce un metodo per l'enumerazione delle aree di memoria specificate dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="ac6a8-107">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="ac6a8-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="ac6a8-108">Fornisce un metodo di callback in modo che `EnumMemoryRegions` segnali al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="ac6a8-109">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="ac6a8-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="ac6a8-110">Fornisce metodi per l'interazione con un processo di Common Language Runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="ac6a8-111">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="ac6a8-112">Sottoclasse di `ICLRDataTarget` usata dal livello dei servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="ac6a8-113">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="ac6a8-114">Una sottoclasse di [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) che consente di accedere alle informazioni sulle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="ac6a8-115">Interfaccia ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="ac6a8-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="ac6a8-116">Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="ac6a8-117">Interfaccia ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="ac6a8-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="ac6a8-118">Include il [metodo ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) metodo, che ottiene un provider di librerie di interfaccia di callback che consente a common language runtime librerie di debug specifiche della versione di individuare e caricare su richiesta.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="ac6a8-119">Interfaccia ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="ac6a8-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="ac6a8-120">Interfaccia usata dal livello dei servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="ac6a8-121">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ac6a8-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="ac6a8-122">Fornisce metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni nell'ambiente Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="ac6a8-123">Interfaccia1 ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="ac6a8-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="ac6a8-124">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="ac6a8-125">Interfaccia1 ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="ac6a8-126">Fornisce metodi che consentono di usare matrici, puntatori, puntatori a funzione e tipi ByRef.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="ac6a8-127">Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="ac6a8-128">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="ac6a8-129">Fornisce metodi che consentono di lavorare con i tipi [!INCLUDE[wrt](../../../../includes/wrt-md.md)] in un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="ac6a8-130">Questa interfaccia è un'estensione delle interfacce `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="ac6a8-131">Interfaccia ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="ac6a8-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="ac6a8-132">Estende logicamente il [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interfaccia da ottenere un oggetto gestito da un COM callable wrapper.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="ac6a8-133">Interfaccia1 ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="ac6a8-134">Fornisce un metodo che restituisce un numero specificato di valori di `ICorDebugAppDomain` a partire dalla posizione successiva nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="ac6a8-135">Interfaccia1 ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="ac6a8-136">Sottoclasse di `ICorDebugHeapValue` che rappresenta una matrice unidimensionale o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="ac6a8-137">Interfaccia1 ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="ac6a8-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="ac6a8-138">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="ac6a8-139">Interfaccia1 ICorDebugAssembly2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="ac6a8-140">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-140">Represents an assembly.</span></span> <span data-ttu-id="ac6a8-141">Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="ac6a8-142">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="ac6a8-143">Estende logicamente il [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interfaccia per fornire supporto per l'assembly del contenitore e gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="ac6a8-144">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-145">Interfaccia1 ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="ac6a8-146">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-147">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="ac6a8-148">Fornisce un enumeratore per un elenco di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="ac6a8-149">Interfaccia1 ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="ac6a8-150">Sottoclasse di `ICorDebugHeapValue` che rappresenta un oggetto classe di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="ac6a8-151">Interfaccia1 ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ac6a8-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="ac6a8-152">Rappresenta un punto di interruzione in una funzione oppure un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="ac6a8-153">Interfaccia1 ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="ac6a8-154">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-155">Interfaccia1 ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="ac6a8-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="ac6a8-156">Rappresenta un segmento di uno stack di chiamate fisico o logico.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="ac6a8-157">Interfaccia1 ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="ac6a8-158">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-159">Interfaccia1 ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="ac6a8-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="ac6a8-160">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="ac6a8-161">Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="ac6a8-162">Interfaccia1 ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="ac6a8-163">Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="ac6a8-164">Questa interfaccia estende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="ac6a8-165">Interfaccia1 ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="ac6a8-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="ac6a8-166">Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="ac6a8-167">Interfaccia1 ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="ac6a8-168">Fornisce metodi per l'estensione delle funzionalità di `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="ac6a8-169">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="ac6a8-170">Fornisce un metodo che estende [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) e [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) per fornire informazioni su un valore restituito gestito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="ac6a8-171">Interfaccia ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="ac6a8-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="ac6a8-172">Fornisce un metodo che consente a un debugger enumerare le variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="ac6a8-173">Interfaccia1 ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="ac6a8-174">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-175">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="ac6a8-176">Fornisce metodi per recuperare gli oggetti dell'interfaccia memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="ac6a8-177">Interfaccia1 ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="ac6a8-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="ac6a8-178">Rappresenta un oggetto di contesto.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-178">Represents a context object.</span></span> <span data-ttu-id="ac6a8-179">Questa interfaccia non è stata ancora implementata.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="ac6a8-180">Interfaccia1 ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="ac6a8-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="ac6a8-181">Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="ac6a8-182">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="ac6a8-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="ac6a8-183">Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="ac6a8-184">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="ac6a8-185">Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="ac6a8-186">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-187">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="ac6a8-188">Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="ac6a8-189">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-190">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="ac6a8-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="ac6a8-191">Definisce l'interfaccia di base da cui derivano tutti gli eventi di debug `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="ac6a8-192">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-193">Interfaccia ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="ac6a8-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="ac6a8-194">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-194">Obsolete.</span></span> <span data-ttu-id="ac6a8-195">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="ac6a8-196">Interfaccia1 ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="ac6a8-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="ac6a8-197">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-197">Obsolete.</span></span> <span data-ttu-id="ac6a8-198">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="ac6a8-199">Interfaccia1 ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="ac6a8-200">Opera da interfaccia di base astratta per il debug degli enumeratori.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="ac6a8-201">Interfaccia1 ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="ac6a8-202">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-202">Obsolete.</span></span> <span data-ttu-id="ac6a8-203">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="ac6a8-204">Interfaccia1 ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="ac6a8-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="ac6a8-205">Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="ac6a8-206">Interfaccia1 ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="ac6a8-207">Estende `ICorDebugEval` per fornire il supporto per tipi generici.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="ac6a8-208">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="ac6a8-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="ac6a8-209">Estende il [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="ac6a8-210">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-211">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="ac6a8-212">Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="ac6a8-213">Interfaccia ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="ac6a8-214">Estende il [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interfaccia per fornire informazioni di traccia dello stack da un oggetto eccezione gestito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="ac6a8-215">Interfaccia1 ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="ac6a8-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="ac6a8-216">Rappresenta un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="ac6a8-217">Interfaccia1 ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="ac6a8-218">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-219">Interfaccia1 ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="ac6a8-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="ac6a8-220">Rappresenta una funzione o un metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="ac6a8-221">Interfaccia1 ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="ac6a8-222">Estende `ICorDebugFunction` a livello logico in modo da fornire il supporto per il debug passo a passo con l'opzione Just My Code attivata.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="ac6a8-223">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="ac6a8-224">Estende logicamente il [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interfaccia per fornire l'accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="ac6a8-225">Interfaccia1 ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ac6a8-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="ac6a8-226">Estende `ICorDebugBreakpoint` per il supporto di punti di interruzione all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="ac6a8-227">Interfaccia ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="ac6a8-228">Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="ac6a8-229">Interfaccia1 ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="ac6a8-230">Sottoclasse di `ICorDebugValue` che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="ac6a8-231">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="ac6a8-232">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="ac6a8-233">Fornisce un enumeratore per un oggetto che mappa i GUID e i relativi oggetti corrispondenti `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="ac6a8-234">Interfaccia1 ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="ac6a8-235">Sottoclasse di `ICorDebugReferenceValue` che rappresenta un valore di riferimento per il quale il debugger ha creato un handle per la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="ac6a8-236">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="ac6a8-237">Fornisce un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="ac6a8-238">Interfaccia ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="ac6a8-239">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="ac6a8-240">Interfaccia1 ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="ac6a8-241">Sottoclasse di `ICorDebugValue` che rappresenta un oggetto su cui è stata operata la Garbage Collection di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="ac6a8-242">Interfaccia1 ICorDebugHeapValue2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="ac6a8-243">Estensione di `ICorDebugHeapValue` che fornisce il supporto per gli handle del runtime.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="ac6a8-244">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="ac6a8-245">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="ac6a8-246">Interfaccia ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="ac6a8-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="ac6a8-247">Rappresenta un segmento di codice di linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="ac6a8-248">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="ac6a8-249">Estende logicamente il [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaccia da fornire metodi che restituiscono il token per la firma di variabile locale di una funzione ed eseguire il mapping di linguaggio intermedio instrumentato del profiler (IL) che viene eseguito l'offset di linguaggio intermedio del metodo originale viene eseguito l'offset.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="ac6a8-250">Interfaccia1 ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="ac6a8-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="ac6a8-251">Rappresenta uno stack frame di codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="ac6a8-252">Interfaccia1 ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="ac6a8-253">Estensione logica di `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="ac6a8-254">Interfaccia ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="ac6a8-255">Fornisce un metodo che incapsula il valore restituito di una funzione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="ac6a8-256">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="ac6a8-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="ac6a8-257">Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="ac6a8-258">L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="ac6a8-259">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="ac6a8-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="ac6a8-260">Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="ac6a8-261">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-262">Interfaccia1 ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="ac6a8-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="ac6a8-263">Identifica i tipi di frame per il debugger.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="ac6a8-264">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="ac6a8-265">Vengono fornite informazioni sui frame interni, inclusi indirizzo dello stack e posizione relativamente al [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="ac6a8-266">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="ac6a8-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="ac6a8-267">Vengono fornite informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-267">Provides information about a loaded module.</span></span> <span data-ttu-id="ac6a8-268">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-269">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ac6a8-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="ac6a8-270">Fornisce metodi per l'elaborazione dei callback del debugger.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="ac6a8-271">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="ac6a8-272">Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="ac6a8-273">`ICorDebugManagedCallback2` è un'estensione logica di `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="ac6a8-274">Interfaccia ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="ac6a8-275">Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="ac6a8-276">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="ac6a8-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="ac6a8-277">Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="ac6a8-278">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="ac6a8-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="ac6a8-279">Rappresenta un buffer in memoria.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="ac6a8-280">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-281">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="ac6a8-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="ac6a8-282">Fornisce informazioni su un assembly unito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="ac6a8-283">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-284">Interfaccia ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="ac6a8-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="ac6a8-285">Fornisce informazioni sui metadati al debugger.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="ac6a8-286">Interfaccia1 ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="ac6a8-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="ac6a8-287">Rappresenta un modulo di Common Language Runtime che è un eseguibile o una DLL.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="ac6a8-288">Interfaccia1 ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="ac6a8-289">Opera come estensione logica di `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="ac6a8-290">Interfaccia ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="ac6a8-291">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="ac6a8-292">Interfaccia1 ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ac6a8-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="ac6a8-293">Estende `ICorDebugBreakpoint` in modo da fornire accesso a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="ac6a8-294">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="ac6a8-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="ac6a8-295">Estende il [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="ac6a8-296">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-297">Interfaccia1 ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="ac6a8-298">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-299">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="ac6a8-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="ac6a8-300">Estende il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per supportare le destinazioni dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="ac6a8-301">Interfaccia1 ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="ac6a8-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="ac6a8-302">Implementazione specializzata di `ICorDebugFrame` usata per i frame nativi.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="ac6a8-303">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="ac6a8-304">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="ac6a8-305">Interfaccia1 ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="ac6a8-306">Implementa i metodi `ICorDebugEnum` ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA, Relative Virtual Address).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="ac6a8-307">Interfaccia1 ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="ac6a8-308">Sottoclasse di `ICorDebugValue` che rappresenta un valore che contiene un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="ac6a8-309">Interfaccia1 ICorDebugObjectValue2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="ac6a8-310">Estende `ICorDebugObjectValue` per fornire il supporto per l'ereditarietà e gli override.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="ac6a8-311">Interfaccia1 ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="ac6a8-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="ac6a8-312">Rappresenta un processo che esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="ac6a8-313">Interfaccia1 ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="ac6a8-314">Estensione logica di `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="ac6a8-315">Interfaccia ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="ac6a8-316">Controlla le notifiche di debugger personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="ac6a8-317">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="ac6a8-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="ac6a8-318">Estende il [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) locale dell'interfaccia per supportare l'accesso all'heap gestito, per fornire informazioni sulla garbage collection di oggetti gestiti e per determinare se un debugger carica immagini dall'applicazione cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="ac6a8-319">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="ac6a8-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="ac6a8-320">Estende logicamente il [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaccia per abilitare funzionalità come la decodifica degli eventi di debug gestiti, codificati negli eventi di debug di eccezioni native e la suddivisione dei moduli virtuali.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="ac6a8-321">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-322">Interfaccia ICorDebugProcess7</span><span class="sxs-lookup"><span data-stu-id="ac6a8-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="ac6a8-323">Fornisce un metodo di configurazione del debugger per consentire la gestione degli aggiornamenti dei metadati in memoria nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="ac6a8-324">Interfaccia ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="ac6a8-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="ac6a8-325">Estende logicamente il [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaccia per abilitare o disabilitare alcuni tipi di [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) callback di eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="ac6a8-326">Interfaccia1 ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="ac6a8-327">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-328">Interfaccia1 ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="ac6a8-329">Sottoclasse di `ICorDebugValue` che supporta i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="ac6a8-330">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="ac6a8-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="ac6a8-331">Rappresenta l'insieme dei registri disponibili sul computer in cui è in corso l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="ac6a8-332">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="ac6a8-333">Estende le funzionalità di `ICorDebugRegisterSet` per le piattaforme hardware con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="ac6a8-334">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="ac6a8-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="ac6a8-335">Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="ac6a8-336">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="ac6a8-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="ac6a8-337">Fornisce metodi che consentono di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="ac6a8-338">Interfaccia ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="ac6a8-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="ac6a8-339">Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="ac6a8-340">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="ac6a8-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="ac6a8-341">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="ac6a8-342">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="ac6a8-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="ac6a8-343">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="ac6a8-344">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-345">Interfaccia1 ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="ac6a8-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="ac6a8-346">Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="ac6a8-347">Interfaccia1 ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="ac6a8-348">Fornisce il supporto per il debug Just My Code (JMC).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="ac6a8-349">Interfaccia1 ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="ac6a8-350">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-351">Interfaccia1 ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="ac6a8-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="ac6a8-352">Sottoclasse di `ICorDebugHeapValue` che si applica ai valori stringa.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="ac6a8-353">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="ac6a8-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="ac6a8-354">Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="ac6a8-355">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-356">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="ac6a8-357">Estende logicamente il [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaccia per il recupero di informazioni sui simboli di debug aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="ac6a8-358">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-359">Interfaccia1 ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="ac6a8-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="ac6a8-360">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-360">Represents a thread in a process.</span></span> <span data-ttu-id="ac6a8-361">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="ac6a8-362">Interfaccia1 ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="ac6a8-363">Opera come estensione logica di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="ac6a8-364">Interfaccia ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="ac6a8-365">Fornisce il punto di ingresso per il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) e alle interfacce corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="ac6a8-366">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="ac6a8-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="ac6a8-367">Fornisce informazioni sui blocchi dei thread.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="ac6a8-368">Interfaccia1 ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="ac6a8-369">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-370">Interfaccia1 ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="ac6a8-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="ac6a8-371">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="ac6a8-372">Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="ac6a8-373">Interfaccia ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="ac6a8-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="ac6a8-374">Estende il [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interfaccia da cui recuperare l'identificatore del tipo di un tipo di base o un tipo complesso (definita dall'utente).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="ac6a8-375">Interfaccia1 ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="ac6a8-376">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-377">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="ac6a8-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="ac6a8-378">Notifica gli eventi nativi non direttamente correlati a Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="ac6a8-379">"ICorDebugValue"</span><span class="sxs-lookup"><span data-stu-id="ac6a8-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="ac6a8-380">Rappresenta un valore di lettura o scrittura nel processo in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="ac6a8-381">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="ac6a8-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="ac6a8-382">Estende `ICorDebugValue` in modo da fornire il supporto per `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="ac6a8-383">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="ac6a8-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="ac6a8-384">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="ac6a8-385">"ICorDebugValueBreakpoint"</span><span class="sxs-lookup"><span data-stu-id="ac6a8-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="ac6a8-386">Estende `ICorDebugBreakpoint` in modo da fornire accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="ac6a8-387">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="ac6a8-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="ac6a8-388">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="ac6a8-389">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="ac6a8-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="ac6a8-390">Rappresenta una variabile locale o un argomento di una funzione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="ac6a8-391">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="ac6a8-392">Fornisce un enumeratore per le variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="ac6a8-393">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="ac6a8-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="ac6a8-394">Recupera le informazioni relative al simbolo di debug per una variabile.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="ac6a8-395">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-396">Interfaccia ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="ac6a8-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="ac6a8-397">Fornisce metodi che facilitano lo svuotamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="ac6a8-398">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="ac6a8-399">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="ac6a8-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="ac6a8-400">Opera come interfaccia generica per i processi di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="ac6a8-401">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="ac6a8-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="ac6a8-402">Rappresenta e fornisce informazioni su un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="ac6a8-403">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="ac6a8-404">Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishAppDomain` attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="ac6a8-405">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="ac6a8-406">Opera da base astratta per la pubblicazione di enumeratori.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="ac6a8-407">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="ac6a8-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="ac6a8-408">Fornisce metodi che accedono alle informazioni su un processo.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="ac6a8-409">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="ac6a8-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="ac6a8-410">Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ac6a8-411">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ac6a8-411">Related Sections</span></span>  
 [<span data-ttu-id="ac6a8-412">Coclassi di debug</span><span class="sxs-lookup"><span data-stu-id="ac6a8-412">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="ac6a8-413">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="ac6a8-413">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="ac6a8-414">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ac6a8-414">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="ac6a8-415">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="ac6a8-415">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
