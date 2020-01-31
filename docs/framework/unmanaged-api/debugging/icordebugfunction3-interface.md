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
ms.openlocfilehash: 7ef983c2f0785cb97baf8ba1ad3483b46c08af9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788662"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="2ac0d-102">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="2ac0d-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="2ac0d-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="2ac0d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2ac0d-104">Estende a livello logico l'interfaccia ICorDebugFunction in modo da fornire accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="2ac0d-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ac0d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="2ac0d-105">Methods</span></span>  
  
|<span data-ttu-id="2ac0d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="2ac0d-106">Method</span></span>|<span data-ttu-id="2ac0d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ac0d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ac0d-108">Metodo GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="2ac0d-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="2ac0d-109">Ottiene un puntatore a interfaccia a un [ICorDebugILCode](icordebugilcode-interface.md) che contiene il il da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="2ac0d-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ac0d-110">Note</span><span class="sxs-lookup"><span data-stu-id="2ac0d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac0d-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2ac0d-111">Requirements</span></span>  
 <span data-ttu-id="2ac0d-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ac0d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac0d-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ac0d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ac0d-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ac0d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ac0d-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac0d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac0d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ac0d-116">See also</span></span>

- [<span data-ttu-id="2ac0d-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2ac0d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2ac0d-118">Debug</span><span class="sxs-lookup"><span data-stu-id="2ac0d-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="2ac0d-119">ReJIT: Guida alle procedure</span><span class="sxs-lookup"><span data-stu-id="2ac0d-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
