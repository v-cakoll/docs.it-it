---
title: Metodo IGCHostControl::RequestVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d163de5f2407d5b541573afe070db812d5980229
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474358"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="9e01d-102">Metodo IGCHostControl::RequestVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="9e01d-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="9e01d-103">Le richieste all'host di modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="9e01d-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e01d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e01d-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e01d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e01d-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="9e01d-106">[in] Dimensioni richieste di memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="9e01d-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="9e01d-107">[in, out] Puntatore alla dimensione effettiva della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="9e01d-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e01d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e01d-108">Requirements</span></span>  
 <span data-ttu-id="9e01d-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e01d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e01d-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e01d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e01d-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9e01d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e01d-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e01d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e01d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e01d-113">See also</span></span>
- [<span data-ttu-id="9e01d-114">Interfaccia IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="9e01d-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
