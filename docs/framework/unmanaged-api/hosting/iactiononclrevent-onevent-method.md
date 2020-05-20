---
title: Metodo IActionOnCLREvent::OnEvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: a216a2925382016adeb100554bdceefdf3ee902b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616060"
---
# <a name="iactiononclreventonevent-method"></a>Metodo IActionOnCLREvent::OnEvent
Esegue callback per gli eventi che sono stati registrati tramite una chiamata al metodo [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `event`  
 in Uno dei valori di [EClrEvent](eclrevent-enumeration.md) , che indica il tipo di evento.  
  
 `data`  
 in Puntatore a un oggetto che contiene i dettagli relativi a `event` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`OnEvent`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante l'attesa di un thread bloccato o di Fiber.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive a qualsiasi metodo di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `data` parametro è un puntatore a un oggetto di tipo non specificato. Se il `event` parametro è `Event_DomainUnload` , `data` è l'identificatore numerico per l'oggetto <xref:System.AppDomain> che è stato scaricato. L'host può intraprendere l'azione appropriata utilizzando questo identificatore come chiave.  
  
 Se `event` è `Event_MDAFired` , `data` è un puntatore a un'istanza di [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) che contiene l'output del messaggio da un assistente al debug gestito (MDA). MDA sono una funzionalità di CLR che consente agli sviluppatori di eseguire il debug, generando messaggi XML sugli eventi che altrimenti sarebbero difficili da intercettare. Tali messaggi possono essere particolarmente utili per il debug di transizioni tra codice gestito e non gestito. Per ulteriori informazioni, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Enumerazione EClrEvent](eclrevent-enumeration.md)
- [Interfaccia IActionOnCLREvent](iactiononclrevent-interface.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfaccia ICLROnEventManager](iclroneventmanager-interface.md)
- [Struttura MDAInfo](mdainfo-structure.md)
