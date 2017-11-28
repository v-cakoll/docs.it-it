---
title: Funzione StrongNameSignatureVerificationFromImage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationFromImage
helpviewer_keywords: StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab890451c44b19be6472ae6c7da060ae71612bc5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="880fb-102">Funzione StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="880fb-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="880fb-103">Verifica che un assembly che è già stato mappato alla memoria sia valido per la chiave pubblica associata.</span><span class="sxs-lookup"><span data-stu-id="880fb-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="880fb-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="880fb-104">This function has been deprecated.</span></span> <span data-ttu-id="880fb-105">Utilizzare il [:: StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="880fb-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="880fb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="880fb-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="880fb-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="880fb-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="880fb-108">[in] L'indirizzo virtuale relativo del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="880fb-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="880fb-109">[in] Le dimensioni in byte, dell'immagine mappata.</span><span class="sxs-lookup"><span data-stu-id="880fb-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="880fb-110">[in] Flag che influenzano il comportamento di verifica.</span><span class="sxs-lookup"><span data-stu-id="880fb-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="880fb-111">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="880fb-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="880fb-112">`SN_INFLAG_FORCE_VER`(0x00000001) - impone la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="880fb-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="880fb-113">`SN_INFLAG_INSTALL`(0x00000002) - specifica che questa è la prima verifica eseguita in questa immagine.</span><span class="sxs-lookup"><span data-stu-id="880fb-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="880fb-114">`SN_INFLAG_ADMIN_ACCESS`(0x00000004) - specifica che la cache verrà concesso l'accesso solo agli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="880fb-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="880fb-115">`SN_INFLAG_USER_ACCESS`(0x00000008) - specifica che l'assembly sarà accessibili solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="880fb-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="880fb-116">`SN_INFLAG_ALL_ACCESS`(0x00000010) - specifica che la cache non fornirà alcuna garanzia di restrizione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="880fb-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="880fb-117">`SN_INFLAG_RUNTIME`(0x80000000) - riservato per il debug interno.</span><span class="sxs-lookup"><span data-stu-id="880fb-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="880fb-118">[out] Flag per informazioni aggiuntive sull'output.</span><span class="sxs-lookup"><span data-stu-id="880fb-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="880fb-119">È supportato il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="880fb-119">The following value is supported:</span></span>  
  
-   <span data-ttu-id="880fb-120">`SN_OUTFLAG_WAS_VERIFIED`(0x00000001) - questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="880fb-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="880fb-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="880fb-121">Return Value</span></span>  
 <span data-ttu-id="880fb-122">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="880fb-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="880fb-123">Note</span><span class="sxs-lookup"><span data-stu-id="880fb-123">Remarks</span></span>  
 <span data-ttu-id="880fb-124">Se il `StrongNameSignatureVerificationFromImage` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="880fb-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="880fb-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="880fb-125">Requirements</span></span>  
 <span data-ttu-id="880fb-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="880fb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="880fb-127">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="880fb-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="880fb-128">**Libreria:** inclusa come risorsa in mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="880fb-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="880fb-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="880fb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="880fb-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="880fb-130">See Also</span></span>  
 [<span data-ttu-id="880fb-131">StrongNameSignatureVerificationFromImage (metodo)</span><span class="sxs-lookup"><span data-stu-id="880fb-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [<span data-ttu-id="880fb-132">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="880fb-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
