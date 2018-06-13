---
title: Interfaccia ICorDebugBlockingObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f22d9d86e2b943a8825e1ec271a401b03f73fb6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407014"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="a7110-102">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="a7110-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="a7110-103">Fornisce un enumeratore per un elenco di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="a7110-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="a7110-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="a7110-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7110-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a7110-105">Methods</span></span>  
  
|<span data-ttu-id="a7110-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a7110-106">Method</span></span>|<span data-ttu-id="a7110-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7110-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7110-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="a7110-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="a7110-109">Enumera un elenco di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="a7110-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7110-110">Note</span><span class="sxs-lookup"><span data-stu-id="a7110-110">Remarks</span></span>  
 <span data-ttu-id="a7110-111">Ogni struttura `CorDebugBlockingObject` rappresenta un oggetto che blocca un thread.</span><span class="sxs-lookup"><span data-stu-id="a7110-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7110-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a7110-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7110-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7110-113">Requirements</span></span>  
 <span data-ttu-id="a7110-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7110-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7110-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a7110-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7110-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a7110-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7110-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7110-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7110-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7110-118">See Also</span></span>  
 [<span data-ttu-id="a7110-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a7110-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a7110-120">Debug</span><span class="sxs-lookup"><span data-stu-id="a7110-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
