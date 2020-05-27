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
ms.openlocfilehash: 09bcebfdcfea3d5728d404cdb6b5fb170a5432c3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008495"
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
  
## <a name="remarks"></a>Commenti  
 L'host chiama `LockClrVersion` prima di inizializzare CLR. `LockClrVersion`accetta tre parametri, che sono tutti callback di tipo [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md). Questo tipo è definito nel modo seguente.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Durante l'inizializzazione del runtime si verificano i passaggi seguenti:  
  
1. L'host chiama [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione del runtime. In alternativa, l'host potrebbe inizializzare il runtime utilizzando l'attivazione di oggetti COM.  
  
2. Il runtime chiama la funzione specificata dal `hostCallback` parametro.  
  
3. La funzione specificata da `hostCallback` esegue quindi la sequenza di chiamate seguente:  
  
    - Funzione specificata dal `pBeginHostSetup` parametro.  
  
    - `CorBindToRuntimeEx`(o un'altra funzione di inizializzazione del Runtime).  
  
    - [ICLRRuntimeHost:: SetHostControl](iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).  
  
    - Funzione specificata dal `pEndHostSetup` parametro.  
  
 Tutte le chiamate da `pBeginHostSetup` a `pEndHostSetup` devono essere eseguite su un singolo thread o Fiber, con lo stesso stack logico. Questo thread può essere diverso dal thread su cui `hostCallback` viene chiamato il metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
