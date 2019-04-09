---
title: Interfaccia ICorDebugUnmanagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60a1546068ae6a8c8be1c0af1ef3c7d770c23d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128680"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="8049b-102">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="8049b-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="8049b-103">Fornisce la notifica degli eventi nativi che non sono direttamente correlati a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8049b-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8049b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8049b-104">Methods</span></span>  
  
|<span data-ttu-id="8049b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8049b-105">Method</span></span>|<span data-ttu-id="8049b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8049b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8049b-107">Metodo DebugEvent</span><span class="sxs-lookup"><span data-stu-id="8049b-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="8049b-108">Notifica al debugger che è stato generato un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="8049b-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8049b-109">Note</span><span class="sxs-lookup"><span data-stu-id="8049b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8049b-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8049b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8049b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8049b-111">Requirements</span></span>  
 <span data-ttu-id="8049b-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8049b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8049b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8049b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8049b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8049b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8049b-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8049b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8049b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8049b-116">See also</span></span>

- [<span data-ttu-id="8049b-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8049b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
