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
ms.openlocfilehash: 6e045a99de9ad30516fd12a7b490e26c860bde7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866013"
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
 in Valore `true` se la chiamata è asincrona. in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Se la richiesta di messaggio è asincrona, la richiesta può essere gestita da qualsiasi thread arbitrario.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
