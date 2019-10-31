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
ms.openlocfilehash: bc488e55bf64468eb62e2dc6eaedca62ebde3310
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098980"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="29b36-102">Enumerazione CorDebugBlockingReason</span><span class="sxs-lookup"><span data-stu-id="29b36-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="29b36-103">Specifica i motivi che possono causare il blocco di un thread su un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="29b36-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29b36-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="29b36-105">Members</span><span class="sxs-lookup"><span data-stu-id="29b36-105">Members</span></span>  
  
|<span data-ttu-id="29b36-106">Member</span><span class="sxs-lookup"><span data-stu-id="29b36-106">Member</span></span>|<span data-ttu-id="29b36-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29b36-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="29b36-108">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="29b36-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="29b36-109">Un thread sta tentando di acquisire la sezione critica associata al blocco di monitoraggio su un oggetto.</span><span class="sxs-lookup"><span data-stu-id="29b36-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="29b36-110">Questa situazione si verifica in genere quando si chiama uno dei metodi <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> o <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="29b36-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="29b36-111">Un thread è in attesa dell'evento associato a un blocco di monitoraggio per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="29b36-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="29b36-112">Questa situazione si verifica in genere quando si chiama uno dei metodi di `Wait` <xref:System.Threading.Monitor?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="29b36-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29b36-113">Note</span><span class="sxs-lookup"><span data-stu-id="29b36-113">Remarks</span></span>  
 <span data-ttu-id="29b36-114">Quando il `BLOCKING_MONITOR_CRITICAL_SECTION` o il membro `BLOCKING_MONITOR_EVENT` viene usato in una struttura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , il membro `pBlockingObject` della struttura punta a un'interfaccia "ICorDebugValue" che rappresenta l'oggetto immesso.</span><span class="sxs-lookup"><span data-stu-id="29b36-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="29b36-115">È inoltre garantita l'implementazione dell'interfaccia [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="29b36-115">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29b36-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29b36-116">Requirements</span></span>  
 <span data-ttu-id="29b36-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29b36-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29b36-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29b36-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29b36-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29b36-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29b36-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29b36-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b36-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29b36-121">See also</span></span>

- [<span data-ttu-id="29b36-122">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="29b36-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="29b36-123">Debug</span><span class="sxs-lookup"><span data-stu-id="29b36-123">Debugging</span></span>](index.md)
