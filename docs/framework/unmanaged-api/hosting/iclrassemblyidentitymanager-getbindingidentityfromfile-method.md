---
title: Metodo ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28e97289eda5949e6d124426eb58105e2e3ad33e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435042"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>Metodo ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
Ottiene l'identità dell'assembly di associazione dati per l'assembly nel percorso del file specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwzFilePath`  
 [in] Il percorso del file da valutare.  
  
 `dwFlags`  
 [in] Il valore di [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumerazione che indica il tipo di identità di un assembly. Fornito per l'estensibilità futura. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore che common language runtime (CLR) versione 2.0 supporta.  
  
 `pwzBuffer`  
 [out] Un buffer contenente i dati di identità di assembly opaca.  
  
 `pcchBufferSize`  
 [in, out] Un puntatore alla dimensione del `pwzBuffer`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il metodo è stato restituito correttamente.|  
|E_INVALIDARG|Fornito `pwzFilePath` è null.|  
|ERROR_INSUFFICIENT_BUFFER|Le dimensioni di `pwzBuffer` è troppo piccolo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `GetBindingIdentityFromFile` viene in genere chiamato due volte. La prima chiamata fornisce un valore null per `pwzBuffer`, e il metodo restituisce le dimensioni appropriate in `pcchBufferSize`. La seconda chiamata viene fornito un buffer allocato in modo appropriato, e il metodo restituisce i dati effettiva del buffer al termine dell'operazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
