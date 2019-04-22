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
ms.openlocfilehash: e33e9be112a6a10f89b88005496ce2e63dff2d54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080683"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="da63d-102">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="da63d-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="da63d-103">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="da63d-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da63d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="da63d-104">Methods</span></span>  
  
|<span data-ttu-id="da63d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="da63d-105">Method</span></span>|<span data-ttu-id="da63d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da63d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da63d-107">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="da63d-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="da63d-108">Restituisce il contesto per il fotogramma corrente il `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="da63d-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="da63d-109">Metodo SetContext</span><span class="sxs-lookup"><span data-stu-id="da63d-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="da63d-110">Imposta il `ICorDebugStackWalk` contesto corrente dell'oggetto a un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="da63d-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="da63d-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="da63d-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="da63d-112">Sposta il `ICorDebugStackWalk` oggetto per il frame successivo.</span><span class="sxs-lookup"><span data-stu-id="da63d-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="da63d-113">Metodo GetFrame</span><span class="sxs-lookup"><span data-stu-id="da63d-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="da63d-114">Ottiene il frame corrente nella `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="da63d-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da63d-115">Note</span><span class="sxs-lookup"><span data-stu-id="da63d-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da63d-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="da63d-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da63d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da63d-117">Requirements</span></span>  
 <span data-ttu-id="da63d-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da63d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da63d-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da63d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da63d-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da63d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da63d-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da63d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da63d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da63d-122">See also</span></span>

- [<span data-ttu-id="da63d-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="da63d-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="da63d-124">Debug</span><span class="sxs-lookup"><span data-stu-id="da63d-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
