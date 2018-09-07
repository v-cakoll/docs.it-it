---
title: Metodo ICLRStrongName::StrongNameSignatureVerificationFromImage
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdbf2126d3da152ce68b6dbb47f5772e3b13d2c6
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44068692"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="e1963-102">Metodo ICLRStrongName::StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="e1963-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="e1963-103">Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata.</span><span class="sxs-lookup"><span data-stu-id="e1963-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1963-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1963-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1963-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1963-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="e1963-106">[in] L'indirizzo virtuale relativo del manifesto dell'assembly con mapping.</span><span class="sxs-lookup"><span data-stu-id="e1963-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e1963-107">[in] Le dimensioni, in byte, dell'immagine mappata.</span><span class="sxs-lookup"><span data-stu-id="e1963-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="e1963-108">[in] Flag che influenzano il comportamento di verifica.</span><span class="sxs-lookup"><span data-stu-id="e1963-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="e1963-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1963-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e1963-110">`SN_INFLAG_FORCE_VER` (0x00000001) - forza la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="e1963-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="e1963-111">`SN_INFLAG_INSTALL` (0x00000002): Specifica che questa è la prima verifica eseguita su questa immagine.</span><span class="sxs-lookup"><span data-stu-id="e1963-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="e1963-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): Specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="e1963-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="e1963-113">`SN_INFLAG_USER_ACCESS` (0x00000008): Specifica che l'assembly è accessibile solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="e1963-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="e1963-114">`SN_INFLAG_ALL_ACCESS` (0x00000010): Specifica che la cache non fornirà offre alcuna garanzia di limitazione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="e1963-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="e1963-115">`SN_INFLAG_RUNTIME` (0x80000000) - riservato per il debug interno.</span><span class="sxs-lookup"><span data-stu-id="e1963-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="e1963-116">[out] Flag per informazioni aggiuntive sull'output.</span><span class="sxs-lookup"><span data-stu-id="e1963-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="e1963-117">È supportato il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="e1963-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="e1963-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - questo valore è impostato su `false` per specificare che la verifica è riuscita a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="e1963-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1963-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1963-119">Return Value</span></span>  
 <span data-ttu-id="e1963-120">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="e1963-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1963-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1963-121">Requirements</span></span>  
 <span data-ttu-id="e1963-122">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1963-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1963-123">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="e1963-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1963-124">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e1963-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1963-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1963-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1963-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1963-126">See Also</span></span>  
 [<span data-ttu-id="e1963-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e1963-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
