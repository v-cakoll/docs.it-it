---
title: Funzioni statiche globali di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bb5d93c91de857ebbee63009cad73fba7e1d284
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="profiling-global-static-functions"></a>Funzioni statiche globali di profilatura
Questa sezione descrive le funzioni API non gestite usate dall'API di profilatura.  
  
## <a name="in-this-section"></a>In questa sezione  
  
## <a name="net-framework-version-1-profiling-functions"></a>Funzioni di profilatura di .NET framework versione 1  
 [Funzione FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Notifica al profiler di controllo viene passato a una funzione. Obsoleto in .NET Framework 2.0.  
  
 [Funzione FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Notifica al profiler che una funzione sta per restituire al chiamante. Obsoleto in .NET Framework 2.0.  
  
 [Funzione FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail a un'altra funzione. Obsoleto in .NET Framework 2.0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Funzioni di profilatura di .NET framework versione 2  
 [Funzione FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da utilizzare per il [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), e [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) i callback per tale funzione. Consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione  
  
 [Funzione FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Notifica al profiler che controllo viene passato a una funzione e fornisce informazioni sullo stack di frame e funzione gli argomenti. Obsoleto nel [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Notifica al profiler che una funzione sta per restituire al chiamante e fornisce informazioni sul valore restituito dello stack frame e la funzione. Obsoleto nel [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sullo stack frame. Obsoleto nel [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Fornisce informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti nello stack durante un'analisi dello stack, che viene avviata dal profiler di [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) metodo.  
  
## <a name="net-framework-version-4-profiling-functions"></a>Funzioni di profilatura di .NET framework versione 4  
 [Funzione FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da utilizzare per il [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), e [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), o[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), e [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) i callback per tale funzione. Consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione.  
  
 `FunctionIDMapper2` estende la [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) funzione con un `clientData` parametro, i profiler possono usare per distinguere tra runtime.  
  
 [Funzione FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Notifica al profiler di controllo viene passato a una funzione.  
  
 [Funzione FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Notifica al profiler di controllo viene passato a una funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare gli argomenti di stack frame e la funzione.  
  
 [Funzione FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Notifica al profiler che controllo viene restituito da una funzione.  
  
 [Funzione FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Notifica al profiler che controllo viene restituito da una funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) per recuperare lo stack frame e il valore restituito.  
  
 [Funzione FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail a un'altra funzione.  
  
 [Funzione FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail a un'altra funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: Getfunctiontailcall3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) per recuperare lo stack frame.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica della profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
