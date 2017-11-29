---
title: Interfaccia ICorDebugBlockingObjectEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum
helpviewer_keywords: ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b62da4047029881ddffff5faee9f06072407bfc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="522db-102">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="522db-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="522db-103">Fornisce un enumeratore per un elenco di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="522db-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="522db-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="522db-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="522db-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="522db-105">Methods</span></span>  
  
|<span data-ttu-id="522db-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="522db-106">Method</span></span>|<span data-ttu-id="522db-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="522db-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="522db-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="522db-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="522db-109">Enumera un elenco di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="522db-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="522db-110">Note</span><span class="sxs-lookup"><span data-stu-id="522db-110">Remarks</span></span>  
 <span data-ttu-id="522db-111">Ogni struttura `CorDebugBlockingObject` rappresenta un oggetto che blocca un thread.</span><span class="sxs-lookup"><span data-stu-id="522db-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="522db-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="522db-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="522db-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="522db-113">Requirements</span></span>  
 <span data-ttu-id="522db-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="522db-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="522db-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="522db-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="522db-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="522db-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="522db-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="522db-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522db-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="522db-118">See Also</span></span>  
 [<span data-ttu-id="522db-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="522db-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="522db-120">Debug</span><span class="sxs-lookup"><span data-stu-id="522db-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
