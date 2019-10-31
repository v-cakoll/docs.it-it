---
title: Strutture di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: 05a321d5025f03d6a0378b462178bf06c0291f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123025"
---
# <a name="debugging-structures"></a>Strutture di debug

Questa sezione descrive le strutture non gestite usate dall'API di debug.

## <a name="in-this-section"></a>Contenuto della sezione
 [Struttura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Definisce un intervallo di indirizzi.

 [Struttura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Definisce un oggetto per IL mapping

 [Struttura CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Definisce la versione del prodotto del Common Language Runtime (CLR) a scopo di debug.

 [Struttura CodeChunkInfo](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Rappresenta un singolo blocco di codice in memoria.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contiene informazioni sulle funzioni attualmente attive nei frame di un thread.

 [Struttura COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Fornisce informazioni sul layout di un oggetto matrice in memoria.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contiene gli offset utilizzati per eseguire il mapping del codice MSIL (Microsoft Intermediate Language) al codice nativo.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contiene le informazioni sull'offset per un intervallo di codice.

 [Struttura COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Fornisce informazioni su un campo in un oggetto.

 [Struttura COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contiene informazioni su un oggetto di cui è necessario eseguire il Garbage Collector.

 [Struttura COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Vengono fornite informazioni generali sull'heap di Garbage Collection, inclusa la possibilità di enumerarli.

 [Struttura COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Fornisce informazioni su un oggetto nell'heap gestito.

 [COR_IL_MAP](cor-il-map-structure.md) Specifica le modifiche nell'offset relativo di una funzione.

 [Struttura COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contiene informazioni su un'area di memoria nell'heap gestito.

 [Struttura COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contiene un identificatore di tipo.

 [Struttura COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Fornisce informazioni sul layout di un oggetto in memoria.

 [COR_VERSION](cor-version-structure.md) Archivia il numero di versione in quattro parti standard del Common Language Runtime.

 [Struttura CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Definisce un oggetto che blocca un thread e il motivo per cui il thread è bloccato.

 [Struttura CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Rappresenta una clausola di gestione delle eccezioni (EH) per una determinata parte di linguaggio intermedio (IL).

 [Struttura CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Rappresenta stack frame informazioni di un oggetto eccezione.

 [Struttura CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Esegue il mapping di un GUID Windows Runtime al relativo oggetto [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) corrispondente.

 [Struttura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Definisce il contenitore per una richiesta di indirizzo del modulo.

 [Struttura DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Definisce un buffer di trasporto per le informazioni di runtime di un metodo.

 [Struttura DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Definisce un buffer di trasporto per le informazioni di runtime di un modulo.

 [Struttura DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Definisce le informazioni di base su un metodo instrumentato fornito dal profiler.

 [Struttura StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Fornisce un contesto semplice che può essere utilizzato al posto di una struttura di `CONTEXT` completa.

## <a name="related-sections"></a>Sezioni correlate

 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
