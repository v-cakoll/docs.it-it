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
ms.openlocfilehash: a05cbe985c2cfebb67756fdfb54398b36e87f441
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008514"
---
# <a name="loadstringrcex-function"></a>Funzione LoadStringRCEx
Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
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
 in Identificatore di impostazioni cultura. Passare-1 per per `lcid` usare le impostazioni cultura predefinite.  
  
 `iResourceID`  
 [in] Un HRESULT.  
  
 `szBuffer`  
 out Un buffer che contiene il messaggio di errore al completamento dell'operazione.  
  
 `iMax`  
 in Dimensioni del buffer dei messaggi di errore.  
  
 `bQuiet`  
 in Ignorato.  
  
 `pcwchUsed`  
 out Puntatore alla lunghezza del messaggio di errore.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szBuffer`è null o `iMax` è zero (0).|  
  
## <a name="remarks"></a>Commenti  
 Se il metodo non viene completato correttamente, `szBuffer` contiene una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [Funzione LoadStringRC](loadstringrc-function.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
