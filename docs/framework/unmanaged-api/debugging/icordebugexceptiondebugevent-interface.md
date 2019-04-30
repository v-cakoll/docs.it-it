---
title: Interfaccia ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e2a147d46412eb4feb192070ff8420cab842a6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995891"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="a0c3c-102">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a0c3c-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="a0c3c-103">Estende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="a0c3c-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0c3c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a0c3c-104">Methods</span></span>  
  
|<span data-ttu-id="a0c3c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a0c3c-105">Method</span></span>|<span data-ttu-id="a0c3c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0c3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0c3c-107">Metodo GetFlags</span><span class="sxs-lookup"><span data-stu-id="a0c3c-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="a0c3c-108">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a0c3c-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="a0c3c-109">Metodo GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="a0c3c-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="a0c3c-110">Ottiene il puntatore all'interfaccia nativa per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a0c3c-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="a0c3c-111">Metodo GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="a0c3c-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="a0c3c-112">Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a0c3c-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0c3c-113">Note</span><span class="sxs-lookup"><span data-stu-id="a0c3c-113">Remarks</span></span>  
 <span data-ttu-id="a0c3c-114">L'interfaccia `ICorDebugExceptionDebugEvent` è implementata dai tipi di evento seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0c3c-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="a0c3c-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a0c3c-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="a0c3c-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a0c3c-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="a0c3c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="a0c3c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="a0c3c-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="a0c3c-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  <span data-ttu-id="a0c3c-119">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a0c3c-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="a0c3c-120">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a0c3c-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c3c-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0c3c-121">Requirements</span></span>  
 <span data-ttu-id="a0c3c-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0c3c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c3c-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0c3c-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0c3c-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0c3c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0c3c-125">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c3c-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c3c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0c3c-126">See also</span></span>

- [<span data-ttu-id="a0c3c-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a0c3c-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a0c3c-128">Debug</span><span class="sxs-lookup"><span data-stu-id="a0c3c-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
