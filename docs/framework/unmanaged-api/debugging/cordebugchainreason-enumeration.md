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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e19897015a00d82da30fd670efcdd97c4d06f56f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406318"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="ade80-102">Enumerazione CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="ade80-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="ade80-103">Indica i motivi che determinano l'avvio di una catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="ade80-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade80-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ade80-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="ade80-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ade80-105">Members</span></span>  
  
|<span data-ttu-id="ade80-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ade80-106">Member</span></span>|<span data-ttu-id="ade80-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ade80-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="ade80-108">Non è stata avviata alcuna catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="ade80-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="ade80-109">La catena è stata avviata da un costruttore.</span><span class="sxs-lookup"><span data-stu-id="ade80-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="ade80-110">La catena è stata avviata da un filtro di eccezione.</span><span class="sxs-lookup"><span data-stu-id="ade80-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="ade80-111">La catena è stata avviata dal codice che applica la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ade80-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="ade80-112">La catena è stata avviata da un criterio di contesto.</span><span class="sxs-lookup"><span data-stu-id="ade80-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="ade80-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="ade80-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="ade80-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="ade80-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="ade80-115">La catena è stata avviata dall'avvio dell'esecuzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="ade80-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="ade80-116">La catena è stata avviata da una voce nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ade80-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="ade80-117">La catena è stata avviata da una voce nel codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="ade80-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="ade80-118">Non usato.</span><span class="sxs-lookup"><span data-stu-id="ade80-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="ade80-119">Non usato.</span><span class="sxs-lookup"><span data-stu-id="ade80-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="ade80-120">La catena è stata avviata da una valutazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="ade80-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ade80-121">Note</span><span class="sxs-lookup"><span data-stu-id="ade80-121">Remarks</span></span>  
 <span data-ttu-id="ade80-122">Utilizzare il [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) metodo per verificare i motivi per l'avvio di una catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="ade80-122">Use the [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ade80-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ade80-123">Requirements</span></span>  
 <span data-ttu-id="ade80-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ade80-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ade80-125">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ade80-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ade80-126">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ade80-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ade80-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ade80-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade80-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ade80-128">See Also</span></span>  
 [<span data-ttu-id="ade80-129">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ade80-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
