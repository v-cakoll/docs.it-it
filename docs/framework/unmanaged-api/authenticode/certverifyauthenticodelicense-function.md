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
ms.openlocfilehash: abbf893b3d49101b5cc9d38ffc31b171ff023f8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965035"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="44628-102">Funzione CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="44628-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="44628-103">Verifica la validità di una licenza Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="44628-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44628-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44628-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44628-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44628-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="44628-106">[in] Licenza Authenticode XrML da verificare.</span><span class="sxs-lookup"><span data-stu-id="44628-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="44628-107">Vedere le [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) struttura.</span><span class="sxs-lookup"><span data-stu-id="44628-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="44628-108">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="44628-108">[in] Optional.</span></span> <span data-ttu-id="44628-109">Una combinazione dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="44628-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="44628-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="44628-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="44628-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="44628-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="44628-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="44628-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="44628-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="44628-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="44628-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="44628-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="44628-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="44628-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="44628-116">[out] Per ricevere le informazioni del firmatario.</span><span class="sxs-lookup"><span data-stu-id="44628-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="44628-117">Se la licenza non è stata firmata, `dwError` viene impostato su TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="44628-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="44628-118">È responsabilità del chiamante liberare risorse mediante il [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) funzione dopo l'uso.</span><span class="sxs-lookup"><span data-stu-id="44628-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="44628-119">Visualizzare [struttura AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="44628-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="44628-120">[out] Per ricevere le informazioni su chi ha apposto il timestamp, se disponibili.</span><span class="sxs-lookup"><span data-stu-id="44628-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="44628-121">Se alla licenza non è stato apposto alcun timestamp, `dwError` viene impostato su TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="44628-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="44628-122">È responsabilità del chiamante liberare risorse mediante il [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) funzione dopo l'uso.</span><span class="sxs-lookup"><span data-stu-id="44628-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="44628-123">Visualizzare [struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="44628-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44628-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="44628-124">Return Value</span></span>  
 <span data-ttu-id="44628-125">Se l'esito è positivo, restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="44628-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="44628-126">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="44628-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44628-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44628-127">See also</span></span>

- [<span data-ttu-id="44628-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="44628-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
- [<span data-ttu-id="44628-129">Metodo GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="44628-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="44628-130">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="44628-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
