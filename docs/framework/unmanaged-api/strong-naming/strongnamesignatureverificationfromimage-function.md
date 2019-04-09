---
title: Funzione StrongNameSignatureVerificationFromImage
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54b1d35d1c40289bad465978750ba738acf28c90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212440"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="0126e-102">Funzione StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="0126e-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="0126e-103">Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata.</span><span class="sxs-lookup"><span data-stu-id="0126e-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="0126e-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="0126e-104">This function has been deprecated.</span></span> <span data-ttu-id="0126e-105">Usare la [:: StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="0126e-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0126e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0126e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0126e-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="0126e-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="0126e-108">[in] L'indirizzo virtuale relativo del manifesto dell'assembly con mapping.</span><span class="sxs-lookup"><span data-stu-id="0126e-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="0126e-109">[in] Le dimensioni, in byte, dell'immagine mappata.</span><span class="sxs-lookup"><span data-stu-id="0126e-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="0126e-110">[in] Flag che influenzano il comportamento di verifica.</span><span class="sxs-lookup"><span data-stu-id="0126e-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="0126e-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0126e-111">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="0126e-112">(0x00000001) - forza la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0126e-112">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="0126e-113">(0x00000002): Specifica che questa è la prima verifica eseguita su questa immagine.</span><span class="sxs-lookup"><span data-stu-id="0126e-113">(0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="0126e-114">(0x00000004): Specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="0126e-114">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="0126e-115">(0x00000008): Specifica che l'assembly è accessibile solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="0126e-115">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="0126e-116">(0x00000010): Specifica che la cache non fornirà offre alcuna garanzia di limitazione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="0126e-116">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="0126e-117">(0x80000000) - riservato per il debug interno.</span><span class="sxs-lookup"><span data-stu-id="0126e-117">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="0126e-118">[out] Flag per informazioni aggiuntive sull'output.</span><span class="sxs-lookup"><span data-stu-id="0126e-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="0126e-119">È supportato il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="0126e-119">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="0126e-120">(0x00000001) - questo valore è impostato su `false` per specificare che la verifica è riuscita a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0126e-120">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0126e-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0126e-121">Return Value</span></span>  
 `true` <span data-ttu-id="0126e-122">al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0126e-122">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0126e-123">Note</span><span class="sxs-lookup"><span data-stu-id="0126e-123">Remarks</span></span>  
 <span data-ttu-id="0126e-124">Se il `StrongNameSignatureVerificationFromImage` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="0126e-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0126e-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0126e-125">Requirements</span></span>  
 <span data-ttu-id="0126e-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0126e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0126e-127">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0126e-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0126e-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0126e-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 **<span data-ttu-id="0126e-129">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0126e-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0126e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0126e-130">See also</span></span>

- [<span data-ttu-id="0126e-131">Metodo StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="0126e-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="0126e-132">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0126e-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
