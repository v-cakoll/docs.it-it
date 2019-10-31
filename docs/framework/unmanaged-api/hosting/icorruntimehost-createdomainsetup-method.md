---
title: Metodo ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 217874e625604613e67170a118a7bc3616e02c4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139653"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a>Metodo ICorRuntimeHost::CreateDomainSetup
Ottiene un puntatore a interfaccia di tipo IAppDomainSetup a un'istanza di <xref:System.AppDomainSetup?displayProperty=nameWithType>. `IAppDomainSetup` fornisce i metodi per configurare gli aspetti di un dominio applicazione prima che venga creato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomainSetup`  
 out Puntatore a un'interfaccia a un'istanza di <xref:System.AppDomainSetup?displayProperty=nameWithType>. Questo parametro è tipizzato come `IUnknown`, quindi i chiamanti devono in genere chiamare `QueryInterface` su questo puntatore per ottenere un puntatore a interfaccia di tipo `IAppDomainSetup`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Operazione completata.|  
|S_FALSE|Non è stato possibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
  
## <a name="remarks"></a>Note  
 Il puntatore restituito da questo metodo viene in genere passato come parametro al metodo [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versione .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
