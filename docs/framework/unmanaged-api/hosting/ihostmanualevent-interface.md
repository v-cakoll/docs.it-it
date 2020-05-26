---
title: Interfaccia IHostManualEvent
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804587"
---
# <a name="ihostmanualevent-interface"></a>Interfaccia IHostManualEvent
Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Reset](ihostmanualevent-reset-method.md)|Reimposta l'istanza corrente `IHostManualEvent` su uno stato non segnalato.|  
|[Metodo Set](ihostmanualevent-set-method.md)|Imposta l' `IHostManualEvent` istanza corrente su uno stato segnalato.|  
|[Metodo Wait](ihostmanualevent-wait-method.md)|Fa `IHostManualEvent` in modo che l'istanza corrente attenda fino a quando non è di proprietà o che trascorre un intervallo di tempo specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interfaccia IHostAutoEvent](ihostautoevent-interface.md)
- [Interfaccia IHostSemaphore](ihostsemaphore-interface.md)
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
