---
title: Funzione StrongNameFreeBuffer
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cdeb446b18adceb4a8ed306a7934d6c905a90f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778035"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="d9d19-102">Funzione StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d9d19-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="d9d19-103">Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="d9d19-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="d9d19-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d9d19-104">This function has been deprecated.</span></span> <span data-ttu-id="d9d19-105">Usare la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="d9d19-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d19-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9d19-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9d19-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9d19-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="d9d19-108">[in] Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="d9d19-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9d19-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9d19-109">Requirements</span></span>  
 <span data-ttu-id="d9d19-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9d19-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9d19-111">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d9d19-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d9d19-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d9d19-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9d19-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9d19-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d19-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9d19-114">See also</span></span>

- [<span data-ttu-id="d9d19-115">Metodo StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d9d19-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="d9d19-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d9d19-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
