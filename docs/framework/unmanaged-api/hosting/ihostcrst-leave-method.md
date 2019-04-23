---
title: Metodo IHostCrst::Leave
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d60cdee0a5357f7e117dc902b073049f3bbaea9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198478"
---
# <a name="ihostcrstleave-method"></a>Metodo IHostCrst::Leave
Esce dalla sezione critica rappresentato dall'istanza corrente di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Leave` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `Leave` consente a CLR comunicare direttamente con l'host implementazione threading, anziché utilizzare Win32 corrispondente `LeaveCriticalSection` (funzione). Un thread che acquisisce la proprietà della sezione critica rappresentata dall'oggetto corrente `IHostCrst` istanza deve chiamare `Leave` una volta per ogni volta che tale sezione critica.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
