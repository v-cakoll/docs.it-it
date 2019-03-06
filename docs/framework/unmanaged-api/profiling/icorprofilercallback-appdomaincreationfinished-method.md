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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08a0ed8303804df1889973fe3ffab6db93249d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481443"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>Metodo ICorProfilerCallback::AppDomainCreationFinished
Notifica al profiler che un dominio dell'applicazione sia stato creato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a>Parametri  
 `appDomainId`  
 [in] Identifica il dominio di cui è stato creato.  
  
 `hrStatus`  
 [in] HRESULT che indica se la creazione del dominio dell'applicazione è stata completata.  
  
## <a name="remarks"></a>Note  
 L'ID dell'applicazione non è valido per qualsiasi richiesta di informazioni finché il `AppDomainCreationFinished` viene chiamato il metodo.  
  
 Alcune parti del caricamento del dominio dell'applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte della creazione del dominio applicazione ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
