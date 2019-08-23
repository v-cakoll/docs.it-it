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
ms.openlocfilehash: a34454e7e007b4eba557c712cb824362aa5047c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952983"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="ca4c2-102">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="ca4c2-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="ca4c2-103">Fornisce la notifica di eventi nativi che non sono direttamente correlati all'Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ca4c2-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca4c2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ca4c2-104">Methods</span></span>  
  
|<span data-ttu-id="ca4c2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ca4c2-105">Method</span></span>|<span data-ttu-id="ca4c2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca4c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca4c2-107">Metodo DebugEvent</span><span class="sxs-lookup"><span data-stu-id="ca4c2-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="ca4c2-108">Notifica al debugger che è stato generato un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="ca4c2-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca4c2-109">Note</span><span class="sxs-lookup"><span data-stu-id="ca4c2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca4c2-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ca4c2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca4c2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca4c2-111">Requirements</span></span>  
 <span data-ttu-id="ca4c2-112">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca4c2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca4c2-113">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ca4c2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca4c2-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca4c2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca4c2-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca4c2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca4c2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca4c2-116">See also</span></span>

- [<span data-ttu-id="ca4c2-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ca4c2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
