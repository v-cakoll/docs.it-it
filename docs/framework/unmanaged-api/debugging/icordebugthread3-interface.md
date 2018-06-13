---
title: Interfaccia ICorDebugThread3
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9cb9217282af53d9788190844e4e52d5405ee2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422776"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="25062-102">Interfaccia ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="25062-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="25062-103">Fornisce il punto di ingresso per il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) e alle interfacce corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="25062-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25062-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="25062-104">Methods</span></span>  
  
|<span data-ttu-id="25062-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="25062-105">Method</span></span>|<span data-ttu-id="25062-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25062-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25062-107">Metodo CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="25062-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="25062-108">Crea un [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto per il thread il cui stack si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="25062-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="25062-109">Metodo GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="25062-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="25062-110">Restituisce una matrice di frame interni ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) oggetti) nello stack.</span><span class="sxs-lookup"><span data-stu-id="25062-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25062-111">Note</span><span class="sxs-lookup"><span data-stu-id="25062-111">Remarks</span></span>  
 <span data-ttu-id="25062-112">`ICorDebugThread3` è un'estensione logica dell'interfaccia ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="25062-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25062-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="25062-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25062-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25062-114">Requirements</span></span>  
 <span data-ttu-id="25062-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25062-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25062-116">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="25062-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25062-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="25062-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25062-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25062-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25062-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25062-119">See Also</span></span>  
 [<span data-ttu-id="25062-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="25062-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="25062-121">Debug</span><span class="sxs-lookup"><span data-stu-id="25062-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
