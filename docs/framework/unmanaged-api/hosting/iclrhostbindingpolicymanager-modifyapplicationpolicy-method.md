---
title: Metodo ICLRHostBindingPolicyManager::ModifyApplicationPolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178093"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>Metodo ICLRHostBindingPolicyManager::ModifyApplicationPolicy
Modifica i criteri di associazione per l'assembly specificato e crea una nuova versione dei criteri.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzSourceAssemblyIdentity`  
 [in] Identità dell'assembly da modificare.  
  
 `pwzTargetAssemblyIdentity`  
 [in] Nuova identità dell'assembly modificato.  
  
 `pbApplicationPolicy`  
 [in] Puntatore a un buffer che contiene i dati dei criteri di associazione per l'assembly da modificare.  
  
 `cbAppPolicySize`  
 [in] Dimensione del criterio di binding da sostituire.  
  
 `dwPolicyModifyFlags`  
 [in] Combinazione logica OR di valori [EHostBindingPolicyModifyFlags,](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) che indica il controllo del reindirizzamento.  
  
 `pbNewApplicationPolicy`  
 [fuori] Puntatore a un buffer che contiene i nuovi dati dei criteri di associazione.  
  
 `pcbNewAppPolicySize`  
 [in, out] Puntatore alla dimensione del nuovo buffer dei criteri di associazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il criterio è stato modificato correttamente.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`o `pwzTargetAssemblyIdentity` era un riferimento nullo.|  
|ERROR_INSUFFICIENT_BUFFER|Il valore di `pbNewApplicationPolicy` è troppo piccolo.|  
|HOST_E_CLRNOTAVAILABLE|Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `ModifyApplicationPolicy` metodo può essere chiamato due volte. La prima chiamata deve fornire `pbNewApplicationPolicy` un valore null per il parametro. Questa chiamata restituirà il `pcbNewAppPolicySize`valore necessario per . La seconda chiamata deve `pcbNewAppPolicySize`fornire questo valore per e `pbNewApplicationPolicy`puntare a un buffer di tale dimensione per .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
