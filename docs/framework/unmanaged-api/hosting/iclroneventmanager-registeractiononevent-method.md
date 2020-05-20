---
title: Metodo ICLROnEventManager::RegisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: e634b3876d51d461446ed3f5ae537ac1db1545bd
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703507"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a>Metodo ICLROnEventManager::RegisterActionOnEvent
Registra un puntatore di callback per l'evento specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `event`  
 in Uno dei valori di [EClrEvent](eclrevent-enumeration.md) , che indica l'evento per il quale registrare il puntatore di callback descritto da `pAction` .  
  
 `pAction`  
 in Puntatore a un oggetto [IActionOnCLREvent](iactiononclrevent-interface.md) che viene chiamato quando viene generato l'evento registrato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`RegisterActionOnEvent`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host può registrare i callback per uno o entrambi i due tipi di evento descritti da `EClrEvent` . L'host ottiene l' `ICLROnEventManager` interfaccia chiamando il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .  
  
> [!NOTE]
> Gli eventi `RegisterActionOnEvent` registrati possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrEvent](eclrevent-enumeration.md)
- [Interfaccia IActionOnCLREvent](iactiononclrevent-interface.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfaccia ICLROnEventManager](iclroneventmanager-interface.md)
