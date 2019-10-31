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
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141045"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>Metodo ICLRHostProtectionManager::SetProtectedCategories
Specifica quali categorie di tipi e membri gestiti devono essere bloccate dall'esecuzione in codice parzialmente attendibile.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `categories`  
 in Combinazione di valori [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) , che indica quali categorie di tipi e membri gestiti devono essere bloccate dall'esecuzione in codice parzialmente attendibile.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Ogni valore `EApiCategories` fa riferimento a un elenco di tipi e membri gestiti. L'enumerazione `EApiCategories` e il metodo `SetProtectedCategories` sono direttamente correlati alla classe <xref:System.Security.Permissions.HostProtectionAttribute> gestita, che viene utilizzata per contrassegnare i tipi e i membri gestiti che espongono le funzionalità corrispondenti alle categorie descritte da `EApiCategories`. Per ulteriori informazioni, vedere <xref:System.Security.Permissions.HostProtectionAttribute> e l'enumerazione <xref:System.Security.Permissions.HostProtectionResource>, che corrisponde direttamente al `EApiCategories`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [Enumerazione EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
