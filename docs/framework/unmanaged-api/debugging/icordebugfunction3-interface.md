---
title: Interfaccia ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: fc50fd7180aaf5c1cff2147268d34921eec39e8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137768"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="3a7a5-102">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="3a7a5-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="3a7a5-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="3a7a5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3a7a5-104">Estende logicamente l'interfaccia ICorDebugFunction per fornire l'accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="3a7a5-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a7a5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3a7a5-105">Methods</span></span>  
  
|<span data-ttu-id="3a7a5-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3a7a5-106">Method</span></span>|<span data-ttu-id="3a7a5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a7a5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a7a5-108">Metodo GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="3a7a5-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="3a7a5-109">Ottiene un puntatore a interfaccia a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) che contiene il il da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="3a7a5-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a7a5-110">Note</span><span class="sxs-lookup"><span data-stu-id="3a7a5-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a7a5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a7a5-111">Requirements</span></span>  
 <span data-ttu-id="3a7a5-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a7a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a7a5-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a7a5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a7a5-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a7a5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a7a5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a7a5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a7a5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a7a5-116">See also</span></span>

- [<span data-ttu-id="3a7a5-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3a7a5-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3a7a5-118">Debug</span><span class="sxs-lookup"><span data-stu-id="3a7a5-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3a7a5-119">ReJIT: Guida alle procedure</span><span class="sxs-lookup"><span data-stu-id="3a7a5-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
