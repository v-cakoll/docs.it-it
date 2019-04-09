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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161460"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="22bed-102">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="22bed-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="22bed-103">Fornisce un enumeratore per un elenco degli [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="22bed-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="22bed-104">Questa interfaccia è una sottoclasse di interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="22bed-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22bed-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="22bed-105">Methods</span></span>  
  
|<span data-ttu-id="22bed-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="22bed-106">Method</span></span>|<span data-ttu-id="22bed-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22bed-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22bed-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="22bed-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="22bed-109">Enumera un elenco dei [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="22bed-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22bed-110">Note</span><span class="sxs-lookup"><span data-stu-id="22bed-110">Remarks</span></span>  
 <span data-ttu-id="22bed-111">Ogni struttura `CorDebugBlockingObject` rappresenta un oggetto che blocca un thread.</span><span class="sxs-lookup"><span data-stu-id="22bed-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22bed-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="22bed-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22bed-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22bed-113">Requirements</span></span>  
 <span data-ttu-id="22bed-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22bed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22bed-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22bed-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22bed-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22bed-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="22bed-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="22bed-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22bed-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22bed-118">See also</span></span>

- [<span data-ttu-id="22bed-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="22bed-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="22bed-120">Debug</span><span class="sxs-lookup"><span data-stu-id="22bed-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
