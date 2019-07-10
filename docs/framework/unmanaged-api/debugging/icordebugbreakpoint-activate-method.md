---
title: Metodo ICorDebugBreakpoint::Activate
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f056e4ae233e70223755c1961cd3ee5da68ec90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745186"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="b1e74-102">Metodo ICorDebugBreakpoint::Activate</span><span class="sxs-lookup"><span data-stu-id="b1e74-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="b1e74-103">Imposta lo stato attivo di questa `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="b1e74-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1e74-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1e74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1e74-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="b1e74-106">[in] Impostare questo valore su `true` per specificare lo stato come attivo; in caso contrario, impostare questo valore su `false`.</span><span class="sxs-lookup"><span data-stu-id="b1e74-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1e74-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1e74-107">Requirements</span></span>  
 <span data-ttu-id="b1e74-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1e74-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e74-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1e74-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1e74-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1e74-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1e74-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e74-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
