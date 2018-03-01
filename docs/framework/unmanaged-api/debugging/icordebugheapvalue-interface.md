---
title: ICorDebugHeapValue Interface1
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2ab132b73369526204f8fd811e1567b07b4a9b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="facc4-102">ICorDebugHeapValue Interface1</span><span class="sxs-lookup"><span data-stu-id="facc4-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="facc4-103">Sottoclasse di "ICorDebugValue" che rappresenta un oggetto raccolto dal garbage collector di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="facc4-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="facc4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="facc4-104">Methods</span></span>  
  
|<span data-ttu-id="facc4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="facc4-105">Method</span></span>|<span data-ttu-id="facc4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="facc4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="facc4-107">Metodo CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="facc4-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="facc4-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="facc4-108">Not implemented.</span></span>|  
|[<span data-ttu-id="facc4-109">Metodo IsValid</span><span class="sxs-lookup"><span data-stu-id="facc4-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="facc4-110">Ottiene un valore che indica se l'oggetto rappresentato da questo `ICorDebugHeapValue` è valido o è stato recuperato dal garbage collector.</span><span class="sxs-lookup"><span data-stu-id="facc4-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="facc4-111">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="facc4-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="facc4-112">Note</span><span class="sxs-lookup"><span data-stu-id="facc4-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="facc4-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="facc4-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="facc4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="facc4-114">Requirements</span></span>  
 <span data-ttu-id="facc4-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="facc4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facc4-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="facc4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="facc4-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="facc4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="facc4-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facc4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facc4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="facc4-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="facc4-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="facc4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
