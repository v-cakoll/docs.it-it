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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121385"
---
# <a name="ihosttask-interface"></a>Interfaccia IHostTask
Fornisce metodi che consentono all'Common Language Runtime (CLR) di comunicare con l'host per gestire le attività.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Richiede che l'host risvegli l'attività rappresentata dall'istanza di `IHostTask` corrente, in modo che l'attività possa essere interrotta.|  
|[Metodo GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Ottiene il livello di priorità del thread dell'attività rappresentata dall'istanza di `IHostTask` corrente.|  
|[Metodo join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Blocca l'attività chiamante finché non viene completata l'attività rappresentata dall'istanza di `IHostTask` corrente, l'intervallo di tempo specificato scade oppure viene chiamato [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .|  
|[Metodo SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Associa un'istanza di [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) all'istanza di `IHostTask` corrente.|  
|[Metodo SetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Richiede che l'host modifichi il livello di priorità del thread per l'attività rappresentata dall'istanza di `IHostTask` corrente.|  
|[Metodo Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Richiede che l'host sposti l'attività rappresentata dall'istanza corrente di `IHostTask` da uno stato sospeso a uno stato attivo, in cui è possibile eseguire il codice.|  
  
## <a name="remarks"></a>Note  
 CLR chiama i metodi definiti da `IHostTask` per avviare un'attività, impostare il livello di priorità del thread e così via.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
