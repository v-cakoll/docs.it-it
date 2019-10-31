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
ms.openlocfilehash: 3c662021894acbb8eb448fa2166498254158caa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133870"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>Metodo IHostIoCompletionManager::GetHostOverlappedSize
Ottiene le dimensioni dei dati personalizzati che l'host intende accodare alle richieste di I/O.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pcbSize`  
 out Puntatore al numero di byte che il Common Language Runtime (CLR) deve allocare oltre alla dimensione dell'oggetto Win32 `OVERLAPPED`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Tutte le chiamate di I/O asincrone alle API della piattaforma Windows accettano un oggetto `OVERLAPPED` Win32, che fornisce informazioni come la posizione del puntatore del file. Per mantenere lo stato, le applicazioni che effettuano chiamate di I/O asincrone aggiungono in genere dati personalizzati alla struttura. `GetHostOverlappedSize` e [IHostIoCompletionManager:: InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) offrono la possibilità per l'host di includere tali dati personalizzati.  
  
 CLR chiama il metodo `GetHostOverlappedSize` per determinare le dimensioni dei dati personalizzati che l'host intende accodare all'oggetto `OVERLAPPED`.  
  
> [!NOTE]
> `GetHostOverlappedSize` viene chiamata una sola volta. I dati personalizzati dell'host devono avere le stesse dimensioni per ogni richiesta di I/O.  
  
> [!IMPORTANT]
> Le dimensioni dell'oggetto `OVERLAPPED` stesso non sono incluse nel valore di `pcbSize`.  
  
 Per ulteriori informazioni sulla struttura `OVERLAPPED`, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.NativeOverlapped>
- [Interfaccia ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [Interfaccia IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
