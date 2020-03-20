---
title: Metodo ICorProfilerCallback::AppDomainCreationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177072"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>Metodo ICorProfilerCallback::AppDomainCreationFinished
Notifica al profiler che è stato creato un dominio applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a>Parametri

- `appDomainId`

  \[in] identifica il dominio che è stato creato.

- `hrStatus`

  \[in] Un HRESULT che indica se la creazione del dominio applicazione è stata completata correttamente.

## <a name="remarks"></a>Osservazioni  
 L'ID applicazione non è valido `AppDomainCreationFinished` per qualsiasi richiesta di informazioni fino a quando non viene chiamato il metodo.  
  
 Alcune parti del caricamento del dominio `AppDomainCreationFinished` applicazione potrebbero continuare dopo il callback. Un HRESULT `hrStatus` di errore in indica un errore. Tuttavia, un HRESULT di esito positivo indica `hrStatus` solo che la prima parte della creazione del dominio applicazione è riuscita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
