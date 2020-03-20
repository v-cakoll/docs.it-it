---
title: Metodo ICorThreadpool::CorChangeTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
ms.openlocfilehash: bb3778a55e7f395ad65f6a9841ca1f31f1de4ebc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178250"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="f2b73-102">Metodo ICorThreadpool::CorChangeTimer</span><span class="sxs-lookup"><span data-stu-id="f2b73-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="f2b73-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="f2b73-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2b73-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f2b73-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2b73-105">Requirements</span></span>  
 <span data-ttu-id="f2b73-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2b73-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2b73-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2b73-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2b73-108">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2b73-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2b73-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2b73-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b73-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2b73-110">See also</span></span>

- [<span data-ttu-id="f2b73-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="f2b73-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
