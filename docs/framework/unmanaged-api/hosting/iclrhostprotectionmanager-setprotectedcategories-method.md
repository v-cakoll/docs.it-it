---
title: Metodo ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6c93566d0909f1dbef46862760d47ede478d51a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>Metodo ICLRHostProtectionManager::SetProtectedCategories
Specifica le categorie di tipi e membri gestiti devono essere impedite l'esecuzione in codice parzialmente attendibile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `categories`  
 [in] Una combinazione di [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) valori, che indica le categorie di tipi e membri gestiti devono essere impedite l'esecuzione in codice parzialmente attendibile.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Ogni `EApiCategories` valore si riferisce a un elenco di tipi e membri gestiti. Il `EApiCategories` enumerazione e `SetProtectedCategories` metodo sono direttamente correlati all'oggetto gestito <xref:System.Security.Permissions.HostProtectionAttribute> (classe), che viene usato per contrassegnare i tipi gestiti e i membri che espongono funzionalità corrispondenti alle categorie descritte da `EApiCategories`. Per ulteriori informazioni, vedere <xref:System.Security.Permissions.HostProtectionAttribute> e <xref:System.Security.Permissions.HostProtectionResource> enumerazione, che corrisponde direttamente a `EApiCategories`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [Enumerazione EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
