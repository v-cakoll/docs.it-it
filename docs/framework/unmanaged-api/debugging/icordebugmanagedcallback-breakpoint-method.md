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
ms.openlocfilehash: ac91a9c662a82c5ab870d01cb4b5d87c7af6b6ba
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782078"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="de907-102">Metodo ICorDebugManagedCallback::Breakpoint</span><span class="sxs-lookup"><span data-stu-id="de907-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="de907-103">Notifica al debugger quando viene rilevato un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="de907-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de907-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de907-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de907-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="de907-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="de907-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="de907-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="de907-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="de907-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="de907-108">in Puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="de907-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de907-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="de907-109">Requirements</span></span>  
 <span data-ttu-id="de907-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de907-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de907-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de907-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de907-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de907-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de907-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de907-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de907-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de907-114">See also</span></span>

- [<span data-ttu-id="de907-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="de907-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
