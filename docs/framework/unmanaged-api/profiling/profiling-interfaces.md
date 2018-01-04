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
ms.workload: dotnet
ms.openlocfilehash: 4f8c2a5ce5e1231c55f598e48d14bec896a4b5f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-interfaces"></a>Interfacce di profilatura
Questa sezione descrive le interfacce non gestite che consentono di definire il profilo di un programma eseguito da Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Interfaccia ICLRProfiling](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 Fornisce il [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) metodo, che consente a un profiler di connettersi a un processo in esecuzione.  
  
 [Interfaccia ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 Consente al profiler di indicare a CLR di riferimenti ad assembly che verranno aggiunti nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.  
  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 Fornisce i metodi usati da CLR per indicare a un Code Profiler il verificarsi degli eventi ai quali il profiler ha effettuato la sottoscrizione.  
  
 [Interfaccia ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 Estende l'interfaccia `ICorProfilerCallback` con callback supportati in .NET Framework 2.0 e versioni successive.  
  
 [Interfaccia ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 Fornisce metodi di callback usati da CLR per comunicare informazioni sullo stato di connessione e disconnessione al profiler.  
  
 [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 Fornisce metodi di callback usati da CLR per comunicare informazioni al profiler.  
  
 [Interfaccia ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 Fornisce un metodo che identifica la chiusura transitiva di oggetti a cui fanno riferimento le radici di Garbage Collection.  
  
 [Interfaccia ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 Fornisce un metodo di callback usato da CLR per indicare a un profiler che un assembly è in fase di caricamento.  
  
 [Interfaccia ICorProfilerCallback7](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 Fornisce un metodo di callback che usa common language runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria viene aggiornato.  
  
 [Interfaccia ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 Fornisce metodi che consentono a un Code Profiler di comunicare con CLR per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di un metodo specifico.  
  
 [Interfaccia ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in CLR.  
  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.  
  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 Estende l'interfaccia `ICorProfilerInfo` con metodi supportati in .NET Framework 2.0 e versioni successive.  
  
 [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 Estende l'interfaccia `ICorProfilerInfo2` con metodi supportati in [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] e versioni successive.  
  
 [Interfaccia ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.  
  
 [Interfaccia ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi.  
  
 [Interfaccia ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 Fornisce un enumeratore per tutti i metodi che appartengono a un determinato modulo NGen e che vengono impostati come inline nel corpo di un metodo specificato.  
  
 [Interfaccia ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 Fornisce un metodo per applicare appena definito i metadati per un modulo e che fornisce l'accesso a un flusso di simboli in memoria.  
  
 [Interfaccia ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.  
  
 [Interfaccia ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 Fornisce metodi per scorrere in sequenza una raccolta di oggetti bloccati generati da [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
 [Interfaccia ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di thread in CLR.  
  
 [Interfaccia IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 Fornisce il [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) per allocare memoria per un nuovo corpo della funzione Microsoft intermediate language (MSIL).  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica della profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
