---
title: Metodo IHostIoCompletionManager::InitializeHostOverlapped
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: cf257ab86d27946c861c89dff5e6f09a42013e58
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804705"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>Metodo IHostIoCompletionManager::InitializeHostOverlapped
Fornisce all'host la possibilità di inizializzare i dati personalizzati da accodare a una `OVERLAPPED` struttura Win32 utilizzata per le richieste di I/O asincrone.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pvOverlapped`  
 in Puntatore alla `OVERLAPPED` struttura Win32 da includere con la richiesta di i/O.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente per l'allocazione della risorsa richiesta.|  
  
## <a name="remarks"></a>Osservazioni  
 Le funzioni della piattaforma Windows utilizzano la `OVERLAPPED` struttura per archiviare lo stato delle richieste di I/O asincrone. CLR chiama il `InitializeHostOverlapped` metodo per concedere all'host la possibilità di accodare dati personalizzati a un' `OVERLAPPED` istanza di.  
  
> [!IMPORTANT]
> Per ottenere l'inizio del blocco di dati personalizzato, gli host devono impostare l'offset sulle dimensioni della `OVERLAPPED` struttura ( `sizeof(OVERLAPPED)` ).  
  
 Un valore restituito di E_OUTOFMEMORY indica che l'host non è stato in grado di inizializzare i dati personalizzati. In questo caso, CLR segnala un errore e non riesce a chiamare.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRIoCompletionManager](iclriocompletionmanager-interface.md)
- [Metodo GetHostOverlappedSize](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [Interfaccia IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
