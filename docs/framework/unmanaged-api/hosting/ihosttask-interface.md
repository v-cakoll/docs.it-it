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
ms.openlocfilehash: 1b7209a36f8e9d6f02bd4cc1882adeef8af30c3d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503925"
---
# <a name="ihosttask-interface"></a>Interfaccia IHostTask
Fornisce metodi che consentono all'Common Language Runtime (CLR) di comunicare con l'host per gestire le attività.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Alert](ihosttask-alert-method.md)|Richiede che l'host risvegli l'attività rappresentata dall' `IHostTask` istanza corrente, in modo che l'attività possa essere interrotta.|  
|[Metodo GetPriority](ihosttask-getpriority-method.md)|Ottiene il livello di priorità del thread dell'attività rappresentata dall' `IHostTask` istanza corrente.|  
|[Metodo join](ihosttask-join-method.md)|Blocca l'attività chiamante fino a quando l'attività rappresentata dall'istanza corrente non `IHostTask` viene completata, l'intervallo di tempo specificato scade oppure [IHostTask:: Alert](ihosttask-alert-method.md) viene chiamato.|  
|[Metodo SetCLRTask](ihosttask-setclrtask-method.md)|Associa un'istanza dell' [interfaccia ICLRTask](iclrtask-interface.md) all' `IHostTask` istanza corrente.|  
|[Metodo SetPriority](ihosttask-setpriority-method.md)|Richiede che l'host modifichi il livello di priorità del thread per l'attività rappresentata dall' `IHostTask` istanza corrente.|  
|[Metodo Start](ihosttask-start-method.md)|Richiede che l'host sposti l'attività rappresentata dall' `IHostTask` istanza corrente da uno stato sospeso a uno stato attivo, in cui è possibile eseguire il codice.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR chiama i metodi definiti da `IHostTask` per avviare un'attività, impostare il livello di priorità del thread e così via.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](iclrtaskmanager-interface.md)
- [Interfaccia IHostTaskManager](ihosttaskmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
