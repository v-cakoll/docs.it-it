---
title: Funzione GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: be7d6ce29a9c9c4e3e530df40432b1a4c3b2d389
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136349"
---
# <a name="getrequestedruntimeversion-function"></a>Funzione GetRequestedRuntimeVersion
Ottiene il numero di versione della Common Language Runtime (CLR) richiesta dall'applicazione specificata. Se tale versione non è installata, ottiene la versione più recente installata prima della versione richiesta.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pExe`  
 in Nome dell'applicazione.  
  
 `pVersion`  
 out Buffer che contiene la stringa del numero di versione al completamento dell'operazione.  
  
 `cchBuffer`  
 in Lunghezza del buffer della versione.  
  
 `pdwLength`  
 out Puntatore alla lunghezza della stringa del numero di versione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|Il buffer della versione non è abbastanza grande per archiviare la stringa di versione.|  
|E_POINTER|`pdwLength` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [Funzione GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
