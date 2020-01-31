---
title: Funzioni statiche globali di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 20ee2a9e045d839aa8ac043e035c438986b987ef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860866"
---
# <a name="profiling-global-static-functions"></a>Funzioni statiche globali di profilatura
Questa sezione descrive le funzioni API non gestite utilizzate dall'API di profilatura.  
  
## <a name="in-this-section"></a>In questa sezione  
  
## <a name="net-framework-version-1-profiling-functions"></a>Funzioni di profilatura .NET Framework versione 1  
 [Funzione FunctionEnter](functionenter-function.md)  
 Notifica al profiler che il controllo viene passato a una funzione. Deprecato nella .NET Framework 2,0.  
  
 [Funzione FunctionLeave](functionleave-function.md)  
 Notifica al profiler che una funzione sta per tornare al chiamante. Deprecato nella .NET Framework 2,0.  
  
 [Funzione FunctionTailcall](functiontailcall-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione. Deprecato nella .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Funzioni di profilatura .NET Framework versione 2  
 [Funzione FunctionIDMapper](functionidmapper-function.md)  
 Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da usare nei callback [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)e [FunctionTailcall2](functiontailcall2-function.md) per tale funzione. Consente inoltre al profiler di indicare se si desidera ricevere callback per tale funzione  
  
 [Funzione FunctionEnter2](functionenter2-function.md)  
 Notifica al profiler che il controllo viene passato a una funzione e fornisce informazioni sugli stack frame e sugli argomenti della funzione. Deprecato nell'.NET Framework 4.  
  
 [Funzione FunctionLeave2](functionleave2-function.md)  
 Notifica al profiler che una funzione sta per tornare al chiamante e fornisce informazioni sull'stack frame e sul valore restituito della funzione. Deprecato nell'.NET Framework 4.  
  
 [Funzione FunctionTailcall2](functiontailcall2-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sul stack frame. Deprecato nell'.NET Framework 4.  
  
 [Funzione StackSnapshotCallback](stacksnapshotcallback-function.md)  
 Fornisce al profiler informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti nello stack durante un percorso stack, avviato dal metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="net-framework-version-4-profiling-functions"></a>Funzioni di profilatura .NET Framework versione 4  
 [Funzione FunctionIDMapper2](functionidmapper2-function.md)  
 Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da usare nei callback [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) per tale funzione. Consente inoltre al profiler di indicare se si desidera ricevere callback per tale funzione.  
  
 `FunctionIDMapper2` estende la funzione [FunctionIDMapper](functionidmapper-function.md) con un parametro `clientData`, che i profiler possono usare per evitare ambiguità tra i Runtime.  
  
 [Funzione FunctionEnter3](functionenter3-function.md)  
 Notifica al profiler che il controllo viene passato a una funzione.  
  
 [Funzione FunctionEnter3WithInfo](functionenter3withinfo-function.md)  
 Notifica al profiler che il controllo viene passato a una funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare gli argomenti della funzione e del stack frame.  
  
 [Funzione FunctionLeave3](functionleave3-function.md)  
 Notifica al profiler che il controllo viene restituito da una funzione.  
  
 [Funzione FunctionLeave3WithInfo](functionleave3withinfo-function.md)  
 Notifica al profiler che il controllo viene restituito da una funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) per recuperare il stack frame e il valore restituito.  
  
 [Funzione FunctionTailcall3](functiontailcall3-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione.  
  
 [Funzione FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)  
 Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce un handle che può essere passato a [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) per recuperare il stack frame.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica della profilatura](profiling-overview.md)  
  
 [Interfacce di profilatura](profiling-interfaces.md)  
  
 [Enumerazioni di profilatura](profiling-enumerations.md)  
  
 [Strutture di profilatura](profiling-structures.md)
