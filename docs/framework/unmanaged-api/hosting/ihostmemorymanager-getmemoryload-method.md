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
ms.openlocfilehash: 2210dcd9e8a8af92b7905ec680c53c1119e6a3cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136714"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>Metodo IHostMemoryManager::GetMemoryLoad
Ottiene la quantità di memoria fisica attualmente in uso e pertanto non disponibile, come segnalato dall'host.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pMemoryLoad`  
 out Puntatore alla percentuale approssimativa della memoria fisica totale attualmente in uso.  
  
 `pAvailableBytes`  
 out Puntatore al numero di byte disponibili per il Common Language Runtime (CLR).  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `GetMemoryLoad` esegue il wrapping della funzione di `GlobalMemoryStatus` Win32. Il valore di `pMemoryLoad` è l'equivalente del campo `dwMemoryLoad` nella struttura `MEMORYSTATUS` restituita da `GlobalMemoryStatus`.  
  
 Il runtime usa il valore restituito come euristica per la Garbage Collector. Se, ad esempio, l'host segnala che la maggior parte della memoria è in uso, è possibile che l'Garbage Collector scelga di raccogliere da più generazioni per aumentare la quantità di memoria potenzialmente disponibile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.GC?displayProperty=nameWithType>
- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
