---
title: Interfaccia ICorDebugInternalFrame2
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
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d87303fbe95804b458a42ed43b65f29233814977
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="2e0c5-102">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="2e0c5-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="2e0c5-103">Vengono fornite informazioni sui frame interni, compresi l'indirizzo dello stack e la posizione rispetto agli oggetti ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="2e0c5-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e0c5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2e0c5-104">Methods</span></span>  
  
|<span data-ttu-id="2e0c5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2e0c5-105">Method</span></span>|<span data-ttu-id="2e0c5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e0c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e0c5-107">Metodo GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="2e0c5-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="2e0c5-108">Restituisce l'indirizzo dello stack del frame interno.</span><span class="sxs-lookup"><span data-stu-id="2e0c5-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="2e0c5-109">Metodo IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="2e0c5-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="2e0c5-110">Controlla se il `this` frame interno è più vicino alla foglia rispetto all'oggetto ICorDebugFrame specificato.</span><span class="sxs-lookup"><span data-stu-id="2e0c5-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e0c5-111">Note</span><span class="sxs-lookup"><span data-stu-id="2e0c5-111">Remarks</span></span>  
 <span data-ttu-id="2e0c5-112">Questa interfaccia estende l'interfaccia ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="2e0c5-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e0c5-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="2e0c5-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e0c5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e0c5-114">Requirements</span></span>  
 <span data-ttu-id="2e0c5-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e0c5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e0c5-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2e0c5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e0c5-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e0c5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e0c5-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e0c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0c5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e0c5-119">See Also</span></span>  
 [<span data-ttu-id="2e0c5-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2e0c5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2e0c5-121">Debug</span><span class="sxs-lookup"><span data-stu-id="2e0c5-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
