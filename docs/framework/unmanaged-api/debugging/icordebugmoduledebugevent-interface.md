---
title: Interfaccia ICorDebugModuleDebugEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dced93ab39529ec57fb6fb99603a197fb957be8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="0fefd-102">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="0fefd-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="0fefd-103">Estende il [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="0fefd-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0fefd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0fefd-104">Methods</span></span>  
  
|<span data-ttu-id="0fefd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0fefd-105">Method</span></span>|<span data-ttu-id="0fefd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fefd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0fefd-107">GetModule (metodo)</span><span class="sxs-lookup"><span data-stu-id="0fefd-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="0fefd-108">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="0fefd-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fefd-109">Note</span><span class="sxs-lookup"><span data-stu-id="0fefd-109">Remarks</span></span>  
 <span data-ttu-id="0fefd-110">Il [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) e [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) evento tipi implementano questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0fefd-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fefd-111">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0fefd-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="0fefd-112">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0fefd-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fefd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0fefd-113">Requirements</span></span>  
 <span data-ttu-id="0fefd-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fefd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fefd-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0fefd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fefd-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fefd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fefd-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fefd-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fefd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fefd-118">See Also</span></span>  
 [<span data-ttu-id="0fefd-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0fefd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0fefd-120">Debug</span><span class="sxs-lookup"><span data-stu-id="0fefd-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
