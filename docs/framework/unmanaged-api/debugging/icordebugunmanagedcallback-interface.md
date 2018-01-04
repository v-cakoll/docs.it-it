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
ms.workload: dotnet
ms.openlocfilehash: e2a0dc561010ead94f1b2ffcd306a6067a04d7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="5e100-102">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="5e100-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="5e100-103">Fornisce notifica degli eventi nativi non direttamente correlati a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5e100-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e100-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5e100-104">Methods</span></span>  
  
|<span data-ttu-id="5e100-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5e100-105">Method</span></span>|<span data-ttu-id="5e100-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e100-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e100-107">Metodo DebugEvent</span><span class="sxs-lookup"><span data-stu-id="5e100-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="5e100-108">Notifica al debugger che un evento nativo è stato attivato.</span><span class="sxs-lookup"><span data-stu-id="5e100-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e100-109">Note</span><span class="sxs-lookup"><span data-stu-id="5e100-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e100-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="5e100-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e100-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e100-111">Requirements</span></span>  
 <span data-ttu-id="5e100-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e100-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e100-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5e100-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e100-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e100-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e100-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e100-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e100-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e100-116">See Also</span></span>  
 [<span data-ttu-id="5e100-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5e100-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
