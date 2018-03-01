---
title: Metodo ICorDebugFunctionBreakpoint::GetFunction
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b9e59c26053d2eec534ca1cd56cf0ed277f87fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="d23b4-102">Metodo ICorDebugFunctionBreakpoint::GetFunction</span><span class="sxs-lookup"><span data-stu-id="d23b4-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="d23b4-103">Ottiene un puntatore a interfaccia ICorDebugFunction che fa riferimento alla funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d23b4-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d23b4-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d23b4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d23b4-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="d23b4-106">[out] Un puntatore all'indirizzo della funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d23b4-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23b4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d23b4-107">Requirements</span></span>  
 <span data-ttu-id="d23b4-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d23b4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23b4-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d23b4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d23b4-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d23b4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d23b4-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23b4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
