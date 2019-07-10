---
title: Metodo ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfd7c835cdc4b53c753d714216d1745eb0b80c2d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772939"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>Metodo ICLRDomainManager::SetPropertiesForDefaultAppDomain
Imposta le proprietà che verranno usate per inizializzare il dominio applicazione predefinito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nProperties`  
 [in] Il numero di voci `pwszPropertyNames` e `pwszPropertyValues`.  
  
 `pwszPropertyNames`  
 [in] Matrice di nomi di proprietà o null se non esistono proprietà. Attualmente, il nome della proprietà solo riconosciuto da questo metodo è "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".  
  
 `pwszPropertyValues`  
 [in] Matrice di valori di proprietà o null se non esistono proprietà.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` include un nome di proprietà che non è riconosciuto da questo metodo.|  
  
## <a name="remarks"></a>Note  
 Il valore della proprietà per "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" è un elenco di assembly con il parametro condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attributo (APTCA) con il <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag che devono essere resi visibili ai chiamanti parzialmente attendibili nell'applicazione predefinita dominio.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Interfaccia ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
