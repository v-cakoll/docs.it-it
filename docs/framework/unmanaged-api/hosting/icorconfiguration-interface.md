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
ms.openlocfilehash: 3b8c9421dea4040a9f183b886f1ad8575cace780
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762429"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="cd372-102">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="cd372-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="cd372-103">Fornisce metodi per la configurazione del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="cd372-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd372-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cd372-104">Methods</span></span>  
  
|<span data-ttu-id="cd372-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cd372-105">Method</span></span>|<span data-ttu-id="cd372-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd372-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd372-107">Metodo AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="cd372-107">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="cd372-108">Indica ai servizi di debug che un determinato thread deve essere in grado di continuare l'esecuzione mentre nel debugger è stata arrestata un'applicazione durante gli scenari di debug gestiti o non gestiti.</span><span class="sxs-lookup"><span data-stu-id="cd372-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="cd372-109">Metodo SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="cd372-109">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="cd372-110">Imposta l'interfaccia di callback che i servizi di debug chiameranno come thread CLR vengono bloccati e sbloccati per il debug.</span><span class="sxs-lookup"><span data-stu-id="cd372-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="cd372-111">Metodo SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="cd372-111">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="cd372-112">Imposta l'interfaccia di callback che deve essere utilizzata dal Garbage Collector per richiedere all'host di modificare i limiti della memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="cd372-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="cd372-113">Metodo SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="cd372-113">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="cd372-114">Imposta l'interfaccia di callback per la pianificazione di thread per le attività non di runtime che altrimenti verrebbero bloccate per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cd372-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd372-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd372-115">Requirements</span></span>  
 <span data-ttu-id="cd372-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd372-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd372-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cd372-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd372-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd372-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd372-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd372-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd372-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd372-120">See also</span></span>

- [<span data-ttu-id="cd372-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="cd372-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="cd372-122">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cd372-122">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
