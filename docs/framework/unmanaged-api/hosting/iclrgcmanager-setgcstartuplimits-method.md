---
title: Metodo ICLRGCManager::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29311f00f5ac4b61380b57cdd9fda07ec7de1b23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966194"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>Metodo ICLRGCManager::SetGCStartupLimits
Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.  
  
> [!IMPORTANT]
> A partire da .NET Framework 4,5, è possibile impostare dimensioni del segmento e dimensioni massime 0 di generazione su `DWORD` valori maggiori di usando il metodo [ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `SegmentSize`  
 in Dimensione specificata di un segmento di Garbage Collection.  
  
 La dimensione minima del segmento è 4 MB. I segmenti possono essere aumentati con incrementi di 1 MB o più grandi.  
  
 `MaxGen0Size`  
 in Dimensione massima specificata per la generazione 0.  
  
 La dimensione minima di generazione 0 è 64 KB.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 I valori `SetGCStartupLimits` impostati possono essere specificati una sola volta. Le chiamate successive `SetGCStartupLimits` a vengono ignorate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione automatica della memoria](../../../standard/automatic-memory-management.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaccia ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
