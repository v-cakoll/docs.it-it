---
title: Metodo IDebuggerThreadControl::StartBlockingForDebugger
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.StartBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99c0bc78705fa07883d92bf0cc1d90300c5ac549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="2c63b-102">Metodo IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="2c63b-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="2c63b-103">Notifica all'host che i servizi di debug stanno per avviare il blocco di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="2c63b-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c63b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c63b-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c63b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c63b-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="2c63b-106">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="2c63b-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c63b-107">Note</span><span class="sxs-lookup"><span data-stu-id="2c63b-107">Remarks</span></span>  
 <span data-ttu-id="2c63b-108">Il `StartBlockingForDebugger` metodo potrebbe essere chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="2c63b-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c63b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c63b-109">Requirements</span></span>  
 <span data-ttu-id="2c63b-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c63b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c63b-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2c63b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c63b-112">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c63b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c63b-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c63b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c63b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c63b-114">See Also</span></span>  
 [<span data-ttu-id="2c63b-115">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="2c63b-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
