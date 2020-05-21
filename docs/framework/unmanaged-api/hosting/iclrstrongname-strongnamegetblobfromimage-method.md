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
ms.openlocfilehash: 82e18db2f5b911f0e7895959119edd7d2c722f3b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763131"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="c3236-102">Metodo ICLRStrongName::StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="c3236-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="c3236-103">Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="c3236-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3236-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3236-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3236-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3236-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="c3236-106">in Indirizzo di memoria del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="c3236-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c3236-107">in Dimensione, in byte, dell'immagine in corrispondenza di `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="c3236-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="c3236-108">in Buffer che contiene la rappresentazione binaria dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c3236-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="c3236-109">[in, out] Dimensione massima richiesta, in byte, di `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="c3236-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="c3236-110">Al ritorno, le dimensioni effettive, in byte, di `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="c3236-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3236-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c3236-111">Return Value</span></span>  
 <span data-ttu-id="c3236-112">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="c3236-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3236-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3236-113">Requirements</span></span>  
 <span data-ttu-id="c3236-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3236-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3236-115">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="c3236-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c3236-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c3236-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3236-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3236-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3236-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3236-118">See also</span></span>

- [<span data-ttu-id="c3236-119">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="c3236-119">StrongNameGetBlob Method</span></span>](iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="c3236-120">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c3236-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
