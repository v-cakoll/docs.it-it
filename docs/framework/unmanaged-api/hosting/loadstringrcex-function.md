---
title: Funzione LoadStringRCEx
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5520aef09c72819ff2b3763cd43af13f013263c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490218"
---
# <a name="loadstringrcex-function"></a>Funzione LoadStringRCEx
Converte un valore HRESULT a un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lcid`  
 [in] Un identificatore delle impostazioni cultura. Passare -1 per `lcid` usare le impostazioni cultura predefinite.  
  
 `iResourceID`  
 [in] Un valore HRESULT.  
  
 `szBuffer`  
 [out] Un buffer che contiene il messaggio di errore dopo il corretto completamento.  
  
 `iMax`  
 [in] Le dimensioni del buffer di messaggi di errore.  
  
 `bQuiet`  
 [in] Ignorato.  
  
 `pcwchUsed`  
 [out] Puntatore alla lunghezza del messaggio di errore.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szBuffer` è null, o `iMax` è zero (0).|  
  
## <a name="remarks"></a>Note  
 Se il metodo non viene completato correttamente, `szBuffer` contiene una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [Funzione LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
