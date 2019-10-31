---
title: Metodo IDebuggerThreadControl::StartBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 72f7bee79e74c69acff90861ceada8a91afe2157
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134923"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="7d93a-102">Metodo IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="7d93a-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="7d93a-103">Notifica all'host che i servizi di debug stanno per iniziare a bloccare tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="7d93a-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d93a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d93a-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d93a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d93a-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="7d93a-106">in Riservato per usi futuri.</span><span class="sxs-lookup"><span data-stu-id="7d93a-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d93a-107">Note</span><span class="sxs-lookup"><span data-stu-id="7d93a-107">Remarks</span></span>  
 <span data-ttu-id="7d93a-108">È possibile chiamare il metodo `StartBlockingForDebugger` su un thread runtime.</span><span class="sxs-lookup"><span data-stu-id="7d93a-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d93a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d93a-109">Requirements</span></span>  
 <span data-ttu-id="7d93a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d93a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d93a-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7d93a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d93a-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7d93a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d93a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d93a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d93a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d93a-114">See also</span></span>

- [<span data-ttu-id="7d93a-115">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="7d93a-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
