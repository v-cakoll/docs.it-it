---
title: Metodo ICLRRuntimeHost::UnloadAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: 293c1764f4c0d857138726b8ed4855b1e3b03116
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703917"
---
# <a name="iclrruntimehostunloadappdomain-method"></a>Metodo ICLRRuntimeHost::UnloadAppDomain
Scarica l'oggetto gestito <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 in Identificatore numerico del dominio dell'applicazione da scaricare.  
  
 `fWaitUntilDone`  
 [in] `true` per indicare che il Common Language Runtime (CLR) deve attendere il completamento dell'esecuzione del thread corrente dell'applicazione prima di tentare di scaricare il dominio dell'applicazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`UnloadAppDomain`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 È possibile ottenere l'identificatore numerico del dominio dell'applicazione in cui è in esecuzione il thread corrente chiamando [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md). Questo identificatore corrisponde alla <xref:System.AppDomain.Id%2A> proprietà del <xref:System.AppDomain> tipo gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeHost](iclrruntimehost-interface.md)
