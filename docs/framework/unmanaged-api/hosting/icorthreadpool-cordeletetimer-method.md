---
title: Metodo ICorThreadpool::CorDeleteTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
ms.openlocfilehash: 42108f8b51954466a94d735ab9c4e49567b307e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133298"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="60a9d-102">Metodo ICorThreadpool::CorDeleteTimer</span><span class="sxs-lookup"><span data-stu-id="60a9d-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="60a9d-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="60a9d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60a9d-104">Syntax</span></span>  
  
```cpp  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="60a9d-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60a9d-105">Requirements</span></span>  
 <span data-ttu-id="60a9d-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60a9d-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60a9d-107">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="60a9d-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60a9d-108">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="60a9d-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60a9d-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60a9d-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a9d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a9d-110">See also</span></span>

- [<span data-ttu-id="60a9d-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="60a9d-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
