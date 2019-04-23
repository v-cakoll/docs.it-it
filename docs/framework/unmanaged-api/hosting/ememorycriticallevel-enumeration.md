---
title: Enumerazione EMemoryCriticalLevel
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ee8705d00e1f63f69863d0bf8e7d0d9d62807e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122291"
---
# <a name="ememorycriticallevel-enumeration"></a>Enumerazione EMemoryCriticalLevel
Contiene valori che indicano l'impatto di un errore quando un'allocazione di memoria specifico è stato richiesto ma non può essere soddisfatta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`eAppDomainCritical`|Indica che l'allocazione è fondamentale per l'esecuzione di codice gestito nel dominio che ha richiesto l'allocazione. Se non è possibile allocare memoria, CLR non può garantire che il dominio è ancora utilizzabile. L'host decide l'azione da intraprendere quando l'allocazione non può essere soddisfatta. È possibile indicare a CLR per interrompere la `AppDomain` automaticamente, oppure consentire di continuare l'esecuzione chiamando metodi sulla [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Indica che l'allocazione è fondamentale per l'esecuzione di codice gestito nel processo. Questo valore viene utilizzato durante l'avvio e durante l'esecuzione dei finalizzatori. Se non è possibile allocare memoria, CLR non può funzionare nel processo. Se l'allocazione ha esito negativo, il CLR è disabilitato in modo efficace. Tutte le chiamate successive in CLR non HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Indica che l'allocazione è fondamentale per l'esecuzione di attività che ha richiesto l'allocazione. Se non è possibile allocare memoria, CLR non può garantire che l'attività possa essere eseguito. In caso di errore, il Common Language Runtime genera una <xref:System.Threading.ThreadAbortException> sul thread del sistema operativo fisico.|  
  
## <a name="remarks"></a>Note  
 I metodi di allocazione di memoria definiti nel [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) e [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfacce accettano un parametro di questo tipo. In base alla gravità dell'errore, un host può decidere se eseguire immediatamente la richiesta di allocazione o in attesa finché può essere soddisfatta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
