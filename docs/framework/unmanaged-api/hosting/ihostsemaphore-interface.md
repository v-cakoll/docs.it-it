---
title: Interfaccia IHostSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803696"
---
# <a name="ihostsemaphore-interface"></a>Interfaccia IHostSemaphore
Rappresenta l'implementazione dell'host di un semaforo per il Threading.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)|Aumenta il numero dell'istanza corrente `IHostSemaphore` in base al valore specificato.|  
|[Metodo Wait](ihostsemaphore-wait-method.md)|Fa `IHostSemaphore` in modo che l'istanza corrente attenda finché non è di proprietà o la quantità di tempo specificata scade.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interfaccia IHostAutoEvent](ihostautoevent-interface.md)
- [Interfaccia IHostManualEvent](ihostmanualevent-interface.md)
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
