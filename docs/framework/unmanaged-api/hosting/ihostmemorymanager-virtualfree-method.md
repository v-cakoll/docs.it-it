---
title: Metodo IHostMemoryManager::VirtualFree
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 663c01d7e4b551ecf18bdd85a63aefc43f9750e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualfree-method"></a>Metodo IHostMemoryManager::VirtualFree
Funge da wrapper logico per la funzione Win32 corrispondente. L'implementazione Win32 di `VirtualFree` rilascia, libera o rilascia e libera un'area di pagine all'interno di spazio degli indirizzi virtuali del processo chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `lpAddress`  
 [in] Un puntatore all'indirizzo di base delle pagine di memoria virtuale da liberare.  
  
 `dwSize`  
 [in] Le dimensioni in byte, dell'area da liberare.  
  
 `dwFreeType`  
 [in] Il tipo di operazione di rilascio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`VirtualFree`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|È stato effettuato un tentativo di liberare la memoria non allocata tramite l'host.|  
  
## <a name="remarks"></a>Note  
 `VirtualFree`libera le pagine di memoria virtuale associate al `lpAddress` parametro tramite una chiamata precedente al [IHostMemoryManager:: VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) (funzione). Tentativo di liberare la memoria non allocata tramite l'host deve restituire HOST_E_INVALIDOPERATION.  
  
 La semantica è identica a quelli dell'implementazione di Win32 `VirtualFree`. Per ulteriori informazioni, vedere la documentazione di piattaforma di Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Interfaccia IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
