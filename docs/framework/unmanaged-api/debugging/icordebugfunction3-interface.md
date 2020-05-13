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
ms.openlocfilehash: 71aa482cc2268da17f1376d8c305dd6a818d92d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213166"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="7833d-102">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="7833d-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="7833d-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="7833d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7833d-104">Estende a livello logico l'interfaccia ICorDebugFunction in modo da fornire accesso al codice da una richiesta ReJIT.</span><span class="sxs-lookup"><span data-stu-id="7833d-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7833d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7833d-105">Methods</span></span>  
  
|<span data-ttu-id="7833d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7833d-106">Method</span></span>|<span data-ttu-id="7833d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7833d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7833d-108">Metodo GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="7833d-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="7833d-109">Ottiene un puntatore a interfaccia a un [ICorDebugILCode](icordebugilcode-interface.md) che contiene il il da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="7833d-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7833d-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7833d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7833d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7833d-111">Requirements</span></span>  
 <span data-ttu-id="7833d-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7833d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7833d-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7833d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7833d-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7833d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7833d-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7833d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7833d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7833d-116">See also</span></span>

- [<span data-ttu-id="7833d-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7833d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7833d-118">Debug</span><span class="sxs-lookup"><span data-stu-id="7833d-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="7833d-119">ReJIT: Guida alle procedure</span><span class="sxs-lookup"><span data-stu-id="7833d-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
