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
ms.openlocfilehash: 5b537d59014afa783d3f8c5046cc02dad7ea7740
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615995"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>Metodo ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
Ottiene i dati dell'associazione di identità dell'assembly per l'assembly nel percorso del file specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzFilePath`  
 in Percorso del file da valutare.  
  
 `dwFlags`  
 in Valore dell'enumerazione [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) che indica il tipo di identità di un assembly. Fornito per l'estendibilità futura. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore supportato dalla versione di Common Language Runtime (CLR) 2,0.  
  
 `pwzBuffer`  
 out Buffer contenente i dati di identità dell'assembly opaco.  
  
 `pcchBufferSize`  
 [in, out] Puntatore alla dimensione di `pwzBuffer` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Il metodo è stato restituito correttamente.|  
|E_INVALIDARG|L'oggetto specificato `pwzFilePath` è null.|  
|ERROR_INSUFFICIENT_BUFFER|La dimensione di `pwzBuffer` è troppo piccola.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `GetBindingIdentityFromFile`viene in genere chiamato due volte. La prima chiamata fornisce un valore null per `pwzBuffer` e il metodo restituisce le dimensioni appropriate in `pcchBufferSize` . La seconda chiamata fornisce un buffer allocato in modo appropriato e il metodo restituisce con i dati del buffer effettivi al completamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)
