---
title: Interfaccia ICorDebugCode3
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b3b29be2bab2d1b4cea5dcec89e31d4720be769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576876"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="c2fed-102">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="c2fed-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="c2fed-103">Fornisce un metodo che estende "ICorDebugCode" e "ICorDebugCode2" per fornire informazioni su un valore restituito gestito.</span><span class="sxs-lookup"><span data-stu-id="c2fed-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2fed-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c2fed-104">Methods</span></span>  
  
|<span data-ttu-id="c2fed-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c2fed-105">Method</span></span>|<span data-ttu-id="c2fed-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2fed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2fed-107">Metodo GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="c2fed-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="c2fed-108">Per un offset IL specificato, ottiene l'offset nativi in cui un punto di interruzione deve essere inserito in modo che il debugger può ottenere il valore restituito da una funzione.</span><span class="sxs-lookup"><span data-stu-id="c2fed-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2fed-109">Note</span><span class="sxs-lookup"><span data-stu-id="c2fed-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2fed-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c2fed-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2fed-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2fed-111">Requirements</span></span>  
 <span data-ttu-id="c2fed-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2fed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2fed-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2fed-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2fed-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2fed-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2fed-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2fed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fed-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2fed-116">See also</span></span>



- [<span data-ttu-id="c2fed-117">Interfaccia ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="c2fed-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
- [<span data-ttu-id="c2fed-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c2fed-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
