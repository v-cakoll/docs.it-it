---
title: Interfaccia ICorDebugInternalFrame2
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd867db8886c1c74d209e080b6b810ed4adc3654
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589334"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="d479f-102">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="d479f-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="d479f-103">Vengono fornite informazioni sui frame interni, compresi l'indirizzo dello stack e la posizione in relazione agli oggetti ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="d479f-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d479f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d479f-104">Methods</span></span>  
  
|<span data-ttu-id="d479f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d479f-105">Method</span></span>|<span data-ttu-id="d479f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d479f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d479f-107">Metodo GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="d479f-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="d479f-108">Restituisce l'indirizzo dello stack del frame interno.</span><span class="sxs-lookup"><span data-stu-id="d479f-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="d479f-109">Metodo IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="d479f-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="d479f-110">Controlla se il `this` frame interno è più simile alla foglia a oggetto ICorDebugFrame specificato.</span><span class="sxs-lookup"><span data-stu-id="d479f-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d479f-111">Note</span><span class="sxs-lookup"><span data-stu-id="d479f-111">Remarks</span></span>  
 <span data-ttu-id="d479f-112">Questa interfaccia estende l'interfaccia ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="d479f-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d479f-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d479f-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d479f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d479f-114">Requirements</span></span>  
 <span data-ttu-id="d479f-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d479f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d479f-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d479f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d479f-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d479f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d479f-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d479f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d479f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d479f-119">See also</span></span>
- [<span data-ttu-id="d479f-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d479f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d479f-121">Debug</span><span class="sxs-lookup"><span data-stu-id="d479f-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
