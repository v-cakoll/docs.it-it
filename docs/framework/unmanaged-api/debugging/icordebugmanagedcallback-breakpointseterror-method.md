---
title: Metodo ICorDebugManagedCallback::BreakpointSetError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27d5b8e0127971cc3a46560590fd9d95f0ffd1f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151021"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="e7200-102">Metodo ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="e7200-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="e7200-103">Notifica al debugger che common language runtime è stato possibile associare con precisione un punto di interruzione è stata impostata prima di una funzione si trovava just-in-time (JIT) compilato.</span><span class="sxs-lookup"><span data-stu-id="e7200-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7200-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7200-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7200-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7200-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e7200-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="e7200-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e7200-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="e7200-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="e7200-108">[in] Un puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="e7200-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="e7200-109">[in] Numero intero che indica l'errore.</span><span class="sxs-lookup"><span data-stu-id="e7200-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7200-110">Note</span><span class="sxs-lookup"><span data-stu-id="e7200-110">Remarks</span></span>  
 <span data-ttu-id="e7200-111">Il punto di interruzione specificato non verrà mai attivato.</span><span class="sxs-lookup"><span data-stu-id="e7200-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="e7200-112">Il debugger deve disattivare e riassociarla.</span><span class="sxs-lookup"><span data-stu-id="e7200-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7200-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7200-113">Requirements</span></span>  
 <span data-ttu-id="e7200-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7200-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7200-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7200-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7200-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7200-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e7200-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e7200-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7200-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7200-118">See also</span></span>

- [<span data-ttu-id="e7200-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e7200-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
