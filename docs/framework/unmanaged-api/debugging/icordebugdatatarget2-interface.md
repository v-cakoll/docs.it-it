---
title: Interfaccia ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85ff64e30519e448b87c2e9ae5d2c66959d836fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412133"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="5d2a0-102">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="5d2a0-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="5d2a0-103">Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d2a0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5d2a0-104">Methods</span></span>  
  
|<span data-ttu-id="5d2a0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5d2a0-105">Method</span></span>|<span data-ttu-id="5d2a0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d2a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d2a0-107">Metodo CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="5d2a0-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="5d2a0-108">Crea un nuovo agente di rimozione dello stack che avvia la rimozione da un contesto iniziale (non necessariamente la foglia di un thread).</span><span class="sxs-lookup"><span data-stu-id="5d2a0-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="5d2a0-109">Metodo EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5d2a0-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="5d2a0-110">Restituisce un elenco di ID thread attivi.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="5d2a0-111">Metodo GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="5d2a0-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="5d2a0-112">Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="5d2a0-113">Metodo GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="5d2a0-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="5d2a0-114">Restituisce il percorso di un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="5d2a0-115">Metodo GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="5d2a0-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="5d2a0-116">Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d2a0-117">Note</span><span class="sxs-lookup"><span data-stu-id="5d2a0-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d2a0-118">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5d2a0-119">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d2a0-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d2a0-120">Requirements</span></span>  
 <span data-ttu-id="5d2a0-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d2a0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d2a0-122">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5d2a0-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d2a0-123">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5d2a0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d2a0-124">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d2a0-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2a0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d2a0-125">See Also</span></span>  
 [<span data-ttu-id="5d2a0-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5d2a0-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5d2a0-127">Debug</span><span class="sxs-lookup"><span data-stu-id="5d2a0-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
