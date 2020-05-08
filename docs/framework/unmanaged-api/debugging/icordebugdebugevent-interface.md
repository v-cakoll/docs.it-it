---
title: Interfaccia ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: a66012651d4b307d06a5a3bff675a248cc0ee376
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976356"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="7a81a-102">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7a81a-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="7a81a-103">Definisce l'interfaccia di base da cui derivano tutti gli evento di debug `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="7a81a-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a81a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7a81a-104">Methods</span></span>  
  
|<span data-ttu-id="7a81a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7a81a-105">Method</span></span>|<span data-ttu-id="7a81a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a81a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a81a-107">Metodo GetEventKind</span><span class="sxs-lookup"><span data-stu-id="7a81a-107">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="7a81a-108">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="7a81a-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="7a81a-109">Metodo GetThread</span><span class="sxs-lookup"><span data-stu-id="7a81a-109">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="7a81a-110">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="7a81a-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a81a-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7a81a-111">Remarks</span></span>  
 <span data-ttu-id="7a81a-112">Le interfacce seguenti sono derivate dall'interfaccia `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="7a81a-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="7a81a-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7a81a-113">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="7a81a-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7a81a-114">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="7a81a-115">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7a81a-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="7a81a-116">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7a81a-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a81a-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a81a-117">Requirements</span></span>  
 <span data-ttu-id="7a81a-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a81a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a81a-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a81a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a81a-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a81a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a81a-121">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a81a-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a81a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a81a-122">See also</span></span>

- [<span data-ttu-id="7a81a-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7a81a-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7a81a-124">Debug</span><span class="sxs-lookup"><span data-stu-id="7a81a-124">Debugging</span></span>](index.md)
