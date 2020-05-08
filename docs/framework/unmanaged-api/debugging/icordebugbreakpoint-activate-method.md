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
ms.openlocfilehash: 24dc55cc9a49c3602829ca627d584c761b4088ce
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894739"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="077fb-102">Metodo ICorDebugBreakpoint::Activate</span><span class="sxs-lookup"><span data-stu-id="077fb-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="077fb-103">Imposta lo stato attivo di questo `ICorDebugBreakpoint`oggetto.</span><span class="sxs-lookup"><span data-stu-id="077fb-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="077fb-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="077fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="077fb-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="077fb-106">in Impostare questo valore su `true` per specificare lo stato come attivo; in caso contrario, impostare questo `false`valore su.</span><span class="sxs-lookup"><span data-stu-id="077fb-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="077fb-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="077fb-107">Requirements</span></span>  
 <span data-ttu-id="077fb-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="077fb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="077fb-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="077fb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="077fb-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="077fb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="077fb-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="077fb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
