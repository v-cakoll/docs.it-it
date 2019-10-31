---
title: Metodo ICorThreadpool::CorSetMaxThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
ms.openlocfilehash: e0183ed0f1556afb660ead042dd0d26a63ef75dd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133232"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="dc966-102">Metodo ICorThreadpool::CorSetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="dc966-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="dc966-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="dc966-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc966-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc966-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dc966-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc966-105">Requirements</span></span>  
 <span data-ttu-id="dc966-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc966-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc966-107">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dc966-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc966-108">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc966-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc966-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc966-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc966-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc966-110">See also</span></span>

- [<span data-ttu-id="dc966-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="dc966-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
