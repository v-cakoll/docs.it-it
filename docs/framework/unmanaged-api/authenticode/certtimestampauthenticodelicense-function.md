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
ms.openlocfilehash: fd77a8a81718837d55f3018564d0f4ba8fdc95ee
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46323972"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="cc6b3-102">Funzione CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="cc6b3-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="cc6b3-103">Aggiunge un timestamp a una licenza Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc6b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc6b3-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc6b3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc6b3-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="cc6b3-106">[in] Licenza Authenticode XrML firmata a cui aggiungere un timestamp.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="cc6b3-107">Vedere le [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) struttura.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="cc6b3-108">[in] URI del server di timestamp.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="cc6b3-109">[out] Puntatore a CRYPT_DATA_BLOB per ricevere la firma del timestamp con codifica base64.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="cc6b3-110">È responsabilità del chiamante liberare `pTimestampSignatureBlob` -> `pbData` con `HepFree()` dopo l'uso.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="cc6b3-111">Vedere le [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) struttura.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-111">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc6b3-112">Note</span><span class="sxs-lookup"><span data-stu-id="cc6b3-112">Remarks</span></span>  
 <span data-ttu-id="cc6b3-113">La firma del timestamp è in realtà un messaggio SignedData PKCS #7 il cui contenuto è il formato binario di SignatureValue dalla firma della licenza.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="cc6b3-114">Agisce fondamentalmente come controfirma della licenza.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc6b3-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cc6b3-115">Return Value</span></span>  
 <span data-ttu-id="cc6b3-116">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="cc6b3-117">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cc6b3-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6b3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc6b3-118">See Also</span></span>  
 [<span data-ttu-id="cc6b3-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="cc6b3-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
