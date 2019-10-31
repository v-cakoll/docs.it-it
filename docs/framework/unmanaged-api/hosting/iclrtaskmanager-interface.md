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
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092192"
---
# <a name="iclrtaskmanager-interface"></a>Interfaccia ICLRTaskManager
Fornisce metodi che consentono all'host di richiedere in modo esplicito che il Common Language Runtime (CLR) crei una nuova attività, ottenga l'attività attualmente in esecuzione e imposta la lingua geografica e le impostazioni cultura per l'attività.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Richiede in modo esplicito che CLR crei una nuova istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .|  
|[Metodo GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Ottiene l'istanza `ICLRTask` che rappresenta l'attività attualmente in esecuzione.|  
|[Metodo GetCurrentTaskType](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Ottiene il tipo dell'attività attualmente in esecuzione.|  
|[Metodo SetLocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Notifica a CLR che l'host ha modificato l'identificatore delle impostazioni locali nell'attività attualmente in esecuzione.|  
|[Metodo SetUILocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Notifica all'Common Language Runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente nell'attività attualmente in esecuzione.|  
  
## <a name="remarks"></a>Note  
 Ogni attività in esecuzione in un ambiente ospitato dispone di rappresentazioni sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione sul lato host deve essere associata a una rappresentazione sul lato CLR corrispondente per garantire la corretta comunicazione tra l'host e CLR in relazione all'attività. È necessario creare e creare un'istanza dei due oggetti prima che il codice gestito possa essere eseguito su un thread del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
