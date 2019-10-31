---
title: Metodo ICorRuntimeHost::CreateDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: 7c3e37fdb8a5afc973c913b1cfa56ab2e9f4fa52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127722"
---
# <a name="icorruntimehostcreatedomain-method"></a>Metodo ICorRuntimeHost::CreateDomain
Crea un dominio applicazione. Il chiamante riceve un puntatore di interfaccia di tipo <xref:System._AppDomain> a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType>.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzFriendlyName`  
 in Parametro facoltativo utilizzato per assegnare un nome descrittivo al dominio. Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio i debugger, per identificare il dominio.  
  
 `pIdentityArray`  
 in Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano l'evidenza mappata tramite i criteri di sicurezza per stabilire un set di autorizzazioni. È possibile ottenere un oggetto `IIdentity` chiamando il metodo [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) .  
  
 `pAppDomain`  
 out Puntatore a un'interfaccia di tipo <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzata per controllare ulteriormente il dominio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Operazione completata.|  
|S_FALSE|Non è stato possibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
