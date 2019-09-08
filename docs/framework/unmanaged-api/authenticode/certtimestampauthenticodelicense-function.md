---
title: Funzione CertTimestampAuthenticodeLicense
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aaf76d4c3d0f5fb59aeb35fae7a7020ee97b74d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776486"
---
# <a name="certtimestampauthenticodelicense-function"></a>Funzione CertTimestampAuthenticodeLicense
Aggiunge un timestamp a una licenza Authenticode XrML.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pSignedLicenseBlob`  
 [in] Licenza Authenticode XrML firmata a cui aggiungere un timestamp. Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `pwszTimestampURI`  
 [in] URI del server di timestamp.  
  
 `pTimestampSignatureBlob`  
 [out] Puntatore a CRYPT_DATA_BLOB per ricevere la firma del timestamp con codifica base64. È responsabilità del chiamante liberarsi `pTimestampSignatureBlob` -> `pbData` `HepFree()` da dopo l'uso. Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
## <a name="remarks"></a>Note  
 La firma del timestamp è in realtà un messaggio SignedData PKCS #7 il cui contenuto è il formato binario di SignatureValue dalla firma della licenza. Agisce fondamentalmente come controfirma della licenza.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la funzione ha esito positivo. In caso contrario, verrà restituito un codice di errore.  
  
## <a name="see-also"></a>Vedere anche

- [Authenticode](index.md)
