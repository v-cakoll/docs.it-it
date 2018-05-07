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
ms.openlocfilehash: 83e32b2b69d53772f8a4ebaabe1c025b95d1da47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackshutdown-method"></a>Metodo ICorProfilerCallback::Shutdown
Notifica al profiler che l'applicazione è in fase di chiusura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Note  
 Il codice del profiler non è possibile chiamare metodi del [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interfaccia dopo il `Shutdown` metodo viene chiamato. Tutte le chiamate a `ICorProfilerInfo` metodi causare comportamenti imprevisti dopo il `Shutdown` metodo restituisce. Alcuni eventi non modificabili possono ancora verificarsi dopo l'arresto; il profiler deve fare attenzione a restituire immediatamente quando ciò si verifica.  
  
 Il `Shutdown` metodo verrà chiamato solo se l'applicazione gestita che si sta profilando avviata come codice gestito (vale a dire iniziale gestito il frame dello stack di processo). Se l'applicazione avviata come codice non gestito, ma in un secondo momento è passato in codice gestito, creando un'istanza di common language runtime (CLR), quindi `Shutdown` non verrà chiamato. In questi casi, il profiler deve essere inclusa nella libreria un `DllMain` valore routine che utilizzi il DLL_PROCESS_DETACH per liberare risorse ed eseguire l'elaborazione di pulizia dei dati, ad esempio svuotando le tracce su disco e così via.  
  
 In generale, il profiler deve far fronte ad arresti imprevisti. Ad esempio, un processo venga arrestato dal Win32 `TerminateProcess` metodo (dichiarato in winbase). In altri casi, Common Language Runtime arresterà alcuni thread gestiti (thread in background) senza il recapito dei messaggi di eliminazione per tali.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
