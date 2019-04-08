---
title: Metodo IHostMemoryManager::VirtualFree
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03cac2b8433d6491d1fa474a0d4064ef4e260d6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099911"
---
# <a name="ihostmemorymanagervirtualfree-method"></a>Metodo IHostMemoryManager::VirtualFree
Funge da wrapper logico per la funzione Win32 corrispondente. L'implementazione di Win32 di `VirtualFree` rilascia, libera o rilascia e libera un'area di pagine nello spazio degli indirizzi virtuali del processo chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lpAddress`  
 [in] Un puntatore all'indirizzo di base delle pagine della memoria virtuale da liberare.  
  
 `dwSize`  
 [in] Le dimensioni, in byte, dell'area da liberare.  
  
 `dwFreeType`  
 [in] Tipo di operazione di rilascio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`VirtualFree` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|È stato effettuato un tentativo per liberare la memoria non allocata tramite l'host.|  
  
## <a name="remarks"></a>Note  
 `VirtualFree` Consente di liberare le pagine di memoria virtuale associate la `lpAddress` al parametro tramite una chiamata precedente al [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) (funzione). Tenta di liberare la memoria non allocata tramite l'host deve restituire HOST_E_INVALIDOPERATION.  
  
 La semantica è identica a quelle dell'implementazione di Win32 `VirtualFree`. Per altre informazioni, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Interfaccia IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
