---
title: Metodo ICLRRuntimeHost::ExecuteInDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e6805dc67f7ec5ceb8c67d77462a0200b6c0317
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205907"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>Metodo ICLRRuntimeHost::ExecuteInDefaultAppDomain
Chiama il metodo specificato nel tipo specificato nell'assembly gestito specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzAssemblyPath`  
 [in] Il percorso per il <xref:System.Reflection.Assembly> che definisce il <xref:System.Type> il cui metodo deve essere richiamato.  
  
 `pwzTypeName`  
 [in] Il nome del <xref:System.Type> che definisce il metodo da richiamare.  
  
 `pwzMethodName`  
 [in] Nome del metodo da richiamare.  
  
 `pwzArgument`  
 [in] Il parametro della stringa da passare al metodo.  
  
 `pReturnValue`  
 [out] Valore intero restituito dal metodo richiamato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo viene restituito E_FAIL, il CRL non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Il metodo richiamato deve avere la firma seguente:  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 in cui `pwzMethodName` rappresenta il nome del metodo richiamato, e `pwzArgument` rappresenta il valore di stringa passato come parametro al metodo. Se il valore HRESULT è impostato su S_OK, `pReturnValue` è impostata sul valore integer restituito dal metodo richiamato. In caso contrario, `pReturnValue` non è impostata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
