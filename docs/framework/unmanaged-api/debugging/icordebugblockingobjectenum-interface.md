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
ms.openlocfilehash: 5a23d21d0ed8c6a6a226d5e58eafb7bde65a4896
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161460"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="390ab-102">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="390ab-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="390ab-103">Fornisce un enumeratore per un elenco degli [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="390ab-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="390ab-104">Questa interfaccia è una sottoclasse di interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="390ab-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="390ab-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="390ab-105">Methods</span></span>  
  
|<span data-ttu-id="390ab-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="390ab-106">Method</span></span>|<span data-ttu-id="390ab-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="390ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="390ab-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="390ab-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="390ab-109">Enumera un elenco dei [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="390ab-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="390ab-110">Note</span><span class="sxs-lookup"><span data-stu-id="390ab-110">Remarks</span></span>  
 <span data-ttu-id="390ab-111">Ogni struttura `CorDebugBlockingObject` rappresenta un oggetto che blocca un thread.</span><span class="sxs-lookup"><span data-stu-id="390ab-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="390ab-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="390ab-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="390ab-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="390ab-113">Requirements</span></span>  
 <span data-ttu-id="390ab-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="390ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="390ab-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="390ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="390ab-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="390ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="390ab-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="390ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390ab-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="390ab-118">See also</span></span>

- [<span data-ttu-id="390ab-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="390ab-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="390ab-120">Debug</span><span class="sxs-lookup"><span data-stu-id="390ab-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
