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
ms.openlocfilehash: ce53137021fe9ccaf170bed28918b8f5fe87715b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504991"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="f6e11-102">Metodo ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="f6e11-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="f6e11-103">Ottiene un puntatore a interfaccia per un "ICorDebugModule" che fa riferimento al modulo in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f6e11-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6e11-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6e11-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6e11-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6e11-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="f6e11-106">[out] Un puntatore all'indirizzo di un `ICorDebugModule` interfaccia che fa riferimento al modulo in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f6e11-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6e11-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6e11-107">Requirements</span></span>  
 <span data-ttu-id="f6e11-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6e11-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6e11-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6e11-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6e11-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6e11-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6e11-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6e11-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e11-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6e11-112">See also</span></span>

