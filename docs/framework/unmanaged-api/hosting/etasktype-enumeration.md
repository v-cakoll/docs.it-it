---
title: Enumerazione ETaskType
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f256195a4cd5b18f568e05156db867aa5dba9161
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229823"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="ea8ef-102">Enumerazione ETaskType</span><span class="sxs-lookup"><span data-stu-id="ea8ef-102">ETaskType Enumeration</span></span>
<span data-ttu-id="ea8ef-103">Contiene valori che indicano il tipo di attività che è rappresentato da un [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o un' [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea8ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea8ef-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="ea8ef-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ea8ef-105">Members</span></span>  
  
|<span data-ttu-id="ea8ef-106">Member</span><span class="sxs-lookup"><span data-stu-id="ea8ef-106">Member</span></span>|<span data-ttu-id="ea8ef-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea8ef-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="ea8ef-108">L'interfaccia rappresenta un'attività di scaricamento del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="ea8ef-109">L'interfaccia rappresenta un'attività di supporto del debugger.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="ea8ef-110">L'interfaccia rappresenta un'attività del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="ea8ef-111">L'interfaccia rappresenta un'attività di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="ea8ef-112">L'interfaccia rappresenta un'attività di thread di attività di controllo.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="ea8ef-113">L'interfaccia rappresenta un'attività di thread dei / o o un'attività di thread di porta di completamento.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="ea8ef-114">L'interfaccia rappresenta un'attività di thread di timer.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="ea8ef-115">L'interfaccia rappresenta un'attività di thread di attesa.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="ea8ef-116">L'interfaccia rappresenta un'attività di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="ea8ef-117">L'attività è sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="ea8ef-118">L'interfaccia rappresenta un'attività definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ea8ef-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea8ef-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea8ef-119">Requirements</span></span>  
 <span data-ttu-id="ea8ef-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8ef-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8ef-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea8ef-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea8ef-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea8ef-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea8ef-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8ef-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8ef-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea8ef-124">See also</span></span>

- [<span data-ttu-id="ea8ef-125">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="ea8ef-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
