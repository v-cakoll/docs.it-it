---
title: Interfaccia ICorDebugDebugEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c4d777d601866ca9600a7e2b88aca8854f32a17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="07cea-102">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="07cea-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="07cea-103">Definisce l'interfaccia di base da cui derivano tutti gli eventi di debug `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="07cea-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07cea-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="07cea-104">Methods</span></span>  
  
|<span data-ttu-id="07cea-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="07cea-105">Method</span></span>|<span data-ttu-id="07cea-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07cea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07cea-107">Metodo GetEventKind</span><span class="sxs-lookup"><span data-stu-id="07cea-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="07cea-108">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="07cea-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="07cea-109">Metodo GetThread</span><span class="sxs-lookup"><span data-stu-id="07cea-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="07cea-110">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="07cea-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07cea-111">Note</span><span class="sxs-lookup"><span data-stu-id="07cea-111">Remarks</span></span>  
 <span data-ttu-id="07cea-112">Le interfacce seguenti sono derivate dall'interfaccia `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="07cea-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="07cea-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="07cea-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="07cea-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="07cea-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="07cea-115">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="07cea-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="07cea-116">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="07cea-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07cea-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07cea-117">Requirements</span></span>  
 <span data-ttu-id="07cea-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07cea-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07cea-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="07cea-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07cea-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07cea-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07cea-121">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07cea-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07cea-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07cea-122">See Also</span></span>  
 [<span data-ttu-id="07cea-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="07cea-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="07cea-124">Debug</span><span class="sxs-lookup"><span data-stu-id="07cea-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
