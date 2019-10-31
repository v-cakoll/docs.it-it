---
title: Funzione GetRealProcAddress
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 9dffc3d197b05bb71443aa60c101260daabadadd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136401"
---
# <a name="getrealprocaddress-function"></a>Funzione GetRealProcAddress
Ottiene l'indirizzo della funzione specificata esportata dalla versione installata più recente del Common Language Runtime (CLR).  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwszProcName`  
 in Nome della funzione.  
  
 `ppv`  
 out Posizione che riceve un puntatore all'indirizzo della funzione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti definiti in CorError. h.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`ppv` non è valido.|  
|CLR_E_SHIM_RUNTIMEEXPORT|La funzione non viene esportata dal runtime.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
