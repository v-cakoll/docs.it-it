---
title: Metodo ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136353"
---
# <a name="iclrruntimeinfoisloaded-method"></a>Metodo ICLRRuntimeInfo::IsLoaded
Indica se il Common Language Runtime (CLR) associato all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) viene caricato in un processo. È possibile caricare un runtime anche senza avviare.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a>Parametri  
 `hndProcess`  
 in Handle per il processo.  
  
 `pbLoaded`  
 [out] `true` se CLR viene caricato nel processo; in caso contrario, `false`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pbLoaded` è null.|  
  
## <a name="remarks"></a>Note  
 Questo metodo è compatibile con le versioni precedenti con le funzioni e le interfacce seguenti:  
  
- Interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) (nell'API di hosting .NET Framework versione 1).  
  
- Interfaccia [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) (nell'API di hosting .NET Framework 2,0).  
  
- Funzioni `CorBindTo*` deprecate (vedere [funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) nell'API di hosting .NET Framework 2,0).  
  
 Un host può chiamare una delle funzioni di `CorBindTo*` deprecate, ad esempio la funzione [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) , per creare un'istanza di una specifica versione di CLR. L'host può quindi chiamare il metodo [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) e specificare lo stesso numero di versione per ottenere un'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .  
  
 Se l'host chiama quindi il metodo `IsLoaded` sull'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) restituita, `pbLoaded` restituisce `true`; in caso contrario, restituisce `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
