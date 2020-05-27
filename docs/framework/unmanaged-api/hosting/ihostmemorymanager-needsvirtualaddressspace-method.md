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
ms.openlocfilehash: bb13c7329c558aa92ec65237aa8a9963c82fe1dc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804518"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="5de88-102">Metodo IHostMemoryManager::NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="5de88-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="5de88-103">Notifica all'host che il Common Language Runtime (CLR) tenterà di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="5de88-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5de88-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5de88-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5de88-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="5de88-106">in Indirizzo iniziale della memoria.</span><span class="sxs-lookup"><span data-stu-id="5de88-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="5de88-107">in Dimensione, in byte, della memoria.</span><span class="sxs-lookup"><span data-stu-id="5de88-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de88-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5de88-108">Remarks</span></span>  
 <span data-ttu-id="5de88-109">Il `NeedsVirtualAddressSpace` metodo è un metodo di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="5de88-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="5de88-110">Viene chiamato da CLR.</span><span class="sxs-lookup"><span data-stu-id="5de88-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="5de88-111">Se l'host non desidera che CLR utilizzi la memoria specificata, può restituire un E_OUTOFMEMORY HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5de88-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de88-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5de88-112">Requirements</span></span>  
 <span data-ttu-id="5de88-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5de88-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de88-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5de88-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5de88-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5de88-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5de88-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de88-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de88-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5de88-117">See also</span></span>

- [<span data-ttu-id="5de88-118">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="5de88-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
