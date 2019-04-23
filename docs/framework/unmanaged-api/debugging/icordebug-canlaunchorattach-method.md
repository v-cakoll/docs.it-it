---
title: Metodo ICorDebug::CanLaunchOrAttach
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cf0065f1ed12ad3a37819b0a15d734a2b51ff5b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125606"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="e65d3-102">Metodo ICorDebug::CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="e65d3-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="e65d3-103">Restituisce un HRESULT che indica se avviare un nuovo processo o connettersi al processo esistente specificato è possibile all'interno del contesto della configurazione del computer e di runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="e65d3-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e65d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e65d3-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e65d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e65d3-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="e65d3-106">[in] L'ID di un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="e65d3-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="e65d3-107">[in] Passare `true` se si intende avviare con Win32 attivato il debug o collegare con Win32 di debug abilitate; in caso contrario, passare `false`.</span><span class="sxs-lookup"><span data-stu-id="e65d3-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e65d3-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e65d3-108">Return Value</span></span>  
 <span data-ttu-id="e65d3-109">S_OK se i servizi di debug determinano che avviare un nuovo processo o connettersi al processo specificato è possibile, in base alle informazioni sulla configurazione di computer e di runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="e65d3-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="e65d3-110">I valori HRESULT possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e65d3-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="e65d3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e65d3-111">S_OK</span></span>  
  
-   <span data-ttu-id="e65d3-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="e65d3-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="e65d3-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="e65d3-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="e65d3-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="e65d3-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e65d3-115">Note</span><span class="sxs-lookup"><span data-stu-id="e65d3-115">Remarks</span></span>  
 <span data-ttu-id="e65d3-116">Questo metodo è puramente informativo.</span><span class="sxs-lookup"><span data-stu-id="e65d3-116">This method is purely informational.</span></span> <span data-ttu-id="e65d3-117">L'interfaccia non verrà interrotta è l'avvio o la connessione a un processo, indipendentemente dal valore restituito da `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="e65d3-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="e65d3-118">Se si intende avviare con Win32 attivato il debug o collegare con Win32 attivato il debug, passare `true` per `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="e65d3-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="e65d3-119">Il valore HRESULT restituito dal `CanLaunchOrAttach` potrebbero essere diversi se si usa questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e65d3-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e65d3-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e65d3-120">Requirements</span></span>  
 <span data-ttu-id="e65d3-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e65d3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e65d3-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e65d3-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e65d3-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e65d3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e65d3-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e65d3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65d3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e65d3-125">See also</span></span>

- [<span data-ttu-id="e65d3-126">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e65d3-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
