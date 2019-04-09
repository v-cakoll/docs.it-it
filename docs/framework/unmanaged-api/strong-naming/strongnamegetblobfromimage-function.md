---
title: Funzione StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b136e1fa480e53bcacfd9ea832d1dc4d1bd69f74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162779"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="a7b2b-102">Funzione StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="a7b2b-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="a7b2b-103">Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="a7b2b-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-104">This function has been deprecated.</span></span> <span data-ttu-id="a7b2b-105">Usare la [StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b2b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7b2b-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7b2b-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7b2b-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="a7b2b-108">[in] L'indirizzo di memoria del manifesto dell'assembly mappata.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="a7b2b-109">[in] Le dimensioni, in byte, dell'immagine in `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="a7b2b-110">[in] Un buffer che deve contenere la rappresentazione binaria dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="a7b2b-111">[in, out] La massima dimensione, espressa in byte, richiesta del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="a7b2b-112">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7b2b-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a7b2b-113">Return Value</span></span>  
 `true` <span data-ttu-id="a7b2b-114">al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-114">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7b2b-115">Note</span><span class="sxs-lookup"><span data-stu-id="a7b2b-115">Remarks</span></span>  
 <span data-ttu-id="a7b2b-116">Se il `StrongNameGetBlobFromImage` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7b2b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7b2b-117">Requirements</span></span>  
 <span data-ttu-id="a7b2b-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7b2b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b2b-119">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a7b2b-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a7b2b-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a7b2b-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a7b2b-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a7b2b-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7b2b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7b2b-122">See also</span></span>

- [<span data-ttu-id="a7b2b-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="a7b2b-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="a7b2b-124">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="a7b2b-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="a7b2b-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a7b2b-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
