---
title: Interfaccia ICorDebugStackWalk
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 018ed69e52efd21ca25029284c70f1c8493d877f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="4bc23-102">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="4bc23-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="4bc23-103">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="4bc23-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4bc23-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4bc23-104">Methods</span></span>  
  
|<span data-ttu-id="4bc23-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4bc23-105">Method</span></span>|<span data-ttu-id="4bc23-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bc23-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4bc23-107">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="4bc23-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="4bc23-108">Restituisce il contesto per il fotogramma corrente il `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4bc23-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="4bc23-109">Metodo SetContext</span><span class="sxs-lookup"><span data-stu-id="4bc23-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="4bc23-110">Imposta il `ICorDebugStackWalk` contesto corrente dell'oggetto a un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="4bc23-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="4bc23-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="4bc23-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="4bc23-112">Sposta il `ICorDebugStackWalk` oggetto al frame successivo.</span><span class="sxs-lookup"><span data-stu-id="4bc23-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="4bc23-113">Metodo GetFrame</span><span class="sxs-lookup"><span data-stu-id="4bc23-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="4bc23-114">Ottiene il frame corrente `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4bc23-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bc23-115">Note</span><span class="sxs-lookup"><span data-stu-id="4bc23-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bc23-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4bc23-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bc23-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bc23-117">Requirements</span></span>  
 <span data-ttu-id="4bc23-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bc23-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bc23-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4bc23-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bc23-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bc23-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bc23-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bc23-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc23-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bc23-122">See Also</span></span>  
 [<span data-ttu-id="4bc23-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4bc23-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4bc23-124">Debug</span><span class="sxs-lookup"><span data-stu-id="4bc23-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
