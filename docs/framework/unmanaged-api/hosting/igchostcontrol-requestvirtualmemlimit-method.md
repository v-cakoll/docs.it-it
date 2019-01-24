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
ms.openlocfilehash: db1572c035242a4a143ee435957409e5d16fca1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607173"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="a63ee-102">Metodo IGCHostControl::RequestVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="a63ee-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="a63ee-103">Le richieste all'host di modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="a63ee-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a63ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a63ee-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a63ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a63ee-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="a63ee-106">[in] Dimensioni richieste di memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="a63ee-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="a63ee-107">[in, out] Puntatore alla dimensione effettiva della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="a63ee-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a63ee-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a63ee-108">Requirements</span></span>  
 <span data-ttu-id="a63ee-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a63ee-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a63ee-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a63ee-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a63ee-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a63ee-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a63ee-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a63ee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a63ee-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a63ee-113">See also</span></span>
- [<span data-ttu-id="a63ee-114">Interfaccia IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="a63ee-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
