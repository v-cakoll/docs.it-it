---
title: Interfaccia ICorDebugFunction3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28d2d0d1058dae69bc17e370cc42ed56dc35b0e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="86937-102">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="86937-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="86937-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="86937-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="86937-104">Estende logicamente l'interfaccia ICorDebugFunction per fornire l'accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="86937-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86937-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="86937-105">Methods</span></span>  
  
|<span data-ttu-id="86937-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="86937-106">Method</span></span>|<span data-ttu-id="86937-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86937-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86937-108">Metodo GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="86937-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="86937-109">Ottiene un puntatore a interfaccia a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) che contiene il linguaggio intermedio da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="86937-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86937-110">Note</span><span class="sxs-lookup"><span data-stu-id="86937-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86937-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86937-111">Requirements</span></span>  
 <span data-ttu-id="86937-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86937-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86937-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="86937-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86937-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86937-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86937-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86937-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86937-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86937-116">See Also</span></span>  
 [<span data-ttu-id="86937-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="86937-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="86937-118">Debug</span><span class="sxs-lookup"><span data-stu-id="86937-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="86937-119">ReJIT: Una Guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="86937-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
