---
title: Metodo IHostMemoryManager::VirtualAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a0764cb212a95412a4dcf9455b7648ee863951e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767673"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>Metodo IHostMemoryManager::VirtualAlloc
Funge da wrapper logico per la funzione Win32 corrispondente. L'implementazione di Win32 di `VirtualAlloc` riserva o impegna un'area di pagine nello spazio degli indirizzi virtuali del processo chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAddress`  
 [in] Un puntatore all'indirizzo iniziale dell'area da allocare.  
  
 `dwSize`  
 [in] Le dimensioni, in byte, dell'area.  
  
 `flAllocationType`  
 [in] Il tipo di allocazione della memoria.  
  
 `flProtect`  
 [in] Protezione della memoria per l'area delle pagine da allocare.  
  
 `dwCriticalLevel`  
 [in] Un' [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valore che indica l'impatto di un errore di allocazione.  
  
 `ppMem`  
 [out] Puntatore all'indirizzo iniziale della memoria allocata, o null se non è stato possibile soddisfare la richiesta.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente era disponibile per completare la richiesta di allocazione|  
  
## <a name="remarks"></a>Note  
 È possibile riservare un'area nello spazio degli indirizzi del processo chiamando `VirtualAlloc`. Il `pAddress` parametro contiene l'indirizzo iniziale del blocco di memoria desiderata. Questo parametro viene in genere impostato su null. Il sistema operativo conserva un record di intervalli di indirizzi liberi disponibili per il processo. Oggetto `pAddress` valore null indica al sistema di riserva l'area, ove opportuno. In alternativa, è possibile fornire uno specifico indirizzo inizio per il blocco di memoria. In entrambi i casi, il parametro di output `ppMem` viene restituito come un puntatore alla memoria allocata. La funzione restituisce un valore HRESULT.  
  
 Win32 `VirtualAlloc` la funzione non ha un `ppMem` parametro e restituisce invece il puntatore alla memoria allocata. Per altre informazioni, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
