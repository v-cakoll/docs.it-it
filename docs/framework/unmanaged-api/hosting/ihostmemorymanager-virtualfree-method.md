---
title: Metodo IHostMemoryManager::VirtualFree
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: 4d37b7d803509ebfa861b7502d419f868bd12e11
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804379"
---
# <a name="ihostmemorymanagervirtualfree-method"></a>Metodo IHostMemoryManager::VirtualFree
Funge da wrapper logico per la funzione Win32 corrispondente. L'implementazione Win32 di `VirtualFree` rilascia, effettua il commit o rilascia un'area di pagine all'interno dello spazio degli indirizzi virtuali del processo chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lpAddress`  
 in Puntatore all'indirizzo di base delle pagine di memoria virtuale da liberare.  
  
 `dwSize`  
 in Dimensione, in byte, dell'area da liberare.  
  
 `dwFreeType`  
 in Tipo di operazione di liberazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`VirtualFree`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|È stato effettuato un tentativo di liberare la memoria non allocata tramite l'host.|  
  
## <a name="remarks"></a>Osservazioni  
 `VirtualFree`libera le pagine di memoria virtuale associate al `lpAddress` parametro tramite una chiamata precedente alla funzione [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) . I tentativi di liberare memoria non allocata tramite l'host devono restituire HOST_E_INVALIDOPERATION.  
  
 La semantica è identica a quella dell'implementazione Win32 di `VirtualFree` . Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](ihostmemorymanager-interface.md)
- [Interfaccia IHostMalloc](ihostmalloc-interface.md)
