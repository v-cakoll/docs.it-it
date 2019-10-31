---
title: Enumerazione CorDebugChainReason
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
ms.openlocfilehash: 2f53e3e938f62e714bf421ee7ba0cbf0a47b9f8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132272"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="e2853-102">Enumerazione CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="e2853-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="e2853-103">Indica i motivi che determinano l'avvio di una catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="e2853-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2853-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2853-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a><span data-ttu-id="e2853-105">Members</span><span class="sxs-lookup"><span data-stu-id="e2853-105">Members</span></span>  
  
|<span data-ttu-id="e2853-106">Member</span><span class="sxs-lookup"><span data-stu-id="e2853-106">Member</span></span>|<span data-ttu-id="e2853-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2853-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="e2853-108">Non è stata avviata alcuna catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="e2853-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="e2853-109">La catena è stata avviata da un costruttore.</span><span class="sxs-lookup"><span data-stu-id="e2853-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="e2853-110">La catena è stata avviata da un filtro di eccezione.</span><span class="sxs-lookup"><span data-stu-id="e2853-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="e2853-111">La catena è stata avviata dal codice che applica la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e2853-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="e2853-112">La catena è stata avviata da un criterio di contesto.</span><span class="sxs-lookup"><span data-stu-id="e2853-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="e2853-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e2853-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="e2853-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e2853-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="e2853-115">La catena è stata avviata dall'avvio dell'esecuzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="e2853-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="e2853-116">La catena è stata avviata da una voce nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e2853-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="e2853-117">La catena è stata avviata da una voce nel codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="e2853-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="e2853-118">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e2853-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="e2853-119">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e2853-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="e2853-120">La catena è stata avviata da una valutazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="e2853-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2853-121">Note</span><span class="sxs-lookup"><span data-stu-id="e2853-121">Remarks</span></span>  
 <span data-ttu-id="e2853-122">Usare il metodo [ICorDebugChain:: GetReason](icordebugchain-getreason-method.md) per verificare i motivi dell'avvio di una catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="e2853-122">Use the [ICorDebugChain::GetReason](icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2853-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2853-123">Requirements</span></span>  
 <span data-ttu-id="e2853-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2853-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2853-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2853-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2853-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2853-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2853-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2853-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2853-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2853-128">See also</span></span>

- [<span data-ttu-id="e2853-129">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="e2853-129">Debugging Enumerations</span></span>](debugging-enumerations.md)
