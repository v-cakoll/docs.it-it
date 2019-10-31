---
title: Metodo ICLRRuntimeHost::SetHostControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 68b06a2840de277bdaed1dc9ce0b51e6b363c897
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120460"
---
# <a name="iclrruntimehostsethostcontrol-method"></a>Metodo ICLRRuntimeHost::SetHostControl
Imposta il puntatore a interfaccia che può essere utilizzato dal Common Language Runtime (CLR) per ottenere l'implementazione dell'host dell' [interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pHostControl`  
 in Puntatore di interfaccia all'implementazione dell'host dell' [interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetHostControl` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_CLR_ALREADY_STARTED|CLR già inizializzato.|  
  
## <a name="remarks"></a>Note  
 È necessario chiamare `SetHostControl` prima che CLR venga inizializzato, ovvero prima di chiamare il [metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) o utilizzare una qualsiasi delle [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md). Si consiglia di chiamare `SetHostControl` immediatamente dopo aver chiamato la funzione [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) o la [funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
