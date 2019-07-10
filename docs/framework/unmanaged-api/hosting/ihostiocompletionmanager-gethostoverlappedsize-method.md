---
title: Metodo IHostIoCompletionManager::GetHostOverlappedSize
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54e72205f8f976498df3b1fe1e055fb7df12d68e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780687"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>Metodo IHostIoCompletionManager::GetHostOverlappedSize
Ottiene le dimensioni dei dati personalizzati che nelle intenzioni di host da aggiungere alle richieste dei / o.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pcbSize`  
 [out] Un puntatore al numero di byte che common language runtime (CLR) è consigliabile allocare oltre alla dimensione di Win32 `OVERLAPPED` oggetto.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Tutte le chiamate dei / o asincrone alle API della piattaforma Windows richiedere Win32 `OVERLAPPED` oggetto, che fornisce informazioni quali la posizione del puntatore di file. Per mantenere lo stato, le applicazioni che effettuano chiamate dei / o asincrone in genere aggiungono dati personalizzati alla struttura. `GetHostOverlappedSize` e [InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) offrono l'opportunità per l'host da includere tali dati.  
  
 CLR chiama il `GetHostOverlappedSize` metodo per determinare le dimensioni dei dati personalizzati che l'host da aggiungere al `OVERLAPPED` oggetto.  
  
> [!NOTE]
>  `GetHostOverlappedSize` viene chiamato una sola volta. Dati personalizzati dell'host devono avere le stesse dimensioni per ogni richiesta dei / o.  
  
> [!IMPORTANT]
>  Le dimensioni dei `OVERLAPPED` oggetto stesso non è incluso nel valore di `pcbSize`.  
  
 Per altre informazioni sul `OVERLAPPED` struttura, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.NativeOverlapped>
- [Interfaccia ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [Interfaccia IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
