---
title: Funzione CertVerifyAuthenticodeLicense
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d8ab96c758b946684af78bfa21822fdaf96530a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786967"
---
# <a name="certverifyauthenticodelicense-function"></a>Funzione CertVerifyAuthenticodeLicense
Verifica la validità di una licenza Authenticode XrML.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pLicenseBlob`  
 [in] Licenza Authenticode XrML da verificare.  
  
 Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `dwFlags`  
 [in] Facoltativo. Una combinazione dei valori seguenti:  
  
- AXL_REVOCATION_NO_CHECK  
  
- AXL_REVOCATION_CHECK_END_CERT_ONLY  
  
- AXL_REVOCATION_CHECK_ENTIRE_CHAIN  
  
- AXL_URL_CACHE_ONLY_RETRIEVAL  
  
- AXL_LIFETIME_SIGNING  
  
- AXL_TRUST_MICROSOFT_ROOT_ONLY  
  
 `pSignerInfo`  
 [out] Per ricevere le informazioni del firmatario. Se la licenza non è stata firmata, `dwError` viene impostato su TRUST_E_NOSIGNATURE. È responsabilità del chiamante liberare risorse mediante la funzione [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) dopo l'utilizzo.  
  
 Vedere [struttura AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md).  
  
 `pTimestamperInfo`  
 [out] Per ricevere le informazioni su chi ha apposto il timestamp, se disponibili. Se alla licenza non è stato apposto alcun timestamp, `dwError` viene impostato su TRUST_E_NOSIGNATURE. È responsabilità del chiamante liberare risorse mediante la funzione [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) dopo l'utilizzo.  
  
 Vedere [struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md).  
  
## <a name="return-value"></a>Valore restituito  
 Se l'esito è positivo, restituisce `S_OK`. In caso contrario, verrà restituito un codice di errore.  
  
## <a name="see-also"></a>Vedere anche

- [Authenticode](index.md)
- [Metodo GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
