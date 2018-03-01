---
title: Metodo ICorDebug::CanLaunchOrAttach
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62ebdb178ef7aaa16bcc163e42662e1d69f1f6f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="1fe5b-102">Metodo ICorDebug::CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="1fe5b-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="1fe5b-103">Restituisce un HRESULT che indica se avviare un nuovo processo o connettersi al processo specificato esistente è possibile all'interno del contesto della configurazione del computer e di runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fe5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fe5b-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fe5b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1fe5b-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="1fe5b-106">[in] L'ID di un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="1fe5b-107">[in] Passare `true` se si prevede di avviare il debug Win32 attivato o connettersi con Win32 debug abilitato; in caso contrario, passare `false`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fe5b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1fe5b-108">Return Value</span></span>  
 <span data-ttu-id="1fe5b-109">S_OK se i servizi di debug determinano che un nuovo processo di avvio o di connettersi al processo specificato è possibile, in base alle informazioni sulla configurazione di computer e di runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="1fe5b-110">I valori HRESULT possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1fe5b-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="1fe5b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fe5b-111">S_OK</span></span>  
  
-   <span data-ttu-id="1fe5b-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="1fe5b-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="1fe5b-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="1fe5b-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="1fe5b-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="1fe5b-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fe5b-115">Note</span><span class="sxs-lookup"><span data-stu-id="1fe5b-115">Remarks</span></span>  
 <span data-ttu-id="1fe5b-116">Questo metodo è puramente informativo.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-116">This method is purely informational.</span></span> <span data-ttu-id="1fe5b-117">L'interfaccia non comporta l'arresto è l'avvio o connettersi a un processo, indipendentemente dal valore restituito da `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="1fe5b-118">Se si prevede di avviare il debug Win32 attivato o la connessione con il debug Win32 attivato, passare `true` per `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="1fe5b-119">Il valore HRESULT restituito da `CanLaunchOrAttach` potrebbero essere diversi se si utilizza questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fe5b-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1fe5b-120">Requirements</span></span>  
 <span data-ttu-id="1fe5b-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fe5b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fe5b-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1fe5b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fe5b-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fe5b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fe5b-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fe5b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fe5b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fe5b-125">See Also</span></span>  
 [<span data-ttu-id="1fe5b-126">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="1fe5b-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
