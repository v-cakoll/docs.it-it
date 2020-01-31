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
ms.openlocfilehash: 23fd44a6865b0487296f3ade37c1219e8feba288
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862581"
---
# <a name="icorprofilerinfo2-interface"></a>Interfaccia ICorProfilerInfo2
Fornisce metodi che i profiler del codice utilizzano per comunicare con il Common Language Runtime (CLR) per controllare il monitoraggio degli eventi e le informazioni sulla richiesta. L'interfaccia `ICorProfilerInfo2` è un'estensione dell'interfaccia [ICorProfilerInfo](icorprofilerinfo-interface.md) . Ovvero fornisce nuovi metodi supportati nella versione .NET Framework 2,0 e versioni successive.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)|Scorre lo stack del thread specificato per segnalare i frame di chiamata gestiti al profiler.|  
|[Metodo EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)|Ottiene un enumeratore che consente l'iterazione sugli oggetti bloccati nel modulo specificato.|  
|[Metodo GetAppDomainStaticAddress](icorprofilerinfo2-getappdomainstaticaddress-method.md)|Ottiene l'indirizzo del campo statico del dominio dell'applicazione specificato nell'ambito del dominio dell'applicazione specificato.|  
|[Metodo GetArrayObjectInfo](icorprofilerinfo2-getarrayobjectinfo-method.md)|Ottiene informazioni dettagliate su un oggetto Array.|  
|[Metodo GetBoxClassLayout](icorprofilerinfo2-getboxclasslayout-method.md)|Ottiene informazioni sul layout della classe per un tipo di valore specificato boxed.|  
|[Metodo GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Ottiene l'`ClassID` di un tipo utilizzando il token di metadati specificato e i valori di `ClassID` di qualsiasi argomento di tipo.|  
|[Metodo GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)|Ottiene il modulo padre della classe generica specificata, il token di metadati per la classe, il `ClassID` della relativa classe padre e il `ClassID` per ogni argomento di tipo, se presente, della classe.|  
|[Metodo GetClassLayout](icorprofilerinfo2-getclasslayout-method.md)|Ottiene le informazioni sul layout, in memoria, dei campi definiti dalla classe specificata. In altri termini, questo metodo ottiene gli offset dei campi della classe.|  
|[Metodo GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)|Ottiene gli ambiti del codice nativo associato al parametro `FunctionID` specificato.|  
|[Metodo GetContextStaticAddress](icorprofilerinfo2-getcontextstaticaddress-method.md)|Ottiene l'indirizzo del campo statico del contesto specificato nell'ambito del contesto specificato.|  
|[Metodo GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Ottiene l'`FunctionID` di una funzione utilizzando il token di metadati specificato, la classe contenente e i valori di `ClassID` di qualsiasi argomento di tipo.|  
|[Metodo GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)|Ottiene la classe padre, il token di metadati e l'elemento `ClassID` di ciascun argomento di tipo, se presente, di una funzione.|  
|[Metodo GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md)|Ottiene le aree di memoria (i segmenti dell'heap) che costituiscono le generazioni dell'heap sottoposta a Garbage Collection.|  
|[Metodo GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Ottiene l'indirizzo nativo e le informazioni sul frame per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguita o che è stata appena eseguita.|  
|[Metodo GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md)|Ottiene il segmento dell'heap che contiene l'oggetto specificato.|  
|[Metodo GetRVAStaticAddress](icorprofilerinfo2-getrvastaticaddress-method.md)|Ottiene l'indirizzo del campo statico dell'indirizzo RVA (relative Virtual Address) specificato.|  
|[Metodo GetStaticFieldInfo](icorprofilerinfo2-getstaticfieldinfo-method.md)|Ottiene l'ambito in cui il campo specificato è statico.|  
|[Metodo GetStringLayout](icorprofilerinfo2-getstringlayout-method.md)|Ottiene informazioni sul layout di un oggetto stringa.|  
|[Metodo GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)|Ottiene l'ID del dominio dell'applicazione in cui il thread specificato esegue attualmente il codice.|  
|[Metodo GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md)|Ottiene l'indirizzo del campo statico del thread specificato nell'ambito del thread specificato.|  
|[Metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Specifica le funzioni implementate dal profiler da chiamare sugli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.|  
  
## <a name="remarks"></a>Note  
 Un profiler chiama un metodo nell'interfaccia `ICorProfilerInfo2` per comunicare con CLR per controllare il monitoraggio degli eventi e le informazioni sulla richiesta.  
  
 I metodi dell'interfaccia `ICorProfilerInfo2` sono implementati da CLR usando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere il file CorError.h.  
  
 CLR passa un'interfaccia `ICorProfilerInfo2` a ogni Code Profiler durante l'inizializzazione, usando l'implementazione del profiler di [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md). Un Code Profiler può quindi chiamare i metodi dell'interfaccia `ICorProfilerInfo2` per ottenere informazioni sul codice gestito eseguito sotto il controllo di CLR.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
