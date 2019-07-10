---
title: Metodo IHostMemoryManager::AcquiredVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 423fbfc2bda9d3544a5c32b6cd650643209f0e86
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767237"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="37277-102">Metodo IHostMemoryManager::AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="37277-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="37277-103">Notifica all'host che common language runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="37277-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37277-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37277-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37277-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="37277-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="37277-106">[in] Indirizzo iniziale della memoria.</span><span class="sxs-lookup"><span data-stu-id="37277-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="37277-107">[in] Le dimensioni, in byte, della memoria.</span><span class="sxs-lookup"><span data-stu-id="37277-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37277-108">Note</span><span class="sxs-lookup"><span data-stu-id="37277-108">Remarks</span></span>  
 <span data-ttu-id="37277-109">Il `AcquiredVirtualAddressSpace` metodo è un metodo di callback e devono essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="37277-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="37277-110">Viene chiamato da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="37277-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37277-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37277-111">Requirements</span></span>  
 <span data-ttu-id="37277-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37277-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37277-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="37277-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37277-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="37277-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37277-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37277-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37277-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37277-116">See also</span></span>

- [<span data-ttu-id="37277-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="37277-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
