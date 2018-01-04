---
title: Metodo IHostIoCompletionManager::GetHostOverlappedSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetHostOverlappedSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41fc1a4a0debe0c302115c79962c0da50cc4ee37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>Metodo IHostIoCompletionManager::GetHostOverlappedSize
Ottiene le dimensioni dei dati personalizzati, che l'host dovrà accodare alle richieste dei / o.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pcbSize`  
 [out] Un puntatore al numero di byte che common language runtime (CLR) è consigliabile allocare oltre alla dimensione dell'oggetto Win32 `OVERLAPPED` oggetto.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Tutte le chiamate dei / o asincrone alle API della piattaforma Windows accettano Win32 `OVERLAPPED` oggetto che fornisce informazioni quali la posizione del puntatore del file. Per mantenere lo stato, le applicazioni che effettuano chiamate dei / o asincrone, in genere aggiungono dati personalizzati alla struttura. `GetHostOverlappedSize`e [IHostIoCompletionManager::](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) forniscono un'opportunità per l'host da includere tali dati.  
  
 CLR chiama il `GetHostOverlappedSize` metodo per determinare le dimensioni dei dati personalizzati che l'host da aggiungere al `OVERLAPPED` oggetto.  
  
> [!NOTE]
>  `GetHostOverlappedSize`viene chiamato una sola volta. Dati personalizzati dell'host devono essere la stessa dimensione per ogni richiesta dei / o.  
  
> [!IMPORTANT]
>  Le dimensioni del `OVERLAPPED` oggetto stesso non è incluso nel valore di `pcbSize`.  
  
 Per ulteriori informazioni sul `OVERLAPPED` struttura, vedere la documentazione di piattaforma di Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.NativeOverlapped>  
 [Interfaccia ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [Interfaccia IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
