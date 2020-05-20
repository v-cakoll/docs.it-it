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
ms.openlocfilehash: 0e1395229b67c4054df62935375a4136edf63078
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616489"
---
# <a name="createdebugginginterfacefromversion-function"></a>Funzione CreateDebuggingInterfaceFromVersion
Crea un oggetto [ICorDebug](../debugging/icordebug-interface.md) in base alle informazioni sulla versione specificate.  
  
 Questa funzione è obsoleta in .NET Framework 4. Per ottenere un'interfaccia per il Common Language Runtime (CLR) 2,0, usare invece il metodo [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) e specificare l'identificatore di classe CLSID_CLRDebuggingLegacy e l'identificatore di interfaccia IID_ICorDebug. Per ottenere un'interfaccia per CLR 4 o versione successiva, chiamare la funzione [CLRCreateInstance](clrcreateinstance-function.md) e specificare l'identificatore di classe CLSID_CLRDebugging e l'identificatore di interfaccia IID_ICLRDebugging.  
  
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
 in Versione di `ICorDebug` prevista dal debugger. Per i valori validi, vedere l'enumerazione [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) .  
  
 `szDebuggeeVersion`  
 in Versione Common Language Runtime associata all'applicazione o al processo di cui eseguire il debug. Per informazioni sul recupero di questo valore, vedere il metodo [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) .  
  
 `ppCordb`  
 out Posizione che riceve un puntatore all' `ICorDebug` oggetto.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard come definito nel file WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|Description|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szDebuggeeVersion`o `ppCordb` è null oppure la stringa di versione non è corretta.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `szDebuggeeVersion` parametro esegue il mapping alla versione corrispondente di mscordbi. dll.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
