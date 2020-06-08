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
ms.openlocfilehash: 0fa72568df77c4916a3c6676e1dcca7c0c616c4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493318"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="a1834-102">Enumerazione ETaskType</span><span class="sxs-lookup"><span data-stu-id="a1834-102">ETaskType Enumeration</span></span>
<span data-ttu-id="a1834-103">Contiene valori che indicano il tipo di attività rappresentato da un'interfaccia [ICLRTask](iclrtask-interface.md) o [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a1834-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](iclrtask-interface.md) or an [IHostTask](ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1834-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1834-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a1834-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a1834-105">Members</span></span>  
  
|<span data-ttu-id="a1834-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a1834-106">Member</span></span>|<span data-ttu-id="a1834-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1834-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="a1834-108">L'interfaccia rappresenta un'attività di scaricamento del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a1834-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="a1834-109">L'interfaccia rappresenta un'attività helper del debugger.</span><span class="sxs-lookup"><span data-stu-id="a1834-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="a1834-110">L'interfaccia rappresenta un'attività del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="a1834-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="a1834-111">L'interfaccia rappresenta un'attività Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a1834-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="a1834-112">L'interfaccia rappresenta un'attività del thread del controllo.</span><span class="sxs-lookup"><span data-stu-id="a1834-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="a1834-113">L'interfaccia rappresenta un'attività thread di I/O o un'attività thread della porta di completamento.</span><span class="sxs-lookup"><span data-stu-id="a1834-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="a1834-114">L'interfaccia rappresenta un'attività thread del timer.</span><span class="sxs-lookup"><span data-stu-id="a1834-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="a1834-115">L'interfaccia rappresenta un'attività thread di attesa.</span><span class="sxs-lookup"><span data-stu-id="a1834-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="a1834-116">L'interfaccia rappresenta un'attività thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a1834-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="a1834-117">L'attività è sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="a1834-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="a1834-118">L'interfaccia rappresenta un'attività utente.</span><span class="sxs-lookup"><span data-stu-id="a1834-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1834-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1834-119">Requirements</span></span>  
 <span data-ttu-id="a1834-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1834-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1834-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a1834-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1834-122">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a1834-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1834-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1834-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1834-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1834-124">See also</span></span>

- [<span data-ttu-id="a1834-125">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="a1834-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
