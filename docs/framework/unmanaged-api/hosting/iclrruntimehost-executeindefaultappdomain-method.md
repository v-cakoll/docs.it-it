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
ms.openlocfilehash: 070c52258b66dcc352f2beef81b9a0694b8301ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703279"
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
 in Percorso dell'oggetto <xref:System.Reflection.Assembly> che definisce il <xref:System.Type> cui metodo deve essere richiamato.  
  
 `pwzTypeName`  
 in Nome dell'oggetto <xref:System.Type> che definisce il metodo da richiamare.  
  
 `pwzMethodName`  
 in Nome del metodo da richiamare.  
  
 `pwzArgument`  
 in Parametro di stringa da passare al metodo.  
  
 `pReturnValue`  
 out Valore integer restituito dal metodo richiamato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il CRL non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo richiamato deve avere la firma seguente:  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 dove `pwzMethodName` rappresenta il nome del metodo richiamato e `pwzArgument` rappresenta il valore stringa passato come parametro al metodo. Se il valore HRESULT è impostato su S_OK, `pReturnValue` viene impostato sul valore integer restituito dal metodo richiamato. In caso contrario, `pReturnValue` non è impostato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeHost](iclrruntimehost-interface.md)
