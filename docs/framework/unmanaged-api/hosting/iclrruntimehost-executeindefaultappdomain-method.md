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
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176409"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>Metodo ICLRRuntimeHost::ExecuteInDefaultAppDomain
Chiama il metodo specificato del tipo specificato nell'assembly gestito specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 [in] Percorso dell'oggetto <xref:System.Reflection.Assembly> che <xref:System.Type> definisce il cui metodo deve essere richiamato.  
  
 `pwzTypeName`  
 [in] Nome dell'oggetto <xref:System.Type> che definisce il metodo da richiamare.  
  
 `pwzMethodName`  
 [in] Nome del metodo da richiamare.  
  
 `pwzArgument`  
 [in] Parametro stringa da passare al metodo.  
  
 `pReturnValue`  
 [fuori] Valore intero restituito dal metodo richiamato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain`restituito con successo.|  
|HOST_E_CLRNOTAVAILABLE|Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il CRL non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo richiamato deve avere la firma seguente:The invoked method must have the following signature:  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 dove `pwzMethodName` rappresenta il nome del metodo `pwzArgument` richiamato e rappresenta il valore stringa passato come parametro a tale metodo. Se il valore HRESULT è `pReturnValue` impostato su S_OK, viene impostato sul valore integer restituito dal metodo richiamato. In `pReturnValue` caso contrario, non è impostato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
