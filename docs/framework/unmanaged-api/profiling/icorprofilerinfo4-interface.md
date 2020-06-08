---
title: Interfaccia ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: 58d11e9084f53c69f2656b4f0ee6bc7d2cc4ae21
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495866"
---
# <a name="icorprofilerinfo4-interface"></a>Interfaccia ICorProfilerInfo4
Fornisce metodi che i profiler del codice utilizzano per comunicare con il Common Language Runtime (CLR) per controllare il monitoraggio degli eventi e le informazioni sulla richiesta. . L' `ICorProfilerInfo4` interfaccia è un'estensione delle altre `ICorProfilerInfo` interfacce. Fornisce nuovi metodi per il supporto della ricompilazione JIT (just-in-Time), aggiunta nella .NET Framework 4,5.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)|Restituisce un enumeratore per tutte le funzioni precedentemente compilate tramite JIT e ricompilate tramite JIT.|  
|[Metodo EnumThreads](icorprofilerinfo4-enumthreads-method.md)|Ottiene un enumeratore che fornisce i metodi per scorrere in sequenza l'insieme di tutti i thread gestiti nel processo profilato.|  
|[Metodo GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md)|Ottiene gli ambiti di codice nativo associati alla versione ricompilata in JIT della funzione specificata.|  
|[Metodo GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)|Esegue il mapping di un puntatore all'istruzione di codice gestito alla versione ricompilata in JIT di una funzione specificata.|  
|[Metodo GetILToNativeMapping2](icorprofilerinfo4-getiltonativemapping2-method.md)|Ottiene una mappa dagli offset MSIL (Microsoft Intermediate Language) agli offset nativi per il codice contenuto nella versione ricompilata in JIT della funzione specificata.|  
|[Metodo GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md)|Restituisce la dimensione di un oggetto specificato.|  
|[Metodo GetReJITIDs](icorprofilerinfo4-getrejitids-method.md)|Restituisce una matrice di ID che identificano tutte le versioni ricompilate in JIT della funzione specificata ancora allocate.|  
|[Metodo InitializeCurrentThread ](icorprofilerinfo4-initializecurrentthread-method.md)|Inizializza il thread corrente prima delle chiamate API del profiler successive sullo stesso thread, in modo che il deadlock possa essere evitato.|  
|[Metodo RequestReJIT](icorprofilerinfo4-requestrejit-method.md)|Richiede la ricompilazione JIT di tutte le istanze delle funzioni specificate.|  
|[Metodo RequestRevert](icorprofilerinfo4-requestrevert-method.md)|Ripristina tutte le istanze delle funzioni specificate alle versioni originali.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR implementa i metodi dell'interfaccia `ICorProfilerInfo4` usando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere il file CorError.h.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
