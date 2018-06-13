---
title: Metodo IHostMemoryManager::ReleasedVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f6a3d425d4c2ae2146723a6acfc5ab9893f0fe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438441"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="eb1be-102">Metodo IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="eb1be-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="eb1be-103">Notifica all'host che common language runtime (CLR) ha terminato di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="eb1be-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb1be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb1be-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb1be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb1be-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="eb1be-106">[in] Puntatore all'indirizzo iniziale della memoria da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="eb1be-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb1be-107">Note</span><span class="sxs-lookup"><span data-stu-id="eb1be-107">Remarks</span></span>  
 <span data-ttu-id="eb1be-108">Il `ReleasedVirtualAddressSpace` metodo è un metodo di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="eb1be-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="eb1be-109">Viene chiamato da CLR.</span><span class="sxs-lookup"><span data-stu-id="eb1be-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb1be-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb1be-110">Requirements</span></span>  
 <span data-ttu-id="eb1be-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb1be-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb1be-112">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="eb1be-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb1be-113">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="eb1be-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb1be-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb1be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1be-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb1be-115">See Also</span></span>  
 [<span data-ttu-id="eb1be-116">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="eb1be-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
