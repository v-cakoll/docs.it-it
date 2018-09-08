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
ms.openlocfilehash: 1c10d5f363d454a64f9052315514e896f90f7081
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208848"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="9069c-102">Funzione CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="9069c-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="9069c-103">Verifica la validità di una licenza Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="9069c-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9069c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9069c-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9069c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9069c-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="9069c-106">[in] Licenza Authenticode XrML da verificare.</span><span class="sxs-lookup"><span data-stu-id="9069c-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="9069c-107">Vedere le [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) struttura.</span><span class="sxs-lookup"><span data-stu-id="9069c-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9069c-108">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9069c-108">[in] Optional.</span></span> <span data-ttu-id="9069c-109">Una combinazione dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9069c-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="9069c-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="9069c-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="9069c-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="9069c-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="9069c-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="9069c-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="9069c-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="9069c-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="9069c-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="9069c-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="9069c-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="9069c-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="9069c-116">[out] Per ricevere le informazioni del firmatario.</span><span class="sxs-lookup"><span data-stu-id="9069c-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="9069c-117">Se la licenza non è stata firmata, `dwError` viene impostato su TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="9069c-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="9069c-118">È responsabilità del chiamante liberare risorse mediante il [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) funzione dopo l'uso.</span><span class="sxs-lookup"><span data-stu-id="9069c-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="9069c-119">Visualizzare [struttura AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="9069c-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="9069c-120">[out] Per ricevere le informazioni su chi ha apposto il timestamp, se disponibili.</span><span class="sxs-lookup"><span data-stu-id="9069c-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="9069c-121">Se alla licenza non è stato apposto alcun timestamp, `dwError` viene impostato su TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="9069c-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="9069c-122">È responsabilità del chiamante liberare risorse mediante il [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) funzione dopo l'uso.</span><span class="sxs-lookup"><span data-stu-id="9069c-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="9069c-123">Visualizzare [struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="9069c-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9069c-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9069c-124">Return Value</span></span>  
 <span data-ttu-id="9069c-125">Se l'esito è positivo, restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="9069c-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="9069c-126">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9069c-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9069c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9069c-127">See Also</span></span>  
 [<span data-ttu-id="9069c-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="9069c-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [<span data-ttu-id="9069c-129">Metodo GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="9069c-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="9069c-130">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9069c-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
