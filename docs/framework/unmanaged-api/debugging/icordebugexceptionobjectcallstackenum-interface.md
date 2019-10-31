---
title: Interfaccia ICorDebugExceptionObjectCallStackEnum
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 99a700270794ca92356cb9d134cb869d456199f9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084435"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="dc1c8-102">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="dc1c8-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="dc1c8-103">Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="dc1c8-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="dc1c8-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="dc1c8-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc1c8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="dc1c8-105">Methods</span></span>  
  
|<span data-ttu-id="dc1c8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="dc1c8-106">Method</span></span>|<span data-ttu-id="dc1c8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc1c8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc1c8-108">ICorDebugExceptionObjectCallStackEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="dc1c8-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="dc1c8-109">Ottiene un numero specificato di oggetti [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) che contengono informazioni sullo stack di chiamate di un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="dc1c8-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc1c8-110">Note</span><span class="sxs-lookup"><span data-stu-id="dc1c8-110">Remarks</span></span>  
 <span data-ttu-id="dc1c8-111">L'interfaccia `ICorDebugExceptionObjectCallStackEnum` implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="dc1c8-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="dc1c8-112">Un'istanza di `ICorDebugExceptionObjectCallStackEnum` viene popolata con gli oggetti [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) chiamando il metodo [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dc1c8-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="dc1c8-113">È possibile enumerare gli elementi dello stack di chiamate nella raccolta chiamando il metodo [ICorDebugExceptionObjectCallStackEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="dc1c8-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc1c8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc1c8-114">Requirements</span></span>  
 <span data-ttu-id="dc1c8-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc1c8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc1c8-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc1c8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc1c8-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc1c8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc1c8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc1c8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1c8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc1c8-119">See also</span></span>

- [<span data-ttu-id="dc1c8-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dc1c8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="dc1c8-121">Debug</span><span class="sxs-lookup"><span data-stu-id="dc1c8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
