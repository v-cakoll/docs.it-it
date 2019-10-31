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
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133768"
---
# <a name="lockclrversion-function"></a>Funzione LockClrVersion
Consente all'host di determinare quale versione di Common Language Runtime (CLR) verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito CLR.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hostCallback`  
 in Funzione che deve essere chiamata da CLR dopo l'inizializzazione.  
  
 `pBeginHostSetup`  
 in Funzione che deve essere chiamata dall'host per informare il CLR che l'inizializzazione è stata avviata.  
  
 `pEndHostSetup`  
 in Funzione che deve essere chiamata dall'host per informare CLR che l'inizializzazione è stata completata.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|Uno o più argomenti sono null.|  
  
## <a name="remarks"></a>Note  
 L'host chiama `LockClrVersion` prima di inizializzare CLR. `LockClrVersion` accetta tre parametri, che sono tutti callback di tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Questo tipo è definito nel modo seguente.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Durante l'inizializzazione del runtime si verificano i passaggi seguenti:  
  
1. L'host chiama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione del runtime. In alternativa, l'host potrebbe inizializzare il runtime utilizzando l'attivazione di oggetti COM.  
  
2. Il runtime chiama la funzione specificata dal parametro `hostCallback`.  
  
3. La funzione specificata da `hostCallback` esegue quindi la sequenza di chiamate seguente:  
  
    - Funzione specificata dal parametro `pBeginHostSetup`.  
  
    - `CorBindToRuntimeEx` o un'altra funzione di inizializzazione del runtime.  
  
    - [ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    - Funzione specificata dal parametro `pEndHostSetup`.  
  
 Tutte le chiamate da `pBeginHostSetup` a `pEndHostSetup` devono essere eseguite su un singolo thread o Fiber, con lo stesso stack logico. Questo thread può essere diverso dal thread sul quale viene chiamato `hostCallback`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
