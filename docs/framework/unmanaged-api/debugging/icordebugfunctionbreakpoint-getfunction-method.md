---
title: Metodo ICorDebugFunctionBreakpoint::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1da93ea073d6ae9f2e79f251014b2db5282a22c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496014"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="d52d6-102">Metodo ICorDebugFunctionBreakpoint::GetFunction</span><span class="sxs-lookup"><span data-stu-id="d52d6-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="d52d6-103">Ottiene un puntatore a interfaccia ICorDebugFunction che fa riferimento alla funzione in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d52d6-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d52d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d52d6-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d52d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d52d6-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="d52d6-106">[out] Un puntatore all'indirizzo della funzione in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d52d6-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d52d6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d52d6-107">Requirements</span></span>  
 <span data-ttu-id="d52d6-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d52d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52d6-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d52d6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d52d6-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d52d6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d52d6-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d52d6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
