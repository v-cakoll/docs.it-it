---
title: Interfaccia ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: dfa65aa1b63c996068e75ff1165111d5fcfe77eb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976005"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="c787a-102">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c787a-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="c787a-103">Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="c787a-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c787a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c787a-104">Methods</span></span>  
  
|<span data-ttu-id="c787a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c787a-105">Method</span></span>|<span data-ttu-id="c787a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c787a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c787a-107">Metodo GetFlags</span><span class="sxs-lookup"><span data-stu-id="c787a-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="c787a-108">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c787a-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="c787a-109">Metodo GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="c787a-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="c787a-110">Ottiene il puntatore all'interfaccia nativa per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c787a-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="c787a-111">Metodo GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="c787a-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="c787a-112">Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c787a-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c787a-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c787a-113">Remarks</span></span>  
 <span data-ttu-id="c787a-114">L'interfaccia `ICorDebugExceptionDebugEvent` è implementata dai tipi di evento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c787a-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="c787a-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="c787a-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="c787a-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="c787a-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="c787a-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="c787a-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="c787a-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="c787a-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="c787a-119">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c787a-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="c787a-120">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c787a-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c787a-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c787a-121">Requirements</span></span>  
 <span data-ttu-id="c787a-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c787a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c787a-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c787a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c787a-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c787a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c787a-125">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c787a-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c787a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c787a-126">See also</span></span>

- [<span data-ttu-id="c787a-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c787a-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c787a-128">Debug</span><span class="sxs-lookup"><span data-stu-id="c787a-128">Debugging</span></span>](index.md)
