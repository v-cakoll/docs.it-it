---
title: ICorDebugHeapValue Interface1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a87790647ed8896f072aa8e943e31fa1980e3f62
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622858"
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="5fddb-102">ICorDebugHeapValue Interface1</span><span class="sxs-lookup"><span data-stu-id="5fddb-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="5fddb-103">Sottoclasse di "ICorDebugValue" che rappresenta un oggetto raccolto dal garbage collector di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5fddb-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5fddb-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5fddb-104">Methods</span></span>  
  
|<span data-ttu-id="5fddb-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5fddb-105">Method</span></span>|<span data-ttu-id="5fddb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5fddb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5fddb-107">Metodo CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5fddb-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="5fddb-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="5fddb-108">Not implemented.</span></span>|  
|[<span data-ttu-id="5fddb-109">Metodo IsValid</span><span class="sxs-lookup"><span data-stu-id="5fddb-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="5fddb-110">Ottiene un valore che indica se l'oggetto rappresentato da questo `ICorDebugHeapValue` è valido o è stato recuperato dal garbage collector.</span><span class="sxs-lookup"><span data-stu-id="5fddb-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="5fddb-111">Questo metodo è stato deprecato in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="5fddb-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fddb-112">Note</span><span class="sxs-lookup"><span data-stu-id="5fddb-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fddb-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="5fddb-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fddb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fddb-114">Requirements</span></span>  
 <span data-ttu-id="5fddb-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fddb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fddb-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fddb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fddb-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fddb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fddb-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fddb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fddb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fddb-119">See also</span></span>



- [<span data-ttu-id="5fddb-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5fddb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
