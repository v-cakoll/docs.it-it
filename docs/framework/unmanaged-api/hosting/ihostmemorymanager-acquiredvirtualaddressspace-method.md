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
ms.openlocfilehash: f5469a6f35826bcb06fe821e3748861dbf3682f3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804535"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="3684d-102">Metodo IHostMemoryManager::AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="3684d-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="3684d-103">Notifica all'host che la Common Language Runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3684d-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3684d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3684d-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3684d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3684d-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="3684d-106">in Indirizzo iniziale della memoria.</span><span class="sxs-lookup"><span data-stu-id="3684d-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="3684d-107">in Dimensione, in byte, della memoria.</span><span class="sxs-lookup"><span data-stu-id="3684d-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3684d-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3684d-108">Remarks</span></span>  
 <span data-ttu-id="3684d-109">Il `AcquiredVirtualAddressSpace` metodo è un metodo di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="3684d-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="3684d-110">Viene chiamato da CLR.</span><span class="sxs-lookup"><span data-stu-id="3684d-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3684d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3684d-111">Requirements</span></span>  
 <span data-ttu-id="3684d-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3684d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3684d-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3684d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3684d-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3684d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3684d-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3684d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3684d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3684d-116">See also</span></span>

- [<span data-ttu-id="3684d-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="3684d-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
