---
title: Interfaccia ICorDebugLoadedModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5cdc89ec81d76a3ce7d39a53e097745d6c9822f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="8476b-102">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="8476b-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="8476b-103">Vengono fornite informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="8476b-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8476b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8476b-104">Methods</span></span>  
  
|<span data-ttu-id="8476b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8476b-105">Method</span></span>|<span data-ttu-id="8476b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8476b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8476b-107">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="8476b-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="8476b-108">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="8476b-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="8476b-109">GetName (metodo)</span><span class="sxs-lookup"><span data-stu-id="8476b-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="8476b-110">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="8476b-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="8476b-111">GetSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="8476b-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="8476b-112">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="8476b-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8476b-113">Note</span><span class="sxs-lookup"><span data-stu-id="8476b-113">Remarks</span></span>  
 <span data-ttu-id="8476b-114">L'interfaccia `ICorDebugLoadedModule` viene implementata da un debugger e viene usata dalle interfacce di debug CLR per ottenere informazioni sul modulo caricato dal debugger.</span><span class="sxs-lookup"><span data-stu-id="8476b-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8476b-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8476b-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8476b-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="8476b-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8476b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8476b-117">Requirements</span></span>  
 <span data-ttu-id="8476b-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8476b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8476b-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8476b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8476b-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8476b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8476b-121">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8476b-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8476b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8476b-122">See Also</span></span>  
 [<span data-ttu-id="8476b-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8476b-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8476b-124">Debug</span><span class="sxs-lookup"><span data-stu-id="8476b-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
