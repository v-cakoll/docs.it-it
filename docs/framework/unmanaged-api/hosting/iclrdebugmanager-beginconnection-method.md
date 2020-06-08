---
title: Metodo ICLRDebugManager::BeginConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
ms.openlocfilehash: 98e4efe149cab1b822c9993e4df28806f773c61d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504251"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a>Metodo ICLRDebugManager::BeginConnection
Stabilisce una nuova connessione tra l'host e il debugger per associare un elenco di attività con un identificatore e un nome descrittivo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwConnectionId`  
 in Identificatore da associare all'elenco di attività di Common Language Runtime (CLR).  
  
 `szConnectionName`  
 in Nome descrittivo da associare all'elenco delle attività CLR.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`BeginConnection`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|`dwConnectionId`è zero oppure `BeginConnection` è già stato chiamato usando questo `dwConnectionId` valore o `szConnectionName` è null.|  
|E_OUTOFMEMORY|Impossibile allocare memoria sufficiente per contenere l'elenco delle attività associate a questa connessione.|  
  
## <a name="remarks"></a>Osservazioni  
 [ICLRDebugManager](iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)e [EndConnection](iclrdebugmanager-endconnection-method.md), per associare elenchi di attività con identificatori e nomi descrittivi.  
  
> [!IMPORTANT]
> Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività. `BeginConnection`viene chiamato per primo per stabilire una nuova connessione. `SetConnectionTasks`viene chiamato Next per fornire il set di attività da associare a tale connessione. `EndConnection`viene chiamato per ultimo per rimuovere l'associazione tra l'elenco attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate per connessioni diverse possono essere nidificate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfaccia ICLRDebugManager](iclrdebugmanager-interface.md)
- [Metodo EndConnection](iclrdebugmanager-endconnection-method.md)
- [Metodo SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)
- [Interfaccia IHostControl](ihostcontrol-interface.md)
