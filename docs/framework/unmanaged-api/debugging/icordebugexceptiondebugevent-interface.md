---
title: Interfaccia ICorDebugExceptionDebugEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c485338f196e4748805231a8391645fdc182d70d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="e5704-102">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e5704-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="e5704-103">Estende il [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="e5704-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5704-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e5704-104">Methods</span></span>  
  
|<span data-ttu-id="e5704-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e5704-105">Method</span></span>|<span data-ttu-id="e5704-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5704-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5704-107">Metodo GetFlags</span><span class="sxs-lookup"><span data-stu-id="e5704-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="e5704-108">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e5704-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="e5704-109">Metodo GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="e5704-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="e5704-110">Ottiene il puntatore all'interfaccia nativa per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e5704-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="e5704-111">Metodo GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="e5704-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="e5704-112">Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e5704-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5704-113">Note</span><span class="sxs-lookup"><span data-stu-id="e5704-113">Remarks</span></span>  
 <span data-ttu-id="e5704-114">L'interfaccia `ICorDebugExceptionDebugEvent` è implementata dai tipi di evento seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5704-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
-   [<span data-ttu-id="e5704-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e5704-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="e5704-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e5704-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="e5704-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="e5704-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="e5704-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="e5704-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  <span data-ttu-id="e5704-119">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e5704-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="e5704-120">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e5704-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5704-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5704-121">Requirements</span></span>  
 <span data-ttu-id="e5704-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5704-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5704-123">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e5704-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5704-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5704-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5704-125">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5704-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5704-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5704-126">See Also</span></span>  
 [<span data-ttu-id="e5704-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e5704-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e5704-128">Debug</span><span class="sxs-lookup"><span data-stu-id="e5704-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
