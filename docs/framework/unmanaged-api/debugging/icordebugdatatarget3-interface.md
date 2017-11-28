---
title: Interfaccia ICorDebugDataTarget3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1ab94e792265916e29ed24239e25cb5d57d1313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="99967-102">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="99967-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="99967-103">Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="99967-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="99967-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="99967-104">Method</span></span>  
  
|<span data-ttu-id="99967-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="99967-105">Method</span></span>|<span data-ttu-id="99967-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99967-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99967-107">Metodo GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="99967-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="99967-108">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="99967-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99967-109">Note</span><span class="sxs-lookup"><span data-stu-id="99967-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99967-110">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="99967-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="99967-111">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="99967-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99967-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99967-112">Requirements</span></span>  
 <span data-ttu-id="99967-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99967-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99967-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="99967-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99967-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99967-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99967-116">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99967-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99967-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99967-117">See Also</span></span>  
 [<span data-ttu-id="99967-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="99967-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="99967-119">Debug</span><span class="sxs-lookup"><span data-stu-id="99967-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
