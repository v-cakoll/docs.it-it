---
title: Funzione CreateDebuggingInterfaceFromVersion
ms.date: 03/30/2017
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
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176448"
---
# <a name="createdebugginginterfacefromversion-function"></a>Funzione CreateDebuggingInterfaceFromVersion
Crea un [oggetto ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) in base alle informazioni sulla versione specificate.  
  
 Questa funzione è obsoleta in .NET Framework 4. Al contrario, per ottenere un'interfaccia per Common Language Runtime (CLR) 2.0, utilizzare il [metodo ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) e specificare l'identificatore di classe CLSID_CLRDebuggingLegacy e l'identificatore di interfaccia IID_ICorDebug. Per ottenere un'interfaccia per CLR 4 o versione successiva, chiamare la funzione [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) e specificare l'identificatore di classe CLSID_CLRDebugging e l'identificatore di interfaccia IID_ICLRDebugging.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iDebuggerVersion`  
 [in] La versione `ICorDebug` di che è previsto dal debugger. Vedere il [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumerazione per i valori validi.  
  
 `szDebuggeeVersion`  
 [in] Versione di Common Language Runtime associata all'applicazione o al processo di cui eseguire il debug. Vedere il [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) metodo per informazioni sul recupero di questo valore.  
  
 `ppCordb`  
 [fuori] Posizione che riceve un puntatore all'oggetto. `ICorDebug`  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard come definito nel file WinError.h oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szDebuggeeVersion`o `ppCordb` è null o la stringa di versione non è corretta.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `szDebuggeeVersion` parametro esegue il mapping alla versione corrispondente di MSCorDbi.dll.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
