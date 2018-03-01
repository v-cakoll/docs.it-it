---
title: Metodo IHostMemoryManager::GetMemoryLoad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 320881447eed00bf0dfeada0f5fbd224c32dfe96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
|S_OK|`GetMemoryLoad`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `GetMemoryLoad`esegue il wrapping di Win32 `GlobalMemoryStatus` (funzione). Il valore di `pMemoryLoad` è l'equivalente del `dwMemoryLoad` campo il `MEMORYSTATUS` struttura restituita da `GlobalMemoryStatus`.  
  
 Il runtime utilizza il valore restituito come un approccio euristico per il garbage collector. Ad esempio, se l'host indica che la maggior parte della memoria è in uso, il garbage collector è possibile scegliere di raccogliere da più generazioni per aumentare la quantità di memoria che può essere potenzialmente diventano disponibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.GC?displayProperty=nameWithType>  
 [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
