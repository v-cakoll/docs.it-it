---
title: _AxlRSAKeyValueToPublicKeyToken (funzione)
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690035ffe0724d3987a198c78bf14e668527b98a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787029"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a>\_AxlRSAKeyValueToPublicKeyToken (funzione)

Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pModulusBlob`  
 in Il BLOB del modulo con codifica Base64 (dall' \<elemento modulo >).  Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `pExponentBlob`  
 in BLOB dell'esponente con codifica Base64 (dall'elemento \<> dell'esponente). Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `ppwszPublicKeyToken`  
 [out] Puntatore a WCHAR * per ricevere il token di chiave pubblica con codifica esadecimale.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la funzione ha esito positivo. In caso contrario, verrà restituito un codice di errore.  
  
## <a name="see-also"></a>Vedere anche

- [Authenticode](index.md)
