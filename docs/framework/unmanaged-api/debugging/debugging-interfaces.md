---
title: Interfacce di debug
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 07b39666637628102e9ffafd2c059ba0d4b51b92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097187"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="83474-102">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="83474-102">Debugging Interfaces</span></span>
<span data-ttu-id="83474-103">Questa sezione descrive le interfacce non gestite che gestiscono il debug di un programma in esecuzione in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="83474-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83474-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="83474-104">In This Section</span></span>  
 <span data-ttu-id="83474-105">[Interfaccia ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="83474-106">Fornisce un metodo per l'enumerazione delle aree di memoria specificate dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="83474-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="83474-107">[Interfaccia ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="83474-108">Fornisce un metodo di callback in modo che `EnumMemoryRegions` segnali al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="83474-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="83474-109">[Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="83474-110">Fornisce metodi per l'interazione con un processo di Common Language Runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83474-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="83474-111">[Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="83474-112">Sottoclasse di `ICLRDataTarget` usata dal livello dei servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83474-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="83474-113">[Interfaccia ICLRDataTarget3](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="83474-114">Sottoclasse di [ICLRDataTarget2](iclrdatatarget2-interface.md) che fornisce l'accesso alle informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="83474-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="83474-115">[Interfaccia ICLRDebugging](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="83474-116">Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.</span><span class="sxs-lookup"><span data-stu-id="83474-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="83474-117">[Interfaccia ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="83474-118">Include il metodo del [Metodo ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , che ottiene un'interfaccia di callback del provider di librerie che consente di trovare e caricare su richiesta Common Language Runtime librerie di debug specifiche della versione.</span><span class="sxs-lookup"><span data-stu-id="83474-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="83474-119">[Interfaccia ICLRMetadataLocator](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="83474-120">Interfaccia usata dal livello dei servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83474-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="83474-121">[Interfaccia ICorDebug](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="83474-122">Fornisce metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni nell'ambiente Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="83474-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="83474-123">[Interfaccia ICorDebugAppDomain](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="83474-124">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="83474-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="83474-125">[Interfaccia ICorDebugAppDomain2](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="83474-126">Fornisce metodi che consentono di usare matrici, puntatori, puntatori a funzione e tipi ByRef.</span><span class="sxs-lookup"><span data-stu-id="83474-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="83474-127">Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="83474-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="83474-128">[Interfaccia ICorDebugAppDomain3](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="83474-129">Fornisce metodi per lavorare con i tipi di Windows Runtime in un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="83474-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="83474-130">Questa interfaccia è un'estensione delle interfacce `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="83474-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="83474-131">[Interfaccia ICorDebugAppDomain4](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="83474-132">Estende logicamente l'interfaccia [ICorDebugAppDomain](icordebugappdomain-interface.md) per ottenere un oggetto gestito da un COM Callable Wrapper.</span><span class="sxs-lookup"><span data-stu-id="83474-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="83474-133">[Interfaccia ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="83474-134">Fornisce un metodo che restituisce un numero specificato di valori di `ICorDebugAppDomain` a partire dalla posizione successiva nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="83474-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="83474-135">[Interfaccia ICorDebugArrayValue](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-136">Sottoclasse di `ICorDebugHeapValue` che rappresenta una matrice unidimensionale o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="83474-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="83474-137">[Interfaccia ICorDebugAssembly](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="83474-138">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="83474-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="83474-139">[Interfaccia ICorDebugAssembly2](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="83474-140">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="83474-140">Represents an assembly.</span></span> <span data-ttu-id="83474-141">Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="83474-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="83474-142">[Interfaccia metodo icordebugassembly3](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="83474-143">Estende logicamente l'interfaccia [ICorDebugAssembly](icordebugassembly-interface.md) per fornire supporto per gli assembly contenitore e i relativi assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="83474-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="83474-144">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-145">[Interfaccia ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="83474-146">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="83474-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="83474-147">[Interfaccia ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="83474-148">Fornisce un enumeratore per un elenco di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="83474-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="83474-149">[Interfaccia ICorDebugBoxValue](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-150">Sottoclasse di `ICorDebugHeapValue` che rappresenta un oggetto classe di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="83474-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="83474-151">[Interfaccia ICorDebugBreakpoint](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="83474-152">Rappresenta un punto di interruzione in una funzione oppure un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="83474-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="83474-153">[Interfaccia ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="83474-154">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="83474-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="83474-155">[Interfaccia ICorDebugChain](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="83474-156">Rappresenta un segmento di uno stack di chiamate fisico o logico.</span><span class="sxs-lookup"><span data-stu-id="83474-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="83474-157">[Interfaccia ICorDebugChainEnum](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="83474-158">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="83474-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="83474-159">[Interfaccia ICorDebugClass](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="83474-160">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="83474-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="83474-161">Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="83474-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="83474-162">[Interfaccia ICorDebugClass2](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="83474-163">Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="83474-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="83474-164">Questa interfaccia estende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="83474-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="83474-165">[Interfaccia ICorDebugCode](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="83474-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="83474-166">Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="83474-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="83474-167">[Interfaccia ICorDebugCode2](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="83474-168">Fornisce metodi per l'estensione delle funzionalità di `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="83474-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="83474-169">[Interfaccia ICorDebugCode3](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="83474-170">Fornisce un metodo che estende [ICorDebugCode](icordebugcode-interface1.md) e [ICorDebugCode2](icordebugcode2-interface.md) per fornire informazioni su un valore restituito gestito.</span><span class="sxs-lookup"><span data-stu-id="83474-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="83474-171">[Interfaccia interfacce icordebugcode4](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="83474-172">Fornisce un metodo che consente a un debugger di enumerare le variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="83474-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="83474-173">[Interfaccia ICorDebugCodeEnum](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="83474-174">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="83474-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="83474-175">[Interfaccia ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-176">Fornisce metodi per recuperare gli oggetti dell'interfaccia memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="83474-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="83474-177">[Interfaccia ICorDebugContext](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="83474-178">Rappresenta un oggetto di contesto.</span><span class="sxs-lookup"><span data-stu-id="83474-178">Represents a context object.</span></span> <span data-ttu-id="83474-179">Questa interfaccia non è stata ancora implementata.</span><span class="sxs-lookup"><span data-stu-id="83474-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="83474-180">[Interfaccia ICorDebugController](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="83474-181">Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="83474-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="83474-182">[Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="83474-183">Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83474-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="83474-184">[Interfaccia metodo icordebugdatatarget2](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="83474-185">Estende logicamente l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="83474-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="83474-186">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-187">[Interfaccia ICorDebugDataTarget3](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="83474-188">Estende logicamente l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="83474-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="83474-189">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-190">[Interfaccia ICorDebugDebugEvent](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="83474-191">Definisce l'interfaccia di base da cui derivano tutti gli evento di debug `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="83474-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="83474-192">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-193">[Interfaccia ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="83474-194">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="83474-194">Obsolete.</span></span> <span data-ttu-id="83474-195">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="83474-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="83474-196">[Interfaccia ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="83474-197">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="83474-197">Obsolete.</span></span> <span data-ttu-id="83474-198">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="83474-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="83474-199">[Interfaccia ICorDebugEnum](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="83474-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="83474-200">Opera da interfaccia di base astratta per il debug degli enumeratori.</span><span class="sxs-lookup"><span data-stu-id="83474-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="83474-201">[Interfaccia ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="83474-202">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="83474-202">Obsolete.</span></span> <span data-ttu-id="83474-203">Non usare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="83474-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="83474-204">[Interfaccia ICorDebugEval](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="83474-205">Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="83474-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="83474-206">[Interfaccia ICorDebugEval2](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="83474-207">Estende `ICorDebugEval` per fornire il supporto per tipi generici.</span><span class="sxs-lookup"><span data-stu-id="83474-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="83474-208">[Interfaccia ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="83474-209">Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="83474-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="83474-210">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-211">[Interfaccia ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="83474-212">Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="83474-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="83474-213">[Interfaccia ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-214">Estende l'interfaccia [ICorDebugObjectValue](icordebugobjectvalue-interface.md) per fornire informazioni sulla traccia dello stack da un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="83474-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="83474-215">[Interfaccia ICorDebugFrame](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="83474-216">Rappresenta un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="83474-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="83474-217">[Interfaccia ICorDebugFrameEnum](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="83474-218">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="83474-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="83474-219">[Interfaccia ICorDebugFunction](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="83474-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="83474-220">Rappresenta una funzione o un metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="83474-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="83474-221">[Interfaccia ICorDebugFunction2](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="83474-222">Estende `ICorDebugFunction` a livello logico in modo da fornire il supporto per il debug passo a passo con l'opzione Just My Code attivata.</span><span class="sxs-lookup"><span data-stu-id="83474-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="83474-223">[Interfaccia ICorDebugFunction3](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="83474-224">Estende logicamente l'interfaccia [ICorDebugFunction](icordebugfunction-interface1.md) per fornire l'accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="83474-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="83474-225">[Interfaccia ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="83474-226">Estende `ICorDebugBreakpoint` per il supporto di punti di interruzione all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="83474-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="83474-227">[Interfaccia ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="83474-228">Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="83474-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="83474-229">[Interfaccia ICorDebugGenericValue](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-230">Sottoclasse di `ICorDebugValue` che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="83474-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="83474-231">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="83474-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="83474-232">[Interfaccia ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="83474-233">Fornisce un enumeratore per un oggetto che mappa i GUID e i relativi oggetti corrispondenti `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="83474-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="83474-234">[Interfaccia ICorDebugHandleValue](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="83474-235">Sottoclasse di `ICorDebugReferenceValue` che rappresenta un valore di riferimento per il quale il debugger ha creato un handle per la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="83474-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="83474-236">[Interfaccia ICorDebugHeapEnum](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="83474-237">Fornisce un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="83474-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="83474-238">[Interfaccia ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="83474-239">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="83474-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="83474-240">[Interfaccia ICorDebugHeapValue](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-241">Sottoclasse di `ICorDebugValue` che rappresenta un oggetto su cui è stata operata la Garbage Collection di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="83474-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="83474-242">[Interfaccia ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="83474-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="83474-243">Estensione di `ICorDebugHeapValue` che fornisce il supporto per gli handle del runtime.</span><span class="sxs-lookup"><span data-stu-id="83474-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="83474-244">[Interfaccia ICorDebugHeapValue3](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="83474-245">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="83474-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="83474-246">[Interfaccia ICorDebugILCode](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="83474-247">Rappresenta un segmento di codice di linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="83474-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="83474-248">[Interfaccia ICorDebugILCode2](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="83474-249">Estende logicamente l'interfaccia [ICorDebugILCode](icordebugilcode-interface.md) per fornire i metodi che restituiscono il token per la firma della variabile locale di una funzione e che mappano gli offset del linguaggio intermedio (il) instrumentato del profiler agli offset il di metodo originali.</span><span class="sxs-lookup"><span data-stu-id="83474-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="83474-250">[Interfaccia ICorDebugILFrame](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="83474-251">Rappresenta uno stack frame di codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="83474-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="83474-252">[Interfaccia ICorDebugILFrame2](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="83474-253">Estensione logica di `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="83474-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="83474-254">[Interfaccia ICorDebugILFrame3](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="83474-255">Fornisce un metodo che incapsula il valore restituito di una funzione.</span><span class="sxs-lookup"><span data-stu-id="83474-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="83474-256">[Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="83474-257">Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="83474-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="83474-258">L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.</span><span class="sxs-lookup"><span data-stu-id="83474-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="83474-259">[Interfaccia ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="83474-260">Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="83474-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="83474-261">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-262">[Interfaccia ICorDebugInternalFrame](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="83474-263">Identifica i tipi di frame per il debugger.</span><span class="sxs-lookup"><span data-stu-id="83474-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="83474-264">[Interfaccia ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="83474-265">Fornisce informazioni sui frame interni, inclusi l'indirizzo dello stack e la posizione in relazione agli oggetti [ICorDebugFrame](icordebugframe-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="83474-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="83474-266">[Interfaccia metodo icordebugloadedmodule](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="83474-267">Vengono fornite informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="83474-267">Provides information about a loaded module.</span></span> <span data-ttu-id="83474-268">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-269">[Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="83474-270">Fornisce metodi per l'elaborazione dei callback del debugger.</span><span class="sxs-lookup"><span data-stu-id="83474-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="83474-271">[Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="83474-272">Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="83474-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="83474-273">`ICorDebugManagedCallback2` è un'estensione logica di `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="83474-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="83474-274">[Interfaccia ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="83474-275">Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="83474-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="83474-276">[Interfaccia ICorDebugMDA](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="83474-277">Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).</span><span class="sxs-lookup"><span data-stu-id="83474-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="83474-278">[Interfaccia ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="83474-279">Rappresenta un buffer in memoria.</span><span class="sxs-lookup"><span data-stu-id="83474-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="83474-280">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-281">[Interfaccia metodo icordebugmergedassemblyrecord](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="83474-282">Fornisce informazioni su un assembly unito.</span><span class="sxs-lookup"><span data-stu-id="83474-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="83474-283">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-284">[Interfaccia ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="83474-285">Fornisce informazioni sui metadati al debugger.</span><span class="sxs-lookup"><span data-stu-id="83474-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="83474-286">[Interfaccia ICorDebugModule](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="83474-287">Rappresenta un modulo di Common Language Runtime che è un eseguibile o una DLL.</span><span class="sxs-lookup"><span data-stu-id="83474-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="83474-288">[Interfaccia ICorDebugModule2](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="83474-289">Opera come estensione logica di `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="83474-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="83474-290">[Interfaccia ICorDebugModule3](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="83474-291">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="83474-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="83474-292">[Interfaccia ICorDebugModuleBreakpoint](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="83474-293">Estende `ICorDebugBreakpoint` in modo da fornire accesso a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="83474-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="83474-294">[Interfaccia ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="83474-295">Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="83474-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="83474-296">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-297">[Interfaccia ICorDebugModuleEnum](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="83474-298">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="83474-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="83474-299">[Interfaccia ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="83474-300">Estende l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) per supportare destinazioni dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="83474-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="83474-301">[Interfaccia ICorDebugNativeFrame](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="83474-302">Implementazione specializzata di `ICorDebugFrame` usata per i frame nativi.</span><span class="sxs-lookup"><span data-stu-id="83474-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="83474-303">[Interfaccia ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="83474-304">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="83474-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="83474-305">[Interfaccia ICorDebugObjectEnum](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="83474-306">Implementa i metodi `ICorDebugEnum` ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA, Relative Virtual Address).</span><span class="sxs-lookup"><span data-stu-id="83474-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="83474-307">[Interfaccia ICorDebugObjectValue](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-308">Sottoclasse di `ICorDebugValue` che rappresenta un valore che contiene un oggetto.</span><span class="sxs-lookup"><span data-stu-id="83474-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="83474-309">[Interfaccia ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="83474-310">Estende `ICorDebugObjectValue` per fornire il supporto per l'ereditarietà e gli override.</span><span class="sxs-lookup"><span data-stu-id="83474-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="83474-311">[Interfaccia ICorDebugProcess](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="83474-312">Rappresenta un processo che esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="83474-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="83474-313">[Interfaccia ICorDebugProcess2](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="83474-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="83474-314">Estensione logica di `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="83474-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="83474-315">[Interfaccia ICorDebugProcess3](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="83474-316">Controlla le notifiche di debugger personalizzate.</span><span class="sxs-lookup"><span data-stu-id="83474-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="83474-317">[Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="83474-318">Fornisce supporto per il controllo dell'esecuzione out-of-process.</span><span class="sxs-lookup"><span data-stu-id="83474-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="83474-319">[Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="83474-320">Estende l'interfaccia [ICorDebugProcess](icordebugprocess-interface.md) per supportare l'accesso all'heap gestito, per fornire informazioni su Garbage Collection di oggetti gestiti e per determinare se un debugger carica immagini dalla cache delle immagini native locali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83474-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="83474-321">[Interfaccia metodo icordebugprocess6](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="83474-322">Estende logicamente l'interfaccia [ICorDebugProcess](icordebugprocess-interface.md) per abilitare funzionalità come la decodifica degli eventi di debug gestiti codificati negli eventi di debug delle eccezioni native e la suddivisione dei moduli virtuali.</span><span class="sxs-lookup"><span data-stu-id="83474-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="83474-323">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-324">[Interfaccia ICorDebugProcess7](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="83474-325">Fornisce un metodo di configurazione del debugger per consentire la gestione degli aggiornamenti dei metadati in memoria nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83474-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="83474-326">[Interfaccia ICorDebugProcess8](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="83474-327">Estende logicamente l'interfaccia [ICorDebugProcess](icordebugprocess-interface.md) per abilitare o disabilitare determinati tipi di callback di eccezione [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="83474-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="83474-328">[Interfaccia ICorDebugProcessEnum](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="83474-329">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="83474-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="83474-330">[Interfaccia ICorDebugReferenceValue](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="83474-331">Sottoclasse di `ICorDebugValue` che supporta i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="83474-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="83474-332">[Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="83474-333">Rappresenta l'insieme dei registri disponibili sul computer in cui è in corso l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="83474-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="83474-334">[Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="83474-335">Estende le funzionalità di `ICorDebugRegisterSet` per le piattaforme hardware con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="83474-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="83474-336">[Interfaccia ICorDebugRemote](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="83474-337">Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="83474-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="83474-338">[Interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="83474-339">Fornisce metodi che consentono di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR.</span><span class="sxs-lookup"><span data-stu-id="83474-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="83474-340">[Interfaccia ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="83474-341">Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.</span><span class="sxs-lookup"><span data-stu-id="83474-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="83474-342">[Interfaccia ICorDebugStackWalk](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="83474-343">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="83474-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="83474-344">[Interfaccia ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="83474-345">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="83474-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="83474-346">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-347">[Interfaccia ICorDebugStepper](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="83474-348">Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="83474-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="83474-349">[Interfaccia ICorDebugStepper2](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="83474-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="83474-350">Fornisce il supporto per il debug Just My Code (JMC).</span><span class="sxs-lookup"><span data-stu-id="83474-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="83474-351">[Interfaccia ICorDebugStepperEnum](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="83474-352">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="83474-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="83474-353">[Interfaccia ICorDebugStringValue](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="83474-354">Sottoclasse di `ICorDebugHeapValue` che si applica ai valori stringa.</span><span class="sxs-lookup"><span data-stu-id="83474-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="83474-355">[Interfaccia metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="83474-356">Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="83474-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="83474-357">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-358">[Interfaccia ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="83474-359">Estende logicamente l'interfaccia [Metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md) per recuperare informazioni aggiuntive sul simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="83474-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="83474-360">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-361">\ dell' [interfaccia ICorDebugThread](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-361">[ICorDebugThread Interface](icordebugthread-interface.md)\</span></span>
 <span data-ttu-id="83474-362">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="83474-362">Represents a thread in a process.</span></span> <span data-ttu-id="83474-363">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="83474-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="83474-364">[Interfaccia ICorDebugThread2](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="83474-365">Opera come estensione logica di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="83474-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="83474-366">[Interfaccia ICorDebugThread3](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="83474-367">Fornisce il punto di ingresso per [ICorDebugStackWalk](icordebugstackwalk-interface.md) e le interfacce corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="83474-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="83474-368">[Interfaccia ICorDebugThread4](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="83474-369">Fornisce informazioni sui blocchi dei thread.</span><span class="sxs-lookup"><span data-stu-id="83474-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="83474-370">[Interfaccia ICorDebugThreadEnum](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="83474-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="83474-371">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="83474-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="83474-372">[Interfaccia ICorDebugType](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="83474-373">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="83474-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="83474-374">Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="83474-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="83474-375">[Interfaccia metodo icordebugtype2](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="83474-376">Estende l'interfaccia [ICorDebugType](icordebugtype-interface.md) per recuperare l'identificatore di tipo di un tipo di base o di un tipo complesso (definito dall'utente).</span><span class="sxs-lookup"><span data-stu-id="83474-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="83474-377">[Interfaccia ICorDebugTypeEnum](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="83474-378">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="83474-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="83474-379">[Interfaccia ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="83474-380">Notifica gli eventi nativi non direttamente correlati a Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="83474-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="83474-381">\ [ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-381">[ICorDebugValue](icordebugvalue-interface.md)\</span></span>
 <span data-ttu-id="83474-382">Rappresenta un valore di lettura o scrittura nel processo in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="83474-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="83474-383">\ [ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-383">[ICorDebugValue2](icordebugvalue2-interface.md)\</span></span>
 <span data-ttu-id="83474-384">Estende `ICorDebugValue` in modo da fornire il supporto per `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="83474-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="83474-385">[Interfaccia ICorDebugValue3](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="83474-386">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire supporto per matrici di dimensioni maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="83474-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="83474-387">\ [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\</span></span>
 <span data-ttu-id="83474-388">Estende `ICorDebugBreakpoint` in modo da fornire accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="83474-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="83474-389">\ [ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\</span></span>
 <span data-ttu-id="83474-390">Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="83474-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="83474-391">[Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="83474-392">Rappresenta una variabile locale o un argomento di una funzione.</span><span class="sxs-lookup"><span data-stu-id="83474-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="83474-393">[Interfaccia ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="83474-394">Fornisce un enumeratore per le variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="83474-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="83474-395">[Interfaccia metodo icordebugvariablesymbol](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="83474-396">Recupera le informazioni relative al simbolo di debug per una variabile.</span><span class="sxs-lookup"><span data-stu-id="83474-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="83474-397">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-398">[Interfaccia ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="83474-399">Fornisce metodi che facilitano lo svuotamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="83474-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="83474-400">**Disponibile solo su .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="83474-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="83474-401">[Interfaccia ICorPublish](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="83474-402">Opera come interfaccia generica per i processi di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="83474-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="83474-403">[Interfaccia ICorPublishAppDomain](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="83474-404">Rappresenta e fornisce informazioni su un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="83474-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="83474-405">[Interfaccia ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="83474-406">Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishAppDomain` attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="83474-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="83474-407">[Interfaccia ICorPublishEnum](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="83474-408">Opera da base astratta per la pubblicazione di enumeratori.</span><span class="sxs-lookup"><span data-stu-id="83474-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="83474-409">[Interfaccia ICorPublishProcess](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="83474-410">Fornisce metodi che accedono alle informazioni su un processo.</span><span class="sxs-lookup"><span data-stu-id="83474-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="83474-411">[Interfaccia ICorPublishProcessEnum](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="83474-412">Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="83474-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="83474-413">[Interfaccia ISOSDacInterface](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="83474-414">Fornisce metodi helper per accedere ai dati da `SOS`.</span><span class="sxs-lookup"><span data-stu-id="83474-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="83474-415">[Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="83474-416">Fornisce metodi per eseguire query sulle informazioni relative a una definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="83474-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="83474-417">[Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="83474-418">Fornisce metodi per l'esecuzione di query sulle informazioni relative a un'istanza di metodo.</span><span class="sxs-lookup"><span data-stu-id="83474-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="83474-419">[Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="83474-420">Fornisce metodi per eseguire query sulle informazioni relative a un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="83474-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="83474-421">[Interfaccia IXCLRDataProcess](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="83474-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="83474-422">Fornisce metodi per l'esecuzione di query sulle informazioni relative a un processo.</span><span class="sxs-lookup"><span data-stu-id="83474-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="83474-423">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="83474-423">Related Sections</span></span>  
 <span data-ttu-id="83474-424">[Coclassi di debug](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="83474-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="83474-425">[Debug di funzioni statiche globali](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="83474-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="83474-426">[Enumerazioni di debug](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="83474-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="83474-427">[Strutture di debug](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="83474-427">[Debugging Structures](debugging-structures.md)</span></span>\
