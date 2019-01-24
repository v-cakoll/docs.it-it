---
title: Metodo ICorProfilerCallback3::ProfilerDetachSucceeded
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52803fc04aa55f40a131e2d53dc4ef7dba70bcde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727118"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a>Metodo ICorProfilerCallback3::ProfilerDetachSucceeded
Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Il valore restituito da questo callback viene ignorato.  
  
## <a name="remarks"></a>Note  
 Il callback `ProfilerDetachSucceeded` viene generato dopo che tutti i thread sono usciti dal codice del profiler. Quando viene chiamato questo metodo, il profiler deve eseguire un'attività dell'ultimo minuto non appropriata per il distruttore, ad esempio inviare una notifica all'interfaccia utente o registrare un componente. Tuttavia, il profiler non deve chiamare funzioni sulle interfacce fornite da CLR durante questo callback (ad esempio la [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) o `IMetaData*` interfacce).  
  
 CLR crea una voce nel registro eventi applicazioni Windows per indicare che l'operazione di rimozione ha esito positivo.  
  
 Dopo che il profiler viene restituito da questo callback, CLR rilascia l'oggetto del profiler e scarica la DLL del profiler. Il profiler quindi non deve eseguire azioni che provocherebbero l'esecuzione nella DLL del profiler dopo essere stato restituito da questo callback. Ad esempio, non deve creare thread o registrare callback del timer.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
