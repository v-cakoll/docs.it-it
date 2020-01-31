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
ms.openlocfilehash: fdd2fee11e9353c3aa3faee2b137597e4ba47801
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791174"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="04a8c-102">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="04a8c-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="04a8c-103">Fornisce la notifica di eventi nativi che non sono direttamente correlati all'Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="04a8c-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04a8c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="04a8c-104">Methods</span></span>  
  
|<span data-ttu-id="04a8c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="04a8c-105">Method</span></span>|<span data-ttu-id="04a8c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04a8c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04a8c-107">Metodo DebugEvent</span><span class="sxs-lookup"><span data-stu-id="04a8c-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="04a8c-108">Notifica al debugger che è stato generato un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="04a8c-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04a8c-109">Note</span><span class="sxs-lookup"><span data-stu-id="04a8c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04a8c-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="04a8c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04a8c-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="04a8c-111">Requirements</span></span>  
 <span data-ttu-id="04a8c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04a8c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04a8c-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04a8c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04a8c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04a8c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04a8c-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04a8c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a8c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04a8c-116">See also</span></span>

- [<span data-ttu-id="04a8c-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="04a8c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
