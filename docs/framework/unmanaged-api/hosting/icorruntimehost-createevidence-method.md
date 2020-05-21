---
title: Metodo ICorRuntimeHost::CreateEvidence
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
ms.openlocfilehash: 4a91f57126c0cf2074bd086ddb2fb4cd9e0716d4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762318"
---
# <a name="icorruntimehostcreateevidence-method"></a>Metodo ICorRuntimeHost::CreateEvidence
Ottiene un puntatore a interfaccia di tipo <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> , che consente all'host di creare evidenze di sicurezza da passare al metodo [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](icorruntimehost-createdomainex-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pEvidence`  
 out Puntatore di interfaccia a un' <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> istanza di utilizzata per creare l'evidenza di sicurezza. Questo puntatore è tipizzato `IUnknown` , quindi i chiamanti devono in genere chiamare `QueryInterface` su questa interfaccia per ottenere un puntatore a un oggetto <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'operazione è stata completata.|  
|S_FALSE|Non è stato possibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo restituisce una raccolta vuota che non può essere popolata dal codice nativo. Usare <xref:System.Security.Policy.Evidence> invece il metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versione .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
