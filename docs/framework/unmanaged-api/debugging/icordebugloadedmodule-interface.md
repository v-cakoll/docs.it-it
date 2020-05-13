---
title: Interfaccia ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: d9b8245d8c37867971aa48ed3befb9cf22bd5b04
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210163"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="1bcb5-102">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="1bcb5-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="1bcb5-103">Vengono fornite informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="1bcb5-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1bcb5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1bcb5-104">Methods</span></span>  
  
|<span data-ttu-id="1bcb5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1bcb5-105">Method</span></span>|<span data-ttu-id="1bcb5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bcb5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1bcb5-107">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="1bcb5-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="1bcb5-108">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="1bcb5-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="1bcb5-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="1bcb5-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="1bcb5-110">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="1bcb5-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="1bcb5-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="1bcb5-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="1bcb5-112">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="1bcb5-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bcb5-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1bcb5-113">Remarks</span></span>  
 <span data-ttu-id="1bcb5-114">L'interfaccia `ICorDebugLoadedModule` viene implementata da un debugger e viene usata dalle interfacce di debug CLR per ottenere informazioni sul modulo caricato dal debugger.</span><span class="sxs-lookup"><span data-stu-id="1bcb5-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bcb5-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1bcb5-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="1bcb5-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1bcb5-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bcb5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bcb5-117">Requirements</span></span>  
 <span data-ttu-id="1bcb5-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bcb5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bcb5-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bcb5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bcb5-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bcb5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bcb5-121">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bcb5-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcb5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bcb5-122">See also</span></span>

- [<span data-ttu-id="1bcb5-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1bcb5-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1bcb5-124">Debug</span><span class="sxs-lookup"><span data-stu-id="1bcb5-124">Debugging</span></span>](index.md)
