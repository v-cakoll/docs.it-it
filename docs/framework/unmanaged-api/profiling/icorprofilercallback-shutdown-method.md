---
title: Metodo ICorProfilerCallback::Shutdown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1696cb49170ba245a657e5efb6c8ba4b694af32f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192641"
---
# <a name="icorprofilercallbackshutdown-method"></a>Metodo ICorProfilerCallback::Shutdown
Notifica al profiler che l'applicazione è in corso l'arresto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Note  
 Il codice del profiler non è possibile chiamare i metodi del [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) dell'interfaccia dopo la `Shutdown` viene chiamato il metodo. Tutte le chiamate a `ICorProfilerInfo` metodi di causare un comportamento indefinito dopo il `Shutdown` restituzione del metodo. Possono comunque si verificano determinati eventi non modificabile dopo l'arresto; il profiler deve prestare attenzione a restituire immediatamente quando ciò si verifica.  
  
 Il `Shutdown` metodo verrà chiamato solo se l'applicazione gestita che si sta profilando avviata come codice gestito (vale a dire, viene gestito il fotogramma iniziale sullo stack del processo). Se l'applicazione avviata come codice non gestito, ma in un secondo momento un salto nel codice gestito, in modo da creare un'istanza di common language runtime (CLR), quindi `Shutdown` non verranno chiamati. In questi casi, il profiler deve essere inclusa nella relativa libreria un `DllMain` routine che utilizzi il DLL_PROCESS_DETACH value per liberare le risorse ed eseguire l'elaborazione di pulizia dei dati, ad esempio lo svuotamento tracce su disco e così via.  
  
 In generale, il profiler deve far fronte ad arresti imprevisti. Ad esempio, un processo venga arrestato di Win32 `TerminateProcess` metodo (dichiarato in winbase. h). In altri casi, CLR si arresta in determinati thread gestiti (thread in background) senza il recapito dei messaggi di eliminazione per loro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
