---
title: Metodo ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43a00d687c6a9ec42cb8573e70d181b4dc2c7d0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433217"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a>Metodo ICLRRuntimeInfo::LoadErrorString
Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 Questo metodo sostituisce le funzioni seguenti:  
  
-   [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
#### <a name="parameters"></a>Parametri  
 `iResourceID`  
 [in] HRESULT da convertire.  
  
 `pwzBuffer`  
 [out] La stringa di messaggio associata all'HRESULT specificato.  
  
 `pcchBuffer`  
 [in, out] Le dimensioni di `pwzbuffer` per evitare sovraccarichi del buffer. Se `pwzbuffer` è null, `pcchBuffer` fornisce la dimensione prevista di `pwzbuffer` per consentire la preallocazione.  
  
 `iLocaleID`  
 [in] L'identificatore delle impostazioni cultura. Per utilizzare le impostazioni cultura predefinite, è necessario specificare -1.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pcchBuffer` è null.|  
|E_INVALIDARG|`pwzBuffer` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
