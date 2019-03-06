---
title: Funzione LockClrVersion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3b263efa95936190ed771e811a84886b11be75b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465751"
---
# <a name="lockclrversion-function"></a>Funzione LockClrVersion
Consente all'host determinare quale versione di common language runtime (CLR) da utilizzare all'interno del processo prima di inizializzare in modo esplicito il CLR.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hostCallback`  
 [in] La funzione che verrà chiamata da CLR in fase di inizializzazione.  
  
 `pBeginHostSetup`  
 [in] La funzione da chiamare dall'host per indicare a CLR che l'inizializzazione sta avviando.  
  
 `pEndHostSetup`  
 [in] La funzione da chiamare dall'host per indicare a CLR che l'inizializzazione è stata completata.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|Uno o più argomenti sono null.|  
  
## <a name="remarks"></a>Note  
 L'host chiama `LockClrVersion` prima di inizializzare il CLR. `LockClrVersion` accetta tre parametri, ognuno dei quali sono i callback typu [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Questo tipo viene definito come segue.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Al momento dell'inizializzazione del runtime vengono eseguite le operazioni seguenti:  
  
1.  L'host chiama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione di runtime. In alternativa, l'host è stato possibile inizializzare il runtime usando l'attivazione di oggetti COM.  
  
2.  Il runtime chiama la funzione specificata dal `hostCallback` parametro.  
  
3.  La funzione specificata da `hostCallback` quindi rende la sequenza di chiamate seguente:  
  
    -   La funzione specificata dal `pBeginHostSetup` parametro.  
  
    -   `CorBindToRuntimeEx` (o un'altra funzione di inizializzazione di runtime).  
  
    -   [ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    -   [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    -   La funzione specificata dal `pEndHostSetup` parametro.  
  
 Tutte le chiamate da `pBeginHostSetup` a `pEndHostSetup` deve verificarsi su un singolo thread o fiber, con lo stesso stack di logico. Questo thread può essere diverso dal thread su cui `hostCallback` viene chiamato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
