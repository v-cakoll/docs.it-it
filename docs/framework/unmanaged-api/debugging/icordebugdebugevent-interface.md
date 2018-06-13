---
title: Interfaccia ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a2543a9629c60fde2b2f14c11898ba3e9df3c82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419312"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="42ebb-102">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="42ebb-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="42ebb-103">Definisce l'interfaccia di base da cui derivano tutti gli eventi di debug `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="42ebb-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42ebb-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="42ebb-104">Methods</span></span>  
  
|<span data-ttu-id="42ebb-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="42ebb-105">Method</span></span>|<span data-ttu-id="42ebb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42ebb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42ebb-107">Metodo GetEventKind</span><span class="sxs-lookup"><span data-stu-id="42ebb-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="42ebb-108">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="42ebb-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="42ebb-109">Metodo GetThread</span><span class="sxs-lookup"><span data-stu-id="42ebb-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="42ebb-110">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="42ebb-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42ebb-111">Note</span><span class="sxs-lookup"><span data-stu-id="42ebb-111">Remarks</span></span>  
 <span data-ttu-id="42ebb-112">Le interfacce seguenti sono derivate dall'interfaccia `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="42ebb-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="42ebb-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="42ebb-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="42ebb-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="42ebb-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="42ebb-115">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="42ebb-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="42ebb-116">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="42ebb-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ebb-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42ebb-117">Requirements</span></span>  
 <span data-ttu-id="42ebb-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42ebb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ebb-119">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="42ebb-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42ebb-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="42ebb-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42ebb-121">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42ebb-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ebb-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42ebb-122">See Also</span></span>  
 [<span data-ttu-id="42ebb-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="42ebb-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="42ebb-124">Debug</span><span class="sxs-lookup"><span data-stu-id="42ebb-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
