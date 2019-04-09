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
ms.openlocfilehash: b60dde31707175a27d2dc6c50484d6089adaeaa6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229625"
---
# <a name="gethistoryfiledirectory-function"></a>Funzione GetHistoryFileDirectory
Recupera il percorso della directory della cronologia dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wzDir`  
 [out] Buffer contenente il percorso della directory della cronologia dell'applicazione.  
  
 `pdwSize`  
 [in, out] La lunghezza del buffer.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror h oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_INVALIDARG|`wzDir` o `pdwSize` è null o una versione stringa non è corretta.|  
  
## <a name="remarks"></a>Note  
 Al termine, il `pdwSize` argomento è impostato per la lunghezza della stringa di percorso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Fusion. dll e mscorwks. dll. Usare Fusion. dll invece di Mscorwks. dll per verificare che da usare come destinazione la versione corretta di .NET Framework.  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CreateHistoryReader](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [Funzione NukeDownloadedCache](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
