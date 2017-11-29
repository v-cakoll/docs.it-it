---
title: Metodo ICorDebugManagedCallback::Breakpoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.Breakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 081e5bf9f119e1a2f2012166a5b27b34718751bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="382c1-102">Metodo ICorDebugManagedCallback::Breakpoint</span><span class="sxs-lookup"><span data-stu-id="382c1-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="382c1-103">Notifica al debugger quando viene rilevato un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="382c1-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="382c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="382c1-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="382c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="382c1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="382c1-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="382c1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="382c1-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="382c1-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="382c1-108">[in] Un puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="382c1-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="382c1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="382c1-109">Requirements</span></span>  
 <span data-ttu-id="382c1-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="382c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="382c1-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="382c1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="382c1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="382c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="382c1-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="382c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="382c1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="382c1-114">See Also</span></span>  
 [<span data-ttu-id="382c1-115">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="382c1-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
