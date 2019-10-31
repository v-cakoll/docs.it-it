---
title: Interfaccia ICorDebugHeapValue
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: 4f87065fc4a3d80a8363f3ae2fbb76c29f3d9b96
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138409"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="c2cb3-102">Interfaccia ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="c2cb3-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="c2cb3-103">Sottoclasse di "ICorDebugValue" che rappresenta un oggetto raccolto dall'Garbage Collector di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c2cb3-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2cb3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c2cb3-104">Methods</span></span>  
  
|<span data-ttu-id="c2cb3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c2cb3-105">Method</span></span>|<span data-ttu-id="c2cb3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2cb3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2cb3-107">Metodo CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c2cb3-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="c2cb3-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="c2cb3-108">Not implemented.</span></span>|  
|[<span data-ttu-id="c2cb3-109">Metodo IsValid</span><span class="sxs-lookup"><span data-stu-id="c2cb3-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="c2cb3-110">Ottiene un valore che indica se l'oggetto rappresentato da questo `ICorDebugHeapValue` è valido o è stato recuperato dall'Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="c2cb3-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="c2cb3-111">Questo metodo è stato deprecato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="c2cb3-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2cb3-112">Note</span><span class="sxs-lookup"><span data-stu-id="c2cb3-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2cb3-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c2cb3-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2cb3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2cb3-114">Requirements</span></span>  
 <span data-ttu-id="c2cb3-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2cb3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2cb3-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2cb3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2cb3-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2cb3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2cb3-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2cb3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cb3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2cb3-119">See also</span></span>

- [<span data-ttu-id="c2cb3-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c2cb3-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
