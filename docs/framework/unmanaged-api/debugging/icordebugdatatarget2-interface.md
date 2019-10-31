---
title: Interfaccia ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 3c59752949ca29cbd0ed5a34ec7aeb3d98b6f9b6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136491"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="62d70-102">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="62d70-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="62d70-103">Estende logicamente l'interfaccia [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="62d70-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62d70-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="62d70-104">Methods</span></span>  
  
|<span data-ttu-id="62d70-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="62d70-105">Method</span></span>|<span data-ttu-id="62d70-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62d70-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62d70-107">Metodo CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="62d70-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="62d70-108">Crea un nuovo agente di rimozione dello stack che avvia la rimozione da un contesto iniziale (non necessariamente la foglia di un thread).</span><span class="sxs-lookup"><span data-stu-id="62d70-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="62d70-109">Metodo EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="62d70-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="62d70-110">Restituisce un elenco di ID thread attivi.</span><span class="sxs-lookup"><span data-stu-id="62d70-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="62d70-111">Metodo GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="62d70-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="62d70-112">Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.</span><span class="sxs-lookup"><span data-stu-id="62d70-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="62d70-113">Metodo GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="62d70-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="62d70-114">Restituisce il percorso di un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="62d70-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="62d70-115">Metodo GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="62d70-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="62d70-116">Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="62d70-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62d70-117">Note</span><span class="sxs-lookup"><span data-stu-id="62d70-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62d70-118">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="62d70-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="62d70-119">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="62d70-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d70-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62d70-120">Requirements</span></span>  
 <span data-ttu-id="62d70-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62d70-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d70-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62d70-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62d70-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62d70-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62d70-124">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d70-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d70-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62d70-125">See also</span></span>

- [<span data-ttu-id="62d70-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="62d70-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="62d70-127">Debug</span><span class="sxs-lookup"><span data-stu-id="62d70-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
