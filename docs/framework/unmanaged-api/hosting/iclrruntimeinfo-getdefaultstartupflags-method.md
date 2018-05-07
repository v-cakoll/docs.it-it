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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 546a26306a1faaeceb1337b79bd2d27970d9f5be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>Metodo ICLRRuntimeInfo::GetDefaultStartupFlags
Ottiene i flag di avvio e di un file di configurazione di host che verrà utilizzato per avviare il runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pdwStartupFlags`  
 [out] Un puntatore per i flag di avvio host attualmente impostati.  
  
 `pwzHostConfigFile`  
 [out] Puntatore al percorso di directory del file di configurazione host corrente.  
  
 `pcchHostConfigFile`  
 [in, out] In input, le dimensioni di `pwzHostConfigFile`, per evitare sovraccarichi del buffer. Se `pwzHostConfigFile` è null, il metodo restituisce la dimensione necessaria della `pwzHostConfigFile` per pre-allocazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce il valore HRESULT specifico seguente nonché gli errori HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="remarks"></a>Note  
 Questo metodo restituisce i valori di flag predefiniti (`STARTUP_CONCURRENT_GC` e `NULL`), i valori forniti da una chiamata precedente a o il [SetDefaultStartupFlags (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), o i valori impostati da qualsiasi il `CorBind*` metodi se vengono associati a questo runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
