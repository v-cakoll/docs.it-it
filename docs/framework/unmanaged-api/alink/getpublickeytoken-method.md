---
title: Metodo GetPublicKeyToken
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215768"
---
# <a name="getpublickeytoken-method"></a>Metodo GetPublicKeyToken
Recupera il token di chiave pubblica per un file di chiave specificata o un contenitore di chiavi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszKeyFile`  
 Nome file della chiave.  
  
 `pszKeyContainer`  
 Nome del contenitore di chiavi.  
  
 `pvPublicKeyToken`  
 Indirizzo in cui viene archiviato il token di chiave.  
  
 `pcbPublicKeyToken`  
 Specifica la dimensione, in byte, del buffer indicato da `pvPublicKeyToken`. Dopo la restituzione, contiene il numero effettivo di byte utilizzati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [API Alink](../../../../docs/framework/unmanaged-api/alink/index.md)
