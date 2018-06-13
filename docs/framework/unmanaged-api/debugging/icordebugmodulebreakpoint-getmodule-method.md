---
title: Metodo ICorDebugModuleBreakpoint::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cbb1aa9c81101eb818a9e7829c777efd3923b5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416153"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="a96f3-102">Metodo ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="a96f3-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="a96f3-103">Ottiene un puntatore a interfaccia a un "ICorDebugModule" che fa riferimento al modulo in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="a96f3-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a96f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a96f3-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a96f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a96f3-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="a96f3-106">[out] Un puntatore all'indirizzo di un `ICorDebugModule` interfaccia che fa riferimento al modulo in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="a96f3-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a96f3-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a96f3-107">Requirements</span></span>  
 <span data-ttu-id="a96f3-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a96f3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a96f3-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a96f3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a96f3-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a96f3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a96f3-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a96f3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a96f3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a96f3-112">See Also</span></span>  
 
