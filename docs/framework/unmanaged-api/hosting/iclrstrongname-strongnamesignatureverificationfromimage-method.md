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
ms.openlocfilehash: 1bfc41fdad35a7e0560d251179ea035c96aecab7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899525"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="8a50e-102">Metodo ICLRStrongName::StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="8a50e-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="8a50e-103">Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata.</span><span class="sxs-lookup"><span data-stu-id="8a50e-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a50e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a50e-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a50e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a50e-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="8a50e-106">in Indirizzo virtuale relativo del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="8a50e-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8a50e-107">in Dimensione, in byte, dell'immagine mappata.</span><span class="sxs-lookup"><span data-stu-id="8a50e-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="8a50e-108">in Flag che influenzano il comportamento di verifica.</span><span class="sxs-lookup"><span data-stu-id="8a50e-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="8a50e-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a50e-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="8a50e-110">`SN_INFLAG_FORCE_VER` (0x00000001): impone la verifica anche se è necessario eseguire l'override delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8a50e-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="8a50e-111">`SN_INFLAG_INSTALL` (0x00000002): specifica che si tratta della prima verifica eseguita su questa immagine.</span><span class="sxs-lookup"><span data-stu-id="8a50e-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="8a50e-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="8a50e-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="8a50e-113">`SN_INFLAG_USER_ACCESS` (0x00000008): specifica che l'assembly sarà accessibile solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="8a50e-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="8a50e-114">`SN_INFLAG_ALL_ACCESS` (0x00000010): specifica che la cache non fornirà alcuna garanzia di restrizione di accesso.</span><span class="sxs-lookup"><span data-stu-id="8a50e-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="8a50e-115">`SN_INFLAG_RUNTIME` (0x80000000)-riservato per il debug interno.</span><span class="sxs-lookup"><span data-stu-id="8a50e-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="8a50e-116">out Flag per informazioni aggiuntive sull'output.</span><span class="sxs-lookup"><span data-stu-id="8a50e-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="8a50e-117">È supportato il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="8a50e-117">The following value is supported:</span></span>  
  
- <span data-ttu-id="8a50e-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8a50e-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a50e-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a50e-119">Return Value</span></span>  
 <span data-ttu-id="8a50e-120">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="8a50e-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a50e-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8a50e-121">Requirements</span></span>  
 <span data-ttu-id="8a50e-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a50e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a50e-123">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="8a50e-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8a50e-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8a50e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a50e-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a50e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a50e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a50e-126">See also</span></span>

- [<span data-ttu-id="8a50e-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8a50e-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
