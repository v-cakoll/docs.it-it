---
title: Interfacce di profilatura
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: 8b6b9acff2945e2d8fd684bfa31e4af086ea5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868148"
---
# <a name="profiling-interfaces"></a>Interfacce di profilatura
Questa sezione descrive le interfacce non gestite che consentono di definire il profilo di un programma eseguito da Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Interfaccia ICLRProfiling](iclrprofiling-interface.md)  
 Fornisce il metodo [AttachProfiler](iclrprofiling-attachprofiler-method.md) , che consente a un profiler di connettersi a un processo in esecuzione.  
  
 [Interfaccia ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)  
 Consente al profiler di indicare a CLR i riferimenti ad assembly che saranno aggiunti dal profiler nel callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
 [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)  
 Fornisce i metodi usati da CLR per indicare a un Code Profiler il verificarsi degli eventi ai quali il profiler ha effettuato la sottoscrizione.  
  
 [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)  
 Estende l'interfaccia `ICorProfilerCallback` con callback supportati in .NET Framework 2.0 e versioni successive.  
  
 [Interfaccia ICorProfilerCallback3](icorprofilercallback3-interface.md)  
 Fornisce metodi di callback usati da CLR per comunicare informazioni sullo stato di connessione e disconnessione al profiler.  
  
 [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)  
 Fornisce metodi di callback usati da CLR per comunicare informazioni al profiler.  
  
 [Interfaccia ICorProfilerCallback5](icorprofilercallback5-interface.md)  
 Fornisce un metodo che identifica la chiusura transitiva di oggetti a cui fanno riferimento le radici di Garbage Collection.  
  
 [Interfaccia ICorProfilerCallback6](icorprofilercallback6-interface.md)  
 Fornisce un metodo di callback usato da CLR per indicare a un profiler che un assembly è in fase di caricamento.  
  
 [Interfaccia ICorProfilerCallback7](icorprofilercallback7-interface.md)  
 Fornisce un metodo di callback usato dal Common Language Runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.  

[Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)  
Fornisce metodi di callback utilizzati dal Common Language Runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è stata avviata e completata.

[Interfaccia ICorProfilerCallback9](icorprofilercallback9-interface.md)  
Fornisce un metodo di callback utilizzato dal Common Language Runtime per notificare al profiler che un metodo dinamico viene sottoposta a Garbage Collection e successivamente scaricato.

 [Interfaccia ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md)  
 Fornisce metodi che consentono a un Code Profiler di comunicare con CLR per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di un metodo specifico.  
  
 [Interfaccia ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)  
 Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in CLR.  
  
 [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)  
 Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.  
  
 [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)  
 Estende l'interfaccia `ICorProfilerInfo` con metodi supportati in .NET Framework 2.0 e versioni successive.  
  
 [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)  
 Estende l'interfaccia `ICorProfilerInfo2` con i metodi supportati in .NET Framework 4 e versioni successive.  
  
 [Interfaccia ICorProfilerInfo4](icorprofilerinfo4-interface.md)  
 Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi e richiedere informazioni.  
  
 [Interfaccia ICorProfilerInfo5](icorprofilerinfo5-interface.md)  
 Fornisce metodi che i Code Profiler possono usare per comunicare con CLR allo scopo di controllare il monitoraggio di eventi.  
  
 [Interfaccia ICorProfilerInfo6](icorprofilerinfo6-interface.md)  
 Fornisce un enumeratore per tutti i metodi che appartengono a un modulo NGen specificato e che sono inline nel corpo di un determinato metodo.  
  
 [Interfaccia ICorProfilerInfo7](icorprofilerinfo7-interface.md)  
 Fornisce un metodo per applicare i metadati appena definiti a un modulo e che fornisce l'accesso a un flusso di simboli in memoria.  
  
 [Interfaccia ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)  
 Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.  
  
 [Interfaccia ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)  
 Fornisce metodi per scorrere in sequenza una raccolta di oggetti bloccati generati da [NGen. exe (Generatore di immagini native)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
 [Interfaccia ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)  
 Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di thread in CLR.  
  
 [Interfaccia IMethodMalloc](imethodmalloc-interface.md)  
 Fornisce il metodo [Alloc](imethodmalloc-alloc-method.md) per allocare memoria per un nuovo corpo della funzione MSIL (Microsoft Intermediate Language).  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica della profilatura](profiling-overview.md)  
  
 [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)  
  
 [Enumerazioni di profilatura](profiling-enumerations.md)  
  
 [Strutture di profilatura](profiling-structures.md)
