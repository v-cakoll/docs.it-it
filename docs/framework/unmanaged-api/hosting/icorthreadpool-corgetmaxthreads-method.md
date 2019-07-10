---
title: Metodo ICorThreadpool::CorGetMaxThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3699a761dfffa9a78e1acb5ea2a775a1386a9401
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751163"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="a194f-102">Metodo ICorThreadpool::CorGetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="a194f-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="a194f-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="a194f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a194f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a194f-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a194f-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a194f-105">Requirements</span></span>  
 <span data-ttu-id="a194f-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a194f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a194f-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a194f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a194f-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a194f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a194f-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a194f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a194f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a194f-110">See also</span></span>

- [<span data-ttu-id="a194f-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="a194f-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
