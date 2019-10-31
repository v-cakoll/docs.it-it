---
title: Interfaccia ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: cca181c6af6db9f35ff7913e045a30e37e07a5e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110244"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="efc74-102">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="efc74-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="efc74-103">Estende l'interfaccia [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="efc74-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efc74-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="efc74-104">Methods</span></span>  
  
|<span data-ttu-id="efc74-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="efc74-105">Method</span></span>|<span data-ttu-id="efc74-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efc74-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efc74-107">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="efc74-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="efc74-108">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="efc74-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efc74-109">Note</span><span class="sxs-lookup"><span data-stu-id="efc74-109">Remarks</span></span>  
 <span data-ttu-id="efc74-110">I tipi di evento [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) e [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) implementano questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="efc74-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efc74-111">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="efc74-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="efc74-112">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="efc74-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efc74-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efc74-113">Requirements</span></span>  
 <span data-ttu-id="efc74-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efc74-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efc74-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efc74-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efc74-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efc74-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efc74-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efc74-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc74-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efc74-118">See also</span></span>

- [<span data-ttu-id="efc74-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="efc74-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="efc74-120">Debug</span><span class="sxs-lookup"><span data-stu-id="efc74-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
