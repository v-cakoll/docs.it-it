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
ms.openlocfilehash: 2377773b471b387376f0284522ebe29d6b003ae3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910117"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="ed440-102">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="ed440-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="ed440-103">Fornisce informazioni sui frame interni, inclusi l'indirizzo dello stack e la posizione in relazione agli oggetti ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="ed440-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed440-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ed440-104">Methods</span></span>  
  
|<span data-ttu-id="ed440-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ed440-105">Method</span></span>|<span data-ttu-id="ed440-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed440-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed440-107">Metodo GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="ed440-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="ed440-108">Restituisce l'indirizzo dello stack del frame interno.</span><span class="sxs-lookup"><span data-stu-id="ed440-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="ed440-109">Metodo IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="ed440-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="ed440-110">Controlla se il `this` frame interno è più vicino alla foglia rispetto all'oggetto ICorDebugFrame specificato.</span><span class="sxs-lookup"><span data-stu-id="ed440-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed440-111">Note</span><span class="sxs-lookup"><span data-stu-id="ed440-111">Remarks</span></span>  
 <span data-ttu-id="ed440-112">Questa interfaccia estende l'interfaccia ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="ed440-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed440-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ed440-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed440-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed440-114">Requirements</span></span>  
 <span data-ttu-id="ed440-115">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed440-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed440-116">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ed440-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed440-117">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed440-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed440-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed440-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed440-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed440-119">See also</span></span>

- [<span data-ttu-id="ed440-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ed440-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ed440-121">Debug</span><span class="sxs-lookup"><span data-stu-id="ed440-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
