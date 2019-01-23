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
ms.openlocfilehash: e564ce63f7bf9e04ebf9a0bdcfc819ea23b3b2ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515560"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="ba722-102">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="ba722-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="ba722-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="ba722-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ba722-104">Estende logicamente l'interfaccia ICorDebugFunction per fornire l'accesso al codice di una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="ba722-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba722-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ba722-105">Methods</span></span>  
  
|<span data-ttu-id="ba722-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ba722-106">Method</span></span>|<span data-ttu-id="ba722-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba722-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba722-108">Metodo GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="ba722-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="ba722-109">Ottiene un puntatore a interfaccia a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) che contiene il linguaggio intermedio da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="ba722-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba722-110">Note</span><span class="sxs-lookup"><span data-stu-id="ba722-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba722-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba722-111">Requirements</span></span>  
 <span data-ttu-id="ba722-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba722-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba722-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba722-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba722-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba722-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba722-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba722-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba722-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba722-116">See also</span></span>
- [<span data-ttu-id="ba722-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ba722-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ba722-118">Debug</span><span class="sxs-lookup"><span data-stu-id="ba722-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ba722-119">ReJIT: Informazioni di Guida</span><span class="sxs-lookup"><span data-stu-id="ba722-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
