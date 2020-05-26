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
ms.openlocfilehash: a97009a4ebc834d867dddcc350033c550364ea42
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804755"
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
 out Puntatore al numero di byte che deve essere allocato dall'Common Language Runtime (CLR) oltre alla dimensione dell' `OVERLAPPED` oggetto Win32.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Tutte le chiamate di I/O asincrone alle API della piattaforma Windows accettano un `OVERLAPPED` oggetto Win32, che fornisce informazioni come la posizione del puntatore del file. Per mantenere lo stato, le applicazioni che effettuano chiamate di I/O asincrone aggiungono in genere dati personalizzati alla struttura. `GetHostOverlappedSize`e [IHostIoCompletionManager:: InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md) offrono la possibilità per l'host di includere tali dati personalizzati.  
  
 CLR chiama il `GetHostOverlappedSize` metodo per determinare le dimensioni dei dati personalizzati che l'host intende accodare all' `OVERLAPPED` oggetto.  
  
> [!NOTE]
> `GetHostOverlappedSize`viene chiamato una sola volta. I dati personalizzati dell'host devono avere le stesse dimensioni per ogni richiesta di I/O.  
  
> [!IMPORTANT]
> Le dimensioni dell' `OVERLAPPED` oggetto stesso non sono incluse nel valore di `pcbSize` .  
  
 Per ulteriori informazioni sulla `OVERLAPPED` struttura, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.NativeOverlapped>
- [Interfaccia ICLRIoCompletionManager](iclriocompletionmanager-interface.md)
- [Interfaccia IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
