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
ms.openlocfilehash: 31329a8674a9991a3f306eeff44ee3437ad64a5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779429"
---
# <a name="ivalidatorformateventinfo-method"></a>Metodo IValidator::FormatEventInfo
Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
