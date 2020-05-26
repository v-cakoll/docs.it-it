---
title: Metodo IHostMemoryManager::VirtualAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
ms.openlocfilehash: de41b5e0aaf835ee2d4e4f32696fe104d5830b57
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804456"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>Metodo IHostMemoryManager::VirtualAlloc
Funge da wrapper logico per la funzione Win32 corrispondente. L'implementazione Win32 di `VirtualAlloc` riserva o viene eseguito il commit di un'area di pagine nello spazio degli indirizzi virtuali del processo chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAddress`  
 in Puntatore all'indirizzo iniziale dell'area da allocare.  
  
 `dwSize`  
 in Dimensione, in byte, dell'area.  
  
 `flAllocationType`  
 in Tipo di allocazione di memoria.  
  
 `flProtect`  
 in Protezione della memoria per l'area di pagine da allocare.  
  
 `dwCriticalLevel`  
 in Valore [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) che indica l'effetto di un errore di allocazione.  
  
 `ppMem`  
 out Puntatore all'indirizzo iniziale della memoria allocata o null se la richiesta non è stata soddisfatta.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente per completare la richiesta di allocazione|  
  
## <a name="remarks"></a>Osservazioni  
 Si riserva un'area nello spazio degli indirizzi del processo chiamando `VirtualAlloc` . Il `pAddress` parametro contiene l'indirizzo iniziale del blocco di memoria desiderato. Questo parametro è in genere impostato su null. Il sistema operativo tiene traccia degli intervalli di indirizzi liberi disponibili per il processo. Il `pAddress` valore null indica al sistema di riservare l'area laddove ritenga appropriato. In alternativa, è possibile specificare un indirizzo iniziale specifico per il blocco di memoria. In entrambi i casi, il parametro `ppMem` di output viene restituito come puntatore alla memoria allocata. La funzione stessa restituisce un valore HRESULT.  
  
 La funzione Win32 non `VirtualAlloc` dispone di un `ppMem` parametro e restituisce invece il puntatore alla memoria allocata. Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](ihostmemorymanager-interface.md)
