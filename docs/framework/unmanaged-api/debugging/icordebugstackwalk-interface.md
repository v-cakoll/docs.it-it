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
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378899"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="e5b10-102">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="e5b10-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="e5b10-103">Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.</span><span class="sxs-lookup"><span data-stu-id="e5b10-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5b10-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e5b10-104">Methods</span></span>  
  
|<span data-ttu-id="e5b10-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e5b10-105">Method</span></span>|<span data-ttu-id="e5b10-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5b10-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5b10-107">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="e5b10-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="e5b10-108">Restituisce il contesto per il frame corrente nell' `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5b10-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="e5b10-109">Metodo SetContext</span><span class="sxs-lookup"><span data-stu-id="e5b10-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="e5b10-110">Imposta il `ICorDebugStackWalk` contesto corrente dell'oggetto su un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="e5b10-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="e5b10-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="e5b10-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="e5b10-112">Sposta l' `ICorDebugStackWalk` oggetto sul frame successivo.</span><span class="sxs-lookup"><span data-stu-id="e5b10-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="e5b10-113">Metodo GetFrame</span><span class="sxs-lookup"><span data-stu-id="e5b10-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="e5b10-114">Ottiene il frame corrente nell' `ICorDebugStackWalk` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5b10-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5b10-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e5b10-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5b10-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e5b10-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b10-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5b10-117">Requirements</span></span>  
 <span data-ttu-id="e5b10-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5b10-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b10-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5b10-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5b10-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5b10-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5b10-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b10-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b10-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5b10-122">See also</span></span>

- [<span data-ttu-id="e5b10-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e5b10-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e5b10-124">Debug</span><span class="sxs-lookup"><span data-stu-id="e5b10-124">Debugging</span></span>](index.md)
