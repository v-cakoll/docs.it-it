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
ms.openlocfilehash: 5096eb1064485c02b599659cc9ae889e7151581c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767693"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="67913-102">Metodo IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="67913-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="67913-103">Notifica all'host che common language runtime (CLR) ha completato l'utilizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="67913-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67913-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67913-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67913-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67913-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="67913-106">[in] Puntatore all'indirizzo iniziale della memoria da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="67913-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67913-107">Note</span><span class="sxs-lookup"><span data-stu-id="67913-107">Remarks</span></span>  
 <span data-ttu-id="67913-108">Il `ReleasedVirtualAddressSpace` metodo è un metodo di callback e devono essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="67913-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="67913-109">Viene chiamato da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="67913-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67913-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67913-110">Requirements</span></span>  
 <span data-ttu-id="67913-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67913-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67913-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67913-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67913-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="67913-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67913-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67913-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67913-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67913-115">See also</span></span>

- [<span data-ttu-id="67913-116">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="67913-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
