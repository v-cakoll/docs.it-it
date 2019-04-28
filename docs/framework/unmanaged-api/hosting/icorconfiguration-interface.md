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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24e278b3449d0e17377495cef0f445c1ebed734
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763273"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="ebc0a-102">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ebc0a-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="ebc0a-103">Fornisce metodi per la configurazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ebc0a-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ebc0a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ebc0a-104">Methods</span></span>  
  
|<span data-ttu-id="ebc0a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ebc0a-105">Method</span></span>|<span data-ttu-id="ebc0a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ebc0a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ebc0a-107">Metodo AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="ebc0a-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="ebc0a-108">Indica che un thread specifico deve essere consentito di continuare l'esecuzione mentre il debugger ha un'applicazione arrestata durante gli scenari di debug gestiti o per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="ebc0a-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="ebc0a-109">Metodo SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="ebc0a-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="ebc0a-110">Imposta l'interfaccia di callback che i servizi di debug verranno chiamato come thread del CLR viene bloccato e sbloccato per eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="ebc0a-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="ebc0a-111">Metodo SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="ebc0a-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="ebc0a-112">Imposta l'interfaccia di callback per essere utilizzata dal garbage collector per richiedere l'host per modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="ebc0a-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="ebc0a-113">Metodo SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="ebc0a-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="ebc0a-114">Imposta l'interfaccia di callback per la pianificazione dei thread per le attività non di runtime che verrebbe bloccate in caso contrario, per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ebc0a-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebc0a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebc0a-115">Requirements</span></span>  
 <span data-ttu-id="ebc0a-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebc0a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc0a-117">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebc0a-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebc0a-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ebc0a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebc0a-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc0a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc0a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebc0a-120">See also</span></span>

- [<span data-ttu-id="ebc0a-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ebc0a-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ebc0a-122">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ebc0a-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
