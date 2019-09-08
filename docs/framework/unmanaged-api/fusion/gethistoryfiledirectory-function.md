---
title: Funzione GetHistoryFileDirectory
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adbbf94dc36c6d82360ed532b283cd666a1a52ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796858"
---
# <a name="gethistoryfiledirectory-function"></a>Funzione GetHistoryFileDirectory
Recupera il percorso della directory della cronologia dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wzDir`  
 out Buffer che consente di memorizzare il percorso della directory della cronologia dell'applicazione.  
  
 `pdwSize`  
 [in, out] Lunghezza del buffer.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard, definiti nel file WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|DESCRIZIONE|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`wzDir`o `pdwSize` è null oppure la stringa di versione non è corretta.|  
  
## <a name="remarks"></a>Note  
 Al termine dell'operazione, `pdwSize` l'argomento viene impostato sulla lunghezza della stringa di percorso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria** Fusion. dll e mscorwks. dll. Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CreateHistoryReader](createhistoryreader-function.md)
- [Funzione NukeDownloadedCache](nukedownloadedcache-function.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
