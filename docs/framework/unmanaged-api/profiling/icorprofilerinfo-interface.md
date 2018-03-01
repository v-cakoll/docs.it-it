---
title: Interfaccia ICorProfilerInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo
helpviewer_keywords:
- ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: eb4e4ce0-06e7-4469-bbc4-edc2eb5da4b1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 08852b10f59e9c400b60287d78c8eb8eed5f109f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo-interface"></a>Interfaccia ICorProfilerInfo
Fornisce metodi per l'utilizzo da code profiler per comunicare con common language runtime (CLR) per controllare il monitoraggio degli eventi e richiedere informazioni.  
  
> [!NOTE]
>  Ogni metodo di `ICorProfilerInfo` interfaccia restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere CorError.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|Inizializza il supporto del debug in-process. Questo metodo è obsoleto in .NET Framework versione 2.0.|  
|[Metodo EndInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|Arresta una sessione di debug in-process. Questo metodo è obsoleto in .NET Framework versione 2.0.|  
|[Metodo ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|Forza il garbage collection si verifichi all'interno del runtime.|  
|[Metodo GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|Ottiene informazioni relative al dominio di applicazione specificata.|  
|[Metodo GetAssemblyInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|Ottiene informazioni sull'assembly specificato.|  
|[Metodo GetClassFromObject](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|Ottiene il `ClassID` di un<br /><br /> oggetto, dato il relativo `ObjectID`.|  
|[Metodo GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|Ottiene l'ID della classe, dato il token di metadati. Questo metodo è obsoleto in .NET Framework versione 2.0. Utilizzare il [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) metodo invece.|  
|[Metodo GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|Ottiene il modulo padre e il token di metadati per la classe specificata.|  
|[Metodo GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|Ottiene l'ambito del codice nativo associato all'ID funzione specificato. Questo metodo è obsoleto. Utilizzare il [ICorProfilerInfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) metodo invece.|  
|[Metodo GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|Ottiene l'ID del thread corrente, se un thread gestito.|  
|[Metodo GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|Ottiene le categorie di eventi correnti per i quali il profiler richiede la ricezione delle notifiche di eventi da CLR.|  
|[Metodo GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|Esegue il mapping di un puntatore all'istruzione di codice gestito a un `FunctionID`.|  
|[Metodo GetFunctionFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|Ottiene l'ID di una funzione. Questo metodo è obsoleto in .NET Framework versione 2.0. Utilizzare il [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) metodo invece.|  
|[Metodo GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|Ottiene la classe padre e i metadati di token per la funzione specificata.|  
|[Metodo GetHandleFromThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|L'ID di un thread viene eseguito il mapping a un handle del thread Win32.|  
|[Metodo GetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|Ottiene un puntatore al corpo di un metodo nel codice di Microsoft intermediate language (MSIL), a partire dalla relativa intestazione.|  
|[Metodo GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|Ottiene un'interfaccia che fornisce un metodo per allocare memoria per essere utilizzato per scambiare il corpo di un metodo in codice MSIL.|  
|[Metodo GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|Ottiene una mappa dagli offset MSIL agli offset nativi per il codice contenuto nella funzione specificata.|  
|[Metodo GetInprocInspectionInterface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|Ottiene un oggetto che è possibile eseguire query per un'interfaccia ICorDebugProcess. Questo metodo è obsoleto in .NET Framework versione 2.0.|  
|[Metodo GetInprocInspectionIThisThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|Ottiene un oggetto che è possibile eseguire query per l'interfaccia ICorDebugThread. Questo metodo è obsoleto in .NET Framework versione 2.0.|  
|[Metodo GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|Dato un ID modulo, restituisce il nome file del modulo e l'ID dell'assembly padre del modulo.|  
|[Metodo GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|Ottiene un'istanza di interfaccia di metadati che esegue il mapping per il modulo specificato.|  
|[Metodo GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|Ottiene le dimensioni di un oggetto specificato.|  
|[Metodo GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|Ottiene l'identità del contesto attualmente associato al thread specificato.|  
|[Metodo GetThreadInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|Ottiene l'identità corrente del thread Win32 per il thread specificato.|  
|[Metodo GetTokenAndMetadataFromFunction](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Ottiene il token di metadati e un'istanza dell'interfaccia di metadati che può essere utilizzato con il token per la funzione specificata.|  
|[Metodo IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|Determina se la classe specificata è una classe della matrice.|  
|[Metodo SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|Specifica di funzioni implementate dal profiler verrà chiamato su "Immettere", "lasciare" e "tailcall" hook delle funzioni gestite.|  
|[Metodo SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|Imposta un valore che specifica i tipi di eventi per i quali il profiler richiede ricevere notifiche da CLR.|  
|[Metodo SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler.|  
|[Metodo SetFunctionReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|Non implementato. Non usare.|  
|[Metodo SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|Sostituisce il corpo della funzione specificata nel modulo specificato.|  
|[Metodo SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|Specifica la modalità di mapping gli offset MSIL originale di una funzione specificata per i nuovi offset MSIL profiler-modifica della funzione.|  
  
## <a name="remarks"></a>Note  
 Un profiler chiama un metodo nel `ICorProfilerInfo` interfaccia per comunicare con Common Language Runtime per controllare il monitoraggio degli eventi e richiedere informazioni.  
  
 I metodi del `ICorProfilerInfo` implementata da CLR utilizzando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere CorError.  
  
 CLR passa attraverso l'implementazione del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md), un `ICorProfilerInfo` interfaccia a ogni code profiler durante l'inizializzazione. Un code profiler può quindi chiamare i metodi del `ICorProfilerInfo` interfaccia da ottenere informazioni sul codice gestito eseguito sotto il controllo di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
