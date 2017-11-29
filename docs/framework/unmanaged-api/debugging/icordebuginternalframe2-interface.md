---
title: Interfaccia ICorDebugInternalFrame2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2
helpviewer_keywords: ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b612cb2fb8b2a84555ccf36a8537ebecff673d47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="bc0f4-102">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="bc0f4-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="bc0f4-103">Vengono fornite informazioni sui frame interni, compresi l'indirizzo dello stack e la posizione rispetto agli oggetti ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc0f4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bc0f4-104">Methods</span></span>  
  
|<span data-ttu-id="bc0f4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bc0f4-105">Method</span></span>|<span data-ttu-id="bc0f4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc0f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc0f4-107">GetFrameAddress (metodo)</span><span class="sxs-lookup"><span data-stu-id="bc0f4-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="bc0f4-108">Restituisce l'indirizzo dello stack del frame interno.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="bc0f4-109">IsCloserToLeaf (metodo)</span><span class="sxs-lookup"><span data-stu-id="bc0f4-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="bc0f4-110">Controlla se il `this` frame interno è più vicino alla foglia rispetto all'oggetto ICorDebugFrame specificato.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc0f4-111">Note</span><span class="sxs-lookup"><span data-stu-id="bc0f4-111">Remarks</span></span>  
 <span data-ttu-id="bc0f4-112">Questa interfaccia estende l'interfaccia ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc0f4-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc0f4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc0f4-114">Requirements</span></span>  
 <span data-ttu-id="bc0f4-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc0f4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc0f4-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bc0f4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc0f4-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc0f4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc0f4-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc0f4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0f4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc0f4-119">See Also</span></span>  
 [<span data-ttu-id="bc0f4-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bc0f4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="bc0f4-121">Debug</span><span class="sxs-lookup"><span data-stu-id="bc0f4-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
