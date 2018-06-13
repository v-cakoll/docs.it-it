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
ms.openlocfilehash: 9d562aef58c1e3b5bbbe690b54eb08384052c657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456775"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="3c3d6-102">Funzione StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="3c3d6-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="3c3d6-103">Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="3c3d6-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-104">This function has been deprecated.</span></span> <span data-ttu-id="3c3d6-105">Utilizzare il [:: StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3d6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c3d6-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c3d6-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c3d6-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="3c3d6-108">[in] L'indirizzo di memoria del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="3c3d6-109">[in] Le dimensioni, in byte, dell'immagine in `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="3c3d6-110">[in] Un buffer che deve contenere la rappresentazione binaria dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="3c3d6-111">[in, out] La richiesta di dimensione massima, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="3c3d6-112">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c3d6-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c3d6-113">Return Value</span></span>  
 <span data-ttu-id="3c3d6-114">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c3d6-115">Note</span><span class="sxs-lookup"><span data-stu-id="3c3d6-115">Remarks</span></span>  
 <span data-ttu-id="3c3d6-116">Se il `StrongNameGetBlobFromImage` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="3c3d6-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3d6-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c3d6-117">Requirements</span></span>  
 <span data-ttu-id="3c3d6-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c3d6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3d6-119">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="3c3d6-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3c3d6-120">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3c3d6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c3d6-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3d6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3d6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c3d6-122">See Also</span></span>  
 [<span data-ttu-id="3c3d6-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="3c3d6-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="3c3d6-124">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="3c3d6-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="3c3d6-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3c3d6-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
