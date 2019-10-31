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
ms.openlocfilehash: 3c5e803c874e1254510f75189846d7cb12cb1ee2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132470"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="a1d6f-102">Funzione CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="a1d6f-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="a1d6f-103">Aggiunge un timestamp a una licenza Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1d6f-104">Syntax</span></span>  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1d6f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1d6f-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="a1d6f-106">[in] Licenza Authenticode XrML firmata a cui aggiungere un timestamp.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="a1d6f-107">Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="a1d6f-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="a1d6f-108">[in] URI del server di timestamp.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="a1d6f-109">[out] Puntatore a CRYPT_DATA_BLOB per ricevere la firma del timestamp con codifica base64.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="a1d6f-110">È responsabilità del chiamante liberare `pTimestampSignatureBlob`->`pbData` con `HepFree()` dopo l'uso.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="a1d6f-111">Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="a1d6f-111">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1d6f-112">Note</span><span class="sxs-lookup"><span data-stu-id="a1d6f-112">Remarks</span></span>  
 <span data-ttu-id="a1d6f-113">La firma del timestamp è in realtà un messaggio SignedData PKCS #7 il cui contenuto è il formato binario di SignatureValue dalla firma della licenza.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="a1d6f-114">Agisce fondamentalmente come controfirma della licenza.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1d6f-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1d6f-115">Return Value</span></span>  
 <span data-ttu-id="a1d6f-116">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="a1d6f-117">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d6f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1d6f-118">See also</span></span>

- [<span data-ttu-id="a1d6f-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="a1d6f-119">Authenticode</span></span>](index.md)
