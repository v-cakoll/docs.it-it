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
ms.openlocfilehash: 0acbf4163e98b1171510260c4fac72c3d6f6fb1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189287"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="b2648-102">Metodo IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="b2648-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="b2648-103">Notifica all'host che common language runtime (CLR) ha completato l'utilizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="b2648-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2648-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2648-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2648-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2648-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="b2648-106">[in] Puntatore all'indirizzo iniziale della memoria da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="b2648-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2648-107">Note</span><span class="sxs-lookup"><span data-stu-id="b2648-107">Remarks</span></span>  
 <span data-ttu-id="b2648-108">Il `ReleasedVirtualAddressSpace` metodo è un metodo di callback e devono essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="b2648-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="b2648-109">Viene chiamato da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b2648-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2648-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2648-110">Requirements</span></span>  
 <span data-ttu-id="b2648-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2648-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2648-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2648-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2648-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b2648-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2648-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2648-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2648-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2648-115">See also</span></span>

- [<span data-ttu-id="b2648-116">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="b2648-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
