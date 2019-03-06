---
title: Metodo IValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 084b80e90ea3950245606c56de7ed3e18fd27662
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486433"
---
# <a name="ivalidatorformateventinfo-method"></a>Metodo IValidator::FormatEventInfo
Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hVECode`  
 [in] Il valore HRESULT passato al gestore di errori di convalida.  
  
 `Context`  
 [in] Oggetto `VEContext` istanza che contiene informazioni contestuali relative all'errore di convalida.  
  
 `msg`  
 [in, out] Stringa che contiene il messaggio di errore restituito.  
  
 `ulMaxLength`  
 [in] La lunghezza massima del messaggio di errore.  
  
 `psa`  
 [in] Una matrice protetta contenente parametri aggiuntivi che descrive l'errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator. H  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

