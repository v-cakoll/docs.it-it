---
title: Interfacce di debug
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afa4e6cd4e99540030d3a9e151da4bbe711d973a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219828"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="cd0ec-102">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd0ec-102">Debugging Interfaces</span></span>
<span data-ttu-id="cd0ec-103">Questa sezione descrive le interfacce non gestite che gestiscono il debug di un programma in esecuzione in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="cd0ec-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd0ec-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cd0ec-104">In This Section</span></span>  
 <span data-ttu-id="cd0ec-105">[Interfaccia ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-106">Fornisce un metodo per l'enumerazione delle aree di memoria specificate dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="cd0ec-107">[Interfaccia ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-108">Fornisce un metodo di callback in modo che `EnumMemoryRegions` segnali al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="cd0ec-109">[Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-110">Fornisce metodi per l'interazione con un processo di Common Language Runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="cd0ec-111">[Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-112">Sottoclasse di `ICLRDataTarget` usata dal livello dei servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="cd0ec-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-114">Una sottoclasse [ICLRDataTarget2](iclrdatatarget2-interface.md) che fornisce accesso alle informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="cd0ec-115">[Interfaccia ICLRDebugging](iclrdebugging-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-115">[ICLRDebugging Interface](iclrdebugging-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-116">Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="cd0ec-117">[Interfaccia ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-118">Include il [metodo ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) metodo, che ottiene un provider di librerie di interfaccia di callback che consente a common language runtime le librerie di debug specifiche della versione di individuare e caricare su richiesta.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="cd0ec-119">[Interfaccia ICLRMetadataLocator](iclrmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-120">Interfaccia usata dal livello dei servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="cd0ec-121">[Interfaccia ICorDebug](icordebug-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-121">[ICorDebug Interface](icordebug-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-122">Fornisce metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni nell'ambiente Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="cd0ec-123">[ICorDebugAppDomain Interface1](icordebugappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-123">[ICorDebugAppDomain Interface1](icordebugappdomain-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-124">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="cd0ec-125">[ICorDebugAppDomain2 Interface1](icordebugappdomain2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-125">[ICorDebugAppDomain2 Interface1](icordebugappdomain2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-126">Fornisce metodi che consentono di usare matrici, puntatori, puntatori a funzione e tipi ByRef.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="cd0ec-127">Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="cd0ec-128">[Interfaccia ICorDebugAppDomain3](icordebugappdomain3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-129">Fornisce metodi che consentono di lavorare con i tipi [!INCLUDE[wrt](../../../../includes/wrt-md.md)] in un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="cd0ec-130">Questa interfaccia è un'estensione delle interfacce `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="cd0ec-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-132">Estende logicamente il [ICorDebugAppDomain](icordebugappdomain-interface.md) interfaccia da ottenere un oggetto gestito da un COM callable wrapper.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="cd0ec-133">[ICorDebugAppDomainEnum Interface1](icordebugappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-133">[ICorDebugAppDomainEnum Interface1](icordebugappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-134">Fornisce un metodo che restituisce un numero specificato di valori di `ICorDebugAppDomain` a partire dalla posizione successiva nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="cd0ec-135">[ICorDebugArrayValue Interface1](icordebugarrayvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-135">[ICorDebugArrayValue Interface1](icordebugarrayvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-136">Sottoclasse di `ICorDebugHeapValue` che rappresenta una matrice unidimensionale o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="cd0ec-137">[Interfaccia1 ICorDebugAssembly](icordebugassembly-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-137">[ICorDebugAssembly Interface1](icordebugassembly-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-138">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="cd0ec-139">[Interfaccia1 ICorDebugAssembly2](icordebugassembly2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-139">[ICorDebugAssembly2 Interface1](icordebugassembly2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-140">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-140">Represents an assembly.</span></span> <span data-ttu-id="cd0ec-141">Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="cd0ec-142">[Interfaccia ICorDebugAssembly3](icordebugassembly3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-143">Estende logicamente il [ICorDebugAssembly](icordebugassembly-interface.md) interfaccia per fornire supporto per l'assembly del contenitore e gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="cd0ec-144">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-145">[ICorDebugAssemblyEnum Interface1](icordebugassemblyenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-145">[ICorDebugAssemblyEnum Interface1](icordebugassemblyenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-146">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-147">[Interfaccia ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-148">Fornisce un enumeratore per un elenco degli [CorDebugBlockingObject](cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="cd0ec-149">[ICorDebugBoxValue Interface1](icordebugboxvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-149">[ICorDebugBoxValue Interface1](icordebugboxvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-150">Sottoclasse di `ICorDebugHeapValue` che rappresenta un oggetto classe di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="cd0ec-151">[Interfaccia1 ICorDebugBreakpoint](icordebugbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-151">[ICorDebugBreakpoint Interface1](icordebugbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-152">Rappresenta un punto di interruzione in una funzione oppure un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="cd0ec-153">[Interfaccia1 ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-153">[ICorDebugBreakpointEnum Interface1](icordebugbreakpointenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-154">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-155">[Interfaccia1 ICorDebugChain](icordebugchain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-155">[ICorDebugChain Interface1](icordebugchain-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-156">Rappresenta un segmento di uno stack di chiamate fisico o logico.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="cd0ec-157">[Interfaccia1 ICorDebugChainEnum](icordebugchainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-157">[ICorDebugChainEnum Interface1](icordebugchainenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-158">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-159">[Interfaccia1 ICorDebugClass](icordebugclass-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-159">[ICorDebugClass Interface1](icordebugclass-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-160">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="cd0ec-161">Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="cd0ec-162">[Interfaccia1 ICorDebugClass2](icordebugclass2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-162">[ICorDebugClass2 Interface1](icordebugclass2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-163">Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="cd0ec-164">Questa interfaccia estende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="cd0ec-165">[Interfaccia1 ICorDebugCode](icordebugcode-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-165">[ICorDebugCode Interface1](icordebugcode-interface1.md)\\</span></span>
 <span data-ttu-id="cd0ec-166">Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="cd0ec-167">[Interfaccia1 ICorDebugCode2](icordebugcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-167">[ICorDebugCode2 Interface1](icordebugcode2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-168">Fornisce metodi per l'estensione delle funzionalità di `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="cd0ec-169">[Interfaccia ICorDebugCode3](icordebugcode3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-170">Fornisce un metodo che estende [ICorDebugCode](icordebugcode-interface1.md) e [ICorDebugCode2](icordebugcode2-interface.md) per fornire informazioni su un valore restituito gestito.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="cd0ec-171">[Interfaccia ICorDebugCode4](icordebugcode4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-172">Fornisce un metodo che consente a un debugger enumerare le variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="cd0ec-173">[ICorDebugCodeEnum Interface1](icordebugcodeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-173">[ICorDebugCodeEnum Interface1](icordebugcodeenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-174">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-175">[Interfaccia ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-176">Fornisce metodi per recuperare gli oggetti dell'interfaccia memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="cd0ec-177">[Interfaccia1 ICorDebugContext](icordebugcontext-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-177">[ICorDebugContext Interface1](icordebugcontext-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-178">Rappresenta un oggetto di contesto.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-178">Represents a context object.</span></span> <span data-ttu-id="cd0ec-179">Questa interfaccia non è stata ancora implementata.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="cd0ec-180">[Interfaccia1 ICorDebugController](icordebugcontroller-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-180">[ICorDebugController Interface1](icordebugcontroller-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-181">Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="cd0ec-182">[Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-183">Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="cd0ec-184">[Interfaccia ICorDebugDataTarget2](icordebugdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-185">Estende logicamente il [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="cd0ec-186">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-187">[Interfaccia ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-188">Estende logicamente il [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="cd0ec-189">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-190">[Interfaccia ICorDebugDebugEvent](icordebugdebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-191">Definisce l'interfaccia di base da cui derivano tutti gli evento di debug `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="cd0ec-192">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-194">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-194">Obsolete.</span></span> <span data-ttu-id="cd0ec-195">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="cd0ec-196">[ICorDebugEditAndContinueSnapshot Interface1](icordebugeditandcontinuesnapshot-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-196">[ICorDebugEditAndContinueSnapshot Interface1](icordebugeditandcontinuesnapshot-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-197">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-197">Obsolete.</span></span> <span data-ttu-id="cd0ec-198">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="cd0ec-199">[Interfaccia1 ICorDebugEnum](icordebugenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-199">[ICorDebugEnum Interface1](icordebugenum-interface1.md)\\</span></span>
 <span data-ttu-id="cd0ec-200">Opera da interfaccia di base astratta per il debug degli enumeratori.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="cd0ec-201">[ICorDebugErrorInfoEnum Interface1](icordebugerrorinfoenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-201">[ICorDebugErrorInfoEnum Interface1](icordebugerrorinfoenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-202">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-202">Obsolete.</span></span> <span data-ttu-id="cd0ec-203">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="cd0ec-204">[Interfaccia1 ICorDebugEval](icordebugeval-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-204">[ICorDebugEval Interface1](icordebugeval-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-205">Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="cd0ec-206">[ICorDebugEval2 Interface1](icordebugeval2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-206">[ICorDebugEval2 Interface1](icordebugeval2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-207">Estende `ICorDebugEval` per fornire il supporto per tipi generici.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="cd0ec-208">[Interfaccia ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-209">Estende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaccia per supportare gli eventi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="cd0ec-210">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-211">[Interfaccia ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-212">Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="cd0ec-213">[Interfaccia ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-214">Estende la [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interfaccia per fornire informazioni sulla traccia dello stack da un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="cd0ec-215">[Interfaccia1 ICorDebugFrame](icordebugframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-215">[ICorDebugFrame Interface1](icordebugframe-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-216">Rappresenta un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="cd0ec-217">[Interfaccia1 ICorDebugFrameEnum](icordebugframeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-217">[ICorDebugFrameEnum Interface1](icordebugframeenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-218">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-219">[Interfaccia1 ICorDebugFunction](icordebugfunction-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-219">[ICorDebugFunction Interface1](icordebugfunction-interface1.md)\\</span></span>
 <span data-ttu-id="cd0ec-220">Rappresenta una funzione o un metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="cd0ec-221">[Interfaccia1 ICorDebugFunction2](icordebugfunction2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-221">[ICorDebugFunction2 Interface1](icordebugfunction2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-222">Estende `ICorDebugFunction` a livello logico in modo da fornire il supporto per il debug passo a passo con l'opzione Just My Code attivata.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="cd0ec-223">[Interfaccia ICorDebugFunction3](icordebugfunction3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-224">Estende logicamente il [ICorDebugFunction](icordebugfunction-interface1.md) interfaccia per fornire l'accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="cd0ec-225">[Interfaccia1 ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-225">[ICorDebugFunctionBreakpoint Interface1](icordebugfunctionbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-226">Estende `ICorDebugBreakpoint` per il supporto di punti di interruzione all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="cd0ec-227">[Interfaccia ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-228">Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="cd0ec-229">[ICorDebugGenericValue Interface1](icordebuggenericvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-229">[ICorDebugGenericValue Interface1](icordebuggenericvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-230">Sottoclasse di `ICorDebugValue` che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="cd0ec-231">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="cd0ec-232">[Interfaccia ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-233">Fornisce un enumeratore per un oggetto che mappa i GUID e i relativi oggetti corrispondenti `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="cd0ec-234">[ICorDebugHandleValue Interface1](icordebughandlevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-234">[ICorDebugHandleValue Interface1](icordebughandlevalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-235">Sottoclasse di `ICorDebugReferenceValue` che rappresenta un valore di riferimento per il quale il debugger ha creato un handle per la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="cd0ec-236">[Interfaccia ICorDebugHeapEnum](icordebugheapenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-237">Fornisce un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="cd0ec-238">[Interfaccia ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-239">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="cd0ec-240">[ICorDebugHeapValue Interface1](icordebugheapvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-240">[ICorDebugHeapValue Interface1](icordebugheapvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-241">Sottoclasse di `ICorDebugValue` che rappresenta un oggetto su cui è stata operata la Garbage Collection di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="cd0ec-242">[Interfaccia1 ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-242">[ICorDebugHeapValue2 Interface1](icordebugheapvalue2-interface1.md)\\</span></span>
 <span data-ttu-id="cd0ec-243">Estensione di `ICorDebugHeapValue` che fornisce il supporto per gli handle del runtime.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="cd0ec-244">[Interfaccia ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-245">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="cd0ec-246">[Interfaccia ICorDebugILCode](icordebugilcode-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-247">Rappresenta un segmento di codice di linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="cd0ec-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="cd0ec-248">[Interfaccia ICorDebugILCode2](icordebugilcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-249">Estende logicamente il [ICorDebugILCode](icordebugilcode-interface.md) interfaccia per fornire i metodi che restituiscono il token di firma della variabile locale di una funzione e che eseguire il mapping di linguaggio intermedio instrumentato del profiler (IL) agli offset linguaggio intermedio del metodo originale viene eseguito l'offset.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="cd0ec-250">[Interfaccia1 ICorDebugILFrame](icordebugilframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-250">[ICorDebugILFrame Interface1](icordebugilframe-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-251">Rappresenta uno stack frame di codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="cd0ec-252">[Interfaccia1 ICorDebugILFrame2](icordebugilframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-252">[ICorDebugILFrame2 Interface1](icordebugilframe2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-253">Estensione logica di `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="cd0ec-254">[Interfaccia ICorDebugILFrame3](icordebugilframe3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-255">Fornisce un metodo che incapsula il valore restituito di una funzione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="cd0ec-256">[Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-257">Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="cd0ec-258">L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="cd0ec-259">[Interfaccia ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-260">Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="cd0ec-261">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-262">[Interfaccia1 ICorDebugInternalFrame](icordebuginternalframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-262">[ICorDebugInternalFrame Interface1](icordebuginternalframe-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-263">Identifica i tipi di frame per il debugger.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="cd0ec-264">[Interfaccia ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-265">Vengono fornite informazioni sui frame interni, compresi l'indirizzo dello stack e la posizione in relazione al [ICorDebugFrame](icordebugframe-interface.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="cd0ec-266">[Interfaccia ICorDebugLoadedModule](icordebugloadedmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-267">Vengono fornite informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-267">Provides information about a loaded module.</span></span> <span data-ttu-id="cd0ec-268">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-269">[Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-270">Fornisce metodi per l'elaborazione dei callback del debugger.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="cd0ec-271">[Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-272">Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="cd0ec-273">`ICorDebugManagedCallback2` è un'estensione logica di `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="cd0ec-274">[Interfaccia ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-275">Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="cd0ec-276">[Interfaccia ICorDebugMDA](icordebugmda-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-276">[ICorDebugMDA Interface](icordebugmda-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-277">Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).</span><span class="sxs-lookup"><span data-stu-id="cd0ec-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="cd0ec-278">[Interfaccia ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-279">Rappresenta un buffer in memoria.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="cd0ec-280">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-281">[Interfaccia ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-282">Fornisce informazioni su un assembly unito.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="cd0ec-283">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-284">[Interfaccia ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-285">Fornisce informazioni sui metadati al debugger.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="cd0ec-286">[Interfaccia1 ICorDebugModule](icordebugmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-286">[ICorDebugModule Interface1](icordebugmodule-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-287">Rappresenta un modulo di Common Language Runtime che è un eseguibile o una DLL.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="cd0ec-288">[Interfaccia1 ICorDebugModule2](icordebugmodule2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-288">[ICorDebugModule2 Interface1](icordebugmodule2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-289">Opera come estensione logica di `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="cd0ec-290">[Interfaccia ICorDebugModule3](icordebugmodule3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-291">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="cd0ec-292">[Interfaccia1 ICorDebugModuleBreakpoint](icordebugmodulebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-292">[ICorDebugModuleBreakpoint Interface1](icordebugmodulebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-293">Estende `ICorDebugBreakpoint` in modo da fornire accesso a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="cd0ec-294">[Interfaccia ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-295">Estende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="cd0ec-296">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-297">[Interfaccia1 ICorDebugModuleEnum](icordebugmoduleenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-297">[ICorDebugModuleEnum Interface1](icordebugmoduleenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-298">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-299">[Interfaccia ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-300">Estende la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia per supportare le destinazioni dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="cd0ec-301">[ICorDebugNativeFrame Interface1](icordebugnativeframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-301">[ICorDebugNativeFrame Interface1](icordebugnativeframe-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-302">Implementazione specializzata di `ICorDebugFrame` usata per i frame nativi.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="cd0ec-303">[Interfaccia ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-304">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="cd0ec-305">[Interfaccia1 ICorDebugObjectEnum](icordebugobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-305">[ICorDebugObjectEnum Interface1](icordebugobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-306">Implementa i metodi `ICorDebugEnum` ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA, Relative Virtual Address).</span><span class="sxs-lookup"><span data-stu-id="cd0ec-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="cd0ec-307">[Interfaccia1 ICorDebugObjectValue](icordebugobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-307">[ICorDebugObjectValue Interface1](icordebugobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-308">Sottoclasse di `ICorDebugValue` che rappresenta un valore che contiene un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="cd0ec-309">[Interfaccia1 ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-309">[ICorDebugObjectValue2 Interface1](icordebugobjectvalue2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-310">Estende `ICorDebugObjectValue` per fornire il supporto per l'ereditarietà e gli override.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="cd0ec-311">[ICorDebugProcess Interface1](icordebugprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-311">[ICorDebugProcess Interface1](icordebugprocess-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-312">Rappresenta un processo che esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="cd0ec-313">[Interfaccia1 ICorDebugProcess2](icordebugprocess2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-313">[ICorDebugProcess2 Interface1](icordebugprocess2-interface1.md)\\</span></span>
 <span data-ttu-id="cd0ec-314">Estensione logica di `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="cd0ec-315">[Interfaccia ICorDebugProcess3](icordebugprocess3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-316">Controlla le notifiche di debugger personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="cd0ec-317">[Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-318">Fornisce supporto per dal controllo l'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="cd0ec-319">[Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-320">Estende la [ICorDebugProcess](icordebugprocess-interface.md) locale dell'interfaccia per supportare l'accesso nell'heap gestito, per fornire informazioni sull'operazione di garbage collection di oggetti gestiti e per determinare se un debugger carica immagini dall'applicazione cache di immagini native.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="cd0ec-321">[Interfaccia ICorDebugProcess6](icordebugprocess6-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-322">Estende logicamente il [ICorDebugProcess](icordebugprocess-interface.md) interfaccia per abilitare funzionalità come la decodifica degli eventi di debug gestito sono codificati in eventi di debug di eccezioni native e suddivisione dei moduli virtuali.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="cd0ec-323">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-324">[Interfaccia ICorDebugProcess7](icordebugprocess7-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-325">Fornisce un metodo di configurazione del debugger per consentire la gestione degli aggiornamenti dei metadati in memoria nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="cd0ec-326">[Interfaccia ICorDebugProcess8](icordebugprocess8-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-327">Estende logicamente il [ICorDebugProcess](icordebugprocess-interface.md) per abilitare o disabilitare determinati tipi di interfaccia [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) callback di eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="cd0ec-328">[ICorDebugProcessEnum Interface1](icordebugprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-328">[ICorDebugProcessEnum Interface1](icordebugprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-329">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-330">[Interfaccia1 ICorDebugReferenceValue](icordebugreferencevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-330">[ICorDebugReferenceValue Interface1](icordebugreferencevalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-331">Sottoclasse di `ICorDebugValue` che supporta i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="cd0ec-332">[Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-333">Rappresenta l'insieme dei registri disponibili sul computer in cui è in corso l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="cd0ec-334">[Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-335">Estende le funzionalità di `ICorDebugRegisterSet` per le piattaforme hardware con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="cd0ec-336">[Interfaccia ICorDebugRemote](icordebugremote-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-336">[ICorDebugRemote Interface](icordebugremote-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-337">Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="cd0ec-338">[Interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-339">Fornisce metodi che consentono di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="cd0ec-340">[Interfaccia ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-341">Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="cd0ec-342">[Interfaccia ICorDebugStackWalk](icordebugstackwalk-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-343">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="cd0ec-344">[Interfaccia ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-345">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="cd0ec-346">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-347">[Interfaccia1 ICorDebugStepper](icordebugstepper-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-347">[ICorDebugStepper Interface1](icordebugstepper-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-348">Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="cd0ec-349">[ICorDebugStepper2 Interface1](icordebugstepper2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-349">[ICorDebugStepper2 Interface1](icordebugstepper2-interface1.md)\\</span></span>
 <span data-ttu-id="cd0ec-350">Fornisce il supporto per il debug Just My Code (JMC).</span><span class="sxs-lookup"><span data-stu-id="cd0ec-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="cd0ec-351">[Interfaccia1 ICorDebugStepperEnum](icordebugstepperenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-351">[ICorDebugStepperEnum Interface1](icordebugstepperenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-352">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-353">[ICorDebugStringValue Interface1](icordebugstringvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-353">[ICorDebugStringValue Interface1](icordebugstringvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-354">Sottoclasse di `ICorDebugHeapValue` che si applica ai valori stringa.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="cd0ec-355">[Interfaccia ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-356">Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="cd0ec-357">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-358">[Interfaccia ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-359">Estende logicamente il [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interfaccia da cui recuperare le informazioni sui simboli di debug aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="cd0ec-360">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-361">[Interfaccia1 ICorDebugThread](icordebugthread-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-361">[ICorDebugThread Interface1](icordebugthread-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-362">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-362">Represents a thread in a process.</span></span> <span data-ttu-id="cd0ec-363">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="cd0ec-364">[ICorDebugThread2 Interface1](icordebugthread2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-364">[ICorDebugThread2 Interface1](icordebugthread2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-365">Opera come estensione logica di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="cd0ec-366">[Interfaccia ICorDebugThread3](icordebugthread3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-367">Fornisce il punto di ingresso per il [ICorDebugStackWalk](icordebugstackwalk-interface.md) e interfacce corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="cd0ec-368">[Interfaccia ICorDebugThread4](icordebugthread4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-369">Fornisce informazioni sui blocchi dei thread.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="cd0ec-370">[ICorDebugThreadEnum Interface1](icordebugthreadenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-370">[ICorDebugThreadEnum Interface1](icordebugthreadenum-interface1.md)\\</span></span>
 <span data-ttu-id="cd0ec-371">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-372">[ICorDebugType Interface1](icordebugtype-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-372">[ICorDebugType Interface1](icordebugtype-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-373">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="cd0ec-374">Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="cd0ec-375">[Interfaccia ICorDebugType2](icordebugtype2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-376">Estende la [ICorDebugType](icordebugtype-interface.md) interfaccia da cui recuperare l'identificatore del tipo di un tipo di base o complesso (tipo definito dall'utente).</span><span class="sxs-lookup"><span data-stu-id="cd0ec-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="cd0ec-377">[ICorDebugTypeEnum Interface1](icordebugtypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-377">[ICorDebugTypeEnum Interface1](icordebugtypeenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-378">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-379">[Interfaccia ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-380">Notifica gli eventi nativi non direttamente correlati a Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="cd0ec-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-382">Rappresenta un valore di lettura o scrittura nel processo in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="cd0ec-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-384">Estende `ICorDebugValue` in modo da fornire il supporto per `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="cd0ec-385">[Interfaccia ICorDebugValue3](icordebugvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-386">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici di dimensioni superiori a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="cd0ec-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-388">Estende `ICorDebugBreakpoint` in modo da fornire accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="cd0ec-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-390">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="cd0ec-391">[Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-392">Rappresenta un argomento di una funzione o variabile locale.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="cd0ec-393">[Interfaccia ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-394">Fornisce un enumeratore per le variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="cd0ec-395">[Interfaccia ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-396">Recupera le informazioni relative al simbolo di debug per una variabile.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="cd0ec-397">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-398">[Interfaccia ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-399">Fornisce metodi che facilitano lo svuotamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="cd0ec-400">**Disponibile solo in .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="cd0ec-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd0ec-401">[Interfaccia ICorPublish](icorpublish-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-401">[ICorPublish Interface](icorpublish-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-402">Opera come interfaccia generica per i processi di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="cd0ec-403">[Interfaccia ICorPublishAppDomain](icorpublishappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-404">Rappresenta e fornisce informazioni su un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="cd0ec-405">[Interfaccia ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-406">Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishAppDomain` attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="cd0ec-407">[Interfaccia ICorPublishEnum](icorpublishenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-408">Opera da base astratta per la pubblicazione di enumeratori.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="cd0ec-409">[Interfaccia ICorPublishProcess](icorpublishprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-410">Fornisce metodi che accedono alle informazioni su un processo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="cd0ec-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-412">Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="cd0ec-413">[Interfaccia ISOSDacInterface](isosdacinterface-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-414">Fornisce metodi helper per accedere ai dati da `SOS`.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="cd0ec-415">[Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-416">Fornisce metodi per l'esecuzione di query informazioni sulla definizione di un metodo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="cd0ec-417">[Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-418">Fornisce metodi per la ricerca delle informazioni relative a un'istanza di metodo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="cd0ec-419">[Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-420">Fornisce metodi per la ricerca delle informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="cd0ec-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\\</span></span>
 <span data-ttu-id="cd0ec-422">Fornisce metodi per l'esecuzione di query informazioni sul processo.</span><span class="sxs-lookup"><span data-stu-id="cd0ec-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="cd0ec-423">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cd0ec-423">Related Sections</span></span>  
 <span data-ttu-id="cd0ec-424">[Coclassi di debug](debugging-coclasses.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-424">[Debugging Coclasses](debugging-coclasses.md)\\</span></span>
 <span data-ttu-id="cd0ec-425">[Funzioni statiche globali di debug](debugging-global-static-functions.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-425">[Debugging Global Static Functions](debugging-global-static-functions.md)\\</span></span>
 <span data-ttu-id="cd0ec-426">[Enumerazioni di debug](debugging-enumerations.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-426">[Debugging Enumerations](debugging-enumerations.md)\\</span></span>
 <span data-ttu-id="cd0ec-427">[Strutture di debug](debugging-structures.md)\\</span><span class="sxs-lookup"><span data-stu-id="cd0ec-427">[Debugging Structures](debugging-structures.md)\\</span></span>
