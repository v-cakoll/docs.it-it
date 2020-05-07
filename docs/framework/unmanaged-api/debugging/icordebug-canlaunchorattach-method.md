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
ms.openlocfilehash: 354df02b27e87550ba602fe102352455c227441b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859684"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="088e3-102">Metodo ICorDebug::CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="088e3-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="088e3-103">Restituisce un valore HRESULT che indica se è possibile avviare un nuovo processo o connettersi al processo esistente specificato all'interno del contesto del computer e della configurazione di runtime correnti.</span><span class="sxs-lookup"><span data-stu-id="088e3-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="088e3-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="088e3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="088e3-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="088e3-106">in ID di un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="088e3-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="088e3-107">in Passare `true` se si intende avviare con il debug Win32 abilitato oppure per connettersi con il debug Win32 abilitato; in caso contrario `false`, passare.</span><span class="sxs-lookup"><span data-stu-id="088e3-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="088e3-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="088e3-108">Return Value</span></span>  
 <span data-ttu-id="088e3-109">S_OK se i servizi di debug stabiliscono che è possibile avviare un nuovo processo o connettersi al processo specificato, in base alle informazioni relative alla configurazione corrente del computer e del runtime.</span><span class="sxs-lookup"><span data-stu-id="088e3-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="088e3-110">I valori HRESULT possibili sono:</span><span class="sxs-lookup"><span data-stu-id="088e3-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="088e3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="088e3-111">S_OK</span></span>  
  
- <span data-ttu-id="088e3-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="088e3-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="088e3-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="088e3-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="088e3-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="088e3-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="088e3-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="088e3-115">Remarks</span></span>  
 <span data-ttu-id="088e3-116">Questo metodo è puramente informativo.</span><span class="sxs-lookup"><span data-stu-id="088e3-116">This method is purely informational.</span></span> <span data-ttu-id="088e3-117">L'interfaccia non impedisce l'avvio o la connessione a un processo, indipendentemente dal valore restituito da `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="088e3-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="088e3-118">Se si intende avviare con il debug Win32 abilitato o Connetti con il debug Win32 abilitato, `true` passare `win32DebuggingEnabled`per.</span><span class="sxs-lookup"><span data-stu-id="088e3-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="088e3-119">Il valore HRESULT restituito `CanLaunchOrAttach` da può essere diverso se si utilizza questa opzione.</span><span class="sxs-lookup"><span data-stu-id="088e3-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="088e3-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="088e3-120">Requirements</span></span>  
 <span data-ttu-id="088e3-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="088e3-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="088e3-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="088e3-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="088e3-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="088e3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="088e3-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="088e3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088e3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="088e3-125">See also</span></span>

- [<span data-ttu-id="088e3-126">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="088e3-126">ICorDebug Interface</span></span>](icordebug-interface.md)
