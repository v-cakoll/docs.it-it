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
ms.openlocfilehash: 0baecc56df18a8ce346f5c4a9f52dd4006583867
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476399"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="5f414-102">Metodo ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="5f414-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="5f414-103">Notifica al debugger che common language runtime è stato possibile associare con precisione un punto di interruzione è stata impostata prima di una funzione si trovava just-in-time (JIT) compilato.</span><span class="sxs-lookup"><span data-stu-id="5f414-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f414-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f414-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f414-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f414-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5f414-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="5f414-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5f414-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="5f414-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="5f414-108">[in] Un puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="5f414-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="5f414-109">[in] Numero intero che indica l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f414-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f414-110">Note</span><span class="sxs-lookup"><span data-stu-id="5f414-110">Remarks</span></span>  
 <span data-ttu-id="5f414-111">Il punto di interruzione specificato non verrà mai attivato.</span><span class="sxs-lookup"><span data-stu-id="5f414-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="5f414-112">Il debugger deve disattivare e riassociarla.</span><span class="sxs-lookup"><span data-stu-id="5f414-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f414-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f414-113">Requirements</span></span>  
 <span data-ttu-id="5f414-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f414-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f414-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f414-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f414-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f414-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f414-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f414-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f414-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f414-118">See also</span></span>
- [<span data-ttu-id="5f414-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5f414-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
