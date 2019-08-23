---
title: Interfaccia ICorDebugChain
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93ada40bd88e53cd06f5e8d8136b2d527d7741e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969298"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="95bf1-102">Interfaccia ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="95bf1-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="95bf1-103">Rappresenta un segmento di uno stack di chiamate fisico o logico.</span><span class="sxs-lookup"><span data-stu-id="95bf1-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95bf1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="95bf1-104">Methods</span></span>  
  
|<span data-ttu-id="95bf1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="95bf1-105">Method</span></span>|<span data-ttu-id="95bf1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95bf1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95bf1-107">Metodo EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="95bf1-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="95bf1-108">Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.</span><span class="sxs-lookup"><span data-stu-id="95bf1-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="95bf1-109">Metodo GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="95bf1-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="95bf1-110">Ottiene il frame attivo (ovvero, più recente) nella catena.</span><span class="sxs-lookup"><span data-stu-id="95bf1-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="95bf1-111">Metodo GetCallee</span><span class="sxs-lookup"><span data-stu-id="95bf1-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="95bf1-112">Ottiene la catena chiamata dalla catena.</span><span class="sxs-lookup"><span data-stu-id="95bf1-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="95bf1-113">Metodo GetCaller</span><span class="sxs-lookup"><span data-stu-id="95bf1-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="95bf1-114">Ottiene la catena che ha chiamato questa catena.</span><span class="sxs-lookup"><span data-stu-id="95bf1-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="95bf1-115">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="95bf1-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="95bf1-116">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="95bf1-116">Not implemented.</span></span>|  
|[<span data-ttu-id="95bf1-117">Metodo GetNext</span><span class="sxs-lookup"><span data-stu-id="95bf1-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="95bf1-118">Ottiene la catena di frame successiva per il thread.</span><span class="sxs-lookup"><span data-stu-id="95bf1-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="95bf1-119">Metodo GetPrevious</span><span class="sxs-lookup"><span data-stu-id="95bf1-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="95bf1-120">Ottiene la catena di fotogrammi precedente per il thread.</span><span class="sxs-lookup"><span data-stu-id="95bf1-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="95bf1-121">Metodo GetReason</span><span class="sxs-lookup"><span data-stu-id="95bf1-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="95bf1-122">Ottiene il motivo per la genesi della catena chiamante.</span><span class="sxs-lookup"><span data-stu-id="95bf1-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="95bf1-123">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="95bf1-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="95bf1-124">Ottiene il set di registri per la parte attiva della catena.</span><span class="sxs-lookup"><span data-stu-id="95bf1-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="95bf1-125">Metodo GetStackRange</span><span class="sxs-lookup"><span data-stu-id="95bf1-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="95bf1-126">Ottiene l'intervallo di indirizzi del segmento dello stack per questa catena.</span><span class="sxs-lookup"><span data-stu-id="95bf1-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="95bf1-127">Metodo GetThread</span><span class="sxs-lookup"><span data-stu-id="95bf1-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="95bf1-128">Ottiene il thread fisico di cui fa parte questa catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="95bf1-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="95bf1-129">Metodo IsManaged</span><span class="sxs-lookup"><span data-stu-id="95bf1-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="95bf1-130">Ottiene un valore che indica se la catena sta eseguendo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="95bf1-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95bf1-131">Note</span><span class="sxs-lookup"><span data-stu-id="95bf1-131">Remarks</span></span>  
 <span data-ttu-id="95bf1-132">Gli stack frame in una catena occupano lo spazio dello stack contiguo e condividono lo stesso thread e lo stesso contesto.</span><span class="sxs-lookup"><span data-stu-id="95bf1-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="95bf1-133">Una catena può rappresentare catene di codice gestite o non gestite.</span><span class="sxs-lookup"><span data-stu-id="95bf1-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="95bf1-134">Un'istanza `ICorDebugChain` vuota rappresenta una catena di codice non gestita.</span><span class="sxs-lookup"><span data-stu-id="95bf1-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95bf1-135">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="95bf1-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95bf1-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95bf1-136">Requirements</span></span>  
 <span data-ttu-id="95bf1-137">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95bf1-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95bf1-138">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="95bf1-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95bf1-139">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95bf1-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95bf1-140">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95bf1-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bf1-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95bf1-141">See also</span></span>

- [<span data-ttu-id="95bf1-142">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="95bf1-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
