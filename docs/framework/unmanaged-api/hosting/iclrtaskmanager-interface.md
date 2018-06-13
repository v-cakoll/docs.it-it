---
title: Interfaccia ICLRTaskManager
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14c2c9b70ac2e57983ea4b16772add6a1dff5ff4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438067"
---
# <a name="iclrtaskmanager-interface"></a>Interfaccia ICLRTaskManager
Fornisce metodi che consentono all'host per richiedere in modo esplicito che common language runtime (CLR) di creano una nuova attività, ottenere l'attività attualmente in esecuzione e impostare la lingua geografica per l'attività.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Le richieste in modo esplicito a CLR di creare un nuovo [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.|  
|[Metodo GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Ottiene il `ICLRTask` istanza che rappresenta l'attività attualmente in esecuzione.|  
|[Metodo GetCurrentTaskType](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Ottiene il tipo di attività attualmente in esecuzione.|  
|[Metodo SetLocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Notifica a Common Language Runtime che l'host ha modificato l'identificatore delle impostazioni locali per l'attività attualmente in esecuzione.|  
|[Metodo SetUILocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Notifica a common language runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente per l'attività attualmente in esecuzione.|  
  
## <a name="remarks"></a>Note  
 Ogni attività che è in esecuzione in un ambiente host dispone di rappresentazioni sia sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione lato host deve essere associata a una rappresentazione sul lato CLR corrispondente per assicurare una corretta comunicazione tra l'host e il CLR riguardanti l'attività. I due oggetti devono essere creati e creare un'istanza prima di eseguire codice gestito in un thread del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
