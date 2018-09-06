---
title: Metodo ICLRStrongName::StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd6cb0116e1080a68c91df365cc7dd1485b21791
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881255"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="89c4a-102">Metodo ICLRStrongName::StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="89c4a-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="89c4a-103">Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="89c4a-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c4a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89c4a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89c4a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89c4a-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="89c4a-106">[in] L'indirizzo di memoria del manifesto dell'assembly mappata.</span><span class="sxs-lookup"><span data-stu-id="89c4a-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="89c4a-107">[in] Le dimensioni, in byte, dell'immagine in `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="89c4a-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="89c4a-108">[in] Un buffer che deve contenere la rappresentazione binaria dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="89c4a-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="89c4a-109">[in, out] La massima dimensione, espressa in byte, richiesta del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="89c4a-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="89c4a-110">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="89c4a-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89c4a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="89c4a-111">Return Value</span></span>  
 <span data-ttu-id="89c4a-112">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="89c4a-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89c4a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89c4a-113">Requirements</span></span>  
 <span data-ttu-id="89c4a-114">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89c4a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c4a-115">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="89c4a-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="89c4a-116">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="89c4a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89c4a-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c4a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c4a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89c4a-118">See Also</span></span>  
 [<span data-ttu-id="89c4a-119">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="89c4a-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="89c4a-120">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="89c4a-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
