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
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176240"
---
# <a name="loadstringrc-function"></a>Funzione LoadStringRC
Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iResourceID`  
 [in] Un HRESULT.  
  
 `szBuffer`  
 [fuori] Buffer che contiene il messaggio di errore al completamento.  
  
 `iMax`  
 [in] Dimensione del buffer dei messaggi di errore.  
  
 `bQuiet`  
 [in] Ignorato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM (Component Object Model) standard, come definito in WinError.h, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`szBuffer`è null `iMax` o è zero (0).|  
  
## <a name="remarks"></a>Osservazioni  
 Se il metodo non `szBuffer` viene completato correttamente, contiene una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll e Mscorwks.dll. Utilizzare MSCorEE.dll anziché Mscorwks.dll per assicurarsi che sia destinata alla versione corretta di .NET Framework.  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
