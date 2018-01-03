---
title: Interfaccia ICorDebugExceptionObjectCallStackEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectCallStackEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords: ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f353ecaf4f0a64920fa7e23b98d09ef3191428cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="c818c-102">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="c818c-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="c818c-103">Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="c818c-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="c818c-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="c818c-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c818c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c818c-105">Methods</span></span>  
  
|<span data-ttu-id="c818c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c818c-106">Method</span></span>|<span data-ttu-id="c818c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c818c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c818c-108">Icordebugexceptionobjectcallstackenum:: Next</span><span class="sxs-lookup"><span data-stu-id="c818c-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="c818c-109">Ottiene un numero specificato di [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) oggetti che contengono informazioni sullo stack di chiamate dell'oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="c818c-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c818c-110">Note</span><span class="sxs-lookup"><span data-stu-id="c818c-110">Remarks</span></span>  
 <span data-ttu-id="c818c-111">Il `ICorDebugExceptionObjectCallStackEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="c818c-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="c818c-112">Un `ICorDebugExceptionObjectCallStackEnum` istanza viene popolata con [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) oggetti chiamando le [icordebugexceptionobjectvalue:: Enumerateexceptioncallstack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="c818c-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="c818c-113">Gli elementi dello stack di chiamate nella raccolta possono essere enumerati chiamando il [icordebugexceptionobjectcallstackenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) (metodo)</span><span class="sxs-lookup"><span data-stu-id="c818c-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c818c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c818c-114">Requirements</span></span>  
 <span data-ttu-id="c818c-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c818c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c818c-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c818c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c818c-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c818c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c818c-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c818c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c818c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c818c-119">See Also</span></span>  
 [<span data-ttu-id="c818c-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c818c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c818c-121">Debug</span><span class="sxs-lookup"><span data-stu-id="c818c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
