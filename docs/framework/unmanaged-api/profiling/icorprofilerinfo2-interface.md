---
title: Interfaccia ICorProfilerInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2
helpviewer_keywords:
- ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type:
- apiref
ms.openlocfilehash: fdac9eedb0ae442d6dd2646859cab13398020a87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449778"
---
# <a name="icorprofilerinfo2-interface"></a>Interfaccia ICorProfilerInfo2
Fornisce metodi che i profiler del codice utilizzano per comunicare con il Common Language Runtime (CLR) per controllare il monitoraggio degli eventi e le informazioni sulla richiesta. L'interfaccia `ICorProfilerInfo2` è un'estensione dell'interfaccia [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) . Ovvero fornisce nuovi metodi supportati nella versione .NET Framework 2,0 e versioni successive.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|description|  
|------------|-----------------|  
|[Metodo DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Scorre lo stack del thread specificato per segnalare i frame di chiamata gestiti al profiler.|  
|[Metodo EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Ottiene un enumeratore che consente l'iterazione sugli oggetti bloccati nel modulo specificato.|  
|[Metodo GetAppDomainStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Ottiene l'indirizzo del campo statico del dominio dell'applicazione specificato nell'ambito del dominio dell'applicazione specificato.|  
|[Metodo GetArrayObjectInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Ottiene informazioni dettagliate su un oggetto Array.|  
|[Metodo GetBoxClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Ottiene informazioni sul layout della classe per un tipo di valore specificato boxed.|  
|[Metodo GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Ottiene l'`ClassID` di un tipo utilizzando il token di metadati specificato e i valori di `ClassID` di qualsiasi argomento di tipo.|  
|[Metodo GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Ottiene il modulo padre della classe generica specificata, il token di metadati per la classe, il `ClassID` della relativa classe padre e il `ClassID` per ogni argomento di tipo, se presente, della classe.|  
|[Metodo GetClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Ottiene le informazioni sul layout, in memoria, dei campi definiti dalla classe specificata. In altri termini, questo metodo ottiene gli offset dei campi della classe.|  
|[Metodo GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Ottiene gli ambiti del codice nativo associato al parametro `FunctionID` specificato.|  
|[Metodo GetContextStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Ottiene l'indirizzo del campo statico del contesto specificato nell'ambito del contesto specificato.|  
|[Metodo GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Ottiene l'`FunctionID` di una funzione utilizzando il token di metadati specificato, la classe contenente e i valori di `ClassID` di qualsiasi argomento di tipo.|  
|[Metodo GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Ottiene la classe padre, il token di metadati e l'elemento `ClassID` di ciascun argomento di tipo, se presente, di una funzione.|  
|[Metodo GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Ottiene le aree di memoria (i segmenti dell'heap) che costituiscono le generazioni dell'heap sottoposta a Garbage Collection.|  
|[Metodo GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Ottiene l'indirizzo nativo e le informazioni sul frame per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguita o che è stata appena eseguita.|  
|[Metodo GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Ottiene il segmento dell'heap che contiene l'oggetto specificato.|  
|[Metodo GetRVAStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Ottiene l'indirizzo del campo statico dell'indirizzo RVA (relative Virtual Address) specificato.|  
|[Metodo GetStaticFieldInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Ottiene l'ambito in cui il campo specificato è statico.|  
|[Metodo GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Ottiene informazioni sul layout di un oggetto stringa.|  
|[Metodo GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Ottiene l'ID del dominio dell'applicazione in cui il thread specificato esegue attualmente il codice.|  
|[Metodo GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Ottiene l'indirizzo del campo statico del thread specificato nell'ambito del thread specificato.|  
|[Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Specifica le funzioni implementate dal profiler da chiamare sugli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.|  
  
## <a name="remarks"></a>Osservazioni  
 Un profiler chiama un metodo nell'interfaccia `ICorProfilerInfo2` per comunicare con CLR per controllare il monitoraggio degli eventi e le informazioni sulla richiesta.  
  
 I metodi dell'interfaccia `ICorProfilerInfo2` sono implementati da CLR usando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere il file CorError.h.  
  
 CLR passa un'interfaccia `ICorProfilerInfo2` a ogni Code Profiler durante l'inizializzazione, usando l'implementazione del profiler di [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Un Code Profiler può quindi chiamare i metodi dell'interfaccia `ICorProfilerInfo2` per ottenere informazioni sul codice gestito eseguito sotto il controllo di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
