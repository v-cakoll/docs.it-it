---
title: Funzione LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 463bcf451574700d02f933d024ea5c24cedd259d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="loadstringrc-function"></a>Funzione LoadStringRC
Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `iResourceID`  
 [in] Un valore HRESULT.  
  
 `szBuffer`  
 [out] Un buffer che contiene il messaggio di errore dopo il completamento.  
  
 `iMax`  
 [in] Le dimensioni del buffer di messaggi di errore.  
  
 `bQuiet`  
 [in] Ignorato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore standard del modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szBuffer` è null o `iMax` è zero (0).|  
  
## <a name="remarks"></a>Note  
 Se il metodo non viene completata correttamente, `szBuffer` contiene una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** Mscoree. dll e mscorwks. dll. Utilizzare MSCorEE.dll anziché Mscorwks.dll per assicurarsi che la versione corretta di .NET Framework di destinazione.  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
