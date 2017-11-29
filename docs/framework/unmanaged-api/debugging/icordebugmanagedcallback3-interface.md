---
title: Interfaccia ICorDebugManagedCallback3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback3
helpviewer_keywords: ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2f24cc8fbd8533ef6717bc1dcd1baab0ea9ab45
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="6da89-102">Interfaccia ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="6da89-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="6da89-103">Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="6da89-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6da89-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6da89-104">Methods</span></span>  
  
|<span data-ttu-id="6da89-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6da89-105">Method</span></span>|<span data-ttu-id="6da89-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6da89-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6da89-107">CustomNotification (metodo)</span><span class="sxs-lookup"><span data-stu-id="6da89-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="6da89-108">Indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="6da89-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6da89-109">Note</span><span class="sxs-lookup"><span data-stu-id="6da89-109">Remarks</span></span>  
 <span data-ttu-id="6da89-110">Questa interfaccia è un'estensione logica del [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfacce.</span><span class="sxs-lookup"><span data-stu-id="6da89-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6da89-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6da89-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6da89-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6da89-112">Requirements</span></span>  
 <span data-ttu-id="6da89-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6da89-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6da89-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6da89-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6da89-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6da89-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6da89-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6da89-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da89-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6da89-117">See Also</span></span>  
 [<span data-ttu-id="6da89-118">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6da89-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 [<span data-ttu-id="6da89-119">ICorDebugManagedCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6da89-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="6da89-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6da89-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6da89-121">Debug</span><span class="sxs-lookup"><span data-stu-id="6da89-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
