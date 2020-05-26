---
title: Metodo IHostAssemblyManager::GetAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
ms.openlocfilehash: 587861529c340fad9fd817b904e4d3651b236e8d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805076"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a>Metodo IHostAssemblyManager::GetAssemblyStore
Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](ihostassemblystore-interface.md) che rappresenta l'elenco di assembly caricati dall'host.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppAssemblyStore`  
 out Puntatore a funzione a un' `IHostAssemblyStore` istanza o null se l'host non implementa `IHostAssemblyStore` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetAssemblyStore`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_NOINTERFACE|L'host non fornisce un'implementazione di `IHostAssemblyStore` .|  
  
## <a name="remarks"></a>Osservazioni  
 `IHostAssemblyStore`fornisce metodi che consentono a un host di eseguire l'associazione a assembly e moduli indipendentemente da CLR. Gli host forniscono in genere archivi di assembly per consentire il caricamento degli assembly da formati diversi dalla file system.  
  
> [!NOTE]
> Se l'host non implementa `IHostAssemblyStore` , `GetAssemblyStore` deve restituire un valore HRESULT di E_NOINTERFACE e deve `ppAssemblyStore` essere impostato su null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](ihostassemblystore-interface.md)
