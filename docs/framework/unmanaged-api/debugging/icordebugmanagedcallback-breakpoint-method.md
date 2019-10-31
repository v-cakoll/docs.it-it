---
title: Metodo ICorDebugManagedCallback::Breakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
ms.openlocfilehash: 8a4f7d4f422d80d044bcb92065dbefc7f421a069
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122595"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="25aed-102">Metodo ICorDebugManagedCallback::Breakpoint</span><span class="sxs-lookup"><span data-stu-id="25aed-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="25aed-103">Notifica al debugger quando viene rilevato un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="25aed-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25aed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25aed-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25aed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25aed-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="25aed-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="25aed-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="25aed-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="25aed-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="25aed-108">in Puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="25aed-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25aed-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25aed-109">Requirements</span></span>  
 <span data-ttu-id="25aed-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25aed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25aed-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25aed-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25aed-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25aed-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25aed-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25aed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25aed-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25aed-114">See also</span></span>

- [<span data-ttu-id="25aed-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="25aed-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
