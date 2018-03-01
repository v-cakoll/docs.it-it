---
title: Funzione CreateDebuggingInterfaceFromVersion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b3f269f5b1758481995d6064e7137e62bff4a868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function"></a>Funzione CreateDebuggingInterfaceFromVersion
Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) oggetto in base alle informazioni di versione specificata.  
  
 Questa funzione è obsoleta nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Per ottenere un'interfaccia per common language runtime (CLR) 2.0, usare invece il [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) (metodo) e specificare l'identificatore di classe CLSID_CLRDebuggingLegacy e l'identificatore di interfaccia IID_ICorDebug. Per ottenere un'interfaccia per 4 di CLR o in un secondo momento, chiamare il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzione e specificare l'identificatore di classe CLSID_CLRDebugging e l'identificatore di interfaccia IID_ICLRDebugging.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `iDebuggerVersion`  
 [in] La versione di `ICorDebug` prevista dal debugger. Vedere il [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumerazione per i valori validi.  
  
 `szDebuggeeVersion`  
 [in] La versione common language runtime associata con l'applicazione o il processo di cui eseguire il debug. Vedere il [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) metodo per informazioni su come recuperare questo valore.  
  
 `ppCordb`  
 [out] La posizione che riceve un puntatore di `ICorDebug` oggetto.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szDebuggeeVersion`o `ppCordb` è null o la versione stringa non è corretta.|  
  
## <a name="remarks"></a>Note  
 Il `szDebuggeeVersion` esegue il mapping di parametro per la versione corrispondente di MSCorDbi.dll.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
