---
title: Metodo ICorProfilerCallback::AppDomainShutdownFinished
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
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e681c64017e99eaaf0b786e48ca96b4435b08890
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>Metodo ICorProfilerCallback::AppDomainShutdownFinished
Notifica al profiler che un dominio applicazione è stato scaricato da un processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `appDomainId`  
 [in] Identifica il dominio in cui sono archiviati gli assembly dell'applicazione.  
  
 `hrStatus`  
 [in] Un valore HRESULT che indica se il dominio applicazione è stato scaricato correttamente.  
  
## <a name="remarks"></a>Note  
 Il valore di `appDomainId` non è valido per una richiesta di informazioni dopo il [AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) metodo restituisce.  
  
 Alcune parti dello scaricamento del dominio applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento del dominio applicazione è stata completata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
