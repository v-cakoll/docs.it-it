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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1945e678dd62f81c698807714d0e71053d6b378
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414785"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="4dedc-102">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="4dedc-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="4dedc-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="4dedc-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4dedc-104">Estende logicamente l'interfaccia ICorDebugFunction per fornire l'accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="4dedc-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4dedc-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4dedc-105">Methods</span></span>  
  
|<span data-ttu-id="4dedc-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="4dedc-106">Method</span></span>|<span data-ttu-id="4dedc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dedc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4dedc-108">Metodo GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="4dedc-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="4dedc-109">Ottiene un puntatore a interfaccia a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) che contiene il linguaggio intermedio da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="4dedc-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dedc-110">Note</span><span class="sxs-lookup"><span data-stu-id="4dedc-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dedc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4dedc-111">Requirements</span></span>  
 <span data-ttu-id="4dedc-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dedc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dedc-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4dedc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dedc-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4dedc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dedc-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dedc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dedc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dedc-116">See Also</span></span>  
 [<span data-ttu-id="4dedc-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4dedc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4dedc-118">Debug</span><span class="sxs-lookup"><span data-stu-id="4dedc-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="4dedc-119">ReJIT: Una Guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="4dedc-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
