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
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177987"
---
# <a name="loadstringrcex-function"></a>Funzione LoadStringRCEx
Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 [in] Identificatore delle impostazioni cultura. Passare -1 `lcid` per utilizzare le impostazioni cultura predefinite.  
  
 `iResourceID`  
 [in] Un HRESULT.  
  
 `szBuffer`  
 [fuori] Buffer che contiene il messaggio di errore al completamento.  
  
 `iMax`  
 [in] Dimensione del buffer dei messaggi di errore.  
  
 `bQuiet`  
 [in] Ignorato.  
  
 `pcwchUsed`  
 [fuori] Puntatore alla lunghezza del messaggio di errore.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito in WinError.h, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szBuffer`è null `iMax` o è zero (0).|  
  
## <a name="remarks"></a>Osservazioni  
 Se il metodo non `szBuffer` viene completato correttamente, contiene una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [Funzione LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
