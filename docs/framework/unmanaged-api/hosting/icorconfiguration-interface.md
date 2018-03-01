---
title: Interfaccia ICorConfiguration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af9a7d4bb1d38fd4a81e954074b074325409ee5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="978f7-102">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="978f7-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="978f7-103">Fornisce metodi per la configurazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="978f7-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="978f7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="978f7-104">Methods</span></span>  
  
|<span data-ttu-id="978f7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="978f7-105">Method</span></span>|<span data-ttu-id="978f7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="978f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="978f7-107">Metodo AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="978f7-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="978f7-108">Indica che un determinato thread dovrebbe poter continuare l'esecuzione mentre il debugger ha un'applicazione è stata arrestata durante gli scenari di debug gestiti o ai servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="978f7-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="978f7-109">Metodo SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="978f7-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="978f7-110">Imposta l'interfaccia di callback che i servizi di debug verranno chiamato quando i thread CLR sono bloccati e non bloccato per il debug.</span><span class="sxs-lookup"><span data-stu-id="978f7-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="978f7-111">Metodo SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="978f7-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="978f7-112">Imposta l'interfaccia di callback per essere utilizzata dal garbage collector per richiedere all'host di modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="978f7-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="978f7-113">Metodo SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="978f7-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="978f7-114">Imposta l'interfaccia di callback per la pianificazione di thread per l'attività non è una fase di esecuzione che altrimenti sarebbero bloccati per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="978f7-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="978f7-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="978f7-115">Requirements</span></span>  
 <span data-ttu-id="978f7-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="978f7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="978f7-117">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="978f7-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="978f7-118">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="978f7-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="978f7-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="978f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="978f7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="978f7-120">See Also</span></span>  
 [<span data-ttu-id="978f7-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="978f7-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="978f7-122">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="978f7-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
