---
title: Metodo ICorThreadpool::CorCreateTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
ms.openlocfilehash: 17afd0922930bc6db122e8dc07125dcafd483cf5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133300"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="906c7-102">Metodo ICorThreadpool::CorCreateTimer</span><span class="sxs-lookup"><span data-stu-id="906c7-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="906c7-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="906c7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="906c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="906c7-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="906c7-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="906c7-105">Requirements</span></span>  
 <span data-ttu-id="906c7-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="906c7-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="906c7-107">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="906c7-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="906c7-108">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="906c7-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="906c7-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="906c7-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906c7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="906c7-110">See also</span></span>

- [<span data-ttu-id="906c7-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="906c7-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
