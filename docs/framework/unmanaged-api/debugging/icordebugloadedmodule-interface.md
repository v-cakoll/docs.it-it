---
title: Interfaccia ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 9d3bdcec9e90dab337b595294d114de4bd3d531f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781996"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="3dfec-102">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="3dfec-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="3dfec-103">Vengono fornite informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="3dfec-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dfec-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3dfec-104">Methods</span></span>  
  
|<span data-ttu-id="3dfec-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3dfec-105">Method</span></span>|<span data-ttu-id="3dfec-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dfec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3dfec-107">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="3dfec-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="3dfec-108">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="3dfec-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="3dfec-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="3dfec-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="3dfec-110">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="3dfec-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="3dfec-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="3dfec-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="3dfec-112">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="3dfec-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dfec-113">Note</span><span class="sxs-lookup"><span data-stu-id="3dfec-113">Remarks</span></span>  
 <span data-ttu-id="3dfec-114">L'interfaccia `ICorDebugLoadedModule` viene implementata da un debugger e viene usata dalle interfacce di debug CLR per ottenere informazioni sul modulo caricato dal debugger.</span><span class="sxs-lookup"><span data-stu-id="3dfec-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dfec-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3dfec-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="3dfec-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3dfec-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dfec-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3dfec-117">Requirements</span></span>  
 <span data-ttu-id="3dfec-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dfec-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dfec-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dfec-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dfec-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dfec-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dfec-121">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dfec-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dfec-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dfec-122">See also</span></span>

- [<span data-ttu-id="3dfec-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3dfec-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3dfec-124">Debug</span><span class="sxs-lookup"><span data-stu-id="3dfec-124">Debugging</span></span>](index.md)
