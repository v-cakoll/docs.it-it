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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176279"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>Metodo IHostMemoryManager::GetMemoryLoad
Ottiene la quantità di memoria fisica attualmente in uso e quindi non disponibile, come indicato dall'host.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pMemoryLoad`  
 [fuori] Puntatore alla percentuale approssimativa della memoria fisica totale attualmente in uso.  
  
 `pAvailableBytes`  
 [fuori] Puntatore al numero di byte disponibili per Common Language Runtime (CLR).  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad`restituito con successo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `GetMemoryLoad`esegue il wrapping `GlobalMemoryStatus` della funzione Win32. Il valore `pMemoryLoad` di è `dwMemoryLoad` l'equivalente `MEMORYSTATUS` del campo `GlobalMemoryStatus`nella struttura restituita da .  
  
 Il runtime utilizza il valore restituito come euristica per il Garbage Collector. Ad esempio, se l'host segnala che la maggior parte della memoria è in uso, il Garbage Collector può scegliere di raccogliere da più generazioni per aumentare la quantità di memoria che può potenzialmente diventare disponibile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.GC?displayProperty=nameWithType>
- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
