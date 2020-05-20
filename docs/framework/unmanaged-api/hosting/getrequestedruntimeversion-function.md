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
ms.openlocfilehash: b7a38d28b55842e9358bd9c7019b84c529526613
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617165"
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
  
|Codice restituito|Description|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|Il buffer della versione non è abbastanza grande per archiviare la stringa di versione.|  
|E_POINTER|`pdwLength` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)
- [Funzione GetVersionFromProcess](getversionfromprocess-function.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
