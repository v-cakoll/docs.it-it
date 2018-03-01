---
title: Funzione StrongNameFreeBuffer
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
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f4f5bde035b0ab9df07bb0ab709a67ae1a4cff3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="fde91-102">Funzione StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="fde91-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="fde91-103">Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="fde91-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="fde91-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="fde91-104">This function has been deprecated.</span></span> <span data-ttu-id="fde91-105">Utilizzare il [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="fde91-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde91-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fde91-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fde91-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="fde91-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="fde91-108">[in] Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="fde91-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde91-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fde91-109">Requirements</span></span>  
 <span data-ttu-id="fde91-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fde91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde91-111">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="fde91-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fde91-112">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fde91-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fde91-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde91-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde91-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fde91-114">See Also</span></span>  
 [<span data-ttu-id="fde91-115">Metodo StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="fde91-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
 [<span data-ttu-id="fde91-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="fde91-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
