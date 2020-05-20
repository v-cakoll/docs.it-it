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
ms.openlocfilehash: 248f1d281697923e2da14517ca174fe615bba4ff
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616203"
---
# <a name="ememorycriticallevel-enumeration"></a>Enumerazione EMemoryCriticalLevel
Contiene valori che indicano l'effetto di un errore quando un'allocazione di memoria specifica è stata richiesta ma non può essere soddisfatta.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`eAppDomainCritical`|Indica che l'allocazione è essenziale per l'esecuzione di codice gestito nel dominio che ha richiesto l'allocazione. Se non è possibile allocare memoria, CLR non può garantire che il dominio sia ancora utilizzabile. L'host decide l'azione da intraprendere quando l'allocazione non può essere soddisfatta. Può indicare a CLR di interrompere automaticamente il `AppDomain` o di mantenerne l'esecuzione chiamando metodi su [ICLRPolicyManager](iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Indica che l'allocazione è fondamentale per l'esecuzione del codice gestito nel processo. Questo valore viene usato durante l'avvio e durante l'esecuzione di finalizzatori. Se non è possibile allocare memoria, il CLR non può funzionare nel processo. Se l'allocazione ha esito negativo, CLR viene disabilitato in modo efficace. Tutte le chiamate successive a CLR hanno esito negativo con HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Indica che l'allocazione è essenziale per l'esecuzione dell'attività che ha richiesto l'allocazione. Se non è possibile allocare memoria, CLR non può garantire che l'attività possa essere eseguita. In caso di errore, CLR genera un oggetto <xref:System.Threading.ThreadAbortException> nel thread del sistema operativo fisico.|  
  
## <a name="remarks"></a>Osservazioni  
 I metodi di allocazione della memoria definiti nelle interfacce [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) e [IHostMalloc](ihostmalloc-interface.md) accettano un parametro di questo tipo. A seconda del livello di gravità di un errore, un host può decidere se interrompere immediatamente la richiesta di allocazione o attendere fino a quando non può essere soddisfatta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
