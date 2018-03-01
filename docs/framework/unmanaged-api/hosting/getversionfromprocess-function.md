---
title: Funzione GetVersionFromProcess
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
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db5054ab9b71eb93005fc0315acba82d807487ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getversionfromprocess-function"></a>Funzione GetVersionFromProcess
Ottiene il numero di versione di common language runtime (CLR) che è associato l'handle del processo specificato.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `hProcess`  
 [in] Un handle a un processo.  
  
 `pVersion`  
 [out] Un buffer che contiene la stringa del numero di versione al completamento del metodo.  
  
 `cchBuffer`  
 [in] La lunghezza del buffer della versione.  
  
 `pdwLength`  
 [out] Puntatore alla lunghezza della stringa di numeri di versione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore standard del modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`pVersion`è null e `cchBuffer` non è null, o viceversa.<br /><br /> oppure<br /><br /> `hProcess`non è un handle a un processo valido.<br /><br /> oppure<br /><br /> CLR non è caricato.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`è null o inferiore alla lunghezza della stringa di versione.|  
|E_NOTIMPL|Questo metodo non è disponibile nel sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Windows Millennium Edition di Microsoft.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [Funzione GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
