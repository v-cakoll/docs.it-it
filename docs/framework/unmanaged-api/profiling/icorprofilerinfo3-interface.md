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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b523c5819994e6da0332188311b4b631e3f9072
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178763"
---
# <a name="icorprofilerinfo3-interface"></a>Interfaccia ICorProfilerInfo3
Fornisce metodi che i Code Profiler possono usare per comunicare con Common Language Runtime (CLR) allo scopo di controllare il monitoraggio di eventi e richiedere informazioni. Il `ICorProfilerInfo3` interfaccia è un'estensione del [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interfaccia. Fornisce nuovi metodi supportati in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] e versioni successive.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)|Restituisce un enumeratore per tutte le funzioni sottoposte in precedenza a compilazione JIT.|  
|[Metodo EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)|Restituisce un enumeratore che fornisce i metodi per scorrere in sequenza una raccolta di moduli gestiti caricati nell'applicazione.|  
|[Metodo GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Ottiene gli identificatori dei domini dell'applicazione in cui è stato caricato il modulo specificato.|  
|[Metodo GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)|Fornisce le informazioni sullo stack frame e l'argomento della funzione da segnalare al profiler tramite la [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) funzione; può essere chiamato solo durante la `FunctionEnter3WithInfo` callback.|  
|[Metodo GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)|Fornisce lo stack frame e il valore restituito della funzione da segnalare al profiler tramite la [funzione FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) funzione; può essere chiamato solo durante la `FunctionLeave3WithInfo` callback.|  
|[Metodo GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)|Fornisce lo stack frame della funzione da segnalare al profiler tramite la [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) funzione; può essere chiamato solo durante la `FunctionTailcall3WithInfo` callback.|  
|[Metodo GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)|Dato un ID modulo, restituisce il nome file del modulo, l'ID dell'assembly padre del modulo e una maschera di bit che descrive le proprietà del modulo.|  
|[Metodo GetRuntimeInformation](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getruntimeinformation-method.md)|Fornisce informazioni sulla versione relative al runtime che viene profilato.|  
|[Metodo GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)|Ottiene informazioni sul layout di un oggetto stringa.|  
|[Metodo GetThreadStaticAddress2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getthreadstaticaddress2-method.md)|Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del dominio dell'applicazione e del thread specificati.|  
|[Metodo RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)|Indica al runtime di disconnettere il profiler.|  
|[Metodo SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Specifica le funzioni implementate dal profiler che verranno chiamate per il [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), e [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) funzioni.|  
|[Metodo SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Specifica le funzioni implementate dal profiler che verranno chiamate per il [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), e [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hook di funzioni gestite.|  
|[Metodo SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)|Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler. Questo metodo estende [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) con un parametro che i profiler possono usare per distinguere tra runtime.|  
  
## <a name="remarks"></a>Note  
 CLR implementa i metodi dell'interfaccia `ICorProfilerInfo3` usando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere il file CorError.h.  
  
 CLR passa un' `ICorProfilerInfo3` interfaccia a ogni code profiler durante l'inizializzazione, usando l'implementazione del profiler il [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) o [ICorProfilerCallback3::I nitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) (metodo). Un Code Profiler può quindi chiamare i metodi `ICorProfilerInfo3` per ottenere informazioni sul codice gestito di cui è in corso l'esecuzione sotto il controllo del runtime CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
