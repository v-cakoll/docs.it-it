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
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975992"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="fee1c-102">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="fee1c-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="fee1c-103">Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="fee1c-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="fee1c-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="fee1c-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fee1c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fee1c-105">Methods</span></span>  
  
|<span data-ttu-id="fee1c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="fee1c-106">Method</span></span>|<span data-ttu-id="fee1c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fee1c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fee1c-108">ICorDebugExceptionObjectCallStackEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="fee1c-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="fee1c-109">Ottiene un numero specificato di oggetti [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) che contengono informazioni sullo stack di chiamate di un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="fee1c-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fee1c-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fee1c-110">Remarks</span></span>  
 <span data-ttu-id="fee1c-111">L' `ICorDebugExceptionObjectCallStackEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="fee1c-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="fee1c-112">Un' `ICorDebugExceptionObjectCallStackEnum` istanza viene popolata con gli oggetti [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) chiamando il metodo [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fee1c-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="fee1c-113">È possibile enumerare gli elementi dello stack di chiamate nella raccolta chiamando il metodo [ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="fee1c-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fee1c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fee1c-114">Requirements</span></span>  
 <span data-ttu-id="fee1c-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fee1c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fee1c-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fee1c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fee1c-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fee1c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fee1c-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fee1c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee1c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fee1c-119">See also</span></span>

- [<span data-ttu-id="fee1c-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fee1c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fee1c-121">Debug</span><span class="sxs-lookup"><span data-stu-id="fee1c-121">Debugging</span></span>](index.md)
