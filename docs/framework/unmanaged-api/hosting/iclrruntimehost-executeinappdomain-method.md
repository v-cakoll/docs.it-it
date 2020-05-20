---
title: Metodo ICLRRuntimeHost::ExecuteInAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: 505c16cb7ead7950b6d2d6d401730cc3368fb6aa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703302"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>Metodo ICLRRuntimeHost::ExecuteInAppDomain
Specifica l'oggetto <xref:System.AppDomain> in cui eseguire il codice gestito specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `AppDomainId`  
 in ID numerico dell'oggetto <xref:System.AppDomain> nel quale eseguire il metodo specificato.  
  
 `pCallback`  
 in Puntatore alla funzione da eseguire all'interno dell'oggetto specificato <xref:System.AppDomain> .  
  
 `cookie`  
 in Puntatore alla memoria allocata dal chiamante opaco. Questo parametro viene passato dal Common Language Runtime (CLR) al callback del dominio. Non si tratta di memoria heap gestita dal runtime; sia l'allocazione che la durata della memoria sono controllate dal chiamante.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `ExecuteInAppDomain`consente all'host di esercitare il controllo su quale gestito <xref:System.AppDomain> deve essere eseguito il metodo gestito specificato. È possibile ottenere il valore dell'identificatore di un dominio dell'applicazione, che corrisponde al valore della <xref:System.AppDomain.Id%2A> proprietà, chiamando il [Metodo GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeHost](iclrruntimehost-interface.md)
