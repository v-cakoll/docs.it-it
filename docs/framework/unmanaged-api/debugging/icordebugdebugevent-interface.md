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
ms.openlocfilehash: b4422b165f06b60dedff95fc3de58e5627db7fac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="296ad-102">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="296ad-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="296ad-103">Definisce l'interfaccia di base da cui derivano tutti gli eventi di debug `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="296ad-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="296ad-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="296ad-104">Methods</span></span>  
  
|<span data-ttu-id="296ad-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="296ad-105">Method</span></span>|<span data-ttu-id="296ad-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="296ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="296ad-107">Metodo GetEventKind</span><span class="sxs-lookup"><span data-stu-id="296ad-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="296ad-108">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="296ad-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="296ad-109">GetThread (metodo)</span><span class="sxs-lookup"><span data-stu-id="296ad-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="296ad-110">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="296ad-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="296ad-111">Note</span><span class="sxs-lookup"><span data-stu-id="296ad-111">Remarks</span></span>  
 <span data-ttu-id="296ad-112">Le interfacce seguenti sono derivate dall'interfaccia `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="296ad-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="296ad-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="296ad-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="296ad-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="296ad-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="296ad-115">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="296ad-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="296ad-116">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="296ad-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="296ad-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="296ad-117">Requirements</span></span>  
 <span data-ttu-id="296ad-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="296ad-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="296ad-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="296ad-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="296ad-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="296ad-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="296ad-121">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="296ad-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="296ad-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="296ad-122">See Also</span></span>  
 [<span data-ttu-id="296ad-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="296ad-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="296ad-124">Debug</span><span class="sxs-lookup"><span data-stu-id="296ad-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
