---
title: Interfaccia ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6392d1040c9d76944f79dc3a39213ae6c2191bef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415568"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="9bc0e-102">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="9bc0e-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="9bc0e-103">Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="9bc0e-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="9bc0e-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="9bc0e-104">Method</span></span>  
  
|<span data-ttu-id="9bc0e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9bc0e-105">Method</span></span>|<span data-ttu-id="9bc0e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bc0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9bc0e-107">Metodo GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="9bc0e-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="9bc0e-108">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="9bc0e-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bc0e-109">Note</span><span class="sxs-lookup"><span data-stu-id="9bc0e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bc0e-110">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9bc0e-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="9bc0e-111">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9bc0e-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bc0e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bc0e-112">Requirements</span></span>  
 <span data-ttu-id="9bc0e-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bc0e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bc0e-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9bc0e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bc0e-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9bc0e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bc0e-116">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bc0e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc0e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bc0e-117">See Also</span></span>  
 [<span data-ttu-id="9bc0e-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9bc0e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9bc0e-119">Debug</span><span class="sxs-lookup"><span data-stu-id="9bc0e-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
