---
title: Metodo ICorDebugManagedCallback::BreakpointSetError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.BreakpointSetError
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d8d75261a0ac1211ec54252b698a2a1b17ccac2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="e3b50-102">Metodo ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="e3b50-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="e3b50-103">Notifica al debugger che common language runtime: Impossibile associare con precisione un punto di interruzione impostato prima della compilazione just-in-time (JIT) compilata di una funzione.</span><span class="sxs-lookup"><span data-stu-id="e3b50-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b50-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3b50-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3b50-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e3b50-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e3b50-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="e3b50-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e3b50-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="e3b50-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="e3b50-108">[in] Un puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="e3b50-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="e3b50-109">[in] Valore intero che indica l'errore.</span><span class="sxs-lookup"><span data-stu-id="e3b50-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3b50-110">Note</span><span class="sxs-lookup"><span data-stu-id="e3b50-110">Remarks</span></span>  
 <span data-ttu-id="e3b50-111">Il punto di interruzione specificato non verrà mai attivato.</span><span class="sxs-lookup"><span data-stu-id="e3b50-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="e3b50-112">Il debugger deve disattivare e riassociarla.</span><span class="sxs-lookup"><span data-stu-id="e3b50-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3b50-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3b50-113">Requirements</span></span>  
 <span data-ttu-id="e3b50-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3b50-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3b50-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e3b50-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3b50-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3b50-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3b50-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3b50-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b50-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3b50-118">See Also</span></span>  
 [<span data-ttu-id="e3b50-119">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e3b50-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
