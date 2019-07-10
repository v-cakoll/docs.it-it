---
title: Enumerazione WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda866c1a1f1f69f0d042ccfde3dfad293df9b37
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776512"
---
# <a name="waitoption-enumeration"></a>Enumerazione WAIT_OPTION
Contiene valori che indicano che l'azione di un host debba eseguire se l'operazione richiesta da common language runtime (CLR) Blocca.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Notifica all'host che l'attività deve essere riattivata se Common Language Runtime chiama il [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) (metodo).|  
|`WAIT_MSGPUMP`|Notifica all'host che è necessario che distribuisca i messaggi sul thread del sistema operativo corrente se il thread si blocca. Il runtime specifica questo valore solo su un <xref:System.Threading.ApartmentState.STA> thread.|  
|`WAIT_NOTINDEADLOCK`|Notifica all'host che la richiesta di sincronizzazione specificato non può essere interrotta da un host. Vale a dire, l'host non può restituire `HOST_E_DEADLOCK`.|  
  
## <a name="remarks"></a>Note  
 Il [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) e [SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) entrambi i metodi accettano un parametro di questo tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
