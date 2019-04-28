---
title: Strutture di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50db519410b9513725c3dc10637421ba8bb37ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698364"
---
# <a name="debugging-structures"></a><span data-ttu-id="af066-102">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="af066-102">Debugging Structures</span></span>

<span data-ttu-id="af066-103">Questa sezione descrive le strutture non gestite usate dall'API di debug.</span><span class="sxs-lookup"><span data-stu-id="af066-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="af066-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="af066-104">In This Section</span></span>
 <span data-ttu-id="af066-105">[Struttura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) definisce un intervallo di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="af066-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="af066-106">[Struttura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) definisce un livello di integrità per il mapping dell'indirizzo</span><span class="sxs-lookup"><span data-stu-id="af066-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="af066-107">[Struttura CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) definisce la versione del prodotto di common language runtime (CLR) per scopi di debug.</span><span class="sxs-lookup"><span data-stu-id="af066-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="af066-108">[Struttura CodeChunkInfo](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="af066-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="af066-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) contiene informazioni sulle funzioni attualmente attive nel frame di un thread.</span><span class="sxs-lookup"><span data-stu-id="af066-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="af066-110">[Struttura COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) fornisce informazioni sul layout di un oggetto matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="af066-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="af066-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) contiene gli offset utilizzati per eseguire il mapping di Microsoft intermediate language (MSIL) del codice in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="af066-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="af066-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) contiene le informazioni sugli offset per un intervallo di codice.</span><span class="sxs-lookup"><span data-stu-id="af066-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="af066-113">[Struttura COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="af066-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="af066-114">[Struttura COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) contiene informazioni su un oggetto che deve essere sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="af066-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="af066-115">[Struttura COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) fornisce informazioni generali sull'heap di garbage collection, ad esempio se è enumerabile.</span><span class="sxs-lookup"><span data-stu-id="af066-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="af066-116">[Struttura COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="af066-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="af066-117">[COR_IL_MAP](cor-il-map-structure.md) specifica le modifiche nell'offset relativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="af066-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="af066-118">[Struttura COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) contiene informazioni su un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="af066-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="af066-119">[Struttura COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) contiene un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="af066-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="af066-120">[Struttura COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) fornisce informazioni sul layout di un oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="af066-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="af066-121">[COR_VERSION](cor-version-structure.md) archivia il numero di versione in quattro parti standard di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="af066-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="af066-122">[Struttura CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) definisce un oggetto che blocca un thread e il motivo per cui il thread è bloccato.</span><span class="sxs-lookup"><span data-stu-id="af066-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="af066-123">[Struttura CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) rappresenta una clausola di gestione (EH) eccezione per una determinata parte del linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="af066-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="af066-124">[Struttura CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) rappresenta le informazioni di frame da un oggetto eccezione dello stack.</span><span class="sxs-lookup"><span data-stu-id="af066-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="af066-125">[Struttura CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) mappe una [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID per il corrispondente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="af066-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="af066-126">[Struttura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) definisce il contenitore per una richiesta del modulo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="af066-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="af066-127">[Struttura DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) definisce un buffer di trasporto per le informazioni di runtime del metodo.</span><span class="sxs-lookup"><span data-stu-id="af066-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="af066-128">[Struttura DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) definisce un buffer di trasporto per le informazioni di runtime del modulo.</span><span class="sxs-lookup"><span data-stu-id="af066-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="af066-129">[Struttura DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) definisce le informazioni di base per un determinato metodo instrumentato del profiler.</span><span class="sxs-lookup"><span data-stu-id="af066-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="af066-130">[Struttura StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) fornisce un contesto semplice che può essere usato al posto di una procedura completa `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="af066-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="af066-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="af066-131">Related Sections</span></span>

 [<span data-ttu-id="af066-132">Coclassi di debug</span><span class="sxs-lookup"><span data-stu-id="af066-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="af066-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="af066-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="af066-134">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="af066-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="af066-135">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="af066-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="af066-136">Debug</span><span class="sxs-lookup"><span data-stu-id="af066-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
