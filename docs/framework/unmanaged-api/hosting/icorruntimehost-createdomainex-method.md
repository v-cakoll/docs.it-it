---
title: Metodo ICorRuntimeHost::CreateDomainEx
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ed45c3975c58331490f89d8ca705f080d01d74e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466804"
---
# <a name="icorruntimehostcreatedomainex-method"></a>Metodo ICorRuntimeHost::CreateDomainEx
Crea un dominio dell'applicazione. Il chiamante riceve un puntatore di interfaccia di tipo <xref:System._AppDomain>, a un'istanza del tipo <xref:System.AppDomain?displayProperty=nameWithType>. Questo metodo consente al chiamante di passare un'istanza IAppDomainSetup per configurare le funzionalità aggiuntive del valore restituito <xref:System._AppDomain> istanza.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzFriendlyName`  
 [in] Un parametro facoltativo utilizzato per assegnare un nome descrittivo per il dominio. Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio ai debugger di identificare il dominio.  
  
 `pSetup`  
 [in] Un puntatore a interfaccia facoltativa di tipo `IAppDomainSetup`, ottenuto da una chiamata per il [CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) (metodo).  
  
 `pIdentityArray`  
 [in] Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano un'evidenza mappata tramite criteri di sicurezza per stabilire un set di autorizzazioni. Un' `IIdentity` oggetto può essere ottenuto chiamando il [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) (metodo).  
  
 `pAppDomain`  
 [out] Un puntatore a interfaccia typu <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzato per controllare ulteriormente il dominio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'operazione è riuscita.|  
|S_FALSE|Impossibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
  
## <a name="remarks"></a>Note  
 `CreateDomainEx` estende le funzionalità di [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) consentendo al chiamante di passare un `IAppDomainSetup` istanza con valori di proprietà per configurare il dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versione di .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vedere anche
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Metodo CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
