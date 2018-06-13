---
title: Interfaccia ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f35c26b98521311267a627265f2dae8fa9e333de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421840"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="61805-102">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="61805-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="61805-103">Estende il [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="61805-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61805-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="61805-104">Methods</span></span>  
  
|<span data-ttu-id="61805-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="61805-105">Method</span></span>|<span data-ttu-id="61805-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61805-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61805-107">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="61805-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="61805-108">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="61805-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61805-109">Note</span><span class="sxs-lookup"><span data-stu-id="61805-109">Remarks</span></span>  
 <span data-ttu-id="61805-110">Il [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) e [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) evento tipi implementano questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="61805-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61805-111">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="61805-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="61805-112">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="61805-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61805-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61805-113">Requirements</span></span>  
 <span data-ttu-id="61805-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61805-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61805-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="61805-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61805-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="61805-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61805-117">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61805-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61805-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61805-118">See Also</span></span>  
 [<span data-ttu-id="61805-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="61805-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="61805-120">Debug</span><span class="sxs-lookup"><span data-stu-id="61805-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
