---
title: Strutture di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: a18094fb2621478dbdb4bbf672df436234112ed0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793748"
---
# <a name="debugging-structures"></a><span data-ttu-id="35717-102">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="35717-102">Debugging Structures</span></span>

<span data-ttu-id="35717-103">Questa sezione descrive le strutture non gestite usate dall'API di debug.</span><span class="sxs-lookup"><span data-stu-id="35717-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="35717-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="35717-104">In This Section</span></span>
 <span data-ttu-id="35717-105">[Struttura CLRDATA_ADDRESS_RANGE](clrdata-address-range-structure.md) Definisce un intervallo di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="35717-105">[CLRDATA_ADDRESS_RANGE Structure](clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="35717-106">[Struttura CLRDATA_IL_ADDRESS_MAP](clrdata-il-address-map-structure.md) Definisce un oggetto per IL mapping</span><span class="sxs-lookup"><span data-stu-id="35717-106">[CLRDATA_IL_ADDRESS_MAP Structure](clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="35717-107">[Struttura CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) Definisce la versione del prodotto del Common Language Runtime (CLR) a scopo di debug.</span><span class="sxs-lookup"><span data-stu-id="35717-107">[CLR_DEBUGGING_VERSION Structure](clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="35717-108">[Struttura CodeChunkInfo](codechunkinfo-structure.md) Rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="35717-108">[CodeChunkInfo Structure](codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="35717-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contiene informazioni sulle funzioni attualmente attive nei frame di un thread.</span><span class="sxs-lookup"><span data-stu-id="35717-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="35717-110">[Struttura COR_ARRAY_LAYOUT](cor-array-layout-structure.md) Fornisce informazioni sul layout di un oggetto matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="35717-110">[COR_ARRAY_LAYOUT Structure](cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="35717-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contiene gli offset utilizzati per eseguire il mapping del codice MSIL (Microsoft Intermediate Language) al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="35717-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="35717-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contiene le informazioni sull'offset per un intervallo di codice.</span><span class="sxs-lookup"><span data-stu-id="35717-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="35717-113">[Struttura COR_FIELD](cor-field-structure.md) Fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="35717-113">[COR_FIELD Structure](cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="35717-114">[Struttura COR_GC_REFERENCE](cor-gc-reference-structure.md) Contiene informazioni su un oggetto di cui è necessario eseguire il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="35717-114">[COR_GC_REFERENCE Structure](cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="35717-115">[Struttura COR_HEAPINFO](cor-heapinfo-structure.md) Vengono fornite informazioni generali sull'heap di Garbage Collection, inclusa la possibilità di enumerarli.</span><span class="sxs-lookup"><span data-stu-id="35717-115">[COR_HEAPINFO Structure](cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="35717-116">[Struttura COR_HEAPOBJECT](cor-heapobject-structure.md) Fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="35717-116">[COR_HEAPOBJECT Structure](cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="35717-117">[COR_IL_MAP](cor-il-map-structure.md) Specifica le modifiche nell'offset relativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="35717-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="35717-118">[Struttura COR_SEGMENT](cor-segment-structure.md) Contiene informazioni su un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="35717-118">[COR_SEGMENT Structure](cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="35717-119">[Struttura COR_TYPEID](cor-typeid-structure.md) Contiene un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="35717-119">[COR_TYPEID Structure](cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="35717-120">[Struttura COR_TYPE_LAYOUT](cor-type-layout-structure.md) Fornisce informazioni sul layout di un oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="35717-120">[COR_TYPE_LAYOUT Structure](cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="35717-121">[COR_VERSION](cor-version-structure.md) Archivia il numero di versione in quattro parti standard del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="35717-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="35717-122">[Struttura CorDebugBlockingObject](cordebugblockingobject-structure.md) Definisce un oggetto che blocca un thread e il motivo per cui il thread è bloccato.</span><span class="sxs-lookup"><span data-stu-id="35717-122">[CorDebugBlockingObject Structure](cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="35717-123">[Struttura CorDebugEHClause](cordebugehclause-structure.md) Rappresenta una clausola di gestione delle eccezioni (EH) per una determinata parte di linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="35717-123">[CorDebugEHClause Structure](cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="35717-124">[Struttura CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) Rappresenta stack frame informazioni di un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="35717-124">[CorDebugExceptionObjectStackFrame Structure](cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="35717-125">[Struttura CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) Esegue il mapping di un GUID Windows Runtime al relativo oggetto [ICorDebugType](icordebugtype-interface.md) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="35717-125">[CorDebugGuidToTypeMapping Structure](cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="35717-126">[Struttura DacpGetModuleAddress](dacpgetmoduleaddress-structure.md) Definisce il contenitore per una richiesta di indirizzo del modulo.</span><span class="sxs-lookup"><span data-stu-id="35717-126">[DacpGetModuleAddress Structure](dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="35717-127">[Struttura DacpMethodDescData](dacpmethoddescdata-structure.md) Definisce un buffer di trasporto per le informazioni di runtime di un metodo.</span><span class="sxs-lookup"><span data-stu-id="35717-127">[DacpMethodDescData Structure](dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="35717-128">[Struttura DacpModuleData](dacpmoduledata-structure.md) Definisce un buffer di trasporto per le informazioni di runtime di un modulo.</span><span class="sxs-lookup"><span data-stu-id="35717-128">[DacpModuleData Structure](dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="35717-129">[Struttura DacpReJitData](dacprejitdata-structure.md) Definisce le informazioni di base su un metodo instrumentato fornito dal profiler.</span><span class="sxs-lookup"><span data-stu-id="35717-129">[DacpReJitData Structure](dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="35717-130">[Struttura StackTrace_SimpleContext](stacktrace-simplecontext-structure.md) Fornisce un contesto semplice che può essere utilizzato al posto di una struttura di `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="35717-130">[StackTrace_SimpleContext Structure](stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="35717-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="35717-131">Related Sections</span></span>

 [<span data-ttu-id="35717-132">Coclassi di debug</span><span class="sxs-lookup"><span data-stu-id="35717-132">Debugging Coclasses</span></span>](debugging-coclasses.md)

 [<span data-ttu-id="35717-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="35717-133">Debugging Interfaces</span></span>](debugging-interfaces.md)

 [<span data-ttu-id="35717-134">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="35717-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

 [<span data-ttu-id="35717-135">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="35717-135">Debugging Enumerations</span></span>](debugging-enumerations.md)

 [<span data-ttu-id="35717-136">Debug</span><span class="sxs-lookup"><span data-stu-id="35717-136">Debugging</span></span>](index.md)
