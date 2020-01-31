---
title: Enumerazioni di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 1a9781fa1b4b608152faa7d5edc80bd4866f0c81
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868135"
---
# <a name="profiling-enumerations"></a>Enumerazioni di profilatura
Questa sezione descrive le enumerazioni non gestite usate dall'API di profilatura.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Enumerazione COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md)  
 Indica il tipo di clausola di eccezione in cui il codice è appena entrato o da cui è appena uscito.  
  
 [Enumerazione COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)  
 Definisce i flag di generazione del codice che possono essere impostati con il metodo [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) .  
  
 [Enumerazione COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md)  
 Descrive il finalizzatore per un oggetto.  
  
 [Enumerazione COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md)  
 Identifica una generazione di Garbage Collection.  
  
 [Enumerazione COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md)  
 Indica il motivo per cui è in corso la Garbage Collection.  
  
 [Enumerazione COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md)  
 Indica le proprietà della radice di un Garbage Collector.  
  
 [Enumerazione COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md)  
 Indica il tipo di Garbage Collector radice esposto dal callback [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .  
  
 [Enumerazione COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)  
 Fornisce i flag oltre a quelli disponibili nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) che il profiler può specificare al metodo [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) durante il caricamento.  
  
 [Enumerazione COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md)  
 Indica il risultato della ricerca di una funzione memorizzata nella cache.  
  
 [Enumerazione COR_PRF_MISC](cor-prf-misc-enumeration.md)  
 Contiene valori costanti che specificano identificatori speciali.  
  
 [Enumerazione COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md)  
 Specifica le proprietà di un modulo.  
  
 [Enumerazione COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)  
 Contiene i valori usati per specificare il comportamento, le funzionalità o gli eventi ai quali il profiler intende effettuare la sottoscrizione.  
  
 [Enumerazione COR_PRF_RUNTIME_TYPE](cor-prf-runtime-type-enumeration.md)  
 Contiene valori che indicano la versione di Common Language Runtime.  
  
 [Enumerazione COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md)  
 Specifica la quantità di dati da passare di nuovo con uno snapshot dello stack in ogni chiamata alla funzione `StackSnapshotCallback` del profiler.  
  
 [Enumerazione COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md)  
 Indica se un campo è statico e, in tal caso, la qualità statica che si applica al campo.  
  
 [Enumerazione COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md)  
 Indica il motivo per cui il runtime è stato sospeso.  
  
 [Enumerazione COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md)  
 Indica il motivo di una transizione da codice gestito a codice non gestito o viceversa.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica della profilatura](profiling-overview.md)  
  
 [Interfacce di profilatura](profiling-interfaces.md)  
  
 [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)  
  
 [Strutture di profilatura](profiling-structures.md)
