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
ms.openlocfilehash: 0b53c80157bfd99a766eb691e8a8a2e6b9659a95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137752"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="db540-102">Metodo ICorDebugFunctionBreakpoint::GetFunction</span><span class="sxs-lookup"><span data-stu-id="db540-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="db540-103">Ottiene un puntatore a interfaccia a un ICorDebugFunction che fa riferimento alla funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="db540-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db540-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db540-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db540-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db540-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="db540-106">out Puntatore all'indirizzo della funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="db540-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db540-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db540-107">Requirements</span></span>  
 <span data-ttu-id="db540-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db540-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db540-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db540-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db540-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db540-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db540-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db540-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
