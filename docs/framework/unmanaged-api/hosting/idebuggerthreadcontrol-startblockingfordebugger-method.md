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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc94c2de1a14842cc017e5c4ef6023154c20f2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194032"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="25f87-102">Metodo IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="25f87-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="25f87-103">Notifica all'host che i servizi di debug stanno per avviare il blocco di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="25f87-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f87-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25f87-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25f87-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25f87-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="25f87-106">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="25f87-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25f87-107">Note</span><span class="sxs-lookup"><span data-stu-id="25f87-107">Remarks</span></span>  
 <span data-ttu-id="25f87-108">Il `StartBlockingForDebugger` metodo può essere chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="25f87-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f87-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25f87-109">Requirements</span></span>  
 <span data-ttu-id="25f87-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25f87-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f87-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25f87-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25f87-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="25f87-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="25f87-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="25f87-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25f87-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25f87-114">See also</span></span>

- [<span data-ttu-id="25f87-115">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="25f87-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
