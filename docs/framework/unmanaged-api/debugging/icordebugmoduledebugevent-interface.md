---
title: Interfaccia ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792891"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="b8f2d-102">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="b8f2d-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="b8f2d-103">Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="b8f2d-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8f2d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b8f2d-104">Methods</span></span>  
  
|<span data-ttu-id="b8f2d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b8f2d-105">Method</span></span>|<span data-ttu-id="b8f2d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8f2d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8f2d-107">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="b8f2d-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="b8f2d-108">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="b8f2d-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8f2d-109">Note</span><span class="sxs-lookup"><span data-stu-id="b8f2d-109">Remarks</span></span>  
 <span data-ttu-id="b8f2d-110">I tipi di evento [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) e [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementano questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b8f2d-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8f2d-111">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b8f2d-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="b8f2d-112">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b8f2d-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8f2d-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b8f2d-113">Requirements</span></span>  
 <span data-ttu-id="b8f2d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8f2d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8f2d-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8f2d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8f2d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8f2d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8f2d-117">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8f2d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f2d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8f2d-118">See also</span></span>

- [<span data-ttu-id="b8f2d-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b8f2d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b8f2d-120">Debug</span><span class="sxs-lookup"><span data-stu-id="b8f2d-120">Debugging</span></span>](index.md)
