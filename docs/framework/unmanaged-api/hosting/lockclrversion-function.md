---
title: Funzione LockClrVersion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LockClrVersion
helpviewer_keywords: LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be41ae47f78a41e2f2be10a1e38d938dde9a4701
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lockclrversion-function"></a>Funzione LockClrVersion
Consente all'host determinare quale versione di common language runtime (CLR) verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito il CLR.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `hostCallback`  
 [in] La funzione deve essere chiamato da Common Language Runtime al momento dell'inizializzazione.  
  
 `pBeginHostSetup`  
 [in] La funzione di essere chiamato dall'host per indicare a CLR che l'inizializzazione sta avviando.  
  
 `pEndHostSetup`  
 [in] La funzione di essere chiamato dall'host per indicare a CLR che l'inizializzazione è stata completata.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|Uno o più argomenti sono null.|  
  
## <a name="remarks"></a>Note  
 L'host chiama `LockClrVersion` prima dell'inizializzazione di Common Language Runtime. `LockClrVersion`accetta tre parametri, ognuno dei quali sono i callback di tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Questo tipo viene definito come segue.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 I passaggi seguenti si verificano durante l'inizializzazione del runtime:  
  
1.  L'host chiama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione di runtime. In alternativa, l'host è stato possibile inizializzare il runtime mediante l'attivazione di oggetti COM.  
  
2.  Il runtime chiama la funzione specificata per il `hostCallback` parametro.  
  
3.  La funzione specificata da `hostCallback` effettua quindi la sequenza di chiamate seguente:  
  
    -   La funzione specificata per il `pBeginHostSetup` parametro.  
  
    -   `CorBindToRuntimeEx`(o un'altra funzione di inizializzazione di runtime).  
  
    -   [ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    -   [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    -   La funzione specificata per il `pEndHostSetup` parametro.  
  
 Tutte le chiamate da `pBeginHostSetup` per `pEndHostSetup` deve verificarsi in un solo thread o fiber, con lo stesso stack logico. Il thread può essere diverso dal thread su cui `hostCallback` viene chiamato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di Hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
