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
ms.openlocfilehash: 91e4967d6820f8f059262e7a18add072332c509d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532785"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="d7c12-102">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="d7c12-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="d7c12-103">Fornisce un enumeratore per un elenco degli [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="d7c12-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="d7c12-104">Questa interfaccia è una sottoclasse di interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="d7c12-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7c12-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d7c12-105">Methods</span></span>  
  
|<span data-ttu-id="d7c12-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d7c12-106">Method</span></span>|<span data-ttu-id="d7c12-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7c12-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7c12-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="d7c12-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="d7c12-109">Enumera un elenco dei [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="d7c12-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7c12-110">Note</span><span class="sxs-lookup"><span data-stu-id="d7c12-110">Remarks</span></span>  
 <span data-ttu-id="d7c12-111">Ogni struttura `CorDebugBlockingObject` rappresenta un oggetto che blocca un thread.</span><span class="sxs-lookup"><span data-stu-id="d7c12-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7c12-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d7c12-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7c12-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7c12-113">Requirements</span></span>  
 <span data-ttu-id="d7c12-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7c12-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7c12-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7c12-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7c12-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7c12-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7c12-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7c12-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c12-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7c12-118">See also</span></span>
- [<span data-ttu-id="d7c12-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d7c12-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d7c12-120">Debug</span><span class="sxs-lookup"><span data-stu-id="d7c12-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
