---
title: Interfaccia IHostTask
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992836"
---
# <a name="ihosttask-interface"></a>Interfaccia IHostTask
Fornisce metodi che consentono di common language runtime (CLR) per comunicare con l'host per gestire le attività.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Richiede che l'host di riattivare l'attività rappresentata dall'oggetto corrente `IHostTask` dell'istanza, in modo che l'attività può essere interrotta.|  
|[Metodo GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Ottiene il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.|  
|[Metodo join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Blocca l'attività chiamante fino a quando l'attività rappresentata dall'oggetto corrente `IHostTask` completamento dell'istanza, è trascorso l'intervallo di tempo specificato, oppure [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) viene chiamato.|  
|[Metodo SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Associa un' [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza con l'attuale `IHostTask` istanza.|  
|[Metodo SetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Il livello di richiede che l'host di modificare la priorità del thread per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.|  
|[Metodo Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Richiede che l'host di spostare l'attività rappresentata dall'oggetto corrente `IHostTask` istanza da uno stato sospeso in uno stato in tempo reale, in cui è possibile eseguire codice.|  
  
## <a name="remarks"></a>Note  
 CLR chiama i metodi definiti da `IHostTask` per avviare un'attività, impostare la priorità di thread livello, e così via.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
