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
ms.openlocfilehash: 4a246fb95ab5b4a7f187aa660f20e590c63ddff2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804463"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="873f7-102">Metodo IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="873f7-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="873f7-103">Notifica all'host che la Common Language Runtime (CLR) ha terminato l'utilizzo della memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="873f7-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="873f7-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="873f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="873f7-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="873f7-106">in Puntatore all'indirizzo iniziale della memoria da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="873f7-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="873f7-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="873f7-107">Remarks</span></span>  
 <span data-ttu-id="873f7-108">Il `ReleasedVirtualAddressSpace` metodo è un metodo di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="873f7-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="873f7-109">Viene chiamato da CLR.</span><span class="sxs-lookup"><span data-stu-id="873f7-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="873f7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="873f7-110">Requirements</span></span>  
 <span data-ttu-id="873f7-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="873f7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="873f7-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="873f7-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="873f7-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="873f7-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="873f7-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="873f7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873f7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="873f7-115">See also</span></span>

- [<span data-ttu-id="873f7-116">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="873f7-116">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
