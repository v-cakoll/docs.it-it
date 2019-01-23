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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4623fecd210ac716824fdc5fede99ec40145e8d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498869"
---
# <a name="icorprofilerinfo2-interface"></a>Interfaccia ICorProfilerInfo2
Fornisce metodi che code profiler possono usare per comunicare con il common language runtime (CLR) per controllare il monitoraggio degli eventi e informazioni sulla richiesta. Il `ICorProfilerInfo2` interfaccia è un'estensione del [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interfaccia. Vale a dire, fornisce nuovi metodi supportati in .NET Framework versione 2.0 e versioni successive.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Analizza lo stack del thread specificato per segnalare i frame di chiamata gestita al profiler.|  
|[Metodo EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Ottiene un enumeratore che consente di scorrere gli oggetti bloccati nel modulo specificato.|  
|[Metodo GetAppDomainStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Ottiene l'indirizzo del campo statico dominio applicazione specificato che è nell'ambito del dominio applicazione specificato.|  
|[Metodo GetArrayObjectInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Ottiene informazioni dettagliate su un oggetto matrice.|  
|[Metodo GetBoxClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Ottiene informazioni sul layout della classe per un tipo di valore specificato che viene sottoposto a boxing.|  
|[Metodo GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Ottiene il `ClassID` di un tipo usando il token di metadati specificati e il `ClassID` valori di qualsiasi tipo di argomenti.|  
|[Metodo GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Ottiene il modulo padre della classe generica specificata, il token di metadati per la classe, il `ClassID` della relativa classe padre e il `ClassID` per ogni argomento di tipo, se presente, della classe.|  
|[Metodo GetClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Ottiene le informazioni sul layout, in memoria, dei campi definiti dalla classe specificata. In altri termini, questo metodo ottiene gli offset dei campi della classe.|  
|[Metodo GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Ottiene gli ambiti del codice nativo associato al parametro `FunctionID` specificato.|  
|[Metodo GetContextStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Ottiene l'indirizzo del campo statico di contesto specificato che si trova nell'ambito del contesto specificato.|  
|[Metodo GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Ottiene il `FunctionID` di una funzione usando il token di metadati specificato, contenente (classe), e `ClassID` valori di qualsiasi tipo di argomenti.|  
|[Metodo GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Ottiene la classe padre, il token di metadati e l'elemento `ClassID` di ciascun argomento tipo, se presente, di una funzione.|  
|[Metodo GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Ottiene le aree di memoria (i segmenti dell'heap) che costituiscono le generazioni dell'heap di garbage collection.|  
|[Metodo GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Ottiene le informazioni di indirizzo e frame native per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguiti o che è stata appena eseguita.|  
|[Metodo GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Ottiene il segmento dell'heap che contiene l'oggetto specificato.|  
|[Metodo GetRVAStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Ottiene l'indirizzo dell'indirizzo virtuale relativo specificato (RVA)-campo statico.|  
|[Metodo GetStaticFieldInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Ottiene l'ambito in cui il campo specificato è statico.|  
|[Metodo GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Ottiene informazioni sul layout di un oggetto stringa.|  
|[Metodo GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Ottiene l'ID del dominio dell'applicazione in cui il thread specificato è attualmente in esecuzione codice.|  
|[Metodo GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Ottiene l'indirizzo del campo statico di thread specificato che è nell'ambito del thread specificato.|  
|[Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Specifica funzioni implementate dal profiler verrà chiamato su "Immettere", "Continua" e "tailcall" hook di funzioni gestite.|  
  
## <a name="remarks"></a>Note  
 Un profiler chiama un metodo `ICorProfilerInfo2` interfaccia per comunicare con CLR per controllare il monitoraggio degli eventi e richiedere informazioni.  
  
 I metodi del `ICorProfilerInfo2` interfaccia vengono implementati da CLR usando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere il file CorError.h.  
  
 CLR passa un' `ICorProfilerInfo2` interfaccia a ogni code profiler durante l'inizializzazione, usando l'implementazione del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Un code profiler può quindi chiamare i metodi del `ICorProfilerInfo2` interfaccia per ottenere informazioni sul codice gestito in esecuzione sotto il controllo di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
