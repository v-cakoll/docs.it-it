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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7ed6c04a46a767ed122e54df0695429cf923b8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988910"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="cd917-102">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="cd917-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="cd917-103">Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd917-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="cd917-104">Questa interfaccia è una sottoclasse di interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="cd917-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd917-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cd917-105">Methods</span></span>  
  
|<span data-ttu-id="cd917-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="cd917-106">Method</span></span>|<span data-ttu-id="cd917-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd917-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd917-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="cd917-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="cd917-109">Ottiene un numero specificato di [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) gli oggetti che contengono informazioni sullo stack di chiamate di un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd917-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd917-110">Note</span><span class="sxs-lookup"><span data-stu-id="cd917-110">Remarks</span></span>  
 <span data-ttu-id="cd917-111">Il `ICorDebugExceptionObjectCallStackEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="cd917-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="cd917-112">Un' `ICorDebugExceptionObjectCallStackEnum` istanza viene popolata con [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) oggetti chiamando le [Icordebugexceptionobjectvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="cd917-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="cd917-113">Gli elementi dello stack di chiamate nella raccolta possono essere enumerati chiamando il [Icordebugexceptionobjectcallstackenum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd917-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd917-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd917-114">Requirements</span></span>  
 <span data-ttu-id="cd917-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd917-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd917-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd917-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd917-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd917-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd917-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd917-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd917-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd917-119">See also</span></span>

- [<span data-ttu-id="cd917-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd917-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cd917-121">Debug</span><span class="sxs-lookup"><span data-stu-id="cd917-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
