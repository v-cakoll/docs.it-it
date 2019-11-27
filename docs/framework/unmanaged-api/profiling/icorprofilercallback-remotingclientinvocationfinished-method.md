---
title: Metodo ICorProfilerCallback::RemotingClientInvocationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
ms.openlocfilehash: c9a750b941b29047206c98410d4b4673d1101a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445840"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>Metodo ICorProfilerCallback::RemotingClientInvocationFinished
Notifica al profiler che una chiamata remota è stata eseguita fino al completamento nel client.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Note  
 Se la chiamata remota è sincrona, viene eseguita anche fino al completamento sul server. Se la chiamata remota era asincrona, una risposta potrebbe essere ancora prevista quando viene gestita la chiamata. Se è prevista una risposta, si verificherà come chiamata a [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e a una chiamata aggiuntiva a `RemotingClientInvocationFinished` per indicare l'elaborazione secondaria richiesta di una chiamata asincrona.  
  
 Ognuna delle coppie di callback seguenti si verificherà nello stesso thread:  
  
- `RemotingClientInvocationStarted` e [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- Metodo [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- Metodo [ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 È necessario tenere presenti i seguenti problemi con i callback di comunicazione remota:  
  
- L'esecuzione di una funzione di comunicazione remota non viene riflessa dall'API del profiler, quindi le notifiche per le funzioni chiamate dal client ed eseguite sul server non vengono ricevute correttamente. La chiamata effettiva avviene tramite un oggetto proxy. il profiler sembra che alcune funzioni siano compilate tramite JIT ma mai usate.  
  
- Il profiler non riceve notifiche accurate per gli eventi di comunicazione remota asincrona.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
