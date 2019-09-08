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
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="0d358-102">Funzione CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="0d358-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="0d358-103">Verifica la validità di una licenza Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="0d358-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d358-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d358-104">Syntax</span></span>  
  
```cpp  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d358-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d358-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="0d358-106">[in] Licenza Authenticode XrML da verificare.</span><span class="sxs-lookup"><span data-stu-id="0d358-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="0d358-107">Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="0d358-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0d358-108">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0d358-108">[in] Optional.</span></span> <span data-ttu-id="0d358-109">Una combinazione dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d358-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="0d358-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="0d358-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="0d358-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="0d358-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="0d358-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="0d358-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="0d358-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="0d358-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="0d358-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="0d358-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="0d358-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="0d358-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="0d358-116">[out] Per ricevere le informazioni del firmatario.</span><span class="sxs-lookup"><span data-stu-id="0d358-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="0d358-117">Se la licenza non è stata firmata, `dwError` viene impostato su TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="0d358-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="0d358-118">È responsabilità del chiamante liberare risorse mediante la funzione [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) dopo l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0d358-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="0d358-119">Vedere [struttura AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="0d358-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="0d358-120">[out] Per ricevere le informazioni su chi ha apposto il timestamp, se disponibili.</span><span class="sxs-lookup"><span data-stu-id="0d358-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="0d358-121">Se alla licenza non è stato apposto alcun timestamp, `dwError` viene impostato su TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="0d358-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="0d358-122">È responsabilità del chiamante liberare risorse mediante la funzione [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) dopo l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0d358-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="0d358-123">Vedere [struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="0d358-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d358-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0d358-124">Return Value</span></span>  
 <span data-ttu-id="0d358-125">Se l'esito è positivo, restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="0d358-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="0d358-126">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0d358-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d358-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d358-127">See also</span></span>

- [<span data-ttu-id="0d358-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="0d358-128">Authenticode</span></span>](index.md)
- [<span data-ttu-id="0d358-129">Metodo GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="0d358-129">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="0d358-130">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0d358-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
