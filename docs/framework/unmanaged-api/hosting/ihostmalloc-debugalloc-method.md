---
title: Metodo IHostMAlloc::DebugAlloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 3f85e7c7fd54079ddce37f739a3a7bc0fa830d31
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493292"
---
# <a name="ihostmallocdebugalloc-method"></a>Metodo IHostMAlloc::DebugAlloc
Richiede che l'host allochi la quantità di memoria specificata dall'heap e tenga traccia anche della posizione in cui è stata allocata la memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cbSize`  
 in Dimensione, in byte, della richiesta di allocazione di memoria corrente.  
  
 `dwCriticalLevel`  
 in Uno dei valori di [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) , che indica l'effetto di un errore di allocazione.  
  
 `pszFileName`  
 in File di codice del file eseguibile di cui è in corso il debug.  
  
 `iLineNo`  
 in Numero di riga in `pszFileName` cui è stata richiesta l'allocazione.  
  
 `ppMem`  
 out Puntatore alla memoria allocata o null se non è stato possibile completare la richiesta.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`DebugAlloc`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente per completare la richiesta di allocazione.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR ottiene un puntatore a interfaccia a un'istanza di [IHostMalloc](ihostmalloc-interface.md) chiamando il metodo [IHostMemoryManager:: CreateMAlloc](ihostmemorymanager-createmalloc-method.md) . `DebugAlloc`consente al runtime di ottenere le informazioni sul file di codice da utilizzare durante il debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](ihostmemorymanager-interface.md)
- [Interfaccia IHostMalloc](ihostmalloc-interface.md)
