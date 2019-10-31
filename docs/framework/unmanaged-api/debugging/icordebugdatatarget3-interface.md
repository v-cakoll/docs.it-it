---
title: Interfaccia ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 5f91db291396589a916933bdc7c2a2390dd61a5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136674"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="86c17-102">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="86c17-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="86c17-103">Estende logicamente l'interfaccia [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="86c17-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="86c17-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="86c17-104">Method</span></span>  
  
|<span data-ttu-id="86c17-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="86c17-105">Method</span></span>|<span data-ttu-id="86c17-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86c17-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86c17-107">Metodo GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="86c17-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="86c17-108">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="86c17-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86c17-109">Note</span><span class="sxs-lookup"><span data-stu-id="86c17-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86c17-110">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="86c17-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="86c17-111">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="86c17-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86c17-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86c17-112">Requirements</span></span>  
 <span data-ttu-id="86c17-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86c17-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86c17-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86c17-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86c17-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86c17-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86c17-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86c17-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c17-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86c17-117">See also</span></span>

- [<span data-ttu-id="86c17-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="86c17-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="86c17-119">Debug</span><span class="sxs-lookup"><span data-stu-id="86c17-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
