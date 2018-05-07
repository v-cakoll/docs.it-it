---
title: Funzione _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b197aa539e60a9dbcee55cf190c44b45da3a5fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="axlgetissuerpublickeyhash-function"></a>Funzione _AxlGetIssuerPublicKeyHash
Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pChainContext`  
 [in] BLOB a chiave pubblica CSP. Vedere il [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) struttura.  
  
 `ppwszPublicKeyHash`  
 [out] Puntatore a WCHAR * per ricevere il token di chiave pubblica con codifica esadecimale.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.  
  
## <a name="see-also"></a>Vedere anche  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
