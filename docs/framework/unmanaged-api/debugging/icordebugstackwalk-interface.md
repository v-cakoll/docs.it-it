---
title: Interfaccia ICorDebugStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06ce2da435df9458ca59d76fa426becbede2e619
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959668"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="f7b84-102">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="f7b84-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="f7b84-103">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="f7b84-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7b84-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f7b84-104">Methods</span></span>  
  
|<span data-ttu-id="f7b84-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f7b84-105">Method</span></span>|<span data-ttu-id="f7b84-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b84-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7b84-107">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="f7b84-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="f7b84-108">Restituisce il contesto per il frame corrente nell' `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="f7b84-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="f7b84-109">Metodo SetContext</span><span class="sxs-lookup"><span data-stu-id="f7b84-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="f7b84-110">Imposta il `ICorDebugStackWalk` contesto corrente dell'oggetto su un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="f7b84-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="f7b84-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="f7b84-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="f7b84-112">Sposta l' `ICorDebugStackWalk` oggetto sul frame successivo.</span><span class="sxs-lookup"><span data-stu-id="f7b84-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="f7b84-113">Metodo GetFrame</span><span class="sxs-lookup"><span data-stu-id="f7b84-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="f7b84-114">Ottiene il frame corrente nell' `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="f7b84-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7b84-115">Note</span><span class="sxs-lookup"><span data-stu-id="f7b84-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7b84-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f7b84-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b84-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7b84-117">Requirements</span></span>  
 <span data-ttu-id="f7b84-118">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b84-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b84-119">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f7b84-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7b84-120">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7b84-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7b84-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b84-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b84-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b84-122">See also</span></span>

- [<span data-ttu-id="f7b84-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f7b84-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f7b84-124">Debug</span><span class="sxs-lookup"><span data-stu-id="f7b84-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
