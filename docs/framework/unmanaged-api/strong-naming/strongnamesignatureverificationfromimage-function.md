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
ms.openlocfilehash: c22339b7d48e89f99d1500cfdda53f00f1234b80
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799075"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="a3cbd-102">Funzione StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="a3cbd-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="a3cbd-103">Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="a3cbd-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-104">This function has been deprecated.</span></span> <span data-ttu-id="a3cbd-105">Usare invece il metodo [ICLRStrongName:: StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a3cbd-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3cbd-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3cbd-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3cbd-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3cbd-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="a3cbd-108">in Indirizzo virtuale relativo del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="a3cbd-109">in Dimensione, in byte, dell'immagine mappata.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="a3cbd-110">in Flag che influenzano il comportamento di verifica.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="a3cbd-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3cbd-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="a3cbd-112">`SN_INFLAG_FORCE_VER`(0x00000001): impone la verifica anche se è necessario eseguire l'override delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="a3cbd-113">`SN_INFLAG_INSTALL`(0x00000002): specifica che si tratta della prima verifica eseguita su questa immagine.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="a3cbd-114">`SN_INFLAG_ADMIN_ACCESS`(0x00000004): specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="a3cbd-115">`SN_INFLAG_USER_ACCESS`(0x00000008): specifica che l'assembly sarà accessibile solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="a3cbd-116">`SN_INFLAG_ALL_ACCESS`(0x00000010): specifica che la cache non fornirà alcuna garanzia di restrizione di accesso.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="a3cbd-117">`SN_INFLAG_RUNTIME`(0x80000000)-riservato per il debug interno.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="a3cbd-118">out Flag per informazioni aggiuntive sull'output.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="a3cbd-119">È supportato il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="a3cbd-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="a3cbd-120">`SN_OUTFLAG_WAS_VERIFIED`(0x00000001): questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3cbd-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a3cbd-121">Return Value</span></span>  
 <span data-ttu-id="a3cbd-122">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3cbd-123">Note</span><span class="sxs-lookup"><span data-stu-id="a3cbd-123">Remarks</span></span>  
 <span data-ttu-id="a3cbd-124">Se la `StrongNameSignatureVerificationFromImage` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="a3cbd-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3cbd-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3cbd-125">Requirements</span></span>  
 <span data-ttu-id="a3cbd-126">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3cbd-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3cbd-127">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="a3cbd-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a3cbd-128">**Libreria** Incluso come risorsa in mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a3cbd-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="a3cbd-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3cbd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cbd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3cbd-130">See also</span></span>

- [<span data-ttu-id="a3cbd-131">Metodo StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="a3cbd-131">StrongNameSignatureVerificationFromImage Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="a3cbd-132">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a3cbd-132">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
