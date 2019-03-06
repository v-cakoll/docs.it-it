---
title: Metodo ICLRStrongName::StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc4f24ae28be49dec7de2c0b9ebf9cc930989bfc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485135"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="2aaf0-102">Metodo ICLRStrongName::StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="2aaf0-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="2aaf0-103">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aaf0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2aaf0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aaf0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2aaf0-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2aaf0-106">[in] Il percorso del file di (con estensione dll o .exe) eseguibile portabile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="2aaf0-107">[in] Flag per modificare il comportamento di verifica.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="2aaf0-108">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2aaf0-108">The following values are supported:</span></span>  
  
-   <span data-ttu-id="2aaf0-109">`SN_INFLAG_FORCE_VER` (0x00000001) - forza la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="2aaf0-110">`SN_INFLAG_INSTALL` (0x00000002): Specifica che questa è la prima volta che viene verificato il manifesto.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="2aaf0-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): Specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="2aaf0-112">`SN_INFLAG_USER_ACCESS` (0x00000008): Specifica che l'assembly è accessibile solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="2aaf0-113">`SN_INFLAG_ALL_ACCESS` (0x00000010): Specifica che la cache non fornirà offre alcuna garanzia di limitazione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="2aaf0-114">`SN_INFLAG_RUNTIME` (0x80000000) - riservato per il debug interno.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="2aaf0-115">[out] Flag che indica se è stata verificata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="2aaf0-116">È supportato il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="2aaf0-116">The following value is supported:</span></span>  
  
-   <span data-ttu-id="2aaf0-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - questo valore è impostato su `false` per specificare che la verifica è riuscita a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2aaf0-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2aaf0-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2aaf0-118">Return Value</span></span>  
 <span data-ttu-id="2aaf0-119">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="2aaf0-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aaf0-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2aaf0-120">Requirements</span></span>  
 <span data-ttu-id="2aaf0-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aaf0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aaf0-122">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2aaf0-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2aaf0-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2aaf0-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2aaf0-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aaf0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aaf0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2aaf0-125">See also</span></span>
- [<span data-ttu-id="2aaf0-126">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="2aaf0-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="2aaf0-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="2aaf0-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
