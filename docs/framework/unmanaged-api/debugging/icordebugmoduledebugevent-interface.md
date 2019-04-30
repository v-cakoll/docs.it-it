---
title: Interfaccia ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bf1fa21872c710ebc69c45e9980aeaa577a45fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942467"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="696eb-102">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="696eb-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="696eb-103">Estende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="696eb-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="696eb-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="696eb-104">Methods</span></span>  
  
|<span data-ttu-id="696eb-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="696eb-105">Method</span></span>|<span data-ttu-id="696eb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="696eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="696eb-107">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="696eb-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="696eb-108">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="696eb-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="696eb-109">Note</span><span class="sxs-lookup"><span data-stu-id="696eb-109">Remarks</span></span>  
 <span data-ttu-id="696eb-110">Il [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) e [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) tipi di eventi implementano questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="696eb-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="696eb-111">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="696eb-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="696eb-112">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="696eb-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696eb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="696eb-113">Requirements</span></span>  
 <span data-ttu-id="696eb-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="696eb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696eb-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="696eb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="696eb-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="696eb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="696eb-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696eb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696eb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="696eb-118">See also</span></span>

- [<span data-ttu-id="696eb-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="696eb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="696eb-120">Debug</span><span class="sxs-lookup"><span data-stu-id="696eb-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
