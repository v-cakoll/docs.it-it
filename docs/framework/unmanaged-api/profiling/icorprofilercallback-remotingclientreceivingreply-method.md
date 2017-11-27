---
title: Metodo ICorProfilerCallback::RemotingClientReceivingReply
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientReceivingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f1dd027dc113abfceeb88abbc82c69ed395584e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a>Metodo ICorProfilerCallback::RemotingClientReceivingReply
Notifica al profiler che la parte del server di una chiamata remota è stata completata e il client è ora di ricezione e sta per elaborare la risposta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a>Parametri  
 `pCookie`  
 [in] Un valore che corrisponde al valore fornito [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) in queste condizioni:  
  
-   I cookie dei GUID remoti sono attive.  
  
-   Il canale riesce a trasmettere il messaggio.  
  
-   I cookie GUID sono attivi sul processo del lato server.  
  
 Ciò consente l'associazione semplice delle chiamate remote.  
  
 `fIsAsync`  
 [in] Un valore che è `true` se la chiamata è asincrona; in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
