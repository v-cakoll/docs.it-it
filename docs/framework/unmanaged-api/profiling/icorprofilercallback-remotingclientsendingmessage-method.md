---
title: Metodo ICorProfilerCallback::RemotingClientSendingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 424e0323c018367560d4cf3542e9e8668575a03f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675194"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a>Metodo ICorProfilerCallback::RemotingClientSendingMessage
Notifica al profiler che il client stia inviando una richiesta al server.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pCookie`  
 [in] Un valore che corrisponde al valore fornito [RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) in queste condizioni:  
  
-   I cookie GUID di .NET Remoting sono attivi.  
  
-   Il canale ha esito positivo la trasmissione del messaggio.  
  
-   I cookie GUID sono attivi nel processo del lato server.  
  
 Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamate logici.  
  
 `fIsAsync`  
 [in] Valore che rappresenta `true` se la chiamata è asincrona; in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
