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
ms.openlocfilehash: f6873de1a864489d144a671b1a9e1349eaf77d15
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503182"
---
# <a name="icorprofilercallbackshutdown-method"></a>Metodo ICorProfilerCallback::Shutdown
Notifica al profiler che l'applicazione è in fase di chiusura.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Osservazioni  
 Il codice del profiler non può chiamare in modo sicuro i metodi dell'interfaccia [ICorProfilerInfo](icorprofilerinfo-interface.md) dopo la `Shutdown` chiamata del metodo. Tutte le chiamate ai `ICorProfilerInfo` metodi generano un comportamento non definito dopo la `Shutdown` restituzione del metodo. Alcuni eventi non modificabili possono ancora verificarsi dopo l'arresto. il profiler deve prestare attenzione a restituire immediatamente quando si verifica questo problema.  
  
 Il `Shutdown` metodo verrà chiamato solo se l'applicazione gestita da profilare è stata avviata come codice gestito, ovvero il frame iniziale nello stack del processo è gestito. Se l'applicazione è stata avviata come codice non gestito, ma in seguito viene passata al codice gestito, creando quindi un'istanza del Common Language Runtime (CLR), `Shutdown` non verrà chiamata. In questi casi, il profiler deve includere nella relativa libreria una `DllMain` routine che usa il valore DLL_PROCESS_DETACH per liberare le risorse ed eseguire l'elaborazione di pulitura dei dati, ad esempio lo scaricamento delle tracce sul disco e così via.  
  
 In generale, il profiler deve far fronte a arresti imprevisti. È ad esempio possibile che un processo venga interrotto dal `TerminateProcess` metodo Win32 (dichiarato in winbase. h). In altri casi, CLR interromperà alcuni thread gestiti (thread in background) senza dover recapitano i messaggi di distruzione ordinata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo Initialize](icorprofilercallback-initialize-method.md)
