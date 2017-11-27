---
title: Interfaccia ICorDebugUnmanagedCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback
helpviewer_keywords: ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa104bee5171b3b28731cf18a4d26e32f49169ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="62725-102">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="62725-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="62725-103">Fornisce notifica degli eventi nativi non direttamente correlati a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="62725-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62725-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="62725-104">Methods</span></span>  
  
|<span data-ttu-id="62725-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="62725-105">Method</span></span>|<span data-ttu-id="62725-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62725-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62725-107">DebugEvent (metodo)</span><span class="sxs-lookup"><span data-stu-id="62725-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="62725-108">Notifica al debugger che un evento nativo è stato attivato.</span><span class="sxs-lookup"><span data-stu-id="62725-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62725-109">Note</span><span class="sxs-lookup"><span data-stu-id="62725-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62725-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="62725-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62725-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62725-111">Requirements</span></span>  
 <span data-ttu-id="62725-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62725-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62725-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="62725-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62725-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62725-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62725-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62725-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62725-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62725-116">See Also</span></span>  
 [<span data-ttu-id="62725-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="62725-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
