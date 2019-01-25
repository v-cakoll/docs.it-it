---
title: Metodo IHostMemoryManager::GetMemoryLoad
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18b4ad9590b57b629587af8f421a3f5902e5527f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704030"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>Metodo IHostMemoryManager::GetMemoryLoad
Ottiene la quantità di memoria fisica che è attualmente in uso e pertanto non disponibile, come indicato dall'host.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pMemoryLoad`  
 [out] Puntatore alla percentuale approssimativa di memoria fisica totale che è attualmente in uso.  
  
 `pAvailableBytes`  
 [out] Puntatore al numero di byte disponibili per common language runtime (CLR).  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `GetMemoryLoad` esegue il wrapping di Win32 `GlobalMemoryStatus` (funzione). Il valore di `pMemoryLoad` equivale al `dwMemoryLoad` campo le `MEMORYSTATUS` struttura restituita da `GlobalMemoryStatus`.  
  
 Il runtime usa il valore restituito come un'euristica per il garbage collector. Ad esempio, se l'host segnala che la maggior parte della memoria è in uso, il garbage collector può scegliere di raccogliere dai più generazioni per aumentare la quantità di memoria che può potenzialmente diventano disponibile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.GC?displayProperty=nameWithType>
- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
