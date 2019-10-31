---
title: Metodo IHostMemoryManager::NeedsVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
ms.openlocfilehash: a3ae474a73f4c8e4b98c4b2bc5d04e55bcae6874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128660"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="303b6-102">Metodo IHostMemoryManager::NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="303b6-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="303b6-103">Notifica all'host che il Common Language Runtime (CLR) tenterà di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="303b6-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="303b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="303b6-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="303b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="303b6-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="303b6-106">in Indirizzo iniziale della memoria.</span><span class="sxs-lookup"><span data-stu-id="303b6-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="303b6-107">in Dimensione, in byte, della memoria.</span><span class="sxs-lookup"><span data-stu-id="303b6-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="303b6-108">Note</span><span class="sxs-lookup"><span data-stu-id="303b6-108">Remarks</span></span>  
 <span data-ttu-id="303b6-109">Il metodo `NeedsVirtualAddressSpace` è un metodo di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="303b6-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="303b6-110">Viene chiamato da CLR.</span><span class="sxs-lookup"><span data-stu-id="303b6-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="303b6-111">Se l'host non desidera che CLR utilizzi la memoria specificata, può restituire un valore HRESULT E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="303b6-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="303b6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="303b6-112">Requirements</span></span>  
 <span data-ttu-id="303b6-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="303b6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="303b6-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="303b6-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="303b6-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="303b6-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="303b6-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="303b6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303b6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="303b6-117">See also</span></span>

- [<span data-ttu-id="303b6-118">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="303b6-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
