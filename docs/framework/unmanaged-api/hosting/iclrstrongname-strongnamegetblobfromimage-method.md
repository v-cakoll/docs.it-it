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
ms.openlocfilehash: ad3b151165eb233bd3a4a78d8f4d612a696b7e93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135101"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="f3826-102">Metodo ICLRStrongName::StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="f3826-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="f3826-103">Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="f3826-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3826-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3826-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3826-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3826-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="f3826-106">in Indirizzo di memoria del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="f3826-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f3826-107">in Dimensione, in byte, dell'immagine in `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="f3826-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="f3826-108">in Buffer che contiene la rappresentazione binaria dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="f3826-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="f3826-109">[in, out] Dimensione massima richiesta, in byte, del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="f3826-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="f3826-110">Al ritorno, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="f3826-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3826-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3826-111">Return Value</span></span>  
 <span data-ttu-id="f3826-112">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="f3826-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3826-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3826-113">Requirements</span></span>  
 <span data-ttu-id="f3826-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3826-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3826-115">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f3826-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f3826-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3826-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3826-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3826-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3826-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3826-118">See also</span></span>

- [<span data-ttu-id="f3826-119">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="f3826-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="f3826-120">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f3826-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
