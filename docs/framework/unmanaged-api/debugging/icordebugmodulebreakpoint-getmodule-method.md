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
ms.openlocfilehash: 51403c52d7f8a216e83b817f157979f4af1c433a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994773"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="7f8ac-102">Metodo ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="7f8ac-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="7f8ac-103">Ottiene un puntatore a interfaccia per un "ICorDebugModule" che fa riferimento al modulo in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="7f8ac-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f8ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f8ac-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f8ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f8ac-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="7f8ac-106">[out] Un puntatore all'indirizzo di un `ICorDebugModule` interfaccia che fa riferimento al modulo in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="7f8ac-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f8ac-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f8ac-107">Requirements</span></span>  
 <span data-ttu-id="7f8ac-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f8ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f8ac-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f8ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f8ac-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f8ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f8ac-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f8ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8ac-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f8ac-112">See also</span></span>
