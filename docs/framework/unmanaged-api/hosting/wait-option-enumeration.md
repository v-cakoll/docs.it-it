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
ms.openlocfilehash: 4c57a3fde3565a21800c60794b6c2d1c7616ddd8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008001"
---
# <a name="wait_option-enumeration"></a>Enumerazione WAIT_OPTION
Contiene valori che indicano l'azione che un host deve eseguire se un'operazione richiesta dal Common Language Runtime (CLR) si blocca.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Notifica all'host che l'attività deve essere riattivata se CLR chiama il metodo [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|`WAIT_MSGPUMP`|Notifica all'host che è necessario pompare i messaggi nel thread del sistema operativo corrente se il thread viene bloccato. Il runtime specifica questo valore solo in un <xref:System.Threading.ApartmentState.STA> thread.|  
|`WAIT_NOTINDEADLOCK`|Notifica all'host che la richiesta di sincronizzazione specificata non può essere interruppe da un host. Ovvero, l'host non può restituire `HOST_E_DEADLOCK` .|  
  
## <a name="remarks"></a>Commenti  
 I metodi [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) e [IHostTaskManager:: SwitchToTask accettano](ihosttaskmanager-switchtotask-method.md) accettano entrambi un parametro di questo tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](hosting-enumerations.md)
