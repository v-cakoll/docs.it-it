---
title: Metodo ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 0ce822533b0699f3467dc08044aa4dab59285a77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120307"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>Metodo ICLRRuntimeInfo::GetDefaultStartupFlags
Ottiene i flag di avvio e il file di configurazione host che verranno utilizzati per avviare il Runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwStartupFlags`  
 out Puntatore ai flag di avvio dell'host attualmente impostati.  
  
 `pwzHostConfigFile`  
 out Puntatore al percorso della directory del file di configurazione dell'host corrente.  
  
 `pcchHostConfigFile`  
 [in, out] In input, dimensioni di `pwzHostConfigFile`, per evitare sovraccarichi del buffer. Se `pwzHostConfigFile` è null, il metodo restituisce la dimensione richiesta di `pwzHostConfigFile` per la pre-allocazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce il seguente HRESULT specifico, oltre a errori HRESULT che indicano un errore del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="remarks"></a>Note  
 Questo metodo restituisce i valori dei flag predefiniti (`STARTUP_CONCURRENT_GC` e `NULL`) o i valori forniti da una chiamata precedente al [Metodo ICLRRuntimeInfo:: SetDefaultStartupFlags](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)o i valori impostati da uno dei metodi di `CorBind*` se sono associati a questo runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
