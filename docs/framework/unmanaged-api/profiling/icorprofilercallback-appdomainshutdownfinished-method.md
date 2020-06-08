---
title: Metodo ICorProfilerCallback::AppDomainShutdownFinished
ms.date: 03/30/2017
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
ms.openlocfilehash: 722a1e0adea41a13ca25829c53372c29187b80bd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500468"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>Metodo ICorProfilerCallback::AppDomainShutdownFinished
Notifica al profiler che un dominio applicazione è stato scaricato da un processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parametri

- `appDomainId`

  \[in] identifica il dominio in cui sono archiviati gli assembly dell'applicazione.

- `hrStatus`

  \[in] valore HRESULT che indica se il dominio applicazione è stato scaricato correttamente.

## <a name="remarks"></a>Osservazioni  
 Il valore di `appDomainId` non è valido per una richiesta di informazioni dopo che il metodo [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) restituisce.  
  
 Alcune parti dello scaricamento del dominio dell'applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback. Un errore HRESULT in `hrStatus` indica un errore. Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento del dominio applicazione è riuscita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
