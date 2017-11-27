---
title: Metodo IHostMemoryManager::ReleasedVirtualAddressSpace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.ReleasedVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0f2588c34429366794fcfb30c6d6e7038814506
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="efb7c-102">Metodo IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="efb7c-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="efb7c-103">Notifica all'host che common language runtime (CLR) ha terminato di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="efb7c-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efb7c-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efb7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="efb7c-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="efb7c-106">[in] Puntatore all'indirizzo iniziale della memoria da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="efb7c-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb7c-107">Note</span><span class="sxs-lookup"><span data-stu-id="efb7c-107">Remarks</span></span>  
 <span data-ttu-id="efb7c-108">Il `ReleasedVirtualAddressSpace` metodo è un metodo di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="efb7c-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="efb7c-109">Viene chiamato da CLR.</span><span class="sxs-lookup"><span data-stu-id="efb7c-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb7c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efb7c-110">Requirements</span></span>  
 <span data-ttu-id="efb7c-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efb7c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb7c-112">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="efb7c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efb7c-113">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efb7c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efb7c-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb7c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb7c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efb7c-115">See Also</span></span>  
 [<span data-ttu-id="efb7c-116">IHostMemoryManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="efb7c-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
