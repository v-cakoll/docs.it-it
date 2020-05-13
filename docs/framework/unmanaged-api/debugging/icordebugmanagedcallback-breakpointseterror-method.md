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
ms.openlocfilehash: 0fa25dd33223ad2a9521aed0917ce35a2a33fa2f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213387"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="c4d02-102">Metodo ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="c4d02-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="c4d02-103">Notifica al debugger che il Common Language Runtime non è stato in grado di associare accuratamente un punto di interruzione impostato prima della compilazione JIT (just-in-Time) di una funzione.</span><span class="sxs-lookup"><span data-stu-id="c4d02-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4d02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4d02-104">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4d02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c4d02-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c4d02-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="c4d02-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c4d02-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="c4d02-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="c4d02-108">in Puntatore a un oggetto ICorDebugBreakpoint che rappresenta il punto di interruzione non associato.</span><span class="sxs-lookup"><span data-stu-id="c4d02-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="c4d02-109">in Intero che indica l'errore.</span><span class="sxs-lookup"><span data-stu-id="c4d02-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4d02-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c4d02-110">Remarks</span></span>  
 <span data-ttu-id="c4d02-111">Il punto di interruzione specificato non verrà mai raggiunto.</span><span class="sxs-lookup"><span data-stu-id="c4d02-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="c4d02-112">Il debugger dovrebbe disattivarlo e riassociarlo.</span><span class="sxs-lookup"><span data-stu-id="c4d02-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4d02-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4d02-113">Requirements</span></span>  
 <span data-ttu-id="c4d02-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4d02-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4d02-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4d02-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4d02-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4d02-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4d02-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4d02-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d02-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4d02-118">See also</span></span>

- [<span data-ttu-id="c4d02-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c4d02-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
