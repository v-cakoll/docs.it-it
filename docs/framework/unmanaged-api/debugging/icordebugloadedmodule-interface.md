---
title: Interfaccia ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e91dda9cbc5957768e98db2b2a9e1026d94c03e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946288"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="313cc-102">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="313cc-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="313cc-103">Vengono fornite informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="313cc-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="313cc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="313cc-104">Methods</span></span>  
  
|<span data-ttu-id="313cc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="313cc-105">Method</span></span>|<span data-ttu-id="313cc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="313cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="313cc-107">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="313cc-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="313cc-108">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="313cc-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="313cc-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="313cc-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="313cc-110">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="313cc-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="313cc-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="313cc-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="313cc-112">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="313cc-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="313cc-113">Note</span><span class="sxs-lookup"><span data-stu-id="313cc-113">Remarks</span></span>  
 <span data-ttu-id="313cc-114">L'interfaccia `ICorDebugLoadedModule` viene implementata da un debugger e viene usata dalle interfacce di debug CLR per ottenere informazioni sul modulo caricato dal debugger.</span><span class="sxs-lookup"><span data-stu-id="313cc-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="313cc-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="313cc-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="313cc-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="313cc-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="313cc-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="313cc-117">Requirements</span></span>  
 <span data-ttu-id="313cc-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="313cc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="313cc-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="313cc-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="313cc-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="313cc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="313cc-121">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="313cc-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313cc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="313cc-122">See also</span></span>

- [<span data-ttu-id="313cc-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="313cc-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="313cc-124">Debug</span><span class="sxs-lookup"><span data-stu-id="313cc-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
