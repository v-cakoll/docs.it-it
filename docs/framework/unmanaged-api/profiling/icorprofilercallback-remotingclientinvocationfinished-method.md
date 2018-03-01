---
title: Metodo ICorProfilerCallback::RemotingClientInvocationFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f0ae2be95b559074ca9dacde493a98008608b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>Metodo ICorProfilerCallback::RemotingClientInvocationFinished
Notifica al profiler che una chiamata remota completamento dell'esecuzione nel client.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Note  
 Se la chiamata remota era sincrona, è inoltre eseguito fino al completamento nel server. Se la chiamata remota è asincrona, potrebbe essere prevede una risposta comunque quando la chiamata è stata gestita. Se si prevede una risposta, si verificherà come una chiamata a [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e una chiamata aggiuntiva al `RemotingClientInvocationFinished` per indicare l'elaborazione necessaria secondario di una chiamata asincrona.  
  
 Ognuna delle seguenti coppie di callback si verificherà sullo stesso thread:  
  
-   `RemotingClientInvocationStarted`e [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
-   [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
-   [ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 È necessario tenere presente quanto segue i callback remoti:  
  
-   Esecuzione di una funzione di comunicazione remota non viene riflessa dal profiler API, in modo non vengono ricevute correttamente le notifiche per le funzioni vengono chiamate dal client ed eseguite nel server. La chiamata effettiva avviene tramite un oggetto proxy. il profiler, perché sembra che alcune funzioni vengono compilati tramite JIT, ma mai utilizzato.  
  
-   Il profiler non riceve notifiche accurate per gli eventi remoti asincroni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
