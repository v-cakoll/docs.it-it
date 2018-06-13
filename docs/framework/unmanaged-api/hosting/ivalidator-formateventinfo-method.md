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
ms.openlocfilehash: 875052ed26e83de50807e33e9c74dcf89f7ee679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440645"
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
  
#### <a name="parameters"></a>Parametri  
 `hVECode`  
 [in] Il valore HRESULT passato al gestore di errori di convalida.  
  
 `Context`  
 [in] Oggetto `VEContext` istanza che contiene informazioni sul contesto relative all'errore di convalida.  
  
 `msg`  
 [in, out] Stringa che contiene il messaggio di errore restituito.  
  
 `ulMaxLength`  
 [in] La lunghezza massima del messaggio di errore.  
  
 `psa`  
 [in] Una matrice protetta che contiene i parametri aggiuntivi che descrive l'errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator.h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 
