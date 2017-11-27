---
title: Interfaccia ICorProfilerInfo4
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4
helpviewer_keywords: ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db91347ad2c951c28ea7b653336450929d37bdcb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4-interface"></a>Interfaccia ICorProfilerInfo4
Fornisce metodi che code profiler possono usare per comunicare con il common language runtime (CLR) per controllare il monitoraggio degli eventi e informazioni sulla richiesta. . Il `ICorProfilerInfo4` interfaccia è un'estensione degli altri `ICorProfilerInfo` interfacce. Fornisce nuovi metodi per supportare la ricompilazione di just-in-time (JIT), aggiunta il [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[EnumJITedFunctions2 (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|Restituisce un enumeratore per tutte le funzioni che erano in precedenza a compilazione JIT e ricompilata in JIT.|  
|[EnumThreads (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|Ottiene un enumeratore che fornisce metodi per scorrere in sequenza la raccolta di tutti i thread gestiti nel processo profilato.|  
|[GetCodeInfo3 (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|Ottiene gli ambiti di codice nativo associati alla versione ricompilata in JIT della funzione specificata.|  
|[GetFunctionFromIP2 (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|Un puntatore all'istruzione di codice gestito viene eseguito il mapping alla versione ricompilata in JIT di una funzione specificata.|  
|[GetILToNativeMapping2 (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|Ottiene una mappa di Microsoft intermediate language (MSIL) agli offset nativi per il codice contenuto nella versione ricompilata in JIT della funzione specificata.|  
|[GetObjectSize2 (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|Restituisce le dimensioni di un oggetto specificato.|  
|[GetReJITIDs (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|Restituisce una matrice di ID che identifica tutte ricompilata in JIT le versioni della funzione specificata che sono ancora allocate.|  
|[Initializereportserver (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|Inizializza il thread corrente prima di installare il profiler successive chiamate API sullo stesso thread, pertanto è possibile evitare il deadlock.|  
|[RequestReJIT (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|Richiede la ricompilazione JIT di tutte le istanze delle funzioni specificate.|  
|[RequestRevert (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|Ripristina tutte le istanze delle funzioni specificate alle versioni originali.|  
  
## <a name="remarks"></a>Note  
 CLR implementa i metodi dell'interfaccia `ICorProfilerInfo4` usando il modello a thread libero. Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo. Per un elenco dei possibili codici restituiti, vedere il file CorError.h.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
