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
ms.openlocfilehash: 158ecc036d56e2ad9a3fa650677c04ebcbfd7696
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777222"
---
# <a name="getpublickeytoken-method"></a>Metodo GetPublicKeyToken
Recupera il token di chiave pubblica per un file di chiave o un contenitore di chiavi specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszKeyFile`  
 Nome del file della chiave.  
  
 `pszKeyContainer`  
 Nome del contenitore di chiavi.  
  
 `pvPublicKeyToken`  
 Indirizzo in cui deve essere archiviato il token di chiave.  
  
 `pcbPublicKeyToken`  
 Specifica la dimensione, in byte, del buffer indicato da `pvPublicKeyToken`. Al momento della restituzione, contiene il numero effettivo di byte utilizzati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink2](ialink2-interface.md)
- [Interfaccia IALink](ialink-interface.md)
- [Alink (API)](index.md)
