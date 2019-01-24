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
ms.openlocfilehash: 9012a38271afdef5e00e9e69eb9b2730834be2fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656154"
---
# <a name="iclrtaskmanager-interface"></a>Interfaccia ICLRTaskManager
Fornisce metodi che consentono all'host per richiedere in modo esplicito che common language runtime (CLR) creare una nuova attività, ottenere l'attività attualmente in esecuzione e impostare il linguaggio geografica e le impostazioni cultura per l'attività.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Le richieste in modo esplicito a CLR di creare una nuova [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.|  
|[Metodo GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Ottiene il `ICLRTask` istanza che rappresenta l'attività attualmente in esecuzione.|  
|[Metodo GetCurrentTaskType](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Ottiene il tipo dell'attività attualmente in esecuzione.|  
|[Metodo SetLocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Notifica CLR che l'host ha modificato l'identificatore delle impostazioni locali dell'attività attualmente in esecuzione.|  
|[Metodo SetUILocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Notifica di common language runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente dell'attività attualmente in esecuzione.|  
  
## <a name="remarks"></a>Note  
 Ogni attività è in esecuzione in un ambiente ospitato dispone di rappresentazioni sia sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione lato host deve essere associata a una rappresentazione lato CLR corrispondente per garantire la corretta comunicazione tra l'host e il CLR riguardanti l'attività. I due oggetti devono essere creati e creare un'istanza prima di eseguire codice gestito in un thread del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
