---
title: Funzione GetVersionFromProcess
ms.date: 03/30/2017
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
ms.openlocfilehash: fbaf45da0902ded8a2f7bf0d470aaed3b5f531aa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617126"
---
# <a name="getversionfromprocess-function"></a>Funzione GetVersionFromProcess
Ottiene il numero di versione del Common Language Runtime (CLR) associato all'handle di processo specificato.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hProcess`  
 in Handle per un processo.  
  
 `pVersion`  
 out Buffer contenente la stringa del numero di versione al completamento del metodo.  
  
 `cchBuffer`  
 in Lunghezza del buffer della versione.  
  
 `pdwLength`  
 out Puntatore alla lunghezza della stringa del numero di versione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|Description|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`pVersion`è null e `cchBuffer` non è null o viceversa.<br /><br /> -oppure-<br /><br /> `hProcess`non è un handle valido per un processo.<br /><br /> -oppure-<br /><br /> CLR non caricato.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`è null o minore della lunghezza della stringa di versione.|  
|E_NOTIMPL|Questo metodo non è disponibile nel sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)
- [Funzione GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
