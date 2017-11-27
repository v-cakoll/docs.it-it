---
title: Metodo IGCHostControl::RequestVirtualMemLimit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHostControl.RequestVirtualMemLimit
api_location: mscoree.dll
api_type: COM
f1_keywords: RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4892cf5dc3a3663f1bccc95d1975bfe96277faa5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="8557e-102">Metodo IGCHostControl::RequestVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="8557e-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="8557e-103">Richiede all'host di modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="8557e-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8557e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8557e-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8557e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8557e-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="8557e-106">[in] La dimensione richiesta di memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="8557e-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="8557e-107">[in, out] Un puntatore alla dimensione effettiva di memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="8557e-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8557e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8557e-108">Requirements</span></span>  
 <span data-ttu-id="8557e-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8557e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8557e-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8557e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8557e-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8557e-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8557e-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8557e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8557e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8557e-113">See Also</span></span>  
 [<span data-ttu-id="8557e-114">IGCHostControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8557e-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
