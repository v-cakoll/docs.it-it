---
title: Interfaccia ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 399f27db0a2d18e3bcd90b87f4470a77cb50595d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646857"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="88c3f-102">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="88c3f-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="88c3f-103">Estende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="88c3f-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88c3f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="88c3f-104">Methods</span></span>  
  
|<span data-ttu-id="88c3f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="88c3f-105">Method</span></span>|<span data-ttu-id="88c3f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88c3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88c3f-107">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="88c3f-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="88c3f-108">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="88c3f-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88c3f-109">Note</span><span class="sxs-lookup"><span data-stu-id="88c3f-109">Remarks</span></span>  
 <span data-ttu-id="88c3f-110">Il [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) e [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) tipi di eventi implementano questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="88c3f-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88c3f-111">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="88c3f-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="88c3f-112">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="88c3f-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88c3f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="88c3f-113">Requirements</span></span>  
 <span data-ttu-id="88c3f-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88c3f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88c3f-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88c3f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88c3f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88c3f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88c3f-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88c3f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c3f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88c3f-118">See also</span></span>
- [<span data-ttu-id="88c3f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="88c3f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="88c3f-120">Debug</span><span class="sxs-lookup"><span data-stu-id="88c3f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
