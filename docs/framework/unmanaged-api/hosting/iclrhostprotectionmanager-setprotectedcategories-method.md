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
ms.openlocfilehash: 5cf6f942add3d090cf830e71a545b9f4d4f69f00
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703171"
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
 in Combinazione di valori [EApiCategories](eapicategories-enumeration.md) , che indica quali categorie di tipi e membri gestiti devono essere bloccate dall'esecuzione in codice parzialmente attendibile.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Ogni `EApiCategories` valore fa riferimento a un elenco di tipi e membri gestiti. L' `EApiCategories` enumerazione e il `SetProtectedCategories` metodo sono direttamente correlati alla classe gestita <xref:System.Security.Permissions.HostProtectionAttribute> , che viene usata per contrassegnare i tipi e i membri gestiti che espongono funzionalità corrispondenti alle categorie descritte da `EApiCategories` . Per ulteriori informazioni, vedere <xref:System.Security.Permissions.HostProtectionAttribute> e l' <xref:System.Security.Permissions.HostProtectionResource> enumerazione, che corrisponde direttamente a `EApiCategories` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [Enumerazione EApiCategories](eapicategories-enumeration.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfaccia ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
