---
title: Interfaccia ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3b0d67d390931cc92c0b6a1320f66545517cde3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223043"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="f2237-102">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="f2237-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="f2237-103">Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="f2237-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="f2237-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="f2237-104">Method</span></span>  
  
|<span data-ttu-id="f2237-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f2237-105">Method</span></span>|<span data-ttu-id="f2237-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2237-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2237-107">Metodo GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="f2237-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="f2237-108">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="f2237-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2237-109">Note</span><span class="sxs-lookup"><span data-stu-id="f2237-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2237-110">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f2237-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f2237-111">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f2237-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2237-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2237-112">Requirements</span></span>  
 <span data-ttu-id="f2237-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2237-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2237-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2237-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2237-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2237-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f2237-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f2237-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2237-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2237-117">See also</span></span>

- [<span data-ttu-id="f2237-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f2237-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f2237-119">Debug</span><span class="sxs-lookup"><span data-stu-id="f2237-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
