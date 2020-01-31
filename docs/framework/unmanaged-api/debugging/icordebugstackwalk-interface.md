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
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791884"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="e9ccd-102">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="e9ccd-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="e9ccd-103">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="e9ccd-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9ccd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e9ccd-104">Methods</span></span>  
  
|<span data-ttu-id="e9ccd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9ccd-105">Method</span></span>|<span data-ttu-id="e9ccd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9ccd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9ccd-107">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="e9ccd-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="e9ccd-108">Restituisce il contesto per il frame corrente nell'oggetto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="e9ccd-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="e9ccd-109">Metodo SetContext</span><span class="sxs-lookup"><span data-stu-id="e9ccd-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="e9ccd-110">Imposta il contesto corrente dell'oggetto `ICorDebugStackWalk` su un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="e9ccd-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="e9ccd-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="e9ccd-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="e9ccd-112">Sposta l'oggetto `ICorDebugStackWalk` al frame successivo.</span><span class="sxs-lookup"><span data-stu-id="e9ccd-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="e9ccd-113">Metodo GetFrame</span><span class="sxs-lookup"><span data-stu-id="e9ccd-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="e9ccd-114">Ottiene il frame corrente nell'oggetto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="e9ccd-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9ccd-115">Note</span><span class="sxs-lookup"><span data-stu-id="e9ccd-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9ccd-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e9ccd-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9ccd-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e9ccd-117">Requirements</span></span>  
 <span data-ttu-id="e9ccd-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9ccd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9ccd-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9ccd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9ccd-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9ccd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9ccd-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ccd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ccd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9ccd-122">See also</span></span>

- [<span data-ttu-id="e9ccd-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e9ccd-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e9ccd-124">Debug</span><span class="sxs-lookup"><span data-stu-id="e9ccd-124">Debugging</span></span>](index.md)
