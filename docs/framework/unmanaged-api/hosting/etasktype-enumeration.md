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
ms.openlocfilehash: 435d23d4a56d6ea98e3d368f0a5aa37c73e31d96
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616164"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="8ea85-102">Enumerazione ETaskType</span><span class="sxs-lookup"><span data-stu-id="8ea85-102">ETaskType Enumeration</span></span>
<span data-ttu-id="8ea85-103">Contiene valori che indicano il tipo di attività rappresentato da un'interfaccia [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8ea85-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea85-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ea85-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="8ea85-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8ea85-105">Members</span></span>  
  
|<span data-ttu-id="8ea85-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8ea85-106">Member</span></span>|<span data-ttu-id="8ea85-107">Description</span><span class="sxs-lookup"><span data-stu-id="8ea85-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="8ea85-108">L'interfaccia rappresenta un'attività di scaricamento del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="8ea85-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="8ea85-109">L'interfaccia rappresenta un'attività helper del debugger.</span><span class="sxs-lookup"><span data-stu-id="8ea85-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="8ea85-110">L'interfaccia rappresenta un'attività del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="8ea85-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="8ea85-111">L'interfaccia rappresenta un'attività Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8ea85-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="8ea85-112">L'interfaccia rappresenta un'attività del thread del controllo.</span><span class="sxs-lookup"><span data-stu-id="8ea85-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="8ea85-113">L'interfaccia rappresenta un'attività thread di I/O o un'attività thread della porta di completamento.</span><span class="sxs-lookup"><span data-stu-id="8ea85-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="8ea85-114">L'interfaccia rappresenta un'attività thread del timer.</span><span class="sxs-lookup"><span data-stu-id="8ea85-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="8ea85-115">L'interfaccia rappresenta un'attività thread di attesa.</span><span class="sxs-lookup"><span data-stu-id="8ea85-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="8ea85-116">L'interfaccia rappresenta un'attività thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8ea85-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="8ea85-117">L'attività è sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="8ea85-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="8ea85-118">L'interfaccia rappresenta un'attività utente.</span><span class="sxs-lookup"><span data-stu-id="8ea85-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ea85-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ea85-119">Requirements</span></span>  
 <span data-ttu-id="8ea85-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ea85-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea85-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8ea85-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ea85-122">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8ea85-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ea85-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ea85-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea85-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ea85-124">See also</span></span>

- [<span data-ttu-id="8ea85-125">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="8ea85-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
