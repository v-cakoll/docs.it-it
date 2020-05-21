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
ms.openlocfilehash: 9e26071181e8e0712c753fa03d5e16eb85e5ee68
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762832"
---
# <a name="iclrtaskmanager-interface"></a>Interfaccia ICLRTaskManager
Fornisce metodi che consentono all'host di richiedere in modo esplicito che il Common Language Runtime (CLR) crei una nuova attività, ottenga l'attività attualmente in esecuzione e imposta la lingua geografica e le impostazioni cultura per l'attività.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Richiede in modo esplicito che CLR crei una nuova istanza di [ICLRTask](iclrtask-interface.md) .|  
|[Metodo GetCurrentTask](iclrtaskmanager-getcurrenttask-method.md)|Ottiene l' `ICLRTask` istanza di che rappresenta l'attività attualmente in esecuzione.|  
|[Metodo GetCurrentTaskType](iclrtaskmanager-getcurrenttasktype-method.md)|Ottiene il tipo dell'attività attualmente in esecuzione.|  
|[Metodo SetLocale](iclrtaskmanager-setlocale-method.md)|Notifica a CLR che l'host ha modificato l'identificatore delle impostazioni locali nell'attività attualmente in esecuzione.|  
|[Metodo SetUILocale](iclrtaskmanager-setuilocale-method.md)|Notifica all'Common Language Runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente nell'attività attualmente in esecuzione.|  
  
## <a name="remarks"></a>Osservazioni  
 Ogni attività in esecuzione in un ambiente ospitato dispone di rappresentazioni sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](iclrtask-interface.md)). L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione sul lato host deve essere associata a una rappresentazione sul lato CLR corrispondente per garantire la corretta comunicazione tra l'host e CLR in relazione all'attività. È necessario creare e creare un'istanza dei due oggetti prima che il codice gestito possa essere eseguito su un thread del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](iclrtask-interface.md)
- [Interfaccia IHostTask](ihosttask-interface.md)
- [Interfaccia IHostTaskManager](ihosttaskmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
