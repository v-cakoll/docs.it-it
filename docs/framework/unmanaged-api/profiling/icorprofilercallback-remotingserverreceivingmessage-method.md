---
title: Metodo ICorProfilerCallback::RemotingServerReceivingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
ms.openlocfilehash: 157e6bc6cb9603fa9558ad6d39f0b086849fc7b0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499896"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>Metodo ICorProfilerCallback::RemotingServerReceivingMessage
Notifica al profiler che il processo ha ricevuto una chiamata al metodo remoto o una richiesta di attivazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCookie`  
 in Valore che corrisponderà al valore fornito in [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) in queste condizioni:  
  
- I cookie GUID di comunicazione remota sono attivi.  
  
- Il canale riesce a trasmettere il messaggio.  
  
- I cookie GUID sono attivi sul processo sul lato client.  
  
 Questo consente di associare facilmente le chiamate remote e la creazione di uno stack di chiamate logico.  
  
 `fIsAsync`  
 in Valore che è `true` se la chiamata è asincrona; in caso contrario, `false` .  
  
## <a name="remarks"></a>Osservazioni  
 Se la richiesta di messaggio è asincrona, la richiesta può essere gestita da qualsiasi thread arbitrario.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
