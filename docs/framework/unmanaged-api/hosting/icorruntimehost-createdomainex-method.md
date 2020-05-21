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
ms.openlocfilehash: 4e5856fbcda83c1dd30559c6f59f63495faea78d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762344"
---
# <a name="icorruntimehostcreatedomainex-method"></a>Metodo ICorRuntimeHost::CreateDomainEx
Crea un dominio applicazione. Il chiamante riceve un puntatore di interfaccia, di tipo <xref:System._AppDomain> , in un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType> . Questo metodo consente al chiamante di passare un'istanza di IAppDomainSetup per configurare funzionalità aggiuntive dell'istanza restituita <xref:System._AppDomain> .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzFriendlyName`  
 in Parametro facoltativo utilizzato per assegnare un nome descrittivo al dominio. Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio i debugger, per identificare il dominio.  
  
 `pSetup`  
 in Puntatore di interfaccia facoltativo di tipo `IAppDomainSetup` , ottenuto da una chiamata al metodo [ICorRuntimeHost:: CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) .  
  
 `pIdentityArray`  
 in Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano l'evidenza mappata tramite i criteri di sicurezza per stabilire un set di autorizzazioni. Un `IIdentity` oggetto può essere ottenuto chiamando il metodo [CreateEvidence](icorruntimehost-createevidence-method.md) .  
  
 `pAppDomain`  
 out Puntatore a un'interfaccia di tipo <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzata per controllare ulteriormente il dominio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'operazione è stata completata.|  
|S_FALSE|Non è stato possibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
  
## <a name="remarks"></a>Osservazioni  
 `CreateDomainEx`estende le funzionalità di [CreateDomain](icorruntimehost-createdomain-method.md) consentendo al chiamante di passare un' `IAppDomainSetup` istanza di con i valori delle proprietà per la configurazione del dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versione .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Metodo CreateDomain](icorruntimehost-createdomain-method.md)
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
