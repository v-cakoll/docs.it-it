---
title: Enumerazione CorDebugBlockingReason
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe5e1267b619d5900ed9af55dd6079a8f38d6550
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406900"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="dbd3f-102">Enumerazione CorDebugBlockingReason</span><span class="sxs-lookup"><span data-stu-id="dbd3f-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="dbd3f-103">Specifica i motivi che possono causare il blocco di un thread su un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd3f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbd3f-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="dbd3f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="dbd3f-105">Members</span></span>  
  
|<span data-ttu-id="dbd3f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="dbd3f-106">Member</span></span>|<span data-ttu-id="dbd3f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbd3f-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="dbd3f-108">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="dbd3f-109">Un thread sta tentando di acquisire la sezione critica è associata al blocco di monitoraggio su un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="dbd3f-110">In genere, questo errore si verifica quando si chiama uno del <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> o <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> metodi.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="dbd3f-111">Un thread è in attesa dell'evento associato a un blocco di monitoraggio per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="dbd3f-112">In genere, questo errore si verifica quando si chiama uno del <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` metodi.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbd3f-113">Note</span><span class="sxs-lookup"><span data-stu-id="dbd3f-113">Remarks</span></span>  
 <span data-ttu-id="dbd3f-114">Quando il `BLOCKING_MONITOR_CRITICAL_SECTION` o `BLOCKING_MONITOR_EVENT` membro viene utilizzato un [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) struttura, il `pBlockingObject` membro della struttura punta a un'interfaccia "ICorDebugValue" che rappresenta l'oggetto in corso di immissione .</span><span class="sxs-lookup"><span data-stu-id="dbd3f-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="dbd3f-115">È inoltre garantito per implementare il [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbd3f-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dbd3f-116">Requirements</span></span>  
 <span data-ttu-id="dbd3f-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd3f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd3f-118">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="dbd3f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbd3f-119">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="dbd3f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbd3f-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd3f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd3f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbd3f-121">See Also</span></span>  
 [<span data-ttu-id="dbd3f-122">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="dbd3f-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="dbd3f-123">Debug</span><span class="sxs-lookup"><span data-stu-id="dbd3f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
