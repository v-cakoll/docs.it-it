---
title: Interfaccia ICorConfiguration
ms.date: 03/30/2017
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
ms.openlocfilehash: 80bb68486e555d6c96cf8ee56ed6d60e41c7c5c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127809"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="826d6-102">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="826d6-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="826d6-103">Fornisce metodi per la configurazione del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="826d6-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="826d6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="826d6-104">Methods</span></span>  
  
|<span data-ttu-id="826d6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="826d6-105">Method</span></span>|<span data-ttu-id="826d6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="826d6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="826d6-107">Metodo AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="826d6-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="826d6-108">Indica ai servizi di debug che un determinato thread deve essere in grado di continuare l'esecuzione mentre nel debugger è stata arrestata un'applicazione durante gli scenari di debug gestiti o non gestiti.</span><span class="sxs-lookup"><span data-stu-id="826d6-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="826d6-109">Metodo SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="826d6-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="826d6-110">Imposta l'interfaccia di callback che i servizi di debug chiameranno come thread CLR vengono bloccati e sbloccati per il debug.</span><span class="sxs-lookup"><span data-stu-id="826d6-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="826d6-111">Metodo SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="826d6-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="826d6-112">Imposta l'interfaccia di callback che deve essere utilizzata dal Garbage Collector per richiedere all'host di modificare i limiti della memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="826d6-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="826d6-113">Metodo SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="826d6-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="826d6-114">Imposta l'interfaccia di callback per la pianificazione di thread per le attività non di runtime che altrimenti verrebbero bloccate per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="826d6-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="826d6-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="826d6-115">Requirements</span></span>  
 <span data-ttu-id="826d6-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="826d6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="826d6-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="826d6-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="826d6-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="826d6-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="826d6-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="826d6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826d6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="826d6-120">See also</span></span>

- [<span data-ttu-id="826d6-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="826d6-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="826d6-122">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="826d6-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
