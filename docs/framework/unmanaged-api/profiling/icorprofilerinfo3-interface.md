---
title: Interfaccia ICorProfilerInfo3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3
helpviewer_keywords:
- ICorProfilerInfo3 interface [.NET Framework profiling]
ms.assetid: 044a262f-0fa7-485d-b0c1-64cdc359c654
topic_type:
- apiref
ms.openlocfilehash: 0a474719935ba763cbd15dc6e18fe5ba99c14ebc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496308"
---
# <a name="icorprofilerinfo3-interface"></a>Interfaccia ICorProfilerInfo3
Fornisce metodi che i Code Profiler possono usare per comunicare con Common Language Runtime (CLR) allo scopo di controllare il monitoraggio di eventi e richiedere informazioni. L' `ICorProfilerInfo3` interfaccia è un'estensione dell'interfaccia [ICorProfilerInfo2](icorprofilerinfo2-interface.md) . Fornisce nuovi metodi supportati in .NET Framework 4 e versioni successive.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)|Restituisce un enumeratore per tutte le funzioni sottoposte in precedenza a compilazione JIT.|  
|[Metodo EnumModules](icorprofilerinfo3-enummodules-method.md)|Restituisce un enumeratore che fornisce i metodi per scorrere in sequenza una raccolta di moduli gestiti caricati nell'applicazione.|  
|[Metodo GetAppDomainsContainingModule](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Ottiene gli identificatori dei domini dell'applicazione in cui è stato caricato il modulo specificato.|  
|[Metodo GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)|Fornisce le informazioni sul stack frame e sull'argomento della funzione segnalata al profiler dalla funzione [FunctionEnter3WithInfo](functionenter3withinfo-function.md) . può essere chiamato solo durante il `FunctionEnter3WithInfo` callback.|  
|[Metodo GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md)|Fornisce il stack frame e il valore restituito della funzione segnalata al profiler dalla funzione della [funzione FunctionLeave3WithInfo](functionleave3withinfo-function.md) . può essere chiamato solo durante il `FunctionLeave3WithInfo` callback.|  
|[Metodo GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md)|Fornisce il stack frame della funzione segnalata al profiler dalla funzione [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) . può essere chiamato solo durante il `FunctionTailcall3WithInfo` callback.|  
|[Metodo GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md)|Dato un ID modulo, restituisce il nome file del modulo, l'ID dell'assembly padre del modulo e una maschera di bit che descrive le proprietà del modulo.|  
|[Metodo GetRuntimeInformation](icorprofilerinfo3-getruntimeinformation-method.md)|Fornisce informazioni sulla versione relative al runtime che viene profilato.|  
|[Metodo GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md)|Ottiene informazioni sul layout di un oggetto stringa.|  
|[Metodo GetThreadStaticAddress2](icorprofilerinfo3-getthreadstaticaddress2-method.md)|Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del dominio dell'applicazione e del thread specificati.|  
|[Metodo RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)|Indica al runtime di disconnettere il profiler.|  
|[Metodo SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Specifica le funzioni implementate dal profiler che verranno chiamate nelle funzioni [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md) .|  
|[Metodo SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Specifica le funzioni implementate dal profiler che verranno chiamate sugli hook [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) delle funzioni gestite.|  
|[Metodo SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)|Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler. Questo metodo estende [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) con un parametro che i profiler possono usare per evitare ambiguità tra i Runtime.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR implementa i metodi dell'interfaccia `ICorProfilerInfo3` usando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere il file CorError.h.  
  
 CLR passa un' `ICorProfilerInfo3` interfaccia a ogni Code Profiler durante l'inizializzazione, usando l'implementazione del profiler del metodo [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) o [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) . Un Code Profiler può quindi chiamare i metodi `ICorProfilerInfo3` per ottenere informazioni sul codice gestito di cui è in corso l'esecuzione sotto il controllo del runtime CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
