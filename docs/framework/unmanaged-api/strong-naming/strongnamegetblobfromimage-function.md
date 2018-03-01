---
title: Funzione StrongNameGetBlobFromImage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3dd5fa1838517baa97079f5d7f75a789384255a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="58dba-102">Funzione StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="58dba-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="58dba-103">Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="58dba-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="58dba-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="58dba-104">This function has been deprecated.</span></span> <span data-ttu-id="58dba-105">Utilizzare il [:: StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="58dba-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58dba-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58dba-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58dba-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="58dba-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="58dba-108">[in] L'indirizzo di memoria del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="58dba-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="58dba-109">[in] Le dimensioni, in byte, dell'immagine in `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="58dba-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="58dba-110">[in] Un buffer che deve contenere la rappresentazione binaria dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="58dba-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="58dba-111">[in, out] La richiesta di dimensione massima, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="58dba-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="58dba-112">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="58dba-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58dba-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="58dba-113">Return Value</span></span>  
 <span data-ttu-id="58dba-114">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="58dba-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58dba-115">Note</span><span class="sxs-lookup"><span data-stu-id="58dba-115">Remarks</span></span>  
 <span data-ttu-id="58dba-116">Se il `StrongNameGetBlobFromImage` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="58dba-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58dba-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58dba-117">Requirements</span></span>  
 <span data-ttu-id="58dba-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58dba-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58dba-119">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="58dba-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="58dba-120">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58dba-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58dba-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58dba-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58dba-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58dba-122">See Also</span></span>  
 [<span data-ttu-id="58dba-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="58dba-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="58dba-124">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="58dba-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="58dba-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="58dba-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
